---
title: Declare Variables
localeTitle: تعلن المتغيرات
---
# تعلن المتغيرات

يمكن فرز تعريفات المتغير JavaScript إلى ثلاثة مكونات متميزة: نوع المتغير ، واسم المتغير ، وقيمة المتغير.

 `    var myName = "Rafael"; 
` 

دعنا نكسر سطر الشفرة الموضح أعلاه في الأجزاء التي تصنعه:

 `    var/const/let 
` 

يمكن أن تحتوي متغيرات JavaScript على ثلاثة أنواع تعريف: var و const و let. تعتبر متغيرات Var-type عالمية ، إذا تم الإعلان عنها خارج إحدى الوظائف ، فيمكن الوصول إليها بواسطة أي ملف JS (أو وحدة التحكم) ، وفي حالة إنشائها داخل إحدى الوظائف ، يمكن الوصول إليها بغض النظر عن نطاق المنع. تقتصر متغيرات Let-type على نطاقها. انظر المثال أدناه للاختلاف.

 `     function varTest() { 
      var x = 1; 
      if (true) { 
        var x = 2;  // same variable! 
        console.log(x);  // 2 
      } 
      console.log(x);  // 2 
    } 
 
    function letTest() { 
      let x = 1; 
      if (true) { 
        let x = 2;  // different variable 
        console.log(x);  // 2 
      } 
      console.log(x);  // 1 
    } 
` 

يكون للمتغيرات من نوع Const نفس النطاق مثل المتغيرات (نطاق الكتلة) ، لكنها غير قابلة للتغيير. أيا كانت القيمة التي يجب تعيين متغير نوع const ، يجب أن يحدث عندما يتم التصريح عن المتغير ، وستقوم JavaScript بإلقاء خطأ إذا تم تغيير المتغير في وقت لاحق.

 `    const genre = "non-fiction"; 
    console.log(genre); // "non-fiction"; 
    genre = "fantasy"; // error 
` 

الآن يمكننا تحديد نوع المتغير ، دعنا نلقي نظرة على الاسم. تتم كتابة أسماء المتغيرات JavaScript في تنسيق `camel case` . مثال على حالة الإبل هو: `camelCase` . في سياق مثالنا:

 `    myName 
` 

الاسم أيضًا سنصل إلى المتغير مرة أخرى لاحقًا:

 `    console.log(myName); // "Rafael" 
` 

أخيرا ، لدينا قيمة:

 `    "Rafael" 
` 

يتم كتابة JavaScript بشكل حيوي ، مما يعني أن أي متغير معين يمكن أن يمثل أي نوع بيانات معين في أي وقت معين. فمثلا:

 `    var example = "This is an example"; 
    example = [0, 1, 2, 3] 
    example = {test: "Result"} 
    example = 5 
` 

جميع هذه التصريحات صالحة تمامًا - يمكن أن تقفز متغيرات جافا سكريبت من السلسلة إلى المصفوفة إلى الاعتراض على عدد صحيح.

### قم بتعريف كائن const

كما ذكر أعلاه ، متغير Const هو قيمة غير قابلة للتغير يتم تعيينها لمثل هذا المتغير في وقت الإعلان ، ولكن هناك نقطة يجب ملاحظتها في بيان حالة الحالة مع const. لا يمكن تحديث كائن نوع const أيضًا بعد تعريفه ولكن تكون خصائص كائن الكائن. فمثلا.

 `    const Car1 = { 
        name: 'BMW', 
        model: 'X1', 
        color: 'black' 
    } 
` 

هنا ، لا يمكننا تحديث الكائن ولكن يمكننا تحديث الخصائص عن طريق الوصول إلى من خلال نقطة (.) المشغل على النحو التالي.

 `    Car1.color = 'Red'; 
    console.log(Car1); 
    O/P - {name: "BMW", model: "X1", color: "Red"} 
` 

إذا احتجنا إلى جعل كائن enitre غير قابل للتغيير (بما في ذلك الخصائص) ، فعلينا استخدام طريقة التجميد.