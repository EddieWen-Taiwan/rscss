# 輔助類別 (Helpers)

可以將一些為了覆寫屬性的類別獨立在一個檔案中，並以底線 `_` 作開頭命名，通常也會將這些覆寫屬性帶上 *!important*。不過在使用這些類別時，請特別小心。

<!--
For general-purpose classes meant to override values, put them in a separate file and name them beginning with an underscore. They are typically things that are tagged with *!important*. Use them *very* sparingly.
-->

~~~css
._unmargin { margin: 0 !important; }
._center { text-align: center !important; }
._pull-left { float: left !important; }
._pull-right { float: right !important; }
~~~

## 輔助類別命名

這類類別命名時皆以底線 `_` 起頭，這能更容易分辨它們與一般類別的不同。而底線的存在，也讓這程式碼看起來有一點點的粗糙，也是提醒開發者，過度使用這些類別不是太好的選擇。

<!--
Prefix classnames with an underscore. This will make it easy to differentiate them from modifiers defined in the component. Underscores also look a bit ugly which is an intentional side effect: using too many helpers should be discouraged.
-->

~~~html
<div class='order-graphs -slim _unmargin'>
</div>
~~~

## 組織輔助類別

請將這些輔助類別統一放置在一個獨立的 `helpers` 檔案中，並盡量讓這份檔案中的類別保持最小數量。

<!--
Place all helpers in one file called `helpers`. While you can separate them into multiple files, it's very preferrable to keep your number of helpers to a minimum.
-->