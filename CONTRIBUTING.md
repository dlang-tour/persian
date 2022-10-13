# روش مشارکت در ترجمه

## شروع کار

### مقدمات

* آخرین نسخه گیت را [دانلود](https://git-scm.com/downloads) و نصب کنید.
* مطمئن شوید که یک حساب [github](https://github.com/join) دارید.
* [نام کاربری](https://docs.github.com/en/get-started/getting-started-with-git/setting-your-username-in-git) و [ایمیل](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-email-preferences/setting-your-commit-email-address) خود را در گیت تنظیم کنید.

```sh
git config --global user.name 'نام کاربری شما'
git config --global user.email 'ایمیل شما'
```

### آماده سازی مخزن

* روی دکمه [Fork](https://github.com/dlang-tour/persian/fork) برای گرفتن یک فورک از این مخزن کلیک کنید
* فورک خودتان را کلون کنید(`{username}` را با نام کاربری خودتان جایگزین کنید.)

```sh
git clone git@github.com:dlang-tour/persian.git persian
cd persian
git remote add fork git@github.com:{username}/persian.git
```

## ترجمه

برای **بحث** و **اختصاص** یک بخش برای ترجمه بهتر است که [ایشو](https://github.com/dlang-tour/persian/issues/new)
با توضیحاتی درباره بخشی که شما برای ترجمه آن مشتاق هستید و همچنین برای مدیریت بهتر پیشرفت ترجمه ایجاد کنید.

* پس از اختصاص بخش، ترجمه را شروع کنید. میتوانید از هر کد ادیتوری برای ترجمه استفاده کنید ولی پیشنهاد میکنیم که از [ایمکس](https://www.gnu.org/software/emacs/) یا [vscode](https://code.visualstudio.com/) -بدلیل پشتیبانی بهتر از rtl- استفاده کنید.

> **نکته:**
> اگر میخواهید از emacs استفاده کنید، پیشنهاد میکنیم که از فریمورک [doomemacs](https://doomemacs.org) استفاده کنید.
> اگر از vscode استفاده خواهید کرد، افزونه [rtl-markdown](https://marketplace.visualstudio.com/items?itemName=dalirnet.rtl-markdown) ممکن است که به شما کمک کند.

برای ترجمه میتوانید از ماشین های ترجمه نظیر [گوگل ترنسلیت](https://translate.google.com) استفاده کنید اما توجه داشته باشید که ممکن است بخشی به اشتباه ترجمه شود.

* اکنون یک برنچ ایجاد کنید(`{name}` را با اسم برنچ جایگزین کنید. پیشنهاد میکنیم که اسم برنچ مشابه اسم بخشی باشد که درحال ترجمه هستید.)

```sh
git checkout -b {name}
```

### واژه نامه

برای ثبات در ترجمه‌های ما، در اینجا چند گزاره و یادآوری برای اصطلاحات مکرر که باید ترجمه کنید، وجود دارد، در صورت مخالفت، از باز کردن ایشو در اینباره دریغ نکنید.

| اصطلاح | ترجمه پیشنهادی |
| ----------- | ------ |
| ... | ... |

## پیش‌نمایش

شما برای اجرا و بررسی پیش‌نمایش مستندات نیاز به [dlang](https://dlang.org/) دارید.

پس از نصب **dlang** مراحل زیر را برای بررسی پیش‌نمایش، مراحل زیر را دنبال کنید:

* شما نیاز دارید که مخزن اصلی(زبان انگلیسی) را توسط [dub](https://github.com/dlang/dub) فتچ کنید.

```sh
dub fetch dlang-tour
```

* اکنون میتوانید `dlang-tour` را برای پیش‌نمایش در دایرکتوری اصلی مخزن اجرا کنید:

```sh
dub run dlang-tour -- --lang-dir .
```

## ارسال ترجمه

حالا وقت آن است که ترجمه را ارسال کنید! برای این کار مراحل زیر را دنبال کنید:

* اول شما باید تغییرات خودتان را کامیت کنید.(`{path}` را با مسیر فایل و `{example}` را با نام بخشی که ترجمه کردید جایگزین کنید.)

```sh
git add {path}
git commit -m "translate {example}
```

* اکنون تغییرات خودتان به برنچی که در مرحله ترجمه ساختید پوش کنید(`{name}` را با اسم برنچ جایگزین کنید)

```sh
git push fork {name}
```

اکنون تنها مرحله ایجاد PR باقی مانده است.

### ایجاد یک PR

* به فورک خود بروید. یک اعلانی خواهید دید. روی Compare & pull request کلیک کنید تا یک PR ایجاد کنید.
* اطلاعات درخواست شده در PR را تکمیل کنید.

ممنونیم! به زودی PR شما بررسی خواهد شد!
