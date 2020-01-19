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
//authorize.proto
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
```javascript
//authorize.json
{
  "authorize": {
    "client": {
      "clientId": "xYzClientId",
      "clientSecret": "xYzClientSec"
    },
    "accessToken": "tokenXYZ..."
  }
}
```
@snapend
---
@snap[north span-100]
### **gRPC** Network Transaction
@snapend
@ul[list-spaced-bullets text-11]
- Unary
- Server Streaming
- Client Streaming
- Bidirectional Streaming
@ulend
---
### How **gRPC** Works?
---
@snap[north span-100]
### How **gRPC** Works?
@snapend
@snap[midpoint span-100 fragment]
@img[shadow](assets/img/grpc_concept_diagram.png)
@snapend
---
### Generate the **Protobuf**
---
@snap[north span-100]
### Generate the **Protobuf**
@snapend
```shell
# Golang
> protoc --go_out=plugins=grpc:/out/folder authorize.proto 
```
```shell
# Node
> protoc \
  --plugin="protoc-gen-grpc=/node_modules/protoc-gen-grpc/bin/grpc_node_plugin" \
  --js_out=import_style=commonjs,binary:/out \
  --grpc_out=/out \
  authorize.proto
```
```shell
# Typescript
> protoc \
  --plugin="protoc-gen-ts=/node_modules/ts-protoc-gen/bin/protoc-gen-ts" \
  --ts_out="service=grpc-node:/out" \
  authorize.proto 
```
---
### Using the **Protobuf**
#### (Let's open up the Editor...)

---?image=assets/img/htmlcode.jpg&opacity=60&position=left&size=45% 100%

@snap[north-east span-50 text-center]
## Thank You!
@snapend

@snap[east span 50]
@ul[list-spaced-bullets text-07]
- grpc.io/docs
- developers.google.com/protocol-buffers
- google.golang.org/grpc
@ulend
@snapend

@snap[south-east span-50 text-center text-06]
[Download GitPitch Desktop @fa[external-link]](https://gitpitch.com/docs/getting-started/tutorial/)
@snapend

