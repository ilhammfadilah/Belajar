# CSS GRID LAYOUT
css grid merupakan merupakan teknik di dalam css untuk memudahkan mengatur dalam me layout halaman sebuah HTML.

## Caram membuat grid pada css
untuk membuat sebuah grid pada css kita buat terlebih dahulu element HTML yang akan kita buat untuk dijadikan sebagai grid.

```html:
  <div class="wrapper">
    <div class="one">One</div>
    <div class="two">Two</div>
    <div class="three">Three</div>
    <div class="four">Four</div>
    <div class="five">Five</div>
    <div class="six">Six</div>
  </div>
```

kemudian kita masukan css pada element tersebut

<code>
.wrapper {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 10px;
  grid-auto-rows: minmax(100px, auto);
}
</code>

code di atas kita seleksi element parent nya untuk dijadikan sebagai grid, sehingga element - element yang ada di dalamnya dapat kita atur.
