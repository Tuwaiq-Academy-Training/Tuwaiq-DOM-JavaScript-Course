# Tuwaiq-DOM-JavaScript-Course


# سوف نتعلم في هذا الدرس :
* مقدمة عن DOM 
* الوصول للعناصر DOM 
* التلاعب في عناصر DOM
* إضافة و حذف عناصر الـDOM
* احداث DOM (DOM Events)  
## مقدمة

ـ `DOM` هي اختصار لـ `Document Object Model` وهي واجهة برمجية للوصول والتعامل مع العناصر والمحتوى على صفحة HTML. يتم تمثيل الصفحة بشكل هرمي
حيث يتم تمثيل العناصر بعناصر الشجرة ويتم تمثيل المحتوى بالفروع.

()[]

### الوصول للعناصر DOM
قبل ان نتعلم التلاعب بعناصر DOM , يجب ان نتعلم طريقة اختيار العنصر ( method ) , هنالك طرق كثرة للوصول للعنصر في جافاسكربت :

### ـgetElementById :
في `getElementById` تقوم بالوصول للعنصر عن طريق `Id` , حيث بالرجوع للخصائص الـID يجب أن يكون فريد . 
مثلا :
```js
// index.html
    <h1 id="page-title">Hello There!</h1>
```
```js
// index.js 
        const element = document.getElementById("page-title");
```
تم تحديد Id خاص بعنصر h1 وقيمته `page-title` في ملف html و في ملف js قمنا بتخزين القنصر في متغير باسم `element ` حتى نستطيع الوصول اليه بسهوله .

### ـ getElementsByClassName
في `getElementByClassName` تقوم بالوصول للعنصر عن طريق `classname` , حيث بالرجوع للخصائص الـclassname يجب أن يكون فريد .
```js
//index.html
 <p class='my-class'><p>
```js
//index.js
const elements = document.getElementsByClassName("my-class");
```


### ـ querySelector 
تم تصميم الطريقة querySelector() في جافاسكريبت للوصول إلى العناصر في مستند HTML باستخدام محددات CSS. تستخدم هذه الطريقة البحث في العناصر التي تطابق المحدد المعطى وترجع العنصر الأول الذي تم العثور عليه. .
وتكون صيغة كالتالي :
```js
element = document.querySelector(selector);
```
حيث:

ـ selector هو المحدد الذي يستخدم للوصول إلى العنصر المطلوب في مستند HTML.
وترجع هذه الطريقة العنصر الأول الذي تم العثور عليه ، وإذا لم يتم العثور على أي عنصر ، فترجع القيمة null.

مثال:
```js
//index.html
<ul>
  <li class="item">Item 1</li>
  <li class="item">Item 2</li>
  <li class="item">Item 3</li>
</ul>

```
```js
//index.js
const listItem = document.querySelector('.item');
console.log(listItem.textContent); // output : Item 1
```
### ـ querySelector
الدالة querySelectorAll() هي دالة من دوال جافاسكريبت المستخدمة في تحديد مجموعة من العناصر في صفحة HTML باستخدام محددات مختلفة وإرجاعها كمجموعة عناصر NodeList.

تستخدم querySelectorAll() بشكل شائع في تحديد جميع العناصر التي تتطابق مع تحديد CSS معين، مثل تحديد جميع الصور في الصفحة أو تحديد جميع الروابط التي تحتوي على كلمة معينة.

يمكن استخدام querySelectorAll() بشكل مشابه لـ querySelector() ولكن بدلاً من إرجاع عنصر واحد فقط، فإنه يعيد مجموعة من العناصر التي تتطابق مع المحدد.

مثال:
```js
//index.html 
<ul id="myList">
  <li>عنصر 1</li>
  <li class="selected">عنصر 2</li>
  <li>عنصر 3</li>
  <li class="selected">عنصر 4</li>
  <li>عنصر 5</li>
</ul>
```

```js
//index.js 
// تحديد جميع العناصر li الذين لديهم الفئة "selected"
const selectedItems = document.querySelectorAll("li.selected");

// تحديد جميع الروابط الذين يحتويون على كلمة "google"
const googleLinks = document.querySelectorAll("a[href*='google']");

// الوصول إلى العناصر في NodeList
for (let i = 0; i < selectedItems.length; i++) {
  console.log(selectedItems[i].textContent);
}
```
في هذا المثال ، تم استخدام querySelectorAll() لتحديد جميع العناصر li التي تحتوي على الفئة selected وجميع الروابط التي تحتوي على كلمة google، ثم تم الوصول إلى العناصر في NodeList باستخدام حلقة for وطباعتها في وحدة التحكم.


## التلاعب في عناصر DOM :
يمكن استخدام JavaScript لتعديل عناصر DOM (Document Object Model) وتغيير مظهر الصفحة بناءً على الأحداث والإجراءات المختلفة. وفيما يلي بعض الطرق الشائعة لتعديل عناصر DOM باستخدام JavaScript:
1 - innerHTML
يتيح لك innerHTML استبدال محتويات عنصر HTML. يمكن استخدام هذه الطريقة لإنشاء أو تعديل عناصر HTML في صفحتك.
مثال :
```js
//index.html
<div id="example"></div>
```
```js
//index.js
let exampleDiv = document.getElementById("example");
exampleDiv.innerHTML = "<p>new text !</p>";
```
2 - textContent
يمكن استخدام textContent لتغيير النص الموجود داخل عنصر HTML.

```js
//index.html
<p id="example">النص الأصلي</p>
```
```js
// index.js
let exampleP = document.getElementById("example");
exampleP.textContent = "النص الجديد";
```

3 - style
يمكن استخدام style لتعيين خصائص CSS لعناصر HTML. يمكن تعيين الخصائص مباشرة باستخدام JavaScript.
```js
//index.html
<p id="example">element HTML</p>
```
```js
//index.js
let exampleP = document.getElementById("example");
exampleP.style.color = "red";
exampleP.style.backgroundColor = "yellow";
```
4 - classList
يمكن استخدام classList لإضافة أو إزالة فئات CSS من عناصر HTML.
```js
//html
<p id="example" class="oldClass">element  HTML</p>
```
```js
//JS
let exampleP = document.getElementById("example");
exampleP.classList.remove("oldClass");
exampleP.classList.add("newClass");
```
5 - setAttribute
يمكن استخدام setAttribute لتعيين أي سمة HTML. يتم تحديد السمة وقيمتها كمعلمات(class,id).
```js
//html
<h1 id="example">h1 element HTML</h1>
```
```js
//JS
let exampleH1 = document.getElementById("example");
exampleH1.setAttribute("class", "newClass");
```

# إضافة و حذف عناصر الـDOM :
يمكن باستخدام JS اضافة عناصر جديده و حذف العناصر .
## إنشاء عنصر جديد 
للإنشاء عنصر جديد نستخدم `createElement()`  :
```js
const element = document.createElement("div");
```
حيث سيقوم createElement() بانشاء عنصر div في صفحة html .
## إضافة عنصر :
للإضافة عنصر جديد للـ صفحة الـHtml نسعمل appendChild مثال :
```js
const parentElement = document.getElementById("myId");
const newElement = document.createElement("div");
parentElement.appendChild(newElement);
```
حيث قمنا بإضافة عنصر div الى العنصر myId الي يعتبر  العنصر الاب .
## حذف العناصر 
للـحذف عنصر من مستند Html باستخدام عناصر DOM , يمكن استعمال remove() :
```js 
const element = document.getElementById("myId");
element.remove();
```
حيث حددنا العنصر "myId" في متغير element و منثما قمنا بإستعمال remove() للحذف العنصر من مستند الـ html .

# احداث DOM (DOM Events) :
تعني مصطلح DOM Events في JavaScript حدوث حدث معين داخل صفحة HTML، مثل النقر على زر أو تحميل صفحة. ويتم استخدام الأحداث في JavaScript لتتبع تفاعل المستخدم مع صفحة الويب وتنفيذ تحديثات وإجراءات محددة استنادًا إلى هذه الأحداث.

يمكن للأحداث أن تحدث بشكل تلقائي أو يتم تنشيطها بواسطة المستخدم. ولكل حدث DOM خاصية (event property) تحتوي على معلومات عن الحدث المحدد. ويمكن استخدام معالجة الأحداث في JavaScript لتنفيذ مهام مختلفة، مثل تغيير خصائص DOM أو تشغيل وظائف معينة.

وفيما يلي بعض أمثلة للأحداث الشائعة في JavaScript:

* click: يحدث عند النقر على عنصر DOM.
* submit: يحدث عند تقديم نموذج HTML.
* keydown: يحدث عندما يضغط المستخدم على زر المفتاح.
* load: يحدث عندما تتم تحميل صفحة الويب بالكامل.
* 
وبشكل عام، يمكن استخدام addEventListener() لربط وظيفة JavaScript بحدث DOM محدد. وفيما يلي مثال بسيط لاستخدام addEventListener() مع الحدث click:

```js
//html
<button id="myBtn">Click me!</button>
```
```js
const myButton = document.querySelector('#myBtn');
myButton.addEventListener('click', function() {
  console.log('Button clicked!');
});
```
في هذا المثال، يتم استخدام querySelector() لتحديد الزر myButton، ثم يتم استخدام addEventListener() لربط وظيفة JavaScript بالحدث click. وعند النقر على الزر، سيتم عرض رسالة "Button clicked!" في وحدة التحكم في المتصفح.
