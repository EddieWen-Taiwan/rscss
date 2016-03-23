# CSS 結構

## 一元件一檔案

將每個元件獨立放在一個檔案中。

<!-- For each component, place them in their own file. -->

~~~scss
/* css/components/search-form.scss */
.search-form {
  > .button { /* ... */ }
  > .field { /* ... */ }
  > .label { /* ... */ }

  // variants
  &.-small { /* ... */ }
  &.-wide { /* ... */ }
}
~~~

## glob matching

在 sass 結構下，可以使用此[插件](https://github.com/chriseppstein/sass-globbing)一次將資料夾下所有檔案輸入。

<!-- In sass-rails and stylus, this makes including all of them easy: -->

~~~scss
@import 'components/*';
~~~

## 避免多層巢狀結構

不要讓巢狀類別多於一層，這很容易讓 CSS 過於複雜混亂。

<!-- Use no more than 1 level of nesting. It's easy to get lost with too much nesting. -->

~~~scss
/* ✗ 不宜: 三層的巢狀結構 */
.image-frame {
  > .description {
    /* ... */

    > .icon { /* ... */ }
  }
}

/* ✓ 推薦: 至多到第兩層巢狀結構 */
.image-frame {
  > .description { /* ... */ }
  > .description > .icon { /* ... */ }
}
~~~
