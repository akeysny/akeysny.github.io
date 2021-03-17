---
layout: post
title: "Password Security and Management"
subtitle: "Cracking your Password"
background: '/img/posts/passwords/pass crack.jpeg'
---

## Improve Password Security

We are in 2021 and password security remains elusive. Many users find it difficult to remember passwords and, because of this, use same passwords to log in to multiple sites or products. As you can imagine, this opens users and your organization up to a security breach. Instead, it is recommended using a password management tool, such as Last Pass or 1Password, with 2FA enabled and a 15-minute timeout, to eliminate the need to remember passwords and increase the likelihood of individuals using very secure, randomized passwords. 

Instead of also creating a random string of characters to protect the password management tool, users should be educated and changed over to passphrases - longer, but easily memorable phrases such as “the peach cobbler at cowboy chicken is great” that unlocks the password management tool. To enable passphrases, you may need to change your password policy and complexity to a minimum of 25-30 characters with no requirement on usage of case, numbers, or symbols.

## Demo 

#### "How do I choose the best password, so I don't end up compromized?"

How about moving on to PASSPHRASES(Pass Sentences) that are 25 characters or longer. How about a simple sentence you can remember that will do, something that is so easy to remember and yet so hard for the attacker to crack. Ooops, did I misspell a word?- think about that for a moment..

You always want to use a Multifactor Authentication, many websites enable the feature. 

#### Password Manager
You can choose a Master Password to unlock a Password Manager and Password Manager takes care of the rest. There are common password managers you can choose from.

#### How easy it is 

Let's take a look how easy it is for a threat adversary to crack your passwords.

First, we are going to generate a word list, say 14 characters long

![IMDb page](/img/posts/passwords/random list.png)

and say we want to pick a random word something that is not too short

{% highlight ruby %}killiecrankie{% endhighlight ruby %}

We want to plug in this word into a different website that will allow us to convert this word to a leet speed.

![IMDb page](/img/posts/passwords/leet.png)

If you take a look here, this new encoded value actually looks quite complex.

{% highlight ruby %}k1ll13cr4nk1316*${% endhighlight ruby %}

Now let your password cracker do the job. Run your program and plug in your leet speed credential, your software will generate [NTLM hash](https://medium.com/@petergombos/lm-ntlm-net-ntlmv2-oh-my-a9b235c58ed4).

Make sure your cracker actually starts up..

It may take under a min with the right software to crack your password hash.

#### How are you going to protect yourself against an adversary cracking your password

Stop using passwords, start using passphrases, 25 characters or more. Don't forget to use your MFA whenever you possibly can.




