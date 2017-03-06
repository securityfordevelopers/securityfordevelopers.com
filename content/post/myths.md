+++
date = "2016-11-15"
draft = true
title = "Myths Developers Believe About Security"
tags = ["myths", "frameworks", "https"]
+++

To the average software developer security is still a murky topic. As often happens in a vacuum of knowledge myths develop to fill the void. Like all good myths they seems plausible until you look a little more closely, which we're going to do here.

[Add note to encourage the reader that believing in the these myths does not make one dumb, but given the subject's inportance they need to devote a little more effort to learning about app sec.]

## My Framework Handles For Me
Once while giving a talk about application security to a local developer group a hand went up in the audience. I was asked, "But doesn't Rails handle all this for me?"

I replied that Rails provides many features to improve security, yes. But there is still a lot frameworks cannot do. Rails (or Django, or React) may provides protection against certain classes of attacks, but it is not comprehensive, and may be bypassed or misused, in the hands of an unknowledgeable developer.

When adopting any framework developers need to understand what security features it provides, and how to properly use them. It's not enough to simply assume you are protected.

Continuing with Rails as an example, it provides protection against SQL Injection attacks, a type of attack where a malicious user can pass arbitrary SQL to be executed by an application, but the protected only works if used correctly.

If you write code like `Person.where("last_name = #{params[:last_name]}")` there is nothing Rails can do to protect you. The reason being that it concatenates the parameter value right into the query.

Most SQL injection protection is based on the use of parameterized queries, which is why you'd normally see that written as `Person.where("last_name = ?", params[:last_name])` (although there is more to be done to make this code safer).

## Don't Worry, We've Got HTTPS
HTTPS is not a magic shell of protection for you application. HTTPS provides valuable protection of communication between HTTP clients and applications, but your app may still have bucket loads of exploitable vulnerabilities and there is nothing HTTPS can do to help.

HTTPS should be the default on web applications, but your work does not end there. It needs to be configured correctly, and maintained as any piece of software does. Setting and forgetting it is a recipe for disaster.

## We've Got A Security Team
Most large technology shops has a dedicated security team. It's a bad idea to think that they are doing all the security stuff so you can just turn the feature crank as fast as you can. In fact, if they have not already made this clear that is a problem too. Security teams can do a lot for organizations like maintaining perimeter security, and auditing code, but they cannot catch every potential vulnerability that developers write. It is the developer's job to understand the types of 

If you do have a security good for you. They are a great resource and you should probably be talking to them more than you already do.

## We're Not A Target
It's easy so think you're not a target because your company is small, or your app is just a side project. The sad truth is that everyone is a target. Some companies are bigger targets than others, but every app's developers need to care about security,

Many attacks are automated and indiscriminate. A bot that attempts to brute force login to your site does not care how big or small you are.

## This App Is Not That Important
This is related to previous. Some people feel that only mission critical applications, or application that take money, or need to meet a regulatory requirement like HIPAA require security, but this is not ture. Every app must my secure. Different apps have different burdens to meet, sure, but exploiting a seemingly unimportant app can provide a the foothold that attackers need to gain access to more important critical systems.

## Security Hurts User Experience
Most security measures have no effect on user experience. Some things like two-factor authentication, but put up a small, but manageable hurdle for uses, especially once they get used to it. 

On the flip side things like arbitrary password requirements, as one example, both worsen security and UX simultaneously. 

## Ship Now; Secure Later
It's true that your application does not have to implement all the security on day one, but you should be addressing some of it. Security debt is like technical debt. It's ususally better to address it now


