##### PART 3
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
<p><strong>1</strong></p>
</td>
<td width="198">
<p>MessageService</p>
</td>
<td width="141">
<p>حذف توابع در MessageService</p>
</td>
<td width="292">
<p>توابع واسط MessageService حذف می‌شوند تا در زیرکلاس‌ها بیهوده پیاده‌سازی نشوند</p>
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
<p>حذف توابع بیهوده</p>
</td>
<td width="292">
<p>توابع پیاده‌سازی خالی، حذف می‌شوند</p>
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
<p>حذف توابع بیهوده</p>
</td>
<td width="292">
<p>توابع پیاده‌سازی خالی، حذف می‌شوند</p>
</td>
</tr>


<tr>
<td width="64">
<p><strong>4</strong></p>
</td>
<td width="198">
<p>TelegramMessageService</p>
</td>
<td width="141">
<p>حذف توابع بیهوده</p>
</td>
<td width="292">
<p>توابع پیاده‌سازی خالی، حذف می‌شوند</p>
</td>
</tr>

<tr>
<td width="64">
<p><strong>5</strong></p>
</td>
<td width="198">
<p>Main</p>
</td>
<td width="141">
<p>تغییر کد</p>
</td>
<td width="292">
<p>با توجه به این‌که تابع send***message به زیرکلاس‌ها منتقل شده، برای call شدن نیاز دارند به کلاس خود cast بشوند.</p>
</td>
</tr>

</tbody>
</table>

##### PART 4

- نیازی به انجام مراحل ۱-۲-۳ نخواهد بود

- تنها ۳  تغییر (افزودن مدل، سرویس و تغییر در Main)

