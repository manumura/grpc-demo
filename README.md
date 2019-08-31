# grpc-demo Java

# PROTOCOL BUFFERS

## Message with fields (type + name + tag)

## Tags :

Used to identify your fields in the message binary format.
Should not be changed once your message type is in use.
Very useful when message needs to evolve (add / remove fields).

## Default values :

All fields, if not specified, will take defauult value:
	bool: false
	number: 0
	string: empty string
	bytes: empty bytes
	enum: first value
	repeated: empty list
	
## Data evolution :

Forward compatible change : write data with new .proto, read from old .proto
Backward compatible change : write data with old .proto, read from new .proto
Rules to follow :
	- Dont change numeric tags for exisiting fields.
	- If adding new field, old code will just ignore it. For new code (reading old data with not found field), default will take place.
	- If data type changes, just create a new field (or go to the doc for complete compatibility reference).
	- If removing a field, for old code (reading new data with not found field), default will take place. New code reading old data will just ignore the removed field.
	When removing a field, we need to RESERVE the tag and name ("reserved" keyword), so that we dont reuse them anymore.
	- Renaming a field is not a problem (only tag matters).

## Why Protocol Buffers ?

Language agnostic
Code can be generated using many languages
Data is binary and efficiently serialized (small payload + sending lots of data)
Easy API evolution
	
# GRPC

vs REST/HTTP/JSON

# COMPARISON GRPC HTTP-REST
https://docs.microsoft.com/en-us/aspnet/core/grpc/comparison?view=aspnetcore-3.0

Performance : https://husobee.github.io/golang/rest/grpc/2016/05/28/golang-rest-v-grpc.html

HTTP2 vs HTTP1.1 : https://imagekit.io/demo/http2-vs-http1

# INSTALL PROTOC

## Mac
brew install protobuf

## Windows

- Download from https://github.com/google/protobuf/releases:
example:
https://github.com/protocolbuffers/protobuf/releases/download/v3.9.0/protoc-3.9.0-win64.zip
- Extract
- Add to path

## HOW-TO
protoc <FILE>.proto --java_out=<GEN_PATH>
