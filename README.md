# HTTP vs HTTPS
![](https://i.imgur.com/7PUIw03.png)

 ### How does HTTPS work? 
   #### What is HTTPS?
Hypertext transfer protocol secure (HTTPS) is the secure version of HTTP, which is the primary protocol used to send data between a web browser and a website. HTTPS is encrypted in order to increase security of data transfer. This is particularly important when users transmit sensitive data, such as by logging into a bank account, email service, or health insurance provider.

 #### How does HTTPS work?
HTTPS uses an encryption protocol to encrypt communications. The protocol is called Transport Layer Security (TLS), although formerly it was known as Secure Sockets Layer (SSL). This protocol secures communications by using what’s known as an asymmetric public key infrastructure. This type of security system uses two different keys to encrypt communications between two parties:

1- **The private key** : this key is controlled by the owner of a website and it’s kept, as the reader may have speculated, private. This key lives on a web server and is used to decrypt information encrypted by the public key.

2- **The public key** : this key is available to everyone who wants to interact with the server in a way that’s secure. Information that’s encrypted by the public key can only be decrypted by the private key.



### What are TLS/SSL certificates?

#### What is SSL :

**SSL** stands for Secure Sockets Layer and, in short, it's the standard technology for keeping an internet connection secure and safeguarding any sensitive data that is being sent between two systems, preventing criminals from reading and modifying any information transferred, including potential personal details. The two systems can be a server and a client (for example, a shopping website and browser) or server to server (for example, an application with personal identifiable information or with payroll information).

It does this by making sure that any data transferred between users and sites, or between two systems remain impossible to read. It uses encryption algorithms to scramble data in transit, preventing hackers from reading it as it is sent over the connection. This information could be anything sensitive or personal which can include credit card numbers and other financial information, names and addresses.

#### What is TLS :
TLS (Transport Layer Security) is just an updated, more secure, version of SSL. We still refer to our security certificates as SSL because it is a more commonly used term, but when you are buying SSL from DigiCert you are actually buying the most up to date TLS certificates with the option of ECC, RSA or DSA encryption.

#### How can i see if a page have a certificate :
HTTPS (Hyper Text Transfer Protocol Secure) appears in the URL when a website is secured by an SSL certificate. The details of the certificate, including the issuing authority and the corporate name of the website owner, can be viewed by clicking on the lock symbol on the browser bar.

#### Type of Validation Certificate :

* **Domain** .
* **Organization** .
* **Extended** .




### Why is this important to implement in your projects?

#### The benefits of HTTPS
![](https://i.imgur.com/fFQoO8C.png)

#### Security
One of the main benefits of HTTPS is that it adds security and trust. It protects users against man-in-the-middle (MitM) attacks that can be launched from compromised or insecure networks. Hackers can use such techniques to steal your customer’s sensitive information.

Implementing SSL secures any data transmitted between server and browser during a users session interacting with your site. This is a key component in the realms of data protection and especially the new GDPR legislation surrounding protecting personal data.

#### Confidence
The green padlock which appears on a secured site can give customers peace of mind that your website can be trusted and their information is safe, this can lead to increased conversion and loyalty. 

#### The SEO / search value
If your domain has the letters https in front of the www, then your site will have a clear advantage over those that are stuck with the old http. This fact comes directly from Google. Back in 2015, *Gary Illyes* revealed that if two web pages are equal in other respects, the Google search engine will always prefer those that are Hypertext Transfer Protocol Secure (HTTPS). Evidence from Mozcast bears that out. Between January and October last year, the number of sites that appeared in the top slot of Google searches that were https compliant rose from 25% to 40%.

The reason why the Google algorithm increasingly prefers https is that the company wants to prioritise secure websites. In fact, Google has been open about its desire to ensure that one day the whole web is secure, including sites that are not handling sensitive information. The Google Chrome update 56 that came out in January 2017 is another step towards this goal. Since this update was rolled out, Chrome users have started to receive security warnings every time they access a site served by http and not https. Over the next few months, Google’s preference for https is likely to severely disadvantage http sites.



 ### Demo how to generate certificates and use them in a node project.
    You need two things more important : 
    * SSL certificate.
    * `https` Node.js module
    Then Follwoing this steps :
   ##### Step 1: download SSL Certificate Files.
   ##### Step 2 :upload SSL files to Server directory.
   ##### Step 3 :

 ```javaScript
 const https = require('https');
const fs = require('fs');

const options = {
  key: fs.readFileSync('key.pem'),
  cert: fs.readFileSync('cert.pem')
};

https.createServer(options, function (req, res) {
  res.writeHead(200);
  res.end("hello world\n");
}).listen(8000);
```
 ##### step 4: run your file