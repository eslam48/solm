# solm

السلام عليكم 
حاولت اعمل نظام مكتبة بسيطه فيه اهم المتطلبات لمصممين الويب 
ايه مميزات المكتبه 
1- تقدر تستدعي ملفات html or css or js باستخدامها و ملفات ال html بتظهار بشكل طبيعي كانه مكتوبه داخل نفس الملف و تقدر تتحكم في الملف المستدعيه و تغير الالوان ... الخ
 
 2- تقدر تعمل موقع 2 لغة و تبدل بينهم بكل بساطه و الغة البتختارها لو قفلت الموقع و فتحتة تاني الموقع بيفتح بنفس الغة الكنت مشغلها قبل كده ولاكن لازم يكون علي شغال علي سيرفر علي جهازك او علي النت
لو الموقع لغتين تقدر تستدعي ملفات الغة الشغاله حالين

3- تقدر تعرف متغيرات عن طريق الجافا سكريبت و المكتبه و تطبع المتغيرات داخل اكواد Html عن طريق بعض الاتربيوتات المستحدثة 

4- فيها اهم حدثين هم on و css

شرح المكتبة 
# 1- تعريف اوبجكت و استخدامه داخل html 
نقدر نخذن مجموعة قيم داخل اوبجت يدعه data و نستعدي الاوبجكت داخل html بطريقة بسيطه جداا
في البداية هنعمل new من الكلاس solm بالشكل ده 
new solm()
الكلام solm هو الكلام الرئيسي داخل المكتبة 
داخل كلاس solm هنكتب {} اقواس الاوبجكت
بنفس الشكل ده

new solm({
el:"هنا نكتب اسم التاج او الكلاس او الايدي",
data:{
test:"solm"
}
})
طبعا ده كود جافا سكريبت 
el بتاخد id او class او tag Html العايز تنفذ عليه الداتا
الاوبجكت data بكتب داخله ممكن نقول انها متغيران و نقدر نستدعيها داخل الصفحة 
داخل ال data يوجد متغير باسم test تقدر تغيره لاي اسم و القيمه solm تقدر تغيرها برضه و تعمل اكتر من keyجديد 
طريقة استدعاء ال key test 
يوجد 4 طرق
الطريقة الاولي 
<p>$test</p>
داخل الكود بنكتب علامه الدولار و اسم المتغير
الطريقة الثانية
<p>${test}</p>
داخل علامات ${} نكتب اسم المتغير

الطريقة الثالثه
<p text="test"></p>
بنكتب اتربيوت text و داخله ال key

الطريقة الرابعه 
لو الvalue مكتوب داخله كود Html 
<p html="test"></p>
بنكتب اتربيوت html و داخله ال key

# 2- استدعاء ملفات Html او css او js

بنكتب داخل كود الجافا سكريبت 
new solm().inc(true)
لازم نستدعي كود الاستدعاء و نمرر براميتر true علشان يشتعل

طريقة استخدامة 
داخل كود html 
<inc src="test.html" type="html"></inc>
src مسار الملف مع الامتداد

type نوع الملف بيقبل 3 انواع html css js

توجد طريقة اخره لاستدعاء الملفات باستخدام الجافا سكريبت فقط
new solm().link("val1","val2")
val1 يستبدل ب مسار الملف
Val2 يستبدل ب نوع الملف 
ملاحظه يقبل نوعين فقط js , Css

# 3- استخدام حدث on و css
طريقة الاستدعاء 
1-css

new solm().css("اسم العنصر",{
"color":"red",
},true)
بدل اسم العنصر بنكتب اسمه او الكلاس او الاي دي و بنقدر نعطي نفس الخواص لاكتر من عنصر
بنكتب اكواد css علي شكل اوبجكت زي ما مكتوب color
بتاخد قيمه true و false
القيمة الافتراضية false
false بمعني كود Css هيتضاف للعنصر نفسه كا اتربيوت
true كواد css بيتضاف في مكان منفصل في ال head

2- on
بنفس طريقة الجيكويري 
new solm().on("اسم الحدث",فانكشن)

# 4- اللغات 
ولاكن علشان يشتغل الغات لازم سيرفر 
في بداية الصفحة في كود html ممكن نضيف اتربيوت lang و نكتب اسم اللغة الافتراضية
اي تاج عايزين نخلي النص لغتين بنضيف اتربيوت $lang و نضيف ليه قيمه 
مثال 
<span $lang="span"></span>

كود الجافا سكريبت بنستدعي ال lang و و بيكون داخل اوبجكت و داخله بنكتب 2 اوبجكت اول اوبجكت بيكون للغة الافتراضية تاني اوبجكة بيكون للغة البديلة و بتاخد قيمه زي مثلا الكود التالي كاتب اسم اللغة البديله en 
new solm().lang({
span:"اختبار",
},{
div1:"eslam",
},"en")
