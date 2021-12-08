Diffie-Hellman key exchange
=====

The DH key exchange solves a problem that's lurking for quite some time now: **How do you encrypt a message so it can only be read by the person you sent the message to?**

The easiest way to solve this would be to come up with a cipher i.e. a=1, b=2, etc. The main problem here is that **both parties need to agree on the cipher.** 

The benefits?

1. **Both parties don't need to know the cipher.**
2. The encrypted messages are **extremely hard to decode.**

Diffie-Hellman has 2 keys: **a public key and a private key.** Everyone can have your public key but when you want to send a message, you can encrypt it using the public key. **Only the private key can be used to decrypt it.**