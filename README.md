# SASS & SCSS Tutorial

![1_Fk9lVjzWan0OgYa828emhw](https://github.com/user-attachments/assets/db64659d-6f19-4e60-8280-655d57c965f1)


Bu repo, **SASS** (Syntactically Awesome Style Sheets) ve **SCSS** (Sassy CSS) ile ilgili temel kavramları öğrenmek isteyenler için hazırlanmıştır. SASS, CSS yazmayı daha modüler, daha hızlı ve bakımı kolay bir hale getiren bir ön işlemcidir. Bu tutorial, SASS'in SCSS sözdizimi üzerinden açıklamalar ve örnekler içermektedir.

## İçindekiler
- [Gereksinimler](#gereksinimler)
- [Kurulum](#kurulum)
- [Temel Kavramlar](#temel-kavramlar)
- [Değişkenler](#değişkenler)
- [İç içe Geçme (Nesting)](#iç-içe-geçme-nesting)
- [Kısaltmalar (Partials)](#kısaltmalar-partials)
- [Mixins](#mixins)
- [Extend (Miras Alma)](#extend-miras-alma)
- [Operatörler](#operatörler)
- [SCSS ve SASS Farkı](#scss-ve-sass-farkı)
- [Watch ve Compile](#watch-ve-compile)
- [Kaynaklar](#kaynaklar)
-   
## Gereksinimler
- **Node.js** ve **npm**'in bilgisayarınıza kurulu olması gerekmektedir.
- **SASS**'i çalıştırabilmek için global olarak `sass` paketini yüklemeniz gerekmektedir.

```bash
npm install -g sass
```
- Ayrıca bunu yerel olarak bir projeye de ekleyebilirsiniz:
```bash
npm install sass
```

<br>

## Kurulum 
Projede SASS ve SCSS kullanmaya başlamak için aşağıdaki adımları takip edebilirsiniz:
1. Projeye bir `styles.scss` dosyası ekleyin.
2. SCSS dosyasını CSS'e çevirmek için şu komutu çalıştırın:

```bash
sass styles.scss styles.css
```
3. HTML dosyanızda oluşturduğunuz `styles.css` dosyasını dahil edin.
```html
<link rel="stylesheet" href="styles.css">
```

<br>

## Temel Kavramlar
### Değişkenler 
SASS ile CSS içinde değişken tanımlayarak aynı değeri birden fazla yerde kullanabilirsiniz.
```scss
$primary-color: #3498db;

body {
  color: $primary-color;
}
```
### İç içe Geçme (Nesting)
SASS, stil kurallarını iç içe yazmanıza olanak tanır ve bu, daha okunabilir ve organize bir kod yazmanıza yardımcı olur.
```scss
nav {
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
    
    li {
      display: inline-block;
    }
  }
}
```
### Kısaltmalar (Partials)
SASS'ta kodlarınızı modüllere ayırarak kısaltmalar oluşturabilirsiniz. Bu dosyalar `_` ile başlar ve derleme işleminde ana SCSS dosyasına dahil edilir.
```scss
// _buttons.scss
.button {
  border-radius: 5px;
}
```
```scss
// main.scss
@import 'buttons';
```
### Mixins
Mixins, stil kurallarını bir araya toplar ve bunları birden fazla sınıfta yeniden kullanmanıza olanak tanır.
```scss
@mixin border-radius($radius) {
  border-radius: $radius;
}

.box { 
  @include border-radius(10px);
}
```
### Extend (Miras Alma)
`@extend`, bir sınıfın stil kurallarını başka bir sınıfa miras almak için kullanılır.
```scss
.message {
  padding: 10px;
  border: 1px solid #ccc;
}

.success {
  @extend .message;
  border-color: green;
}
```
### Operatörler
SASS, CSS ile çalışırken matematiksel işlemleri kullanmanıza izin verir.
```scss
.container {
  width: 100% - 20px;
}
```

<br>

## SCSS ve SASS Farkı
- SCSS: CSS ile tamamen uyumludur ve süslü parantezler ve noktalı virgüller kullanır.
- SASS: Daha sade bir sözdizimi sunar ve süslü parantez ile noktalı virgüller olmadan çalışır.

### Örnek SCSS 
```scss
$font-stack: Helvetica, sans-serif;
$primary-color: #333;

body {
  font: 100% $font-stack;
  color: $primary-color;
}
```
### Örnek SASS
```sass
$font-stack: Helvetica, sans-serif
$primary-color: #333

body
  font: 100% $font-stack
  color: $primary-color
```
<br>

## Watch Ve Compile
- SCSS'nizi CSS'ye derlemek için terminalinizde aşağıdaki komutu kullanabilirsiniz:
```bash
sass --watch scss:css
```
- Bu komut, SCSS dosyalarınızı değişikliklere karşı izler ve bir değişiklik algılandığında bunları otomatik olarak CSS'ye derler.

<br>

## Kaynaklar 
- Sass Official : https://sass-lang.com/
- Sass Playground : https://sass-lang.com/playground/
- Learn Sass : https://sass-lang.com/guide/
- Install Sass : https://sass-lang.com/install/














