<div dir="rtl" markdown=1>
[**![Lang_Farsi](https://user-images.githubusercontent.com/125398461/234186932-52f1fa82-52c6-417f-8b37-08fe9250a55f.png) &nbsp;فارسی**](https://docs.hiddify.com/fa/Hiddify-Manager.wiki/%D8%A2%D9%85%D9%88%D8%B2%D8%B4-%D8%A7%D8%B3%D8%AA%D9%81%D8%A7%D8%AF%D9%87-%D8%A7%D8%B2-%D8%B2%DB%8C%D8%B1%D8%AF%D8%A7%D9%85%D9%86%D9%87%E2%80%8C%D9%87%D8%A7%DB%8C-%D9%85%D8%AA%D8%BA%DB%8C%D8%B1-%D8%AF%D8%B1-%D9%87%DB%8C%D8%AF%DB%8C%D9%81%D8%A7%DB%8C)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="https://github.com/hiddify/hiddify-config/wiki/All-tutorials-and-videos"><img width="100" src="https://github.com/hiddify/hiddify-config/assets/125398461/8ac5b906-105c-4b98-acf5-0e12e39e33f6" /></a>

</div>

# Tutorial for using wildcard subdomains on Hiddify

## Wildcard domain registration on Cloudflare

First, create a `*` record on your registered domain on Cloudflare. That is, go to the DNS section and click `Add record`. Then enter a star in the opened page. Fill the field type as A and the value of the IP field with the IP of your server. Make sure the proxy tick is on. That is, if, for example, your domain is `yourdomain.com`, finally register a field `*.yourdomain.com`. [More information on how to register a domain](https://github.com/hiddify/hiddify-config/wiki/Domain-types-and-how-to-register-them)

![image](https://user-images.githubusercontent.com/125398461/235923115-6eaa6bdd-3032-4a9b-aa98-f2fbd8ec4001.png)

For IP version 6, you can do the same thing with a record of `AAAA` type.

![image](https://user-images.githubusercontent.com/125398461/235923332-af16b27e-e624-4d39-974d-1574ad44ea79.png)

## Registration of wildcard domain on Hiddify panel

To do this, go to the domain settings and create a new domain. Create a CDN or AutoCDN domain.

- Therefore, enter `*.yourdomain.com` in the domain name field of the subdomain you registered in the previous step.

- Give the alias a name of your choice.

- Select the mode from CDN or AutoCDN. The difference between CDN domain and AutoCDN is in the way the address field is applied in the configuration, CDN returns the domain name and AutoCDN returns the IP. [More information on this](https://github.com/hiddify/hiddify-config/wiki/Guide-for-using-mode-Auto_CDN_IP-on-Hiddify)

![Screenshot_20230503_164s956](https://user-images.githubusercontent.com/125398461/235928869-3b740a41-ffc0-479a-97a5-65a40ac9de34.png)

- Finally, save the settings to register the domain. If the message to apply changes is given, be sure to click the apply changes button so that the settings are fully applied to the server.

## Viewing configs of wildcard domain

First, go to the subscription domain and tick the wildcard domain in the domain configuration field. Suppose that the domain of the subscription links is `t1.hiddify.com`, edit it and tick the wildcard domain as shown below. With this, the configs of wildcard domain are connected to the subscription link.

![](https://user-images.githubusercontent.com/125398461/235927616-6a5829f0-2558-4584-a3af-4b8f7a286213.png)

## Using configs of wildcard domain

Now, if you have different users on the server, you will see that the configurations created on the wildcard domain for each user, are created on a random subdomain and a separate subdomain is created for each user on Cloudflare.

This helps to prevent the subdomain from being blocked.
