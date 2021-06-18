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

### ZRTP over voice over IP

This is what Signal uses for calls


### What is ZRTP?

This is a similar encryption to end to end encryption. But the first part is different.
I think the main document can give a proper overview on this

<i> ZRTP is a key agreement protocol that performs a Diffie-Hellman key exchange during call setup in the media path and is transported over the same port as the Real-time Transport Protocol (RTP) media stream which has been established using a signaling protocol such as Session Initiation Protocol (SIP). This generates a shared secret, which is then used to generate keys and salt for a Secure RTP (SRTP) session </i>

Basically, its pretty good. But if I were to say only this, then there is no mitigation for MITM attacks. If I don't say the mitigation, I will be chastized by the encryption community. So the document also stated the way it mitigates this.

### Mitigation against MITM

[ZRTP] allows the detection of man-in-the-middle (MiTM) attacks by displaying a short authentication string (SAS) for the users to read and verbally compare over the phone. … But even if the users are too lazy to bother with short authentication strings, we still get reasonable authentication against a MiTM attack, based on a form of key continuity. It does this by caching some key material to use in the next call, to be mixed in with the next call’s DH shared secret, giving it key continuity properties analogous to Secure SHell (SSH).


So our protection is twofold: 
(1) every time we establish a connection with some remote party, we can verbally compare a “short authentication string” (SAS) to ensure that we’ve both agreed on the same key. Assuming that our attacker isn’t a voice actor, this should let us easily detect a typical MiTM. And just in case we’re too lazy to bother with this, even completing one ‘un-attacked’ connection leaves us with 
(2) a long-term shared secret that we can use to validate future connection attempts.

Now this doesn't protect rollback to an earlier version or changing identification. So Hash, SAS and Cipher information is repeated in the Commit message, so that should provide an extra layer of protection against rollback on those fields.

Overall this is too complicated and without the help of this blog
https://blog.cryptographyengineering.com/2012/11/24/lets-talk-about-zrtp/

I would be scratching my head at evrything. I just gave a simple overview. If anyone wanted more,read the blog. Many of this is paraphrasing the blog.


### WebRTC(Dischord)

This is not hidden as per say. It isn't end to end encrypted. It decrypts on the server side before it goes to the recipient. So your calls can be tracked on the server you use. So this isn't good and is not recommended for private calls

### E2E encrypted(Zoom) (In some cases)

They are using GCM with the encryption keys with the users only. Just like end to end encryption, there is a publick key and private key. Usually zoom servers have all the key and they still do. But you have te option to make your calls end to end encrypted.




## Here is my pick of free of messaging platform.

### Whatsapp (Not recommended at all)

I CANNOT STATE THIS ENOUGH. DO NOT USE WHATSAPP. IT IS OWNED BY FACEBOOK WHICH IS BASED AROUND USER DATA. But aside from that, it is end to end encrypted. Uses the same encryption as signal for its calls and messages and is overall an okay platform. The policy changes should make you rethink your decision to pick it though. This is a closed source app meaning we have to take their word for everthing they say.There is a downside being that whatsapp requires phone numbers which can be traced baxk to you. So it isn't private as per say the contents of the conversation won't be known. But it can be traced back to you using metadata.

### Signal (Reccomended alternative to Whatsapp)

Signal is he industry standard when it comes to encryption. This is almost as good as whatsapp and has more secure features like verification of contacts using qr codes. Their calls and messages are end to end encrypted and their bussiness model relies on donations. They are open source and have been audited on multiple locations. Many people reccomend this. The only downside being that this and whatsapp requires phone numbers which can be traced baxk to you. So its privacy levels are okay.
So it isn't private as per say the contents of the conversation won't be known. But it can be traced back to you using metadata.

### Telegram (Never EVER EVER EVER USE THIS)

This app is worse than whatsapp. It is only encrypted on private chats. Public rooms are all plain text. But it is filled with features like group channels and personal ones. It doesn't have much for video call encryption. But ita usability and ease of use is amazing with its lots of features. Unofficial Clients of telegram are open source but the server side is closed. Also the official client is closed source as well.


### Session

Session is one of the best mix for ease of use and privacy. It doesn't require phone number to create, not controlled by a central server. It is being transferred through the Loki network which is filled with thousands of nodes. So your messages can't be  traced even if the government tried. You get an unique identifier when you first start the app. You share that with your friends and they contact you through the network. Currently, it only supports media upto 10 mb and audio calls.


### Briar

This is the most secure and private messaging on android. This can never be traced back. This is also one of the least daily driver friendly messager on this list. It is P2P and can work without internet. It connects to the tor network when it does require internet. Two parties need to be on site together to connect each other. Plus this is arguably one of the most abttery draining apps on your phone. It keeps on running in the background. The messages are non recoverable. They can never be recovered if yolosue the phone. So you can kiss message recovery goodbye. This requires no phone number or accounts and only works on android.

### Dischord (Not reccomended for private conversation)

Dischord is an amazing app for gamers and many people alike. Their call features are amazing and their voice and vido calls are smooth. Be careful as dischord is sceptible to shutdowns on the server side. It isn't end to end encrypted. And they store the messages in plain text. But its plethora of features more than make up for its lack of security and privacy. You need an account to sign up to dischord.

### Matrix (Element)

This is a secure messaging platform. Its security by obscurity. There is no single server in matrix. You can set up your own server for you and your friends. So the metadat issue is resolved by the fact that you are the owner of your own server and your own account. But you can join other servers as well. This js a pro and a con. The pro is that if a server is down, you and your friends can join another server and chat there. End to end encryption depends on the client. Element supports end to end encryption. The good thing about matrix is there is more than a single client for accessing matrix on multiple operating systems. The con is that it is hard to set up a matrix account. You have to find the server you want snd join that server. There is a main server for matrix which is highly not reccomneded. It is slow and Janky as heck due to having too many people.
Matrix requires no phone number or account to sign up

### XMPP (Converaations)

This is similar to matrix. You can set up your own server and your own conversations with your account and your friends. Or pick a free or premium server option on this platform. XMPP is cross platform and has multiple clients. Conversation is one of the best on android. Chdck your server whether it supports end to end encrypted. So that you can use that.


## My pick of foss apps and its use cases

## 1) Signal (For people in your contacts and people you do know)

## 2) Session ( For people who wants privacy and security.)

## 3) Matrix(Element) (For large group of people who want to use messaging like dischord but also want privacy and security)

## 4) Briar (For jounalist, human rights activists and whistleblowers)

## 5) XMPP(Converaations) (For people you don't know)


Pick your favourite app and hopfully you have what you need. I am out. PEACE.
