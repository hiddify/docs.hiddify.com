[**🇺🇸 English**](https://docs.hiddify.com/Hiddify-Manager.wiki/How-to-change-SSH-port-on-your-server)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="https://github.com/hiddify/hiddify-config/wiki/%D9%87%D9%85%D9%87-%D8%A2%D9%85%D9%88%D8%B2%D8%B4%E2%80%8C%D9%87%D8%A7-%D9%88-%D9%88%DB%8C%D8%AF%D8%A6%D9%88%D9%87%D8%A7"><img width="100" src="https://github.com/hiddify/hiddify-config/assets/125398461/3704cd84-eee6-4c45-abe7-3c02936bbebb" /></a>

<div dir=rtl markdown=1>
# نحوه تغییر پورت SSH روی سرور

برای تغییر پورت SSH در ابونتو، باید فایل پیکربندی SSH Daemon را تغییر دهید. در اینجا مراحل انجام این کار وجود دارد:

1. **فایل پیکربندی SSH Daemon را باز کنید:**
   فایل پیکربندی SSH daemon یا `sshd_config` را در یک ویرایشگر متن باز کنید. برای ویرایش این فایل معمولاً به سطح دسترسی بالاتری نیاز دارید. می‌توانید از یک ویرایشگر متن خط فرمان مانند `nano` یا `vim` استفاده کنید. مثلا:

<div dir=ltr markdown=1>

    sudo nano /etc/ssh/sshd_config

</div>

2. **بخش `port` را بیابید:**
   به دنبال خطی باشید که با `port` شروع می‌شود. این خط پورتی را مشخص می‌کند که SSH Server به آن گوش می‌دهد. پیش فرض معمولاً `22` است. می‌توانید آن را به هر پورت استفاده نشده تغییر دهید، به عنوان مثال:

<div dir=ltr markdown=1>
    port 2222
</div>

3. **ذخیره و خروج:**
   تغییرات را ذخیره کرده و از ویرایشگر متن خارج شوید. برای `nano`، معمولاً می‌توانید این کار را با فشار دادن `Ctrl + x`، سپس `Y` برای تأیید تغییرات و در نهایت `Enter` برای خروج انجام دهید.

4. **سرویس SSH را راه اندازی مجدد کنید:**
   پس از اصلاح فایل پیکربندی، باید سرویس SSH را مجددا راه اندازی کنید تا تغییرات اعمال شوند. از دستور زیر استفاده کنید:

<div dir=ltr markdown=1>

    sudo service ssh restart

</div>

همچنین، می‌توانید از دستور زیر در نسخه‌های جدیدتر اوبونتو استفاده کنید:

<div dir=ltr markdown=1>
    sudo systemctl restart ssh
</div>

5. **تغییرات را تأیید کنید:**
   با اجرای دستور زیر می‌توانید چک کنید که SSH اکنون به پورت جدید گوش می‌دهد:

<div dir=ltr markdown=1>
    netstat -tuln | grep <new_port>
</div>

`<new_port>` را با شماره پورتی که در فایل پیکربندی مشخص کرده‌اید، جایگزین کنید.

6. **به روز رسانی قوانین فایروال با استفاده از `iptables` در لینوکس:**
   اگر از `iptables` برای مدیریت فایروال استفاده می کنید، مطمئن شوید که قوانین را به روز کنید تا ترافیک در پورت SSH جدید مجاز باشد.

<div dir=ltr markdown=1>
    sudo iptables -A INPUT -p tcp --dport 2222 -j ACCEPT
</div>

`2222` را با پورت SSH جدید خود جایگزین کنید.

پس از افزودن یک قانون، ممکن است لازم باشد تغییرات را ذخیره کنید تا در طول راه‌اندازی مجدد پایدار بماند. روش ذخیره قوانین بسته به توزیع لینوکس شما می تواند متفاوت باشد.

برای اوبونتو، می توانید از دستورات iptables-save و iptables-restore استفاده کنید:

<div dir=ltr markdown=1>
    sudo sh -c 'iptables-save > /etc/iptables/rules.v4'
</div>

این دستور قوانین فعلی iptables را در یک فایل ذخیره می کند و می توانید آنها را با:

<div dir=ltr markdown=1>
    sudo sh -c 'iptables-restore < /etc/iptables/rules.v4'
</div>

به یاد داشته باشید که تغییر پورت SSH می تواند امنیت را با کاهش قابل پیش بینی آن افزایش دهد، اما همچنین ضروری است که قوانین فایروال خود را به روز کنید و پورت جدید را هنگام اتصال به خاطر بسپارید.
