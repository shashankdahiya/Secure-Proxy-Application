# Secure-Proxy-Application
### At a high level the system interacts in a simple manner.
![](https://github.com/shashankdahiya/Secure-Proxy-Application/blob/master/src/Client:server%20setup.png)
At every interaction between entities, there is a TLS handshake in order to ensure that the connection is secured with TLS. Information is then sent over a secure TLS connection. The client will only interact with the proxy, we can see this as a security feature as to not allow direct interaction with the server from a random client.

The proxy will only ping the server for information if the file is not blacklisted and not found in the cache, otherwise the proxy will immediately send the file content back to the client if it is found within the cache or a message saying that the file is blacklisted if the file is found within the bloom filter. Files contents returned from the server are stored within a cache inside the proxies for quick retrieval the next time the file is requested.
