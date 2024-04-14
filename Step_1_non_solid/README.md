##### Step 1

<table dir='rtl'>
<tbody>
<tr>
<td width="64">
<p><strong>ردیف</strong></p>
</td>
<td width="198">
<p><strong>محل اعمال تغییرات (کلاس/واسط)</strong></p>
</td>
<td width="141">
<p><strong>عنوان تغییر</strong></p>
</td>
<td width="292">
<p><strong>شرحی کوتاه از تغییر</strong></p>
</td>
</tr>

<tr>
<td width="64">
<p><strong>۱</strong></p>
</td>
<td width="198">
<p>MessageService</p>
</td>
<td width="141">
<p>افزودن تابع ارسال پیام تلگرامی</p>
</td>
<td width="292">
<p>افزودن یک تابع void با عنوان sendTelegramMessage</p>
</td>
</tr>

<tr>
<td width="64">
<p><strong>2</strong></p>
</td>
<td width="198">
<p>EmailMessageService</p>
</td>
<td width="141">
<p>افزودن متد ارسال پیام تلگرام</p>
</td>
<td width="292">
<p>افزودن متد sendTelegramMessage به صورت خالی</p>
</td>
</tr>

<tr>
<td width="64">
<p><strong>3</strong></p>
</td>
<td width="198">
<p>SmsMessageService</p>
</td>
<td width="141">
<p>افزودن متد ارسال پیام تلگرام</p>
</td>
<td width="292">
<p>افزودن متد sendTelegramMessage به صورت خالی</p>
</td>
</tr>


<tr>
<td width="64">
<p><strong>4</strong></p>
</td>
<td width="198">
<p>TelegramMessage</p>
</td>
<td width="141">
<p>افزودن کلاس</p>
</td>
<td width="292">
<p>افزودن کلاس برای نوع مسیج های تلگرام و گرفتن ایدی مبدا و مقصد</p>
</td>
</tr>

<tr>
<td width="64">
<p><strong>5</strong></p>
</td>
<td width="198">
<p>TelegramMessageService</p>
</td>
<td width="141">
<p>افزودن کلاس</p>
</td>
<td width="292">
<p>افزود کلاس برای هندل کردم ارسال پیام به از مبدا به مقصد</p>
</td>
</tr>

<tr>
<td width="64">
<p><strong>6</strong></p>
</td>
<td width="198">
<p>Main</p>
</td>
<td width="141">
<p>افزودن تلگرام</p>
</td>
<td width="292">
<p>افزودن انتخاب تلگرام و گرفتن ایدی ها برای اراسل پیام و ساخت اینستنس های کلاس مانند دیگر کلاس ها</p>
</td>
</tr>


</tbody>
</table>

مجموع تعداد تغییرات: 6

##### Step 2 - a

<table dir='rtl'>
<tbody>
<tr>
<td rowspan="2" width="240">
<p>اصل 1</p>
<p>Single Responsibility</p>
</td>
<td width="95">
<p><strong>موارد تحقق</strong></p>
</td>
<td width="454">
<p>میتوان گفت کلاس های ایمیل و اس ام اس  یک کار واحد میکنند و حتی کلاس main نیز یک کنترلر است</p>
</td>
</tr>
<tr>
<td>
<p><strong>موارد نقض</strong></p>
</td>
<td>
<p>&nbsp;</p>
</td>
</tr>
<tr>
<td rowspan="2">
<p>اصل 2</p>
<p>Open-Close Principle (OCP)</p>
</td>
<td>
<p><strong>موارد تحقق</strong></p>
</td>
<td>
<p>نابع main میتوان گفت دقیقا همین موضوع را نشان میدهد و کلاس Message نیز به این صورت است.</p>
</td>
</tr>
<tr>
<td>
<p><strong>موارد نقض</strong></p>
</td>
<td>
<p>کلاس MessageService دقیقا مشکل ماست برای اضافه شدن سرویس جدید هم در خودشو هم در تمامی فرزندانش تغییر ایجاد میشود.</p>
</td>
</tr>
<tr>
<td rowspan="2">
<p>اصل 3</p>
<p>Liskov Substitution Principle</p>
</td>
<td>
<p><strong>موارد تحقق</strong></p>
</td>
<td>
<p>در ارث بری سرویس ها میتوان دید که متد ها به طور درست حضور دارند ولی خالی هستند ولی هر سرویس دقیقا زیر مجموعه از نوع سرویس ماست و حتی خود مسیج ها نیز یر مجموعه از مسیج است </p>
</td>
</tr>
<tr>
<td>
<p><strong>موارد نقض</strong></p>
</td>
<td>
<p>نقض نشده است.</p>
</td>
</tr>
<tr>
<td rowspan="2">
<p>اصل 4</p>
<p>Interface Segregation Principle</p>
</td>
<td>
<p><strong>موارد تحقق</strong></p>
</td>
<td>
<p>ندارد.</p>
</td>
</tr>
<tr>
<td>
<p><strong>موارد نقض</strong></p>
</td>
<td>
<p>اینترفیس سرویس که داریم به طور کامل مشکل دارد  و دقیقا هر متد آن برای یکی از کلاس های زیرین خودش بدرد میخورد و باقی متد ها باید خالی بمانند.</p>
</td>
</tr>
<tr>
<td rowspan="2">
<p>اصل 5</p>
<p>Dependency Inversion Principle</p>
</td>
<td>
<p><strong>موارد تحقق</strong></p>
</td>
<td>
<p>کلاس Message به درستی است و به طور کامل این وابسنگی در آن رعایت شده است.</p>
</td>
</tr>
<tr>
<td>
<p><strong>موارد نقض</strong></p>
</td>
<td>
<p>وابستگی سرویس به زیر مجموعه هایش برای افزایش متد به نظرم مشکل زااست</p>
</td>
</tr>
</tbody>
</table>

##### Step 2 - b
<table dir='rtl'>
<tbody>
<tr>
<td width="198">
<p><strong>اصول مربوطه</strong></p>
</td>
<td width="292">
<p><strong>علت نقض</strong></p>
</td>
<td width="292">
<p><strong>راه حل پیشنهادی</strong></p>
</td>
</tr>

<tr>
<td>
<p>OCP</p>
</td>
<td>
<p>برای گسترش سرویس‌های ارسال پیام واسط MessageService باید تغییر کند</p>
</td>
<td>
<p>حذف توابع مربوط به متود ارسال پیام از MessageService</p>
</td>
</tr>

<tr>
<td>
<p>ISP</p>
</td>
<td>
<p>کلاس‌هایی که واسط MessageService را پیاده‌سازی می‌کنند مجبورند توابع مربوط به دیگر کلاس‌ها را به طور خالی پیاده‌کنند</p>
</td>
<td>
<p>جابجایی این توابع به زیر کلاس‌ها و عدم استفاده از آن‌ها در سطح انتزاع واسط</p>
</td>
</tr>

<tr>
<td>
<p>DIP</p>
</td>
<td>
<p>کلاس MessageService به زیرمجموعه‌هایش وابسته‌است، یعنی اگر متود جدیدی اضافه شود این کلاس باید تغییر کند. پس توابع send message‌ باید به زیر کلاس‌ها منتقل شوند</p>
</td>
<td>
<p>افزودن توابع send message به زیر کلاس‌ها</p>
</td>
</tr>
</tbody>
</table>
