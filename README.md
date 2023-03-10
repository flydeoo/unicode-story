> **Warning**
>
> This README is a work in progress and is subject to change.


<div dir=rtl align=right>

# داستان یونیکد

<p align = "center">
<img src="/asset/saturn-ascii-i.png"  width="500" height="525">
</p>

<p align = "center">
داستان یونیکد

<p align = "center">
(
این تصویر با عنوان ascii art از 
سایت 
 <a href="https://scipython.com/blog/ascii-art">scipython</a> 
قرض گرفته شده است
)

# فهرست 
- [در مورد داستان یونیکد](#در-مورد-داستان-یونیکد)
- [در مورد اسپولسکی](#در-مورد-اسپولسکی)
- [مقدمه](#مقدمه)
- [قسمت اول: یک بیت اضافی](#قسمت-اول-یک-بیت-اضافی)
- [قسمت دوم: اینکدینگ های شخصی](#قسمت-دوم-اینکدینگ-های-شخصی)
- [قسمت سوم: کمی تعریف](#قسمت-سوم-کمی-تعریف)
- [قسمت چهارم: تولد Ansi، سازگاری با آسیا](#قسمت-چهارم-تولد-ansi-سازگاری-با-آسیا)
- [قسمت پنجم: تولد یونیکد](#قسمت-پنجم-تولد-یونیکد)
- [قسمت ششم: صفر های اضافی و UTF-8](#قسمت-ششم-صفر-های-اضافی-و-utf-8)
- [خلاصه](#خلاصه)

- [در حال تهیه: فونت](#)




## در مورد داستان یونیکد

<span dir=ltr>
&nbsp;Joel Spolsky
</span>
بلاگی به نام
joelonsoftware
 دارد
 که داستان یونیکد از دل یکی از نوشته های او در این بلاگ، متولد شده است.

این مقاله در لیست 10 مطلب پرطرفدار این سایت با عنوان:

[The Absolute Minimum Every Software Developer Absolutely, Positively Must Know About Unicode and Character Sets (No Excuses!)](https://www.joelonsoftware.com/2003/10/08/the-absolute-minimum-every-software-developer-absolutely-positively-must-know-about-unicode-and-character-sets-no-excuses/) 

قرار دارد.

> **نکته**
>
> داستان یونیکد با الهام گرفتن از نوشته ی جوئل اسپولسکی و منابع دیگر نوشته شده و طبیعتا به علاقه مندان، دنبال کردن منابع اصلی پیشنهاد می شود.

`داستان یونیکد به جهت نیاز اش به نظرات، پیشنهادات و همکاری در جهت بهبود آن، در گیت هاب منتشر می شود.`


##  در مورد اسپولسکی

<p align = "center">
<img src="/asset/Joel-2016.webp">
</p>


اسپولسکی در سال 2000 از هم بنیانگذاران Fog Creek Software بود که چیز های جالب زیادی مثل FogBugz ، Trello و  Glitch را ایجاد کرد.

همچنین او به همراه Jeff Atwood سایت محبوب برنامه نویسان، Stack Overflow، را ساخت و طی سال های 2010 تا 2019 در آن جا به عنوان CEO مشغول بوده است.


بیشتر بخوانید: [About Joel Spolsky](https://www.joelonsoftware.com/about-me)



##  مقدمه

<p align = "center">
<img src="/asset/onions in submarine.png">

<p align = "center">
پوست کندن پیاز در زیردریایی

<p align = "center">
(
این تصویر توسط هوش مصنوعی
 <a href="https://hotpot.ai/art-generator">hotpot</a> 
ساخته شده است
)



آیا تا به حال در مورد تگ مرموز Content-Type فکر کرده اید؟

 می دانید که همان چیزی است که قرار است در HTML قرار دهید ولی نمیدانید دقیقا چه باید باشد؟

آیا تا به حال یک ایمیل از دوست تان در بلغارستان با عنوان " ???? ?????? ??? ???? " دریافت کرده اید؟

خب این دقیقا issue  اصلی این نوشته است که:  تعدادی از توسعه دهندگان نرم افزار واقعاً در دنیای مرموز character sets, encodings, Unicode و همه این چیزها، کاملاً آماده نیستند.

در اینجاست که اسپولسکی بیانیه ی جالبی دارد:

> اگر شما یک برنامه نویس در سال 2003 هستید و اصول اولیه ی characters, character sets, encodings و Unicode  را نمی دانید، و (اگر) من شما را دستیگر کنم، من شما را به پوست کردن پیاز به مدت 6 ماه در زیر دریایی تنبیه خواهم کرد. قسم میخورم که این کار رو می کنم.

و یک چیز دیگر:

> ### **(یادگیری این مطالب) آن قدر ها هم سخت نیست.**





##  قسمت اول: یک بیت اضافی

در ابتدای مقاله اصلی عنوان میشه که نمی خواد خیلی به قدیم بر گرده و کد گذاری های اون ها رو بررسی کنه.

داستان از این جا شروع میشه که آره، اون اوایل که اینترنت نبود و عملا خیلی ارتباطی به اون صورت شکل نمی گرفت یه جدول ASCII داشتیم که به هر حرف الفبای لاتین یک عدد اختصاص داده بودیم، این رو بهش میگن character encoding.



<p align = "center">
<img src="/asset/ascii table.png">

<p align = "center">
جدول ASCII که جهت "ذخیره سازی" کاراکتر ها، به هر کاراکتر یک عدد نگاشت می دهد.

توی جدول  ASCII، کارکتر های اصلی زبان انگلیسی (حروف الفبا + یک سری علائم نگارشی مثل !،؟،"، + اعداد + ...) بین اعداد 32 تا 127 قرار داشت. 

از 0 تا خود 32 هم یک سری چیز های عمومی مثل space یا null و shift in  و.. قرار داشت.

همونطور که مشخص هست، del آخرین کاراکتر موجود در جدول ascii هست که با عدد 127 مشخص شده.


پس تا اینجا میدونیم که: یک جدول به نام ASCII داریم که به کاراکتر های زبان انگلیسی یک عدد اختصاص میده که بشه ذخیره شون کرد. 

این یعنی چی ؟ یعنی حتی اگر بزرگ ترین کاراکتر توی جدول که به صورت عدد دارای مقدار 127 هست (کاراکتر del ) رو بخوایم ذخیره کنیم، باید عدد 127  ذخیره بشه. 

عدد 127 هم معادل باینری : 

<p align = "center">
<img src="/asset/127.png">


حالا چرا معادل باینری اش رو حساب کردیم؟ می خواستیم به چی برسیم؟

کامپیوتر های اون زمان، بایت های 8 بیتی داشتند. (همین بایت های 8 بیتی هم از اون موقع به ارث رسید برای ما.)

خب کل حرف این هست که اگر کاراکتر هامون رو با ASCII کد کنیم، در نهایت یک عدد بین 0 تا 127 رو باید ذخیره کنیم. این یعنی همیشه یک بیتِ پر ارزش از 8 بیتِ یک بایت خالی می مونه. 

این یعنی اعداد 128 تا 255 همچنان برای اینکد کردن یک کاراکتر موجود هستند ولی در ascii کاراکتری برای اون ها وجود نداره.

<br />


> شما می تونید جدول ascii به همراه فضای خالی باقی مونده در یک بایت رو در [اینجا](/asset/table.md) مشاهده کنید. 

<br />
<br />
<br />

در انتهای قسمت اول، فرصت مناسبی هست برای اینکه بیان کنیم عبارت: 
<div align= left dir= ltr>

```
plain text = ascii = characters are 8 bits
```
 </div>
نه تنها غلط هست بلکه به صورت نا امید کننده ای هم غلط هست. (به نظرتون چرا غلطه؟)




##  قسمت دوم: اینکدینگ های شخصی

تا الان از کاراکتر های ascii و نحوه ی ذخیره شون صحبت کردیم. اینجا مقاله میگه که اگر انگلیسی زبان باشید همه چی تا اینجا برای شما خوبه. (راست میگه)


گفتیم که بایت 8 بیت داره. زمانی که با ascii کد می کنیم کاراکترمون رو، 1 بیت از 8 بیت خالی میمونه.

این یعنی رنج اعداد 128 تا 255 هم برای تعریف کاراکتر موجود هستند (ولی ascii از 0 تا 127 رو فقط استفاده می کرد)


<p align = "center">
<img src="/asset/section 2 .jpg" width="700">




پس خیلی ها به فکرشون افتاد که بیایم از  128 تا 255 رو برای هدف خودمون استفاده کنیم.

<p align = "center">
<img src="/asset/imagination.jpg">

<p align = "center">
ساخت یک اینکدینگ اختصاصی با استفاده از فضایی که در کنار ascii برای تعریف کاراکترها وجود داشت.


این ایده خوب بود ولی مشکل اینجا بود که خیلی ها به صورت همزمان همین ایده رو به صورت های مختلف برای خودشون پیش بردند.

مثلا IBM اومد از 128 تا 255 یه سری کاراکتر درست کرد به اسم OEM که برای رسم خط استفاده میشد و دارای کاراکتر هایی مثل bar افقی و عمودی و خلاصه هر چیزی که مربوط به line drawing میشد، بود.


<p align = "center">
<img src="/asset/oem.webp">

<p align = "center">
OEM


حالا باید اشاره کنم که در همین حین مردم بیرون از آمریکا هم کم کم داشتند pc می خریدند و یکسری هاشون به این فکر افتادند که از 128 (128 تا 255 )کاراکتر ای که بالای جدول ascii وجود داره برای تعریف char set (مجموعه کاراکتر) خودشون استفاده کنند.
مثلا بعضی ها کد 130 رو برای نمایش é استفاده میکردند ولی دقیقا همین کد توی کامپیوتر هایی که زبان عبری داشتند، کاراکتر ג بود.

برا همین اگر یک آمریکایی کلمه ی  résumés رو برای یک اسرائیلی میفرستاد، اون طرف اسرائیلی اون کلمه رو sגsumגr میدید.


در خیلی از موارد مثل زبان روسی، ایده های بسیار مختلفی در مورد اینکه با 128 کاراکتر بالایی (منظور همون 128 کارکتری که بعد از کاراکتر های جدول ascii هستند) چه باید کرد، وجود داشت. به صورتی که با اطمینان نمیشد اسناد روسی رو تبادل کرد. به صورت خلاصه " نمیشد با یکی چهار خط روسی تبادل پیام کنی و اعتماد داشته باشی که اونم همون چیزی که تو نوشتی رو می بینه."



خلاصه وضعیتی شده بود ...


##  قسمت سوم: کمی تعریف

خب حالا که تا اینجا جلو اومدیم، یک مقدار تعاریف رو داشته باشیم:

ما در هر زبانی یک سری کاراکتر داریم، از کاراکتر های حروف الفبا گرفته تا کاراکتر های نگارشی اون زبان و ...
به اینها میگیم مجموعه ی کاراکتری یا همون charset

مثلا همین ascii خودمون، که در  [قسمت اول](#قسمت-اول-یک-بیت-اضافی)
  گفتیم char encoding هست، داره عملیات اینکدینگ خودش رو برای یک مجموعه کارکتر انجام میده.
به اون مجموعه کاراکتر میگیم charset


مثلا خود ascii میگه من  charset ای که دارم رو اینجوری تعریفش میکنم :


<div align= left dir= ltr>

> standard character set for computers and electronic devices

</div>

(یک مجموعه ی کاراکتر استاندارد برای کامپیوتر ها و لوازم الکترونیکی)



این رو هم بگم که این مفاهیم encoding و charset یه مقدار مرزبندی هاش در جا های مختلف؛ اشتباه میشه


صرفا برای اینکه مطمئن بشیم چیزی که گفتیم در مورد charset و encoding درسته، میتونیم [ویکیپدیا](https://en.wikipedia.org/wiki/ASCII) رو چک کنیم  : 

<p align = "center">
<img src="/asset/wikipedia on ascii.jpg">


<div align= left dir= ltr>

> ascii is a character encoding standard for electronic communication

</div>


پس اگر بخواییم خلاصه بگیم، ascii میگه من یک مجموعه ی کاراکتری دارم (char set  ) که 128 تا عضو داره و میتونید توی جدول اسکی ببینیدش.
 بعد اون ها رو میام و به یک عدد 1 بایتی، نگاشت میدم ( encoding  )


دو مفهوم هستند که احتمالا در آینده خیلی باهاشون کار داریم:
 
<div align= left dir= ltr>

> Unicode is a character set. 

> UTF-8 is encoding.

</div>

(بعدا میخونیم یونیکد چی هست، فعلا این رو از ما قبول کنید)





##  قسمت چهارم: تولد Ansi، سازگاری با آسیا
 
 در قسمت دوم [قسمت دوم](#قسمت-دوم-اینکدینگ-های-شخصی)
 گفتیم که کامپیوتر ها 8 بیت برای ذخیره سازی داشتند که ascii  که به هر کاراکتر از مجموعه ی کاراکتری خودش یک عدد اختصاص میداد (ascii is char encoding)، از 0 تا 127 استفاده میکرد. همین باعث شده بود تا بقیه مثل IBM به این فکر بیافتند که "بایت 8 بیت داره، اسکی از 7 بیت استفاده میکنه، پس ما بیاییم از 1 بیت باقی مونده که اعداد 128 تا 255 را برای ما تشکیل می ده، برای خودمون استفاده کنیم و encoding  خودمون رو درست کنیم."


 <br />
<br />
 
 
 
<p align = "center">
<img src="/asset/ansi.jpg">


<div align= center dir= ltr>

windows notepad with ansi encoding

</div>


 در نهایت از دل این ماجرا استاندارد ANSI  متولد شد. در استاندارد ANSI ، همه روی این توافق کردند که 128 کاراکتر اول، همون مجموعه ی کاراکتری ascii  باشند اما اینکه از عدد 128 تا 255 چه کاراکتری قرار داشته باشه، بستگی داره به اینکه شما کجا زندگی میکند. یعنی برای اعداد 128 تا 255 (همون بیت آخری که خالی مونده بود)، یک سیستمی درست کردند به اسم code page . مثلا dos  در اسرائیل از کد پیج 862 استفاده میکرد و در یونان از کد پیج 737. اونها در 128 کاراکتر اول یکی بودند ولی از 128 به بالا متفاوت بودند.
 
 

اما این استاندارد هم مشکلات خودش رو داشت، اول اینکه دو تا زبان رو روی یک سیستم نمیشد به کاربرد چون برای اعداد ها 128 به بالا تفاسیر متفاوتی از کاراکتر ها میشد و مشکل بزرگتر این بود که در آسیا، اوضاع احمقانه به نظر می رسید چون این واقعیت وجود داشت که حروف الفبای بعضی زبان های آسیایی هزاران حرف داشت که عمرا در 8 بیت جا میشد.

 
<p align = "center">
<img src="/asset/am i joke to you.jpg">


<div align= center dir= rtl>

حروف الفبای بعضی زبان های آسیایی

</div>
 
 
این مشکل توسط یه سیستم نامنظم به اسم DBCS (double byte character set) معمولا حل میشد که به این معنا بود که کاراکتر ها در 1 یا 2 بایت ذخیره می شدند. در این سیستم حرکت رو به جلو در یک رشته آسون بود ولی حرکت رو به عقب تقریبا غیر ممکن بود و نهایت کاری که برنامه نویس ها می تونستند انجام بدن استفاده از Windows’ AnsiNext and AnsiPrev بود که بلد بود چجوری با DBCS   کار کنه.

به قول اسپولسکی، whole mess  بود.




##  قسمت پنجم: تولد یونیکد

یونیکد یک تلاش شجاعانه بود برای درست کردن یک مجموعه ی کاراکتری که هر سیستم نوشتاری معقولی رو داشته باشه.

 بعضی ها این تصور غلط رو دارند که در مجموعه ی کاراکتری یونیکد به هر کاراکتر 16 بیت اختصاص داده میشه و در نتیجه بیشتر از 65536 کاراکتر در یونیکد وجود نداره. اما در واقع این درست نیست، هر چند که رایج ترین افسانه در مورد یونیکد همین مورد هست، ولی اگر تا الان اینچنین فکر میکردید، احساس بدی نداشته باشید و ادامه مطلب رو بخونید 😊.

یونیکد به شیوه ی متفاوتی در مورد یک حرف الفبا فکر میکنه. در یونیکد هر حرف به یک چیزی به نام code point  مپ میشه و یک مفهوم تئوری هست.

<p align = "center">
<img src="/asset/Unicode-codePoints.png">


<div align= center dir= ltr>
unicode code point. from <a href="https://wiki.secondlife.com/wiki/Unicode_In_5_Minutes">wiki secondlife</a>

 </div>

<br />
<br />

برای مثال میشه گفت در یونیکد، حرف A  یک مفهوم انتزاعی هست. مثلا A  با B و a متفاوت هست ولی مشابه _A_ و A حساب میشه.

 ایده ی اینکه A در فونت New Roman همان کاراکتری باشد که در فونت Helvetica  است، ولی با a  متفاوت باشد، خیلی بحث برانگیز نیست.

 ولی در بعضی زبان ها اینکه یک حرف چیست، بحث برانگیز می شود. مثلا در زبان آلمانی آیا ß یک حرف واقعی است یا یک شیوه ی تفننی برای نوشتن کاراکتر ss ؟
آیا تغییر حرف در انتهای کلمه(مثل ه در انتهای کلمات فارسی)، یک حرف متفاوت باید حساب شود؟ عبری میگوید آری، عربی میگوید نه.
به هر حال آدم های باهوش در کنسرسیوم یونیکد حواسشون به این موارد هم بوده و نیازی نیست نگران باشید.


تا اینجا یک ذهنیت کلی راجع به یونیکد پیدا کردیم اما این کافی نیست.
گفتیم که در یونیکد به هر کاراکتر یک کد پوینت اختصاص داده میشود. مثلا کاراکتر های کلمه ی Hello دارای کد پوینت های زیر هستند:
 
<div align= center dir= ltr>


> U+0048   U+0065   U+006C   U+006C   U+006F
</div>


 <br />
<br />
 
اما در مورد ذخیره سازی اونها در مموری چیزی نگفتیم و این جایی است که encoding  وارد میشود.

 اولین ایده ی اینکدینگ در یونیکد که باعث آن افسانه شد(محدودیت 2 بایت) این بود که بیاییم قسمت عددی هر کد پوینت را در 2 بایت ذخیره کنیم.

(نکته: خود قسمت عددی کد پوینت ها در چندین plane  قرار می گیرند که توضیح آن مفصل است) به این روش UCS-2  هم می گفتند(به دلیل ذخیره در 2 بایت).


> تفاوتی بین utf-16 , ucs-2 وجود دارد اما به صورت کلی دارای کد پوینت های یکسانی هستند.

 <br />
<br />
 

برای مثال بالا (Hello) داریم : 


<div align= center dir= ltr>


> 00 48 00 65 00 6C 00 6C 00 6F
 </div>

 
که البته میتواند به اینصورت هم باشد :
<div align= center dir= ltr>

> 48 00 65 00 6C 00 6C 00 6F 00
 </div>

 
برای کد پوینت 2 بایت در نظر گرفته شده که به صورت هگز نمایش داده شده و اگر به صورت اول باشه، بهش میگیم big endian  و اگر به صورت دومی باشه بهشون میگیم little endian )



<p align = "center">
<img src="/asset/bom.png">


<div align= center dir= ltr>
Byte Order Mark (BOM). from <a href="https://w3c.github.io/i18n-drafts/questions/qa-byte-order-mark-TEST.en">w3c</a>

 </div>

<br />
<br />
 

خب، در واقع به صورت تکنیکی هر دو مورد ممکن هست و بحث سر low endian  یا hight endian بودن است که بسته به اینکه cpu  آنها در کدام نوع سریع تر بود باید یکی را انتخاب میکردند. بنابراین مردم باید این کار رو با یک نشونه اول هر رشته ی یونیکدی، نشون میدادند که آیا اول FE FF  شروع میشه رشته یا FF FE .  بنابراین مردم مجبور شدند قرارداد عجیب و غریبی برای ذخیره یک FEFF در ابتدای هر رشته یونیکد ایجاد کنند.


به این میگفتن یونیکد بایت اوردر مارک. این یعنی اگر جای بایت های بزرگ و کوچیک برای هر کد پوینت رو تغییر میدادید و اون رو در اول متن با FF FE معرفی میکردید، اون فردی که میخواست متن رو بخونه باید جای هر دو بایت رو با هم عوض کنه. همچنین هر متن یونیکدی که اون زمان وجود داشت، این بایت اوردر مارک رو نداشت.

 <br />
<br />
 
 اوایل به نظر می رسید این به اندازه ی کافی خوب هست ولی برنامه نویسان، غر میزدند که "اون همه صفر رو نگاه کنید"  منظورشون چی بود ؟

 



##  قسمت ششم: صفر های اضافی و UTF-8

گفتیم که در نسخه های ابتدایی یونیکد به هر کد پوینت 2 بایت فضا برای اینکدینگ داده شده بود که البته ابتدای هر رشته ی متنی که قرار بود با یونیکد نوشته بشه هم باید مشخص میشد که ترتیب بایت های هر کد پوینت چه جوری هست.

 اما مشکل برنامه نویس ها چی بود که میگفتند "اون همه صفر رو نگاه کنید"؟


آمریکایی ها متن های انگلیسی رو نگاه می کردند و کاراکتر های این متن ها تا U+00FF بودند و کاراکتر های بعدی اون ها رو معمولا انگلیس زبان ها باهاش کاری نداشتند.


> در عمل برای انگلیس زبان ها همان کاراکتر های جدول اسکی کافی بود، بنابراین 128 کاراکتر جدول اسکی که عددی از 0 تا 127 به آنها نگاشت داده می شود، در کد پوینتی بین U+0000 تا U+007F قرار دارند. در نتیجه انگلیسی زبان ها فقط از کد پوینت های بین 00 تا 7F استفاده می کنند.


خب حالا مشکل چی بود؟ از U+0000 تا U+00FF 
 ، چیزی در حدود 255
تا کاراکتر انگلیسی بود که برای هر کاراکتر 2 بایت فضا اشغال میشد و منظور از صفر ها هم همین صفر هایی بود که در ذخیره سازی این کاراکتر ها بی استفاده می موندن.

<p align = "center">
<img src="/asset/problem.jpg">


اینجا 2 تا مشکل پیش می اومد:


اول اینکه هیچ کس دوست نداشت متنی که داره، 2 برابر فضا بگیره ازش. ( اسکی  با 7 بیت + 1 بیت خالی یک کاراکتر رو ذخیره میکرد، OEM ها با 1 بایت، ANSI با 1 بایت،  DBSC  با 1 تا 2 بایت و یونیکد هم فعلا 2 بایت)


دوم : داکیومنت هایی که از قبل با ANSI  و DBCS نوشته بودیم چی؟ کی حوصله داره اون ها رو به این اینکدینگ جدیدی که یونیکد پیشنهاد میده، تبدیل کنه؟

 
به همین دلایل اکثر مردم تصمیم گرفتند که یونیکد رو نادیده بگیرند ... .

<br />
<br />
<br />
<br />
اوضاع داشت بدتر میشد که UTF-8 ابداع شد.



<pre class="cow">  _____
&lt; UTF-8 &gt;
  -----
         \   ^__^ 
          \  (oo)\_______
             (__)\       )\/\
                 ||----w |
                 ||     ||
    
</pre>
    


 در یو تی اف هشت، کد پوینت های بیت 0 تا 127 در یک بایت ذخیره میشدند، و از 128 به بالا در 2 و 3 و در واقع، تا 6 بایت ذخیره میشدند. با این نوع کد گذاری دیگه هیچ ساید افکتی متوجه کتاب های متنی انگلیسی نمیشد و آمریکایی ها متوجه هیچ خطایی نمیشدند. چرا؟ 


مثلا کلمه ی Hello  رو در نظر بگیرید، این کلمه دارای کد پوینت های زیر هست:


<div align="center">


> U+0048 U+0065 U+006C U+006C U+006F 
 </div>




این کدپوینت ها در یو تی اف 8 به صورت


<div align="center"> 


> 48 65 6C 6C 6F
 </div>


 ذخیره میشه.


صبر کنید!!! این دقیقا همون چیزی هست که توی ASCII ذخیره میکردیم.


همچنین در ANSI، همچنین در هر مجموعه ی کاراکتری OEM.

بله، درسته. با utf-8 سازگاری رو به عقب حفظ میشه.


<p align = "center">
<img src="/asset/Unicode-Encoding.png">


<div align= center dir= ltr>
compare Unicode Encoding. from <a href="https://wiki.secondlife.com/wiki/Unicode_In_5_Minutes">wiki secondlife</a>

 </div>


<br />
<br />
خب تقریبا در انتهای داستان هستیم و باید دلیل یک گزاره که در [قسمت اول](#قسمت-اول-یک-بیت-اضافی) بیان کردیم رو عنوان کنیم:


چرا جمله ی plain text  همون ASCII هست، یک گزاره ی غلطی هست؟


چون اصلا چیزی به عنوان Plain text  وجود نداره. اگر شما یک string  در حافظه، فایل، ایمیل یا هر جای دیگه ای دارید، باید بدونید که چه encoding  ای داره، وگرنه قادر به نمایش اون رشته ی متنی به صورت صحیح نیستید.







##  خلاصه


برای اینکه یک رشته ی متنی رو ذخیره کنیم، راه های متفاوتی رو طی کردیم. شاید کلمه اول درست نباشه ولی از اونجایی که قصد نداریم خیلی خیلی دقیق صحبت کنیم، میگیم که اول با اینکدینگ ASCII  با مجموعه ی کاراکتری 128 عضوی که علی رغم اینکه 1 بیت اضافه میاورد، ولی در 1 بایت ذخیره میشد، شروع کردیم.


بعد اومدند و اون 1 بیت اضافه ی ASCII  رو براش کدینگ های مختلف ارائه کردند. از OEM  گرفته تا ... . تمام این اینکدینگ ها دارای مجموعه ی کاراکتری 256 کاراکتری بودند و در 1 بایت ذخیره می شدند و اتفاقا از 8 بیت اون 1 بایت استفاده می کردند.


در ادامه بر سر این توافق شد که 128 کاراکتر اول مجموعه ی کاراکتری همون 128 تای  ASCII باشه و از 128 تا 255 رو برای هر زبان کاراکتر های اختصاصی خودشون رو قرار بدیم. اینجوری بود که ANSI متولد شد و برای هر زبان یک  code page ارائه شد. خب طبیعتا  اینکدینگ ANSI  دارای مجموعه های کاراکتری مختلف بود که برای هر زبان یک مجموعه ی کاراکتری به خصوص تعریف شده بود که همونطور که اشاره کردیم، بهش page code هم گفته میشد و هر کاراکتر در 1 بایت ذخیره میشد.


بعد از اون مشکلاتی پدید اومد که به سمت DBCS  رفتیم که اندازه ی ثابتی برای هر کاراکتر نداشت و بعضی کاراکتر ها رو در 1 بایت و بعضی ها رو در 2 بایت ذخیره می کرد.

 ولی این اینکدینگ همونطور که حدس می زنید تمام مشکلات ما رو حل نمیکرد و نهایتا مجموعه ی کاراکتری اون 65536 عضو داشت و  از اون مهمتر این بود که پیمایش داخلش خیلی بد بود و خیلی نامنظم نوشته شده بود. اما به هر حال قدم بزرگی بود چون بعد از اون به سمت یونیکد رفتیم. 


در یونیکد یک مقدار مفاهیم انتزاعی شد و برای هر کاراکتر یک کد پوینت در نظر می گرفتیم. در ابتدا اینکدینگ USC-2 رو داشتیم که هر کد پوینت رو در 2 بایت ذخیره میکرد. این یعنی در نهایت مجموعه ی کاراکتری 2 به توان 16، یعنی 65536 عضو داشت. یه مشکل واضح  UCS-2که تا الان نگفتیم، این بود که با ASCII  سازگار(backwards compatible) نبود. ASCII در یک بایت کاراکتر رو ذخیره میکرد ولی  UCS-2در 2 بایت.


با محدودیت تعداد کاراکتر و ناسازگاری و همچنین مشکل high-low-endian  و 2 برابر فضا گرفتن نسبت به ASCII، از UCS-2 استقبال نشد.



تا اینکه UTF-8 قهرمان متولد شد. UTF-8  واقعا هیچکدوم از مشکلات اینکدینگ های قبلی رو نداشت. سازگاری رو به عقب داشت و متون با اینکدینگ ASCII و ... رو ساپورت میکرد و این به خاطر این بود که کد پوینت های یونیکد رو با سایز های متفاوتی ذخیره میکرد. بعضی 1 بایت، بعضی 2، 3، و در نهایت تا 6 بایت. این یعنی یونیکد با UTF-8  تا 2 به توان 48 کاراکتر رو در مجموعه ی کاراکتری اش میتونه ساپورت کنه. 


یعنی 281,474,976,710,656 کاراکتر.



شگفت انگیز است!


</div>
