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

### grid-template-area

dalam grid juga kita bisa meletakan element html yang kita buat sesuai dengan area yang kita buat, ini sangat memudahkan sekali untuk membuat layout.
sebagai contoh disini saya membuat sebuah element sederhana:

```html:
<div id="wrapper">
  <header> header </header>
  <nav> navigation </nav>
  <aside> aside </aside>
  <main> main </main>
  <footer> footer </footer>
</div>
```

kemudian kita buat css untuk meletakan element berdasarkan area yang akan kita buat, kita beri display grid terlebih dahulu pada element parent kita.

```css:
#wrapper {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-template-areas: 
    "header header"
    "nav nav"
    "aside main"
    "aside main"
    "footer footer";
  grid-auto-rows: 1fr;
  grid-gap: 4px;
}
```
kira beri style juga untuk setiap elemnt yang ada di dalam parent

```css:
#wrapper > * {
  padding: 20px;
  background: #c4c4c4;
}
```

kemudian setiap elemnent bisa kita kita identifikasi agar dapat dikenali oleh ```grid-template-areas``

```css:
header {
  grid-area: header;
}
nav {
  grid-area: nav;
}
aside {
  grid-area: aside;
}
main {
  grid-area: main;
}
footer {
grid-area: footer;
}
```

### grid-template

properti ini merupakan property shorthand untuk menyatakan langsung dari aturan grid-columns, rows, areas.

```css:
/* Keyword value */
grid-template: none;

/* grid-template-rows / grid-template-columns values */
grid-template: 100px 1fr / 50px 1fr;
grid-template: auto 1fr / auto 1fr auto;
grid-template: [linename] 100px / [columnname1] 30% [columnname2] 70%;
grid-template: fit-content(100px) / fit-content(40%);

/* grid-template-areas grid-template-rows / grid-template-column values */
grid-template: "a a a"
               "b b b";
grid-template: "a a a" 20%
               "b b b" auto;
grid-template: [header-top] "a a a"     [header-bottom]
                 [main-top] "b b b" 1fr [main-bottom]
                            / auto 1fr auto;

/* Global values */
grid-template: inherit;
grid-template: initial;
grid-template: unset;
```

### grid-auto-column

membuat ukuran kolom secara implisit, ada beberapa sintak yang dapat digunakan

```css:
/* Keyword values */
grid-auto-columns: min-content;
grid-auto-columns: max-content;
grid-auto-columns: auto;

/* <length> values */
grid-auto-columns: 100px;
grid-auto-columns: 20cm;
grid-auto-columns: 50vmax;

/* <percentage> values */
grid-auto-columns: 10%;
grid-auto-columns: 33.3%;

/* <flex> values */
grid-auto-columns: 0.5fr;
grid-auto-columns: 3fr;

/* minmax() values */
grid-auto-columns: minmax(100px, auto);
grid-auto-columns: minmax(max-content, 2fr);
grid-auto-columns: minmax(20%, 80vmax);

/* fit-content() values */
grid-auto-columns: fit-content(400px);
grid-auto-columns: fit-content(5cm);
grid-auto-columns: fit-content(20%);

/* multiple track-size values */
grid-auto-columns: min-content max-content auto;
grid-auto-columns: 100px 150px 390px;
grid-auto-columns: 10% 33.3%;
grid-auto-columns: 0.5fr 3fr 1fr;
grid-auto-columns: minmax(100px, auto) minmax(max-content, 2fr) minmax(20%, 80vmax);
grid-auto-columns: 100px minmax(100px, auto) 10% 0.5fr fit-content(400px);

/* Global values */
grid-auto-columns: inherit;
grid-auto-columns: initial;
grid-auto-columns: unset;
```

### grid-auto-rows

mengatur ukuran baris secara auto, bisa menggunakan sintak sintak berikut:

```css:
/* Keyword values */
grid-auto-rows: min-content;
grid-auto-rows: max-content;
grid-auto-rows: auto;

/* <length> values */
grid-auto-rows: 100px;
grid-auto-rows: 20cm;
grid-auto-rows: 50vmax;

/* <percentage> values */
grid-auto-rows: 10%;
grid-auto-rows: 33.3%;

/* <flex> values */
grid-auto-rows: 0.5fr;
grid-auto-rows: 3fr;

/* minmax() values */
grid-auto-rows: minmax(100px, auto);
grid-auto-rows: minmax(max-content, 2fr);
grid-auto-rows: minmax(20%, 80vmax);

/* multiple track-size values */
grid-auto-rows: min-content max-content auto;
grid-auto-rows: 100px 150px 390px;
grid-auto-rows: 10% 33.3%;
grid-auto-rows: 0.5fr 3fr 1fr;
grid-auto-rows: minmax(100px, auto) minmax(max-content, 2fr) minmax(20%, 80vmax);
grid-auto-rows: 100px minmax(100px, auto) 10% 0.5fr fit-content(400px);

/* Global values */
grid-auto-rows: inherit;
grid-auto-rows: initial;
grid-auto-rows: unset;
```

### grid-auto-flow

properti ini dapat digunakan untuk penempatan secara otomatis

```css:
/* Keyword values */
grid-auto-flow: row;
grid-auto-flow: column;
grid-auto-flow: dense;
grid-auto-flow: row dense;
grid-auto-flow: column dense;

/* Global values */
grid-auto-flow: inherit;
grid-auto-flow: initial;
grid-auto-flow: unset;
```
