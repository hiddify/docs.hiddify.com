<div dir="rtl" markdown="1">

[**![flag_of_Iran](https://user-images.githubusercontent.com/125398461/234186932-52f1fa82-52c6-417f-8b37-08fe9250a55f.png) &nbsp;فارسی**](https://docs.hiddify.com/fa/Hiddify-Manager.wiki/%D8%A2%D9%85%D9%88%D8%B2%D8%B4-%D8%AE%D8%A7%D9%85%D9%88%D8%B4-%DA%A9%D8%B1%D8%AF%D9%86-%D8%A2%DB%8C%D9%BE%DB%8C-%D9%88%D8%B1%DA%98%D9%86-%DB%B6-%D8%AF%D8%B1-%D9%87%DB%8C%D8%AF%DB%8C%D9%81%D8%A7%DB%8C)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="https://github.com/hiddify/hiddify-config/wiki/All-tutorials-and-videos"><img width="100" src="https://github.com/hiddify/hiddify-config/assets/125398461/8ac5b906-105c-4b98-acf5-0e12e39e33f6" /></a>

</div>

# How to disable IP version 6 on Hiddify

IP version 6 is a new IP structure that was introduced after IP version 4. This structure is 64 bits and contains 6 sections of 4 hex characters. Hex is based on 16 numbers.

Its structure is as follows:

`1ec2:5b7a:9fab:cdef:cfab:5a7c`

Because IP version 6 has a wide range, it is much harder to filter than IP version 4. But sometimes, despite the advantages of IP version 6, it is necessary to turn off this version of IP. For example, the Google search error (403 error) is solved by turning off IP version 6. There are two ways to do this.

## How to disable IP version 6 on Hiddify

Just enter the general settings in the panel settings and activate the `IP version 4 only` option.

<div align=center markdown=1>
<img src="https://github.com/hiddify/hiddify-config/assets/125398461/6f2d4977-6e79-4849-9d10-0c765051306c" />
</div>

## How to disable IP version 6 via SSH

- If for any reason you need to turn off IP version 6 via SSH, [connect to your server via SSH](https://github.com/hiddify/hiddify-config/wiki/How-to-connect-to-server-via-SSH), and exit the Hiddify menu with `ctrl+c`.

- Open the system settings file with nano text editor.

```
sudo nano /etc/sysctl.conf
```

- At the end of the opened file, put the following three lines.

```
net.ipv6.conf.all.disable_ipv6=1
net.ipv6.conf.default.disable_ipv6=1
net.ipv6.conf.lo.disable_ipv6=1
```

- Save the file with `ctrl+s` and press `ctrl+x` to exit.
- Finally, reset the settings file with the command below.

```
sudo sysctl -p
```

- By doing this, IP version 6 will be turned off on your server and the server will only work with IP version 4.
