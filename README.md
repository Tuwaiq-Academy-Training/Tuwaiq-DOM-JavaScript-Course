# Tuwaiq-DOM-JavaScript-Course


# سوف نتعلم في هذا الدرس :
* مقدمة عن DOM 
* الوصول للعناصر DOM 
*
* 
## مقدمة

ـ `DOM` هي اختصار لـ `Document Object Model` وهي واجهة برمجية للوصول والتعامل مع العناصر والمحتوى على صفحة HTML. يتم تمثيل الصفحة بشكل هرمي
حيث يتم تمثيل العناصر بعناصر الشجرة ويتم تمثيل المحتوى بالفروع.
()[]

## الوصول للعناصر DOM
قبل ان نتعلم التلاعب بعناصر DOM , يجب ان نتعلم طريقة اختيار العنصر ( method ) , هنالك طرق كثرة للوصول للعنصر في جافاسكربت :

## ـgetElementById :
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

## ـ getElementsByClassName
في `getElementByClassName` تقوم بالوصول للعنصر عن طريق `classname` , حيث بالرجوع للخصائص الـclassname يجب أن يكون فريد . 

