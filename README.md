# Which messanger should you pick and why
Many people have asked this question but have never gave a proper documentation on it. People tell you to choose this or choose that and it's not well documented. So today I am gonna try to document each messenger, why you should pick them and the threat model associated. Along with each how private they are, 

## Why is open source so wanted and why your privacy friends recommend you use open source application.

Jus as the title says, Many privacy people will tell you to pick open source apps. What is open source? It is when the code of the app is shown to the public when it is posted on server available to access via thr internet. Some website host the code of open source projects like github,GitLab,Codeberg etc. Of cource some times people make their own git server. Basically you can see the code of the project if you google search it.

## The common misconception of open source between the common people
People think that when an app is open source, it is sceptible to hackers more. This is wrong. Open source means ths app can be seen by everyone and when people find bugs, they help in fixing it by contributing to the project. So it is secure by design. And close sourcing isn't gonna make an app more secure. This is the case with windows. Even though it is closed source, it is not secure at all and is sceptible to malware. And one more misconception, Open source apps are not always secure. Think aout it, thousands of open source projects are there and many more are being made. who in their right mind has the timr to check the source code of each application. Or a large project like linux, How will you find a way to check the source code of the whole kernel. No matter how you see it, its extremely difficult. So no, open source apps are not always secure.

## What are security audits and why should I care when an open source app gets audited?
An audit is a security cehck done by third party to see whether the code is secure and not having bugs or major flaws. It helps in identifying issues in the code and also tells us normal people how secure the code is. It is like your buddy that checks the source code and tells you that you can use the app and say its secure.


## Why people say to pick open source apps over closed source apps for messaging?
It is a matter of trust. Open source apps are more trustworthy than closed source as everyone can see the code behind it. Yeah, since you can technically see the code, you don't need trust. The code will speak for itself. So they can't do anything malicious since everyone will see the code and find out. Closed source is based on trust from the developers that they won't add anything malicious. And security audits from an independent theird party to the open source code will further that trust.


## The different types of messaging

### SMS
This is connected to your phone and is the most insecure form of communication. It is connected directly to your phone number and your SMS provider can see this. It is stored as plain text on their server and is very insecure. A malicious party could easily take advantage of this and it could potentially leak all of your SMSs. DO NOT CONTACT ANYONE THIS WAY UNLESS YOU NEED TO.

### End to End encryption (What it is?)

This is a very secure and private way of communication. What this does is basically in simple terms is, Imagine your X and your girlfriend is Y. First your message gets encrypted by a public key available to the server so that it could decrypt and send to Y. But then the question arises, but how is it end to end encrypted if a server can see this? Thid is the amazing part. The end to end part comes here. Along with a public key, your message also gets encrypted by a private key which is only available between you and Y. The server doesn't know the private key and can only decrypt half and send. and that is all it is required to. Your Y's phone will decrypt the rest. So no server and no MITM (Man In The Middle) can see your messages. Not even the FBI or CIA can see those messages


### End to End Encryption (the problem)

Even though the contents of your message is secure, your not completely anonymous. First of all, whatsapp, Signal and Telegram also. You are not anonymous. There is a thing called metadata. It is essentially a trail of the occurence of the exchange. Think of it like this. Your calls are end to end encrypted. You called your mother at 3 am. Then you called a suicide association near the tower at 4am. Then you called the police at 5am. I might not know what was the contents of your messages, but  can guess that. I know you called these people at these different times and where you were at the time. So I can roughly estimate what you wanted to say and do. So I can catch you that way.


Video based on this, click [here](https://www.youtube.com/watch?v=jkV1KEJGKRA)


### End to End Encrypted (Telegram style)
ooooohhhhh, this one is an interesting case. End to End encryption. More like half assed work. This is by no means end to end encryption as the server has all your keys and can decrypt your messages anytime. It can defend against MITM attacks. But really though, it can decrypted on the server side. And thw worst of all, Not all telegram is end to end encrypted.


### End to End Encrypted (Signal Style) (Whatsapp use this and many e2e encrypted use the Signal way(aka the Signal protocol))
This is the true end to end encrypted. These guys pioneered the new wave of e2e encrypted apps. And they are truly end to end encrypted and no one except the parties involved can see the messages. True end to end encryption.

### IRC or Slack
This is an old messaging type. It isn't encrypted and MITM attack is possible. Not many people use it these days. But in the earlier days on the internet, this was used a lot. So no problem of encountering this these days.

This is similar to SMS. But there is not much identification like SMS. You can put a throwaway account on IRC.

### TLS (Dischord uses this)

TLS (Transport Layer Security) is a protocol that is meant for website encryption but is also used for chats. This has vulnerabilities and have been successfully MITM before. Also the server has all logs of your picture and videos and everything. Email,IP address, your contacts etc. This is not meant for private communication. TLS is good in a sense that it is faster than E2E. And requires less workload. But it isn't good. And dischord is very sceptible to phishing links. Even if you delete your account, your messages will still be there on the server. Please be careful when using this. Do not click on suspicious links and download suspicious files.

### End to End Encrypted (Session style)

This is similar to Signal. But it is geared towards working on the Loki Network. And due to some perks in session, is more anonymous than Signal.

## Video Encryption


## Here is a list of free of messaging platform
