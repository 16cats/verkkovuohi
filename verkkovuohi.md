# Verkkovuohi

OWASP WebGoat installation for a Debian based virtual machine. Throughout this markdown, I will be using references of [this particular document by Tero Karvinen](https://terokarvinen.com/2023/webgoat-2023-4-ethical-web-hacking/) from 2023 that I found by scavenging the internet.


## The installation process
We're going to install Java to run Java files first.
```
$ sudo apt-get update
$ sudo apt-get install openjdk-17-jre
```

Then a firewall for protection. We're also going to enable it.
```
$ sudo apt-get install ufw
$ sudo ufw enable
```

![image](https://github.com/16cats/verkkovuohi/assets/97065659/4f2951ac-6a8c-43f6-90af-11079f34c5a2)

According to the WebGoat GitHub, the newest version is `2023.8`, so I'll just edit the guide a bit to match the newest version. 

```
$ wget https://github.com/WebGoat/WebGoat/releases/download/v2023.8/webgoat-2023.8.jar
```

![image](https://github.com/16cats/verkkovuohi/assets/97065659/250cd76a-adff-4853-8a1a-a16f6413540b)

Alright, and the last step of installation.

```
$ java -Dfile.encoding=UTF-8 -Dwebgoat.port=8888 -Dwebwolf.port=9090 -jar webgoat-2023.8.jar
```
Where
- `-Dfile.encoding=UTF-8` is setting the file encoding to UTF-8.
- `-Dwebgoat.port=8888` is setting what port WebGoat will be listening to.
- `-Dwebwolf.port=9090`* is to tell WebWolf to communicate with WebGoat on 9090.
- `-jar webgoat-2023.8.jar` is to run WebGoat.

*_"[WebWolf](https://owasp.org/www-project-webgoat/) is a separate web application which simulates an attackers machine. It makes it possible for us to make a clear distinction between what takes place on the attacked website and the actions you need to do as an “attacker”"._

It's telling us to browse to http://127.0.0.1:8080/WebGoat, so let's do that.

![image](https://github.com/16cats/verkkovuohi/assets/97065659/141c0445-0dca-4c1f-96bf-dddf99ab75fd)

![image](https://github.com/16cats/verkkovuohi/assets/97065659/abe8f3ad-9dd0-4f6b-80d6-bf8515eb635a)

Et voilà.

Although, as we can see, it's telling us to just go to port 8080 instead of 8888. I have my assumptions as to why, but if I ever find out why actually, I'll come edit this markdown.


### Sources
* [Webgoat installation](https://terokarvinen.com/2023/webgoat-2023-4-ethical-web-hacking/)
* [WebGoat Github](https://github.com/WebGoat/WebGoat/releases)
* [Owasp Official Page](https://owasp.org/www-project-webgoat/)
