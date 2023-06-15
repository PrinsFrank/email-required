---
layout: home
---

<h1>{{- site.description | escape -}}</h1>

_Imagine;_

You are working at a help desk or in a physical store signing people up for a service.

You just made a sale, and now you're inputting the personal data of your new customer.
Their first and last name are easy. But wait, they don't have an email address?
The field in the registration form is required, and has to contain a valid email.
What if we put a random adress here? <a href="mailt:user@hasnomail.com">user@hasnomail.com</a>? or <a href="mailt:user@example.com">user@example.com</a>?

The user is signed up (and hopefully happy about their new purchase).
But in the background the **confirmation of this signup was sent** to a **random person** that is trying to intercept your data. Why? And how?

An assumption was made by the creator of the registration form: that all prospective clients have access to email. 
In 2021, only 89% of people in the Netherlands had access to email <sup><a href="https://longreads.cbs.nl/ict-kennis-en-economie-2022/ict-gebruik-bij-personen/" target="_blank">1</a></sup>. 

Another assumption by the internal system: That the email address connected to a client is accessible by that client and no-one else.

So a confirmation email is sent:

> Hello John Doe
> 
> 
> Welcome at FooBar! Great to have you as a customer!
> 
> 
> Just to confirm, we have this information about you:
> 
> 
> Name: John Doe<br>
> Phone number: +31 12 34 56 78<br>
> Bank account number: 123 456 789<br>
> 
> With Kind regards,

**Which is read by the attacker waiting for all these emails**

After I heard about a colleague receiving a bunch of emails that were not intended for him and realising the above scenario, I registered a bunch of domain names:

- <a href="https://hasnomail.com" target="_blank">hasnomail.com</a>
- <a href="https://heeftgeenmail.com" target="_blank">heeftgeenmail.com</a> (Dutch translation of hasNoMail)
- <a href="https://heeftgeenmail.nl" target="_blank">heeftgeenmail.nl</a> (Dutch translation of hasNoMail
- ... And a bunch more which I stopped paying for since the low volume of emails

**Together, these domain names received more than 2000 emails per minute** when I started this project, all of them not intended for me and a bunch of them containing personal information.

Now, three years later, after notifying hundreds of companies that number has decreased a lot. And as **a lot of similar domains are not guarded by me so might be actually used to harvest personal data**.


## What should I do?

First and foremost, check if you are affected. If you were sent to this website by me you probably are. Then:

- Don't require an email to register for an offline service.
- Update all incorrect email address in your database. Remove them if possible, otherwise contact your customers for an email address they have access to.
- Instruct personnel to not fill in an email address when a customer doesn't have one. If this is not directly possible because changes in your software are needed, instruct them to use <a href="mailto:foo@example.com">foo@example.com</a> instead as that is a reserved domain name<sup><a href="https://www.iana.org/domains/reserved" target="_blank">2</a></sup>. 
- Don't send personal information in emails. If you really have to, only send these emails after you are sure the user has access to it. (Let them verify it's really them reading the emails)

