**It stands for Content Delivery Network**

A **CDN is a network of servers placed around the world that stores (caches) copies of your website's static content and delivers it from a server close to the user.**

Instead of every user requesting files directly from your main server, a CDN keeps copies of commonly requested files such as:

- Images
- CSS
- JavaScript
- Videos
- Fonts
- HTML pages
- Other static assets

These copies are stored on **edge servers** located in different geographical locations.

```
                  USERS
                    │
          ┌─────────┼─────────┐
          ↓         ↓         ↓
       Delhi     Mumbai    London
          │         │         │
          └─────────┼─────────┘
                    ↓
                  CDN
              Edge Servers
                    │
             ┌──────┴──────┐
             │    CACHE     │
             │              │
             │ images       │
             │ CSS          │
             │ JS           │
             │ fonts        │
             └──────────────┘
                    │
             Cache Miss only
                    ↓
             ORIGIN SERVER
```

```
User
 ↓
CDN
 ↓
Is content cached?
 ├── YES → Return cached content ⚡
 │
 └── NO
      ↓
   Origin Server
      ↓
   Store in CDN
      ↓
   Return to User
```


![[Pasted image 20261006014437.png]]


# Why do we need a CDN?

Without a CDN, every request can go directly to your main server.

Imagine:

```
1000 users
     ↓
Main Server
     ↓
1000 requests
```

This can cause:

- Higher server load
- Slower response times
- More bandwidth usage
- Higher latency
- Poor performance for users far away from the server

With a CDN:

```
                 ┌── User
                 │
Users → CDN ─────┼── User
                 │
                 └── User
                    ↓
              Main Server
```

The CDN handles many requests using its cached copies.


![[Pasted image 20261006014535.png]]

# How does CDN caching work?

The important concept is **cache**.

### First request

Suppose a user requests:

```
/logo.png
```

The CDN doesn't have it yet.

```
User
 ↓
CDN
 ↓
Origin Server
 ↓
logo.png
```

The CDN gets the file from your server.

Then it **stores a copy**:

```
CDN Cache

/logo.png
```

---

### Next request

Another user requests:

```
/logo.png
```

Now the CDN already has it.

```
User
 ↓
CDN
 ↓
Cached logo.png
```

The CDN doesn't need to contact your main server.

This is called a **cache hit**.

![[Pasted image 20261006014707.png]]


# Real-world CDN examples

Popular CDN providers include:

- Cloudflare
- AWS CloudFront
- Akamai
- Fastly