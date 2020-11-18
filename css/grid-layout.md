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

```css:
.wrapper {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 10px;
  grid-auto-rows: minmax(100px, auto);
}
```

code di atas kita seleksi element parent nya untuk dijadikan sebagai grid, sehingga element - element yang ada di dalamnya dapat kita atur.

## Properti pada css grid

### grid-template-column
properti ini adalah untuk mengatur kolom dalam sebuah grid, contoh:

```grid-template-columns: 60px 60px;```
dari kode di atas kita mengatur sebuah kolom menjadi 2 kolom, yang mana setiap kolom diberi ukuran lebar 60px.

```grid-template-columns: 1fr 60px;```
selain menggunakan pixel kita juga dapat mengisi nilai fraction atau fr untuk mengatur ukuran kolom kita.

```grid-template-columns: minmax(100px, auto);```
kita juga dapat memberikan nilai minmax bila mana setiap kolom memiliki isi yang berbeda beda.

```grid-template-columns: repeat(3, 1fr);```
nilai repeat memiliki 2 argumen yang pertama itu untuk jumlah kolom yang ingin kita buat kemudian argumen kedua adalah ukuran dari setia kolom yang kita buat.


### grid-template-rows
properti ini adalah untuk mengatur baris dari sebuah grid, contoh:

```grid-template-rows: auto;```
dengan nilai auto maka grid akan membuat baris secara otomatis sesuai degan ukuran dari grid tersebut.

```grid-template-rows: 200px;```
ukuran dari baris tersebuat akan sebesar 200 pixel.

```grid-template-rows: 1fr 1fr;```
baris juga dapat menggunakan nilai fraction.

```grid-template-rows: minmax(100px, auto);```
baris juga dapat di isi dengan nilai minmax sama seperti kolom.
