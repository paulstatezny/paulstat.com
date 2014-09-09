---
title: "There's a Bug in Sprint's Billing System"
layout: post
excerpt: <p>My wife and I recently switched cell phone plans from Verizon to Sprint. We were saving money, and Sprint's service was better than we expected. Then, the bug happened.</p>
---

> **TL;DR**

> If Sprint gives you a credit toward your next bill, their billing system does not apply it to the "paying off your cell phone" part of the bill.

> The website shows your true balance, but after paying this balance the billing system sends emails and texts claiming the account is past due and threatening to discontinue service.

---

My wife and I recently switched from Verizon to Sprint for our cell phone service. Sprint was running a promotion where they would pay your early termination fees, so we made the move. We were saving money, and Sprint's service was better than expected; we were pleased with the decision.

And then, the bug happened. To get the full picture, you need a few details...

#### The $72 Credit

As part of the deal, we were forced to trade in our old Verizon iPhones and to buy new ones from Sprint. (No surprise here; Sprint's out to make money too.)

I'd spoken to a Sprint salesman over the phone who claimed they'd give us $150 for each of our Verizon iPhone 5's. At the store, they offered less, so I stood my ground. (False advertising anyone?) To make it right the salesman agreed to credit us the cost of the activation fees.

The activation fees were $36 per phone, which means we would get a $72 credit.

#### The First Bill

Our first Sprint bill showed up. In the "My Account" section of the website there was a nice, prominient box showing our current balance. **Bill + Credits - Payments = Total Due** &mdash;  like a 2nd grade math problem.

![Sprint bill formula]({{ site.url }}/images/sprint-bill-formula.jpg "So easy a second grader could read it!")

Sure enough, there was the $72 credit. The numbers lined up and we paid the remaining balance as shown.

The bill looked a little something like this:

| Item                                | $$$*       |
|-------------------------------------|------------|
| Phone 1 service                     | XXX        |
| Phone 2 service                     | XXX        |
| Payment toward iPhone 1             | XXX        |
| Payment toward iPhone 2             | XXX        |
| Activation fee                      | $36.00     |
| Yep, another activation fee         | $36.00     |
| Credit 1 for selling your old phone | XXX        |
| Credit 2 for selling your old phone | XXX        |
| Taxes and such                      | $1,000,000 |
| Total                               | XXX        |

#### Warning Sign #1: The Email

A couple of days after the due date of the bill, I received this email:

![Sprint email]({{ site.url }}/images/sprint-email.jpg "'A review of our records indicates a past due balance on your account.'")

> A review of our records indicates a past due balance on your account.

"Avoid service interruption"? $46.78 past due? That's...odd.

So I called in to their automated billing line, which said: "We received your payment of X, and your balance is $0.00." Okay, I guess the email was a glitch.

Remember that number: **$46.78**.

#### Warning Sign #2: The Automated Texts

Two days after the email came, my wife received this text:

> Sprint Free Msg: Your account is scheduled to be disconnected. Avoid a service interruption by calling *3 today to make a payment.

And then this morning, she started receiving this text any time she sent a group text:

> You are currently not allowed to use this service. Please contact customer care support. Msg 2126

The group texts weren't going through.

#### Phone Call #1

On my drive in to work, I called up Sprint customer service. In a case of flawless irony, I was told by a computer voice that "your balance is $0.00" just before I was transfered to a human.

The man with whom I spoke claimed that we did indeed owe the $46.78. (Hey! I was just told we have a $0 balance!) He said it was a charge for our new devices. We had paid for the service, but not the phones.

*(Weird... "Payment toward iPhone" is one of the line items on the bill. Hmm, whatever.)*

So I said, "Ok, well that bill didn't appear on your website, but that's fine. We'll pay whatever we owe. We just want this resolved."

He said the bill would appear on their website next time I looked. I got to work and opened their website.

No bill.

#### Phone Call #2

So I dialed customer service again and got a kind woman named Sue. After explaining the situation, we were both trying to make sense of it. That's when it hit me.

Take the monthly payment for our iPhones, subtract the amount we paid on the bill &mdash; you get **$46.78**! The system is refusing to apply out $72 credit toward the "payment for our iPhones" part of the bill.

Sue decided to elevate my call to George, an "Issue Resolution Specialist" (or something like that). I spoke with George for 45 straight minutes. It seemed George's mind simply couldn't compute that their system could have made a mistake. He tried to explain it away from 5 or 6 different angles, claiming I should pay the amount and it would all get settled in the next billing cycle. But the math didn't add up for any of his stories.

While talking to George, I'd pulled up my bill on the Sprint website. After going in circles with George for about 35 minutes, a box popped up in the browser:

> Have questions about your Sprint bill? Click here to chat.

Well, it's worth a shot. George doesn't seem to be getting it.

#### Alicia S.

Man am I glad that chat box popped up. Alicia S. was on the other end of the screen &mdash; one of those over-the-top customer service people that treat you like your happiness is as valuable as shares of Apple Inc. (To them, I guess it is. Wise woman.)

For your appreciation, (and as a kudos to Sprint customer service,) here are some actual quotes from Alicia S.:

> Please don't worry. You are in good hands. We care for you. After all you are responsible for Sprint's reason for existing. Everything will be alright !!

And:

> Your smile is all that matters.

While I appreciated Alicia S.'s demeanor, I had far more appreciation for her perspective on the situation. She got it; this is a glitch on Sprint's end.

Ironically, as I was chatting with her, George finally agreed to create a dispute against the supposed "past due" balance. It was only minutes later that Alicia S. made a dispute as well.

#### Dear Sprint, Please Fix Your Software

So the billing errors are being disputed. But what now? I asked both George and Alicia S. to report this bug, but corporate communication channels have more layers than an onion. Part of my hope in writing this blog is that the right person at Sprint will notice and have it patched. (And others won't have to go through the same hoops.)

Edge case bugs are hard to identify. So here's my bug report, Sprint!

Are you a Sprint customer with a similar experience? A Sprint employee with some insight? Leave a comment!
