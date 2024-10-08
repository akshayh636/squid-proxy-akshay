# Squid Proxy Installer

https://serverok.in/squid

Auto install Squid 3 proxy on following linux OS.

* Ubuntu 24.04, 22.04, 20.04, 18.04 
* Debian 12, 11, 10, 9, 8
* CentOS 8
* CentOS Steam 9, 8
* AlmaLinux 9, 8


## Install Squid

To install, run the script

```
wget https://raw.githubusercontent.com/akshayh636/squid-proxy-akshay/master/squid3-install.sh -O squid3-install.sh
sudo bash squid3-install.sh
```
# Create Proxy Users
Already Created a user 
```
user-akshay , password-akshay
```

To create new users, run

```
sudo squid-add-user
```

OR run following commands

```
sudo /usr/bin/htpasswd -b -c /etc/squid/passwd USERNAME_HERE PASSWORD_HERE
```

To update password for am existing user, run

```
sudo /usr/bin/htpasswd /etc/squid/passwd USERNAME_HERE
```

replace USERNAME_HERE and PASSWORD_HERE with your desired user name and password.

Reload squid proxy

```
sudo systemctl reload squid
```
# Change Squid Proxy Port

Default squid proxy port is 3128. This blog post will show how to change squid port.

You can use the sed command to replace the port number
```
sudo sed -i 's/^http_port.*$/http_port NEW_PORT_HERE/g'  /etc/squid/squid.conf
```

In the above command, replace NEW_PORT_HERE with the port number you need.

For example, to run squid proxy on port 5555, run
```
sudo sed -i 's/^http_port.*$/http_port 5555/g'  /etc/squid/squid.conf
```

Now restart Squid Proxy server
```
sudo systemctl restart squid
```

# Support

If you need professional assistance, reach out to

https://serverok.in/contact
