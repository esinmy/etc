## JS and TS code generation from proto files

### JS
To generate JS files for grpc-web client:

```
# examples
protoc --proto_path=$DIR echo.proto \
    --js_out=import_style=commonjs:$OUT_DIR \
    --grpc-web_out=import_style=commonjs,mode=grpcwebtext:$OUT_DIR

protoc --proto_path="../protos/hub-api-remote" "hub/api-remote/"tasks.proto \ 
       --js_out=import_style=commonjs:"../src/protos" \
       --grpc-web_out=import_style=commonjs,mode=grpcwebtext:"../src/protos"
```

### TS
To generate TS files (JS + TS types) for grpc-web client:

```
# examples
# binary format for payload
protoc --proto_path=$DIR echo.proto \
  --js_out=import_style=commonjs,binary:$OUT_DIR \
  --grpc-web_out=import_style=typescript,mode=grpcweb:$OUT_DIR

# base64 format for payload
protoc --proto_path="./protos" "./protos/licenses.proto" --js_out=import_style=commonjs:"./" --grpc-web_out=import_style=typescript,mode=grpcwebtext:"./"
```

### Legend
```
--proto_path=PATH           Specify the directory in which to search for
                            imports.  May be specified multiple times;
                            directories will be searched in order.  If not
                            given, the current working directory is used.
                            If not found in any of the these directories,
                            the --descriptor_set_in descriptors will be
                            checked for required proto file.

--js_out=OUT_DIR            Generate JavaScript source (e.g. echo_pb.js)

--grpc-web_out=OUT_DIR      Generate TypeScript gRPC-web code (e.g.  
                            EchoServiceClientPb.ts) and 
                            TypeScript definitions for JavaScript source 
                            (e.g. echo_pb.d.ts)

import_style=typescript     The service stub will be generated in TypeScript. 
                            See TypeScript Support below for information on 
                            how to generate TypeScript files.

import_style=commonjs       The CommonJS style require() is also supported.      

mode=grpcwebtext            The default generated code sends the payload in the grpc-web-text format.

mode=grpcweb                A binary protobuf format is also supported.
```

## Reference:
- [Official documentation](https://github.com/grpc/grpc-web)
- [Implementation of gRPC in web and server with TypeScript](https://medium.com/front-end-weekly/implementation-of-grpc-in-web-and-server-with-typescript-165e8ca0155b)
