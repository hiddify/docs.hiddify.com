<div dir="rtl" markdown="1">

[**![Lang_Farsi](https://user-images.githubusercontent.com/125398461/234186932-52f1fa82-52c6-417f-8b37-08fe9250a55f.png) &nbsp;فارسی**](https://docs.hiddify.com/fa/Hiddify-Manager.wiki/%D9%86%D8%AD%D9%88%D9%87-%D8%AA%D8%BA%DB%8C%DB%8C%D8%B1-%D9%BE%D9%88%D8%B1%D8%AA-SSH-%D8%B1%D9%88%DB%8C-%D8%B3%D8%B1%D9%88%D8%B1)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="https://github.com/hiddify/hiddify-config/wiki/All-tutorials-and-videos"><img width="100" src="https://github.com/hiddify/hiddify-config/assets/125398461/8ac5b906-105c-4b98-acf5-0e12e39e33f6" /></a>

</div>

# How to change SSH port on your server

To change the SSH port on Ubuntu, you'll need to modify the SSH daemon configuration file. Here are the steps to do this:

1. **Open the SSH Daemon Configuration File:**
   Open the SSH daemon configuration file (`sshd_config`) in a text editor. You will typically need elevated privileges to edit this file. You can use a command-line text editor like `nano` or `vim`. For example:

   ```bash
   sudo nano /etc/ssh/sshd_config
   ```

2. **Locate the 'Port' Directive:**
   Look for the line that starts with `Port`. This line specifies the port on which the SSH server listens. The default is usually `22`. You can change it to any unused port, for example:

   ```
   Port 2222
   ```

3. **Save and Exit:**
   Save the changes and exit the text editor. For `nano`, you can typically do this by pressing `Ctrl + X`, then `Y` to confirm the changes, and finally `Enter` to exit.

4. **Restart the SSH Service:**
   After modifying the configuration file, you need to restart the SSH service for the changes to take effect. Use the following command:

   ```bash
   sudo service ssh restart
   ```

   Alternatively, you can use the following command on more recent Ubuntu versions:

   ```bash
   sudo systemctl restart ssh
   ```

5. **Verify the Changes:**
   You can verify that SSH is now listening on the new port by running:

   ```bash
   netstat -tuln | grep <new_port>
   ```

   Replace `<new_port>` with the port number you specified in the configuration file.

6. **Update Firewall Rules using `iptables` in Linux:**
   If you are using `iptables` as firewall manager, make sure to update the rules to allow traffic on the new SSH port.

   ```bash
   sudo iptables -A INPUT -p tcp --dport 2222 -j ACCEPT

   ```

   Replace `2222` with your new SSH port.

   After adding a rule, you may need to save the changes to make them persistent across reboots. The method for saving rules can vary depending on your Linux distribution.

   For Ubuntu, you can use the iptables-save and iptables-restore commands:

   ```bash
   sudo sh -c 'iptables-save > /etc/iptables/rules.v4'
   ```

   This command saves the current iptables rules to a file, and you can restore them with:

   ```bash
   sudo sh -c 'iptables-restore < /etc/iptables/rules.v4'
   ```

Remember that changing the SSH port can enhance security by making it less predictable, but it's also essential to update your firewall rules and remember the new port when connecting.
