# 佈局 (Layouts)

![](images/layouts.png)

## 避免定位相關的屬性

所有元件都應該被設計成可重複使用在任何內容上，因此要避免將下列屬性寫進 CSS 類別中。

<!--
Components should be made in a way that they're reusable in different contexts. Avoid putting these properties in components:
-->

* Positioning (`position`, `top`, `left`, `right`, `bottom`)
* Floats (`float`, `clear`)
* Margins (`margin`)
* Dimensions (`width`, `height`)

## 固定尺寸

除了那些本應該具有固定長寬的物件，如頭像、標誌。

<!--
Exception to these would be elements that have fixed width/heights, such as avatars and logos.
-->

## 從父元件定義上述屬性

請試著從父元件定義這些屬性，如下面範例中，`width` & `float` 都是寫在 *list* 元件上，並在非 *card* 元件本身。

<!--
If you need to define these, try to define them in whatever context they will be in. In this example below, notice that the widths and floats are applied on the *list* component, not the component itself.
-->

~~~css
.article-list {
  & {
    @include clearfix;
  }

  > .article-card {
    width: 33.3%;
    float: left;
  }
}

.article-card {
  & { /* ... */ }
  > .image { /* ... */ }
  > .title { /* ... */ }
  > .category { /* ... */ }
}
~~~

該如何定義佈局外的 `margin`？使用 Helper
[Continue →](helpers.md)

<!-- How do you apply margins outside a layout? Try it with Helpers. -->
