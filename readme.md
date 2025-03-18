
![alt img](./images/sass.png)

<br><br><br>

# 🟢 Asosiy tushunchalar

- Sass nima va u qanday ishlaydi?
- Sass va CSS o‘rtasidagi asosiy farqlar qanday?
- Sassning qaysi ikki sintaksisi mavjud?
- .scss va .sass o‘rtasidagi farq nima?
- Sassni loyihaga qanday ulash mumkin?

<hr>
<br>

# 🔵 Mixins, Functions, va Variables

- Sass’da variables nima? Misol bilan tushuntiring.
- Sass’da mixin nima va u qanday qo‘llanadi?
- @include va @extend direktivalari o‘rtasidagi farq nima?
- Sass’da function qanday ishlaydi? Misol keltiring.
- Sass’da default qiymatni qanday o‘rnatish mumkin?

<hr>
<br>

# 🟣 Nest (ichma-ich kod yozish)

- Sass’da nesting nima? Misol bilan tushuntiring.
- Sass’da parent selector (&) qanday ishlaydi? Misol bilan tushuntiring.
- Nesting chuqurligi qanchalik bo‘lishi kerak?
- Sass’da BEM metodologiyasini qanday amalga oshirish mumkin?

<hr>
<br>

# 🟠 Matematik amallar va funksiyalar

- Sass’da qanday matematik amallarni bajarish mumkin?
- Sass’da ranglar bilan ishlash uchun qaysi funksiyalar mavjud?
- Sass’da lighten() va darken() funksiyalari qanday ishlaydi?
- Sass’da map va list bilan qanday ishlash mumkin?

<hr>
<br>

# 🔴 Advanced (Ilg‘or tushunchalar)

- Sass’da @import va @use o‘rtasidagi farq nima?
- Sass’da @forward direktivasi nima va u qanday ishlaydi?
- Sass’da modul tizimi qanday ishlaydi?
- Sass’da if, for, each, va while direktivalari qanday ishlaydi?
- Sass’da placeholder selector (%) nima va u qanday ishlatiladi?

<hr>
<br>

# 🟤 Performance va Optimization

- Sass kodlarini optimallashtirish uchun qanday usullarni bilasiz?
- Sass’ni ishlab chiqarish (production) uchun qanday kompilyatsiya qilish kerak?
- Sass bilan birga autoprefixer va postcss ishlatish mumkinmi?
- Sass bilan ishlashda qanday umumiy xatolar uchraydi va ularni qanday tuzatish mumkin?

<hr> <br><br><br><br><br><br><br><br>

# `Sass nima va u qanday ishlaydi.?`

## Sass nima?

> Sass (Syntactically Awesome Stylesheets) — bu CSS preprocessor bo‘lib, u CSS kodini yozishni osonlashtiradi va kodni qisqaroq, tuzilishga ega, va qayta ishlatiladigan holga keltiradi.

Sass orqali quyidagi imkoniyatlar mavjud:

- Variables (o‘zgaruvchilar) – Kodni qayta ishlatish imkonini beradi.
- Nesting – Ichma-ich kod yozish orqali strukturani soddalashtiradi.
- Mixins – Kod bloklarini qayta ishlatishga imkon beradi.
- Inheritance – Kodni boshqa qismga meros qilib olishga imkon beradi.
- Modullar – Kodni qismlarga ajratib boshqarish imkonini beradi.
- Matematik amallar – CSSda qo‘llab bo‘lmaydigan matematik amallarni bajara oladi.

<br>

## Sass qanday ishlaydi?

- Sass kodini yozasiz – .sass yoki .scss fayllarda yoziladi.
- Kompilyatsiya qilasiz – Sass kodini kompilyator (masalan, node-sass) orqali oddiy CSS'ga o‘girasiz.
- Hosil bo‘lgan CSS kodini brauzer yuklaydi va ishlatadi.

<br>

## Misol (SCSS sintaksisida):

```
// _variables.scss
$primary-color: #3490dc;
$font-size: 16px;



// style.scss
@import 'variables';

body {
  font-size: $font-size;
  background-color: $primary-color;

  h1 {
    color: darken($primary-color, 10%);
  }
}
```

Bu kod Sass kompilyator orqali CSS'ga o‘girganda quyidagi natija hosil bo‘ladi:

```
body {
 font-size: 16px;
 background-color: #3490dc;
}

body h1 {
 color: #2779bd;
}
```

<br>

## Ish jarayoni:

- Sassda kod yoziladi
- sass style.scss style.css orqali kompilyatsiya qilish
- CSS faylni HTML faylga ulash

<br>

Sass ishlashi uchun Node.js o‘rnatilgan bo‘lishi kerak va quyidagicha o‘rnatiladi:

```
npm install -g sass
```

Kompilyatsiya qilish:

```
sass style.scss style.css
```

<hr> <br><br><br><br><br>

# `Sass va CSS o‘rtasidagi asosiy farqlar qanday?`

## Sass va CSS o‘rtasidagi asosiy farqlar

| #   | Sass                                                                       | CSS                                                          |
| --- | -------------------------------------------------------------------------- | ------------------------------------------------------------ |
| 1   | Preprocessor (CSS'dan oldin ishlaydi)                                      | Stil yozish uchun oddiy tillardan biri                       |
| 2   | Variables (o‘zgaruvchilar) ishlatish mumkin                                | O‘zgaruvchilar faqat var() orqali qo‘llanadi (cheklangan)    |
| 3   | Nesting (ichma-ich kod yozish) mumkin                                      | Nestingni to‘liq qo‘llab-quvvatlamaydi                       |
| 4   | Mixins orqali kodni qayta ishlatish mumkin                                 | Mixins mavjud emas                                           |
| 5   | Inheritance orqali kodni meros qilib olish mumkin                          | Meros olish imkoniyati cheklangan                            |
| 6   | Matematik amallar (qo‘shish, ayirish, ko‘paytirish, bo‘lish) bajariladi    | Matematik amallar faqat calc() orqali ishlaydi               |
| 7   | Kodni modullarga bo‘lish va boshqarish mumkin                              | CSS’da to‘g‘ridan-to‘g‘ri modullar yo‘q                      |
| 8   | @import, @use va @forward kabi direktivalar orqali kodni boshqarish mumkin | @import mavjud, lekin to‘liq boshqarish imkoniyati yo‘q      |
| 9   | Kodni kompilyatsiya qilish kerak                                           | Kompilyatsiya qilish shart emas                              |
| 10  | Kengaytirilgan funksiyalar va operatorlar bilan ishlash mumkin             | CSS’da funksiyalar cheklangan (masalan, calc(), var() bilan) |

<br>

## Misollar:

## 1. Variables

### ✅ Sass:

```
$primary-color: #3490dc;

body {
  background-color: $primary-color;
}
```

### ❌ CSS (faqat var() bilan):

```
:root {
  --primary-color: #3490dc;
}

body {
  background-color: var(--primary-color);
}
```

<br>

## 2. Nesting (Ichma-ich yozish)

### ✅ Sass:

```
nav {
  ul {
    list-style: none;

    li {
      display: inline-block;
    }
  }
}
```

### ❌ CSS:

```
nav ul {
  list-style: none;
}

nav ul li {
  display: inline-block;
}
```

<br>

## 3. Mixins

### ✅ Sass:

```
@mixin flex-center {
  display: flex;
  justify-content: center;
  align-items: center;
}

.container {
  @include flex-center;
}
```

### ❌ CSS:

> CSS’da mixin’lar mavjud emas. Kodni qayta yozish kerak.

<br>

### 4. Inheritance

### ✅ Sass:

```
%button-base {
  padding: 10px 20px;
  border-radius: 5px;
}

.btn-primary {
  @extend %button-base;
  background-color: blue;
}
```

### ❌ CSS:

> CSS’da to‘g‘ridan-to‘g‘ri meros olish imkoniyati yo‘q. Kodni qayta yozish kerak.

<br>

## 5. Matematik amallar

### ✅ Sass:

```
$base-size: 16px;

h1 {
  font-size: $base-size * 2;
}
```

### ❌ CSS:

> Faqat `calc()` bilan ishlaydi:

```
h1 {
  font-size: calc(16px * 2);
}
```

## Xulosa

- Sass – Dasturlashga o‘xshash qulayliklarni taqdim etadi (o‘zgaruvchilar, funksiyalar, nesting, va h.k.).
- CSS – To‘g‘ridan-to‘g‘ri brauzer tomonidan tushuniladi va ishlaydi.
- Sass – Murakkab loyihalar uchun juda qulay, CSS esa oddiy loyihalar uchun yetarli.

<hr> <br><br><br><br><br>

# `Sassning qaysi ikki sintaksisi mavjud?`

## 1. SCSS (Sassy CSS)

- 2009-yilda paydo bo‘lgan.
- CSS bilan to‘liq mos keladi (oddiy CSS kodlarini SCSS ichida ishlatish mumkin).
- Qo‘shimcha imkoniyatlar: `variables`, `nesting`, `mixins`, `functions` va boshqalar.
- Qavslar `{}` va nuqta-vergul `;` ishlatish kerak.

## Misol:

```
$primary-color: #3490dc;

body {
  background-color: $primary-color;

  h1 {
    color: darken($primary-color, 10%);
  }
}
```

> `SCSS` sintaksisi `CSS`ga juda o‘xshash, shuning uchun `CSS` yozishga o‘rganib qolgan dasturchilar uchun tushunarli va oson.

<br>

# 2. Indented Syntax (Sass)

- Sassning asosiy sintaksisi bo‘lib, CSS bilan mos emas.
- Qavslar `{}` va nuqta-vergul `;` ishlatilmaydi.
- Joy tashlash `indentation` orqali tuzilish aniqlanadi.
- Kodni soddalashtiradi va kamroq yozishga imkon beradi.

Misol:

```
$primary-color: #3490dc

body
  background-color: $primary-color

  h1
    color: darken($primary-color, 10%)
```

> `Indented syntax` qisqaroq va minimal kod yozishga imkon beradi, lekin CSS bilan mos emas.

<br>

## Asosiy farqlar

| Sintaksis turi | Qavslar `{} ` | Nuqta-vergul`;` | CSS bilan moslik | Joy tashlash orqali tuzilish |
| -------------- | ------------- | --------------- | ---------------- | ---------------------------- |
| SCSS           | Ha            | Ha              | To‘liq mos       | Yo‘q                         |
| Sass           | Yo‘q          | Yo‘q            | Mos emas         | Ha                           |

## Qaysi sintaksisni ishlatish kerak?

- SCSS → Agar CSS bilan ishlashga o‘rgangan bo‘lsangiz va CSS kodlarini to‘g‘ridan-to‘g‘ri ko‘chirishni xohlasangiz.
- Indented Syntax (Sass) → Agar kodni qisqartirishni xohlasangiz va minimal kod yozishga intilsangiz.

> Odatda SCSS kengroq ishlatiladi, chunki u CSS bilan to‘liq mos keladi va o‘rganish osonroq.

<hr> <br><br><br><br><br>

# `.scss va .sass o‘rtasidagi farq`

### SASS ikkita asosiy sintaksisga ega:

- SCSS → `.scss` fayl kengaytmasidan foydalanadi.
- Indented Syntax (Sass) → `.sass` fayl kengaytmasidan foydalanadi.

<br>

| Xususiyat                    | SCSS (.scss)                              | Sass (.sass)                      |
| ---------------------------- | ----------------------------------------- | --------------------------------- |
| Qo‘shilgan yili              | 2009-yil 2006-yil                         |
| Qavslar `{}`                 | Ha                                        | Yo‘q                              |
| Nuqta-vergul `;`             | Ha                                        | Yo‘q                              |
| CSS bilan mosligi            | To‘liq mos                                | Mos emas                          |
| Joy tashlash orqali tuzilish | Yo‘q                                      | Ha                                |
| Ko‘proq ishlatilishi         | Ha (SCSS kengroq tarqalgan)               | Kamroq ishlatiladi                |
| Soddalik                     | CSS’ga o‘xshashligi sababli tushunarliroq | Minimal kod yozishga imkon beradi |


<br>

## Misol:

- CSS bilan to‘liq mos
- Qavslar va nuqta-vergul ishlatiladi

```
$primary-color: #3490dc;

body {
  background-color: $primary-color;

  h1 {
    color: darken($primary-color, 10%);
  }
}
```
> SCSS — oddiy CSS kodiga o‘xshagani uchun o‘rganish oson.


<br>

## Misol:

- Joy tashlash orqali struktura belgilanadi
- Qavslar va nuqta-vergul ishlatilmaydi

```
$primary-color: #3490dc

body
  background-color: $primary-color

  h1
    color: darken($primary-color, 10%)
```

> Sass — minimal kod yozishga imkon beradi, lekin sintaksisi o‘ziga xos.

## Xulosa:

- SCSS - CSS bilan mos, boshlovchilar uchun tushunarliroq.
- Sass - Minimal kod yozish imkonini beradi, lekin o‘rganish biroz qiyinroq.

## Qaysi birini ishlatish kerak?
- SCSS kengroq qo‘llaniladi, chunki u CSS bilan mos keladi.
- Sass qisqaroq sintaksis bilan kod yozish imkonini beradi, lekin ko‘pchilik SCSS'ni tanlaydi.

> Odatda SCSS'ni ishlatish tavsiya qilinadi, chunki u universal va CSS bilan to‘liq mos keladi. 😎

<hr> <br><br><br><br><br>


# `Sassni loyihaga qanday ulash mumkin?`


### Sassni loyihaga ulash uchun 3 ta asosiy usul mavjud:

- `Node.js` va npm orqali o‘rnatish
- `CDN` orqali ulash
- `VS Code` yoki `WebStorm` orqali ulash

<br>

## 1. Node.js va npm orqali ulash

- Bu usul hozirgi kunda eng ko‘p ishlatiladi.
- Sass kodini `.scss` yoki `.sass` faylga yozasiz.
- Kodni kompilyatsiya qilib, `.css` faylga o‘giradi.

<br>

### 1.1 Node.js o‘rnatish

> Agar Node.js o‘rnatilmagan bo‘lsa, `https://nodejs.org` saytidan yuklab oling.

<br>

### 1.2. Sassni npm orqali o‘rnatish

>Terminalni ochib, quyidagi buyruqni bajaring:

```
npm install -g sass
```

> sass global (-g) tarzda o‘rnatiladi.

<br>

### 1.3. Sass kodini yozish
 
 > SCSS fayl: style.scss

```
$primary-color: #3490dc;

body {
  background-color: $primary-color;

  h1 {
    color: darken($primary-color, 10%);
  }
}
```

<br>

### 1.4. SCSS’ni CSS'ga o‘girish

> Terminalda quyidagicha yozing:
  `sass style.scss style.css`
  Kuzatish rejimida ishga tushirish `watch mode`

``` 
sass --watch style.scss:style.css
```

> Bu rejimda `.scss` faylda o‘zgarish qilinsa, avtomatik ravishda `.css` fayl yangilanadi.

<br>

### 1.5. CSS faylni HTML faylga ulash

>index.html faylda style.css faylni chaqirish:

```
<head>
  <link rel="stylesheet" href="style.css" />
</head>
```
