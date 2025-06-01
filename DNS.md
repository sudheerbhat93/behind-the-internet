**🌐 DNS - Domain Name System 🧠📡**

📄 In this document, I’ve shared my learning about the Domain Name System (DNS). 🌐 You’ll find answers to the “what,” “why,” and “how” ❓🔍⚙️ based on my current understanding and research.

**❓ What is DNS? 🌐💻📞**
- DNS stands for Domain Name System. It's like the 🌍 internet’s phonebook, translating human-friendly domain names 🧑‍💻 into machine-friendly IP addresses.

**🌟 Why use DNS? 🧭🌐**

🌐 Without DNS, we would have to remember the IP address of every website, which is a very hard task. 🧠💥
✅ With DNS, we can use easily memorable domain names to access websites. ✍️🔗
😊 DNS makes the internet user-friendly, simple to navigate, and much more accessible! 🚀📱💻

**🔍 How DNS Works 🌐💡
- To understand how DNS works, we need to know about the DNS servers that help us find the IP address of any website we visit. 🧭💻

**❓ What are DNS Servers? 🖥️🌍**

- DNS servers are servers that work together to find the correct IP address of the website we’re trying to open. 🌐➡️📦

There are 4 main DNS servers involved in this process:

- 1️⃣ DNS Resolver 🧠🔄
Also called a recursive resolver, it’s the first server your device contacts.
It acts like a helper or middleman, doing the job of asking other servers to find the IP address for us. 📨🛠️

- 2️⃣ Root Name Server 🌍📛
This server knows where to find Top Level Domain (TLD) servers like .com, .org, .in, etc.
It is like a directory that points us to the next level. 🗂️➡️

- 3️⃣ TLD Server 🏷️🔎
This server handles domain extensions like .com, .net, .in, etc.
It tells the resolver which authoritative server to contact for the exact domain name. 🧭📬

- 4️⃣ Authoritative Name Server ✅📬
This is the final source of truth.
It contains the actual IP address of the domain.
It gives the final answer so our browser can load the website. 🧾➡️🖥️

🧠 In simple terms:
Each DNS server plays a role like steps in a treasure hunt — guiding our request until it finds the exact location (IP) of the website we want to visit. 🗺️🎯💻

**🚀 Let’s see how DNS works step-by-step when a user loads www.example.com in the browser:**

- 1️⃣ The browser checks its own cache 🧠💾
When www.example.com is entered, the browser first looks in its cache to see if it already knows the IP address.

- 2️⃣ If not found, it asks the OS 🖥️📡
If the browser doesn’t know, it asks the Operating System (OS). The OS is configured to contact a DNS Resolver (usually provided by your ISP or custom DNS like Google or Cloudflare).

- 3️⃣ DNS Resolver checks its cache 🧠🔁
The DNS Resolver checks its own cache. If the IP isn’t cached, it moves to the next step.

- 4️⃣ DNS Resolver contacts the Root Name Server 🌍📍
The Resolver sends a request to a Root Name Server, asking where to find the TLD (Top Level Domain) server for .com.

- 5️⃣ Root Server replies with TLD Server info 📛📬
The Root Server looks at the extension .com and responds with the IP address of the appropriate TLD Name Server (for .com domains).

- 6️⃣ Resolver contacts the TLD Server 🏷️📡
The Resolver then asks the TLD Server for the Authoritative Name Server of example.com.

- 7️⃣ TLD Server replies with Authoritative Name Server info ✅📤
The TLD Server responds with the IP address of the Authoritative Name Server responsible for example.com.

- 8️⃣ Resolver contacts the Authoritative Name Server 📬🔎
The Resolver now asks this Authoritative Server for the actual IP address of www.example.com.

- 9️⃣ Authoritative Server responds with the IP address 💡📩
It gives the Resolver the final answer — the IP address of the domain.

- 🔟 Resolver contacts the Web Server 🖥️🌐
With the IP address, the Resolver reaches out to the actual host server where the website is stored. The website’s content is returned.

- 1️⃣1️⃣ Resolver caches the result and forwards to OS 🧠➡️🖥️
To speed up future requests, the Resolver caches the result and sends the data to the OS.

- 1️⃣2️⃣ OS sends data to the browser 🌐📤
The OS delivers the website data to the browser.

**This is my understanding and learning about Domain Name System**

- 1️⃣3️⃣ Browser caches and loads the website 🧠🧭
The browser saves (caches) the result and finally loads the content on your screen! 🎉💻


