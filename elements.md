# 元素 (Elements)

數個元素構成一個元件(Component)。

<!-- Elements are things inside your component. -->

![](images/component-elements.png)

## 元素命名

元素的名稱只能是 **一個字**。

<!-- Each component may have elements. They should have classes that are only one word. -->

~~~scss
.search-form {
	> .field { /* ... */ }
	> .action { /* ... */ }
}
~~~

## 選擇元素

建議盡可能地使用 `>` 子元素選擇器，相較於後代選擇器(descendant selectors)，這在遇上巢狀元件時，可避免類別衝突的發生，而在效能上也有著比較好的表現。

<!-- Prefer to use the `>` child selector whenever possible. This prevents bleeding through nested components, and performs better than descendant selectors. -->

~~~scss
.article-card {
	.title     { /* 尚可 */ }
	> .author  { /* ✓ 推薦 */ }
}
~~~

## 多字命名

若非得使用多個字來命名的話，各字間直接相連，不需要底線 `_` 或是破折號 `-`。

<!-- For those that need two or more words, concatenate them without dashes or underscores. -->

~~~scss
.profile-box {
	> .firstname { /* ... */ }
	> .lastname { /* ... */ }
	> .avatar { /* ... */ }
}
~~~

## 避免標籤選擇器 (tag selectors)

盡可能地使用類別選擇器(classnames)，標籤選擇器可能會帶來一點效能問題而且無法表達其語意。

<!-- Use classnames whenever possible. Tag selectors are fine, but they may come at a small performance penalty and may not be as descriptive. -->

~~~scss
.article-card {
	> h3    { /* ✗ 不宜 */ }
	> .name { /* ✓ 推薦 */ }
}
~~~

同一個元件在不同地方會有些差異需要調整，這時可以使用變形(Variants)。
[Continue →](variants.md)

<!-- Not all elements should always look the same. Variants can help. -->