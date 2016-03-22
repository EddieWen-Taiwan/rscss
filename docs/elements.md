# 元素 (Elements)

由數個元素構成一個元件(Component)。

![](images/component-elements.png)

## 元素命名
元素的名稱只能是 **一個字**。

~~~scss
.search-form {
  > .field { /* ... */ }
  > .action { /* ... */ }
}
~~~

## 選擇元素
建議盡可能地使用 `>` 子元素選擇器，相較於後代選擇器(descendant selectors)，這在遇上巢狀元件時，可避免子元素衝突的發生，而在效能上也有著比較好的表現。

~~~scss
.article-card {
  .title     { /* 尚可 */ }
  > .author  { /* ✓ 推薦 */ }
}
~~~

## 多字命名
若真的需要多個字來命名的話，各字間直接相連，不需要底線 `_` 或是破折號 `-`。

~~~scss
.profile-box {
  > .firstname { /* ... */ }
  > .lastname { /* ... */ }
  > .avatar { /* ... */ }
}
~~~

## 避免標籤選擇器
(tag selectors)
盡可能地使用 css 類別選擇器，標籤選擇器可能會帶來一點點效能問題而且無法表達完整語意。

~~~scss
.article-card {
  > h3    { /* ✗ 不宜 */ }
  > .name { /* ✓ 推薦 */ }
}
~~~

相同的元件常常在不同地方會有一些改變的需要，這時可以使用變形(Variants)。
[Continue →](variants.md)

