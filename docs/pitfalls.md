# 陷阱 (Pitfalls)

## 巢狀元件的 `Bleeding`

請謹慎使用巢狀元件，其中可能會出現相同類別名稱的元件。

<!-- Be careful about nested components with elements sharing the same name as elements in its container. -->

~~~html
<article class='article-link'>
 <div class='vote-box'>
    <button class='up'></button>
    <button class='down'></button>
    <span class='count'>4</span>
  </div>

  <h3 class='title'>Article title</h3>
  <p class='count'>3 votes</p>
</article>
~~~

~~~scss
.article-link {
  > .title { /* ... */ }
  > .count { /* ... (!!!) */ }
}

.vote-box {
  > .up { /* ... */ }
  > .down { /* ... */ }
  > .count { /* ... */ }
}
~~~

這上面的例子中，若是 `.article-link > .count` 並不是使用 `>` 子元素選擇器(而是用後代選擇器)，那此類別的屬性也會寫入 `.vote-box .count` 元素中。也因此作者較推薦使用子元素選擇器。

<!-- In this case, if `.article-link > .count` did not have the `>` (child) selector, it will also apply to the `.vote-box .count` element. This is one of the reasons why child selectors are preferred. -->
