# Which messanger should you pick and why
Many people have posed this question, but no one has ever provided enough documentation. People will tell you to do this or that, but it isn't well documented. So now I'm going to try to document each messenger, why you should choose them, and the threat model that goes along with it. Also how private they are,

## Why is open source so popular, and why do your privacy buddies advise you to adopt open source software?.

Many privacy experts will advise you to use open source programs, as the title suggests. What is open source software? It is when the app's code is made public by posting it on a server that is accessible via the internet. Some websites, such as github, GitLab, and Codeberg etc hold the code of open source projects. Of cource some times people make their own git server. Basically, if you google the project's code, you'll find it.

## The prevalent misunderstanding about open source among the general public

People think that open source apps are more vulnerable to hackers. This is incorrect. Because the program is open source, anyone can access it, and if they notice flaws, they can help repair them by contributing to the project. As a result, it is secure by design. Close sourcing isn't going to make an app safer. This is the case when it comes to windows. Despite being closed source, it is not secure and is vulnerable to malware. Another misunderstanding is that all open source apps completely secure. Open source are not necessarily secure. Consider this: there are thousands of open source projects out there, and more are being created all the time. Who in their right mind has the time to go through each application's source code? Alternatively, a major project such as Linux, How are you going to check the entire kernel's source code? It's really challenging no matter how you look at it. No, open source software isn't always safe.

## What are security audits and why should I care when an open source app gets audited?
An audit is a security examination performed by a third party to determine whether the code is secure and free of severe vulnerabilities or errors. It aids in the detection of code flaws and also informs us, the general public, about the code's security. It's like when your friend analyzes the source code and advises you that the program is safe to use.

## Why do people advise to choose open source messaging apps over closed source messaging apps?
It's all about trust. Because everyone can see the code underlying open source apps, they are more trustworthy than closed source apps. Because you can view the code, you don't need to trust it. The code will be self-explanatory. As a result, they won't be able to do anything bad because everyone would see the code and figure it out. Closed source relies on the developers' assurance that no malicious code will be added. And Security audits of open source code by an independent third party will add to that trust.

## The different types of messaging

### SMS
This is the most vulnerable mode of communication because it is linked to your phone. It's directly linked to your phone number, and your SMS provider is aware of this. It is saved on their server as plain text, which is extremely unsafe. This might easily be exploited by a malevolent party, resulting in the leakage of all of your SMSs. DO NOT CONTACT ANYONE THIS WAY UNLESS YOU NEED TO.

### SMS Issues ( Thanks @wizzwiz4 from fosstodon for telling me this)

> [[SMS] is stored as plain text on their server.] This is his response from my above statement.

We have no way of knowing whether this is true, and it's not why SMS is insecure. SMS is always encrypted in transit, but not strongly; an attacker can downgrade the encryption to a “64-bit” key (actually 40-bit because of US government export restrictions, and the ensuing shenanigans) which is easy to brute-force.

Its right that it's best to *assume* it's stored in plain-text, though. It definitely has been in the past – and if it's stored encrypted (which I'd expect for more modern systems), they have the encryption keys.

That's not the main issue with SMS, though. The main issue is spoofing. Telecoms systems are designed with the assumption that everyone on the telecoms side of the telecoms network is fully trustworthy – but that's not the case at all. Given how many dubious organisations have authorised access to the innards of the telecoms system, a text can be sent *from* any number you like. If you receive a text, you have no real certainty that it's from who it says it's from.

Also, it's not that hard to spoof numbers and intercept other people's texts. Unlike everything he's mentioned so far, this is illegal – but it still happens (Unfortunately, SMS is used for authentication.)


### End to End encryption (What it is?)

This is an extremely private and secure method of communicating. In simple terms, imagine that you are X and your girlfriend is Y. Your message is first encrypted using a secret key that is not sent anywhere yet. Then comes the intriguing part of this end-to-end encryption. Then there's a public key that encrypts the private key before being transferred to the server through TLS. The server sends the private key to Y, who decrypts it with the public key she received from the server, and then with the secret key you both possess. The first exchange is carried out in this manner. But there are a few more factors that make this much more difficult and worthless to solve. Following this exchange, the two participants are given a shared key, which they exchange through the server each time they start a session. After a few rounds of messages, these keys will change. Even if hackers were able to gain this key, they would only have access to a subset of the communications.


### End to End Encryption (the problem)

Even though the contents of your message is secure, your not completely anonymous. First of all, whatsapp, Signal and Telegram also. You are not anonymous. There is a thing called metadata. It is essentially a trail of the occurence of the exchange. Think of it like this. Your calls are end to end encrypted. You called your mother at 3 am. Then you called a suicide association near the tower at 4am. Then you called the police at 5am. I might not know what was the contents of your messages, but  can guess that. I know you called these people at these different times and where you were at the time. So I can roughly estimate what you wanted to say and do. So I can catch you that way.


Video based on this, click [here](https://www.youtube.com/watch?v=jkV1KEJGKRA)


### End to End Encrypted (Telegram style)
This is an intriguing situation, to say the least. End to end encrypted? It's more like a half-assed job. The server possesses all of your keys and can decode your messages at any time, thus this isn't end-to-end encryption. It has the ability to defend against MITM attacks. However, it can be decrypted on the server side. Worse yet, not all telegrams are end-to-end encrypted.


### End to End Encrypted (Signal Style) (Whatsapp use this and many e2e encrypted use the Signal way(aka the Signal protocol))
This is real end-to-end encryption. These folks were the first to create e2e encrypted apps. And the messages are genuinely end-to-end encrypted, with no one other than the parties engaged having access to them. Encryption that works from beginning to end..

### IRC or Slack
This is an old messaging type. It isn't encrypted and MITM attack is possible. Not many people use it these days. But in the earlier days on the internet, this was used a lot. So no problem of encountering this these days.

This is similar to SMS. But there is not much identification like SMS. You can put a throwaway account on IRC.

### TLS (Discord uses this)

TLS (Transport Layer Security) is a protocol that is meant for website encryption but is also used for chats. This has vulnerabilities and have been successfully MITM before. Also the server has all logs of your picture and videos and everything. Email,IP address, your contacts etc. This is not meant for private communication. TLS is good in a sense that it is faster than E2E. And requires less workload. But it isn't good in terms of privacy. And dischord is very sceptible to phishing links. Even if you delete your account, your messages will still be there on the server. Please be careful when using this. Do not click on suspicious links and download suspicious files.

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


### WebRTC(Discord)

This is not hidden as per say. It isn't end to end encrypted. It decrypts on the server side before it goes to the recipient. So your calls can be tracked on the server you use. So this isn't good and is not recommended for private calls

### E2E encrypted(Zoom) (In some cases)

They are using GCM with the encryption keys with the users only. Just like end to end encryption, there is a public key and private key. Usually zoom servers have all the key and they still do. But you have te option to make your calls end to end encrypted.




## Here is my pick of free of messaging platform.

### Whatsapp (Not recommended at all)

I CANNOT STATE THIS ENOUGH. DO NOT USE WHATSAPP. IT IS OWNED BY FACEBOOK WHICH IS BASED AROUND USER DATA. Apart from that, it is fully encrypted from beginning to end. For calls and messages, it uses the same encryption as Signal, and it's a good platform overall. However, the policy revisions should cause you to reconsider your choice. We have to accept their word for whatever they claim because this is a closed source program.There is a downside being that whatsapp requires phone numbers which can be traced back to you. Whatsapp has a drawback in that it requires phone numbers that can be tracked back to you. As a result, it isn't private in the sense that the contents of the discussion will not be revealed. However, metadata can be used to track it back to you.

### Signal (Reccomended alternative to Whatsapp)

When it comes to encryption, Signal is the industry standard. This app is nearly as excellent as Whatsapp and has additional secure features such as contact verification using QR codes. Their calls and texts are encrypted from beginning to end, and their revenue model is based on donations. They're open source, and they've been audited on several occasions. This is something that a lot of people recommend. The only drawback is that this, like Whatsapp, necessitates the use of phone numbers that can be tracked back to you. As a result, the amount of privacy is acceptable.
As a result, it isn't private in the sense that the contents of the discussion will not be revealed. However, metadata can be used to track it back to you.

### Telegram (Never EVER EVER EVER USE THIS)

This app is significantly worse than WhatsApp. Only private chats are encrypted. All of the text in the public areas is plain text. It does, however, have features such as group channels and personal channels. It doesn't have much in the way of encryption for video calls. However, with so many features, its usability and convenience of use are fantastic. Telegram's unofficial clients are open source, while the server side is closed source. Also the official client is closed source as well.


### Session

Session is a great combination of ease of use and privacy. It is not controlled by a central server and does not require a phone number to create. It's being sent over the Loki network, which has tens of thousands of nodes. So even if the government tried, they wouldn't be able to track your messages. When you initially open the app, you are given a unique identifier. You tell your friends about it, and they contact you through the network. It currently only allows media files of up to 10 megabytes and audio calls.


### Briar

On Android, this is the most secure and private texting app. This can never be traced back to the source. This is also one of the least user-friendly messagers on this list for daily drivers. It is peer-to-peer (P2P) and can function without the need of the internet. When it needs to connect to the internet, it uses the Tor network. To connect with each other, two parties must be present on the same site at the same time. Furthermore, this is arguably one of your phone's most battery-draining apps. It continues to run in the background. The messages can't be recovered. If you lose your phone, you will never be able to recover them. As a result, you may say goodbye to message recovery. This app only works on Android and does not require a phone number or an account.

### Dischord (Not reccomended for private conversation)

Dischord is a fantastic app for both gamers and non-gamers alike. Their call features are fantastic, and voice and video calls are seamless. Dischord is vulnerable to server-side shutdowns, so be cautious. It isn't encrypted from beginning to conclusion. They also save the messages as plain text. However, the abundance of features more than compensate for the lack of security and privacy. You need an account to sign up to dischord.

### Matrix (Element)

This is a secure messaging platform. Its security by obscurity. There is no single server in matrix. You can set up your own server for you and your friends. So the metadata issue is resolved by the fact that you are the owner of your own server and your own account. But you can join other servers as well. This is a pro and a con. The pro is that if a server is down, you and your friends can join another server and chat there. End to end encryption depends on the client. Element supports end to end encryption. The good thing about matrix is there is more than a single client for accessing matrix on multiple operating systems. The con is that it is hard to set up a matrix account. You have to find the server you want snd join that server. There is a main server for matrix which is highly not reccomneded. Due of the large number of people, it is extremely slow and jerky.
Matrix requires no phone number or account to sign up.

### XMPP (Converaations)

This is similar to matrix. You can create your own server and have private talks with your friends and account. Alternatively, on this platform, you can choose between a free and a paid server. XMPP is a cross-platform protocol with a large number of clients. On Android, one of the best apps is Conversation. Check to see if your server supports end-to-end encryption. So that you can put it to good use.


## My pick of foss apps and its use cases

## 1) Signal (For people in your contacts and people you do know)

## 2) Session ( For people who wants privacy and security.)

## 3) Matrix(Element) (For large group of people who want to use messaging like dischord but also want privacy and security)

## 4) Briar (For jounalist, human rights activists and whistleblowers)

## 5) XMPP(Converaations) (For people you don't know)


Pick your favourite app and hopfully you have what you need. I am out. PEACE.


## Contributions

1) Me, aka, Wisem. Did all of the work.
2) Wizzwizz4 at fosstodon, he helped in the sms problem and fixed some mistakes I made in end to end encryption.
