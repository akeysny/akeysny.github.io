---
layout: post
title: "Find your cookies"
subtitle: "Javascript and your Browser"
background: '/img/posts/cookies/cookies.png'
---

## Warm Up

Let's warm up by taking a look at what cookies look like. Try to look and inspect them a few different ways.

#### 1. Using Burp

Go to facebook.com, and look at the request header in Burp. As you can see, multiple cookies are sent with each request. The cookies are sent as a single string, where each cookie is a key-value pair, separated by semicolons.

![IMDb page](/img/posts/cookies/Cookies-Burp.JPG)

#### 2. Using Chrome

Go to Chrome settings. In the search box in the upper right, type "cookies". Click "Content Settings" and then "All cookies and site data". Search for "Facebook" and look at the cookies there. Click on one of the cookies. Each cookie comes with some meta data.

![IMDb page](/img/posts/cookies/meta data for cookies.JPG)

#### 3. In the Chrome Developer Console

In Chrome, while on facebook.com, go to View->Developer->JavaScript Console. In the prompt, type "document.cookie". If a hacker is able to inject JavaScript onto the site, that's how they will access the cookies. Notice that not all cookies are being printed. As a developer, you can designate that a cookie is inaccessible to JavaScript, and should only be added for HTTP requests. That will prevent hackers from stealing a session cookie outright, although they can still exploit the fact that there is a logged in session in different ways.

#### 4. XSS Cookie Theft

One of the most common targets for XSS attacks are user cookies. Cookies are data stored in the user's browser by a website. They are stored on a per-domain basis, so that a website only has access to cookies it set itself.

In XSS, JavaScript is embedded in the response coming from the website, so the browser views it as trustworthy code from the current domain and gives access to the website's previously stored cookies. In JavaScript, accessing cookie data is as simple as calling{% highlight ruby %}document.cookie{% endhighlight ruby %}

#### 5. PHP Cookies

Cookies, or browser cookies, are small pieces of data which the web server asks the client's web browser to store. Each request back to the server will include these pieces of data. The data is organized as key/value pairs.

A cookie can be set using PHP's{% highlight ruby %}setcookie(){% endhighlight ruby %}function.

{% highlight ruby %}
<?php
  setcookie('language', 'english');
?>
{% endhighlight ruby %}

On future requests, the cookie key/value pairs will be assigned to the{% highlight ruby %}$_COOKIE{% endhighlight ruby %}superglobal.

{% highlight ruby %}
<?php
  echo $_COOKIE['language'];
  // english
?>
{% endhighlight ruby %}

In addition to the{% highlight ruby %}$name{% endhighlight ruby %} and {% highlight ruby %}$value{% endhighlight ruby %} arguments, {% highlight ruby %}setcookie(){% endhighlight ruby %} also accepts many other arguments for configuration.

{% highlight ruby %}
<?php
  $name = 'language';
  $value = 'english';
  $expire = time() + 60*60*24*3; // 3 days from now
  $path = '/blog';
  $domain = 'www.mysite.com';
  $secure = isset($_SERVER['HTTPS']); // or use true/false
  $httponly = true;

  setcookie($name, $value, $expire, $path, $domain, $secure, $httponly);
?>
{% endhighlight ruby %}

#### 6. Encoding

Encoding is the act of escaping user input so that the browser interprets it only as data, not as code. The most recognizable type of encoding in web development is HTML escaping, which converts characters like < and > into {% highlight ruby %}&lt;{% endhighlight ruby %} and {% highlight ruby %}&gt;{% endhighlight ruby %} respectively.

The following pseudocode is an example of how user input could be encoded using HTML escaping and then inserted into a page by a server-side script:

{% highlight ruby %}
print "<html>"
print "Latest comment: "
print encodeHtml(userInput)
print "</html>"
{% endhighlight ruby %}

#### 7. Encoding on the client-side

When encoding user input on the client-side using JavaScript, there are several built-in methods and properties that automatically encode all data in a context-aware manner:

{% highlight ruby %}          
HTML element content	node.textContent = userInput
	                element.setAttribute(attribute, userInput)
HTML attribute value    or
                        element[attribute] = userInput
URL query value	        window.encodeURIComponent(userInput)
CSS value	        element.style.property = userInput
{% endhighlight ruby %}

#### 8. Which prevention technique to use

Encoding should be your first line of defense against XSS, because its very purpose is to neutralize data so that it cannot be interpreted as code. In some cases, encoding needs to be complemented with validation, as explained earlier. This encoding and validation should be outbound, because only when the input is included in a page do you know which context to encode and validate for.

As a second line of defense, you should use inbound validation to sanitize or reject data that is clearly invalid, such as links using the javascript: protocol. While this cannot by itself provide full security, it is a useful precaution if at any point outbound encoding and validation is improperly performed due to mistakes or errors.

If these two lines of defense are used consistently, your website will be protected from XSS attacks. However, due to the complexity of creating and maintaining an entire website, achieving full protection using only secure input handling can be difficult. As a third line of defense, you should also make use of Content Security Policy (CSP), which we will describe next.