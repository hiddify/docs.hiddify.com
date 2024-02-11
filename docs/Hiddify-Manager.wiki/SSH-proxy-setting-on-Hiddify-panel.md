<div dir=rtl markdown=1>
[**![Lang_farsi](https://user-images.githubusercontent.com/125398461/234186932-52f1fa82-52c6-417f-8b37-08fe9250a55f.png) &nbsp;فارسی**](https://docs.hiddify.com/fa/Hiddify-Manager.wiki/%D8%AA%D9%86%D8%B8%DB%8C%D9%85-%D9%BE%D8%B1%D9%88%DA%A9%D8%B3%DB%8C-SSH-%D8%AF%D8%B1-%D9%BE%D9%86%D9%84-%D9%87%DB%8C%D8%AF%DB%8C%D9%81%D8%A7%DB%8C)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="https://github.com/hiddify/hiddify-config/wiki/All-tutorials-and-videos"><img width="100" src="https://github.com/hiddify/hiddify-config/assets/125398461/8ac5b906-105c-4b98-acf5-0e12e39e33f6" /></a>

</div>

# SSH proxy setting on Hiddify panel

As you know, in version 8 of the Hiddify panel, a proxy for the SSH service has been created, which does not have any access to the server and can only be used as a proxy. This proxy is completely secure and has no fingerprints for identification. (except the SSH protocol itself, which is in general use)

Continue with this tutorial to learn how to make its settings on Hiddify panel.

## Configure SSH proxy settings

First, go to the `SSH proxy` section in the panel `Settings`.

<div align=center markdown=1>
![SSH proxy](https://github.com/hiddify/hiddify-config/assets/125398461/427891b5-dc5a-42c8-beaf-a4e004f06a99)

</div>

Here you can choose your desired port for this proxy. You can also enable or disable this protocol.

## Enable or disable proxy

To do this, go to the `Proxies` section from the `Settings` menu.

<div align=center markdown=1>
![SSH proxy proxy](https://github.com/hiddify/hiddify-config/assets/125398461/bdb7548a-2348-4038-a36e-6e8c37c3e8be)

</div>

Here you can enable or disable the SSH proxy.

## Use config to connect

Now, if you go to your user page in the panel, you will see that the SSH configuration has been added to the previous configurations. This configuration can be added to client app separately.

<div align=center markdown=1>
![user link](https://github.com/hiddify/hiddify-config/assets/125398461/61ec5d9d-40e1-4ac8-825a-2b20f60fdfb8)

</div>

To use this proxy in the client, you must currently use the SingBox app, which is explained in [this tutorial](https://github.com/hiddify/hiddify-config/wiki/Tutorial-for-SingBox-app).
