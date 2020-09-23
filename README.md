<div align="center">

## Cookies in PHP explained\. Easy to use function


</div>

### Description

Cookies in PHP can sometimes be a huge pain in the butt. This function is simple, and teaches you how cookies work, how to write them, expire them, and check their values.

Use this cookie for whatever you want, but feedback is always appreciated :o)
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Piotr Sienkiewicz](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/piotr-sienkiewicz.md)
**Level**          |Beginner
**User Rating**    |4.0 (52 globes from 13 users)
**Compatibility**  |PHP 3\.0, PHP 4\.0
**Category**       |[Security](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/security__8-14.md)
**World**          |[PHP](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/php.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/piotr-sienkiewicz-cookies-in-php-explained-easy-to-use-function__8-357/archive/master.zip)





### Source Code

```
<font face="Tahoma" size="-1"><?php<br>
<br>
<b>setcookie() </b>is the main function that is used to work with cookiesin PHP<br>
<br>
parameters are as follows:<br>
<br>
setcookie (string name , string value , int expire , string path , string domain
, int secure)<br>
<br>
<br>
Cookies are sent to the user's computer thru the header: in static files, because
this is the case you must set, expire your cookies before displaying anything
thru your script.. before any echo() and/or print() functions. This is not a PHP
setback, it the way HTML works :o) Check out this simple function i have written.
. . </font>
<p><font face="Tahoma" size="-1">function cookie($function, $value) {</font></p>
<p><font face="Tahoma" size="-1"> if ($function == "set") {<br>
 <br>
    setcookie ("CookieValue", "$value",
 time() + 14400);<font color="#009933">// Cookie is Valid for 4 hours. 3 value
 in function is the time expiration in seconds. </font><font color="#009933">...
 3600 seconds = 1 hour</font><br>
 <br>
    return true;<font color="#009933">// cookie
 set, return true</font></font></p>
<p><font face="Tahoma" size="-1"> } else if ($function = "logout") {</font></p>
<p><font face="Tahoma" size="-1">    setcookie
 ("CookieValue", "$value", time() - 14400);<font color="#009933">// Cookie is now expired as we set the expiration value to 4 hours ago</font><br>
    return true;<font color="#009933"> // logout
 complete<br>
 </font><br>
 } else if ($function = "check") {</font></p>
<p><font face="Tahoma" size="-1">    if (isset($CookieValue))
 {<br>
     if ($CookieValue == $value)
 {<br>
        print("ALL
 GOOD.. cookie verified");<br>
        return
 true;<br>
     } else {<br>
       print("Value
 does not much cookie");<br>
       return
 false; <font color="#009933">// Failed, so return false</font><br>
     }<br>
    }</font></p>
<p><font face="Tahoma" size="-1"> } else {</font></p>
<p><font face="Tahoma" size="-1">    return false;<font color="#009933">// Failed, since no operations match</font></font></p>
<p><font face="Tahoma" size="-1"> }</font></p>
<p><font face="Tahoma" size="-1">}</font></p>
<p><font face="Tahoma" size="-1">?></font></p>
```

