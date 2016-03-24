# 巢狀元件 (Nested components)

![](images/component-nesting.png)

~~~html
<div class='article-link'>
	<div class='vote-box'>
		...
	</div>
	<h3 class='title'>...</h3>
	<p class='meta'>...</p>
</div>
~~~

有時候勢必得用上巢狀元件，接下來解釋該如何組織 CSS 類別。

<!--
Sometimes it's necessary to nest components. Here are some guidelines for doing that.
-->

## 變形

當元件內需要有另一個元件存在時，就形成巢狀元件。這時最好避免將 CSS 寫在父類別下的子類別中。

<!--
A component may need to appear a certain way when nested in another component. Avoid modifying the nested component by reaching into it from the containing component.
-->

~~~scss
.article-header {
  > .vote-box > .up { /* ✗ 不宜 */ }
}
~~~

可以選擇以變形(Variant)的方式來定義父元件下的子元件。

<!--
Instead, prefer to add a variant to the nested component and apply it from the containing component.
-->

~~~html
<div class='article-header'>
	<div class='vote-box -highlight'>
		...
	</div>
	...
</div>
~~~

~~~scss
.vote-box {
	&.-highlight > .up { /* ... */ }
}
~~~

## 簡化巢狀元件

以上述方式進行時，很有可能讓你的標籤變得過於複雜：

<!-- Sometimes, when nesting components, your markup can get dirty: -->

~~~html
<div class='search-form'>
	<input class='input' type='text'>
	<button class='search-button -red -large'></button>
</div>
~~~

可以通過 CSS 的預處理器 - `@extend` 來簡化這種情況：

<!-- You can simplify this by using your CSS preprocessor's `@extend` mechanism: -->

~~~html
<div class='search-form'>
	<input class='input' type='text'>
	<button class='submit'></button>
</div>
~~~

~~~scss
.search-form {
	> .submit {
		@extend .search-button;
		@extend .search-button.-red;
		@extend .search-button.-large;
	}
}
~~~

該如何處理清單這種重複元件？佈局(Layouts)
[Continue →](layouts.md)

<!-- What about repeating elements like lists? Learn about Layouts. -->
