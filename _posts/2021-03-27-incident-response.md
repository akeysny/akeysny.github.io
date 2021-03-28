---
layout: post
title: "Designing an Incident Response Program"
subtitle: "Incident Investigations and Digital Forensic"
background: '/img/posts/incident response/pic1.jpeg'
---

# Incident Response Programs

- Failure to conduct advance planning may lead to disaster.
This is the recipe for failure. The reality is that people make bad decisions in the heat of a crisis. Developing an Incident Response plan in advance of an incident taking place, allows you to make decisions in a calm environment of a planning phase and exercise good judgement in the heat of an incident.

- Insident Response Plan Elements

`Statement of Purpose` Is the plan restricted only to cybersecurity incidents? It should describe clear goals for the incident response effort.

`Strategies and goals for incident response` Who is responsible for incident handling?

`Approach to incident response`  What authority did they have?

`Communication with other groups` Incident Response Plan should also include communication within the teams, with other groups within the organization and the third parties

`Senior Leadership Approval` You might need that authority when you are taking unpopular actions during Incident Response.

- Incident response teams must have peronnel available 24/7

## Building an IR Team

- Management
- Information Security
- Subject matter experts
- Legal counsel
- Public affairs
- Human resources
- Physical security

Make sure that you are ready now to design and train your team so they are ready to respond in the event of an actual cybersecurity incident.

## [MITRE ATT&CK](https://mitre.org)

Cybersecurity is one of the framework's focus areas.
One of their research efforts is the develpment of 
- Adversarial
- Tactics
- Techniques
- &
- Common
- Knowledge

This att&ck framework is the collection of knowledge about attackers gathered from real-world organizations over many years.

Let's look at this table of attack techniques

![IMDb page](/img/posts/incident response/pic2.jpeg)

Each column of a table represents a tactic of an attacker, the general strategy they are trying to pursue.

## the Diamond Model assists with intrusion analysis.

- Let's look at 4 core features of a Diamond Model

`Adversary`

`Victim`

`Capability`

`Infrastructure`

## Password forensics

Password cracking plays a role in the forensic analysis toolkit. Let's take a look at how passwords are stored and how those password cracking utilities can be used to access stored passwords.

When user attempts to login into the system, the password files contain user credentials on Linux for instance, so the login process checks the password file to determine whether the password is valid. The file doesn't contain the copy of the password but a `password hash`. Hash is computed by using a one-way function. When a user logs in, the login process takes the password provided by the user, computes a hash and then compares that hash with a hash stored in the password file. If the two hashes match- the user is logged in succesfully. 

This is however still not secure, so the first step in `securing` this approach is to remove password hashes from the publicly available `etc` password file.

{% highlight ruby %}/etc/passwd: Removed Passwords{% endhighlight ruby %}

Passwords still exist, however they could be stored in a `Shadow File`

{% highlight ruby %}/etc/shadow: Shadow File{% endhighlight ruby %}

The shadow file could be `highly restricted`, so only a superuser can have access to it.

Now, let's take a look `how the hashing works`.

## Hash Function

A mathematical function that converts a variable-length input into a fixed-length output.

## Hash Function Criteria

- It must produce a completely different output for each input
- It must be computationally difficult to retrieve the input from the output
- It must be computationally difficult to find two different inputs that generate the same output.








