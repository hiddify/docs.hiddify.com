<div dir="rtl" markdown=1>
[**![Lang_Farsi](https://user-images.githubusercontent.com/125398461/234186932-52f1fa82-52c6-417f-8b37-08fe9250a55f.png) &nbsp;فارسی**](https://docs.hiddify.com/fa/Hiddify-Manager.wiki/%D8%A2%D9%85%D9%88%D8%B2%D8%B4-%DA%A9%D8%A7%D8%B1-%D8%A8%D8%A7-%D9%86%D8%B1%D9%85%E2%80%8C%E2%80%8C%D8%A7%D9%81%D8%B2%D8%A7%D8%B1-Nekobox)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="https://github.com/hiddify/hiddify-config/wiki/All-tutorials-and-videos"><img width="100" src="https://github.com/hiddify/hiddify-config/assets/125398461/8ac5b906-105c-4b98-acf5-0e12e39e33f6" /></a>

</div>

# Tutorial for Nekobox app

This application is one of the applications that can be used for Android, which works relatively well for old devices.

## Download the application

To download, you can refer to the GitHub of the project [here](https://github.com/MatsuriDayo/NekoBoxForAndroid).

## Initial settings

- Activate the `use system dns as direct dns option` through `Settings`.
- Also set `subscription min tls version` to `1.3`.

> Note: if you are using old devices, set `tls` to `1.2`.

<div align=center markdown=1>
<img width=30% src="https://github.com/hiddify/hiddify-config/assets/125398461/f1a0c7d6-ab17-4b82-9018-894675826633" />

</div>

<div align=center markdown=1>
<img width=30% src="https://github.com/hiddify/hiddify-config/assets/125398461/79262031-045c-4b20-b6da-9c52cdc0b37c" />

</div>

## Add subscription link

- Copy the `subscription link` of the user from the panel.
- Enter the `group` section and create a `new group`.

<div align=center markdown=1>
<img width=30% src="https://github.com/hiddify/hiddify-config/assets/125398461/d57ce407-f0b6-4b98-ade4-e9b3e40b62e5" />

</div>

- Set the `group type` option to `subscription`.
- Click on `subscription link` and enter the subscription link.
- Enable `force resolve` and `auto update` options.
- Save the created `group` and wait for the update to finish.

<div align=center markdown=1>
<img width=30% src="https://github.com/hiddify/hiddify-config/assets/125398461/0f8151e7-935b-49ba-a3f6-aa40f5b482ac" />

</div>

## Tutorial on making Proxy Chain

In this method, the traffic is transferred from one proxy to another, and it allows you to remain hidden or anonymous much longer than the previous methods, and also to be more secure.

- Configure the `add` or `import` option through `manual settings`.

- Select `Proxy chain`.

<div align=center markdown=1>
<img width=30% src="https://github.com/hiddify/hiddify-config/assets/125398461/b6f50216-4560-4ca5-97ac-143e14b2f466" />

</div>

- Click `Add profile` and select and enter, for example, a reality config.

- For the second proxy, for example, we use Cloudflare worker and save the profile.

- Now go [here](https://ip.gs/) to check if it was done correctly. If Cloudflare's IP is seen, it means the job is done correctly.

<div align=center markdown=1>
<img width=30% src="https://github.com/hiddify/hiddify-config/assets/125398461/3451ad3c-c87c-47d0-a970-f497450a2af3" />

</div>

> Note: When using this method, the ping test may encounter an error, which is a bug that needs to be fixed. But the filter connection is established and there is no problem.

> You can also use `http` and `socks5` in this method.

> You can also use more than 2 proxies to connect at the same time.
