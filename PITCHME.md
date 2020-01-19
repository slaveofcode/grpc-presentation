# a little deep dive to **gRPC**

---?image=assets/img/curious-cat.jpg&opacity=60&position=left&size=50% 100%

@snap[north-east span-50 text-center]
#### What is gRPC actually?
@snapend

@snap[east span-45]
@ul[list-spaced-bullets text-07]
- Modern, open source remote procedure call (RPC)
- Enables **Client** and **Server** app to communicate transparently
- Transport via HTTP2 protocol (2 way communication)
- Easier to build connected system via consistent .proto
@ulend
@snapend

---?image=assets/img/thinking-kong-resized.jpg&opacity=60&position=right&size=50% 100%
@snap[north-west span-50 text-center]
#### The Benefit for using gRPC
@snapend

@snap[west span-55]
@ul[list-spaced-bullets text-07]
- Low latency
- Scallable
- Simple communication contract
- Language independent
- Self descriptive message
@ulend
@snapend


---
@snap[west span-55 text-center]
## Who using this?
@snapend

@snap[east span-45]
![IMAGE](assets/img/Gojek_logo_2019.png)
![IMAGE](assets/img/tokopedia-logo-resized.png)
![IMAGE](assets/img/xendit.png)
@snapend
---
## So...?
### **gRPC** vs **JSON**
@snap[south span-100 text-05]
... It's actually **protobuf** vs **JSON**
@snapend
---
@snap[west span-50]
```protobuf
package authorize;

message Client {
  string clientId = 1;
  string clientSecret = 2;
}

message Authorization {
  Client client = 1;
  string accessToken = 2;
}

message Grant {
  bool isAllowed = 1;
  repeated string messages = 2;
}

service AuthService {
  rpc AuthorizeBearer (Authorization) returns (Grant) {};
}
```
@snapend

@snap[east span-50]
```json
{
    authorize: {
        client: {
            clientId: "xYzClientId",
            clientSecret: "xYzClientSec"
        },
        accessToken: "tokenXYZ..."
    }
}
```
@snapend
---
### gRPC Network Transaction
@ul[list-spaced-bullets text-07]
- Unary
- Server Streaming
- Client Streaming
- Bidirectional Streaming
@ulend
---
### How gRPC Works?

---
### Generate Protobuf (Golang)
---
### Using the Protobuf (Golang)
---
### Using Protobuf (Node)
---
@title[Add A Little Imagination]

@snap[north-west span-50 text-center]
#### Engage your Audience
@snapend

@snap[west span-55]
@ul[list-spaced-bullets text-09]
- You will be amazed
- What you can achieve
- With a **little imagination**
- And GitPitch Markdown
@ulend
@snapend

@snap[east span-45]
![IMAGE](assets/img/conference.png)
@snapend

@snap[south span-100 bg-black fragment]
@img[shadow](assets/img/conference.png)
@snapend

---

@snap[north-east span-100 text-pink text-06]
Let your code do the talking!
@snapend

```sql zoom-18
CREATE TABLE "topic" (
    "id" serial NOT NULL PRIMARY KEY,
    "forum_id" integer NOT NULL,
    "subject" varchar(255) NOT NULL
);
ALTER TABLE "topic"
ADD CONSTRAINT forum_id
FOREIGN KEY ("forum_id")
REFERENCES "forum" ("id");
```

@snap[south span-100 text-gray text-08]
@[1-5](You can step-and-ZOOM into fenced-code blocks, source files, and Github GIST.)
@[6,7, zoom-13](Using GitPitch live code presenting with optional annotations.)
@[8-9, zoom-12](This means no more switching between your slide deck and IDE on stage.)
@snapend


---?image=assets/img/curious-cat.jpg&opacity=60&position=left&size=45% 100%

@snap[east span-50 text-center]
## Now It's **Your** Turn
@snapend

@snap[south-east span-50 text-center text-06]
[Download GitPitch Desktop @fa[external-link]](https://gitpitch.com/docs/getting-started/tutorial/)
@snapend

