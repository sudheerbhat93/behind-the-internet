**🌐 CDN - Content Delivery Network 🚀📦**

📄 In this document, I’ve shared my learning about Content Delivery Networks (CDNs). 🌐 You’ll find answers to the “what,” “why,” and “how” ❓💡⚙️ based on my current understanding and research.

**❓ What is CDN?🌐**
A Content Delivery Network (CDN) is a network of distributed servers 🖥️ that work together to deliver web content 📄 to users based on their geographic location 📍.  

**🌟 Why use a CDN?**
1. 🚀 Faster Content Delivery – CDNs serve content from the nearest server to the user, reducing latency and improving load times.
2. 📉 Reduced Load on Origin Server – By caching content across multiple edge servers, the main server handles less traffic.
3. 🔒 Improved Security – CDNs help mitigate DDoS attacks, provide TLS/SSL encryption, and hide the origin server. - (Im yet to learn and research more into this point)
4. 📈 Better Scalability – Easily handle spikes in traffic without impacting performance or availability.

**⚙️ How CDN Works? 🌐📡**
Let’s understand this with an example of a user hitting www.example.com in their browser 🖥️:
1. 🌐 DNS Resolution: The browser contacts the DNS Resolver to find the website’s address. The DNS for www.example.com is configured to route requests through a CDN.
2. 📍 The request is routed to the nearest CDN edge server based on the user’s location.
3. 🔍 Cache Check: The edge server checks if it already has the content cached for www.example.com.
  ✅ Cache Hit: The content is served immediately from the edge server to the browser.
  ❌ Cache Miss: The edge server fetches the content from the origin server (host server of www.example.com), stores it locally, and delivers it to the user.
4. 🔄 Subsequent Requests: Other users nearby sending requests to this edge server get the cached content directly.
This reduces load on the origin server and speeds up content delivery 🚀.

