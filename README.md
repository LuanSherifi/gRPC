# gRPC Documentation

**Autor: Luan Sherifi**
**Datum: 27.02.2024**

## Questions

- What is gRPC and why does it work accross languages and platforms?

  gRPC is a tool for connecting services in different programming  languages, making them work together because it uses common protocols  understood by all.

- Describe the RPC life cycle starting with the RPC client?

  In the RPC life cycle, the client sends a request to the server, the server processes it and sends back a response.

- Describe the workflow of Protocol Buffers?

  Protocol Buffers workflow involves defining data structures, compiling  them to generate code, and then using this code in applications to  serialize and deserialize data.

- What are the benefits of using protocol buffers?

  Benefits of protocol buffers include efficient data storage, faster  processing, and compatibility across different languages and systems.

- When is the use of protocol not recommended?

  Using protocol buffers is not recommended when simple data interchange is needed, or for human-readable data formats.

- List 3 different data types that can be used with protocol buffers?

  Three data types for protocol buffers are: `string`, `int32`, and `bool`.



## Code - Explanation

1. **HelloWorldServer**: This class establishes a gRPC server on a predefined port (50051). It uses a `ServerBuilder` to configure and start the server. The server includes a service (`HelloWorldServiceImpl`) that defines the actions to take when specific requests are received. Once started, the server remains running, awaiting termination, effectively listening for any incoming requests.
2. **HelloWorldClient**: This class represents the client side of the application. It establishes a connection to the server using a `ManagedChannel`, specifically connecting to "localhost" on port 50051. The client creates a stub, a way to call methods on the server, and uses it to send a "hello" request with a first name and last name. After receiving the response, it prints out the returned message and then shuts down the channel.
3. **HelloWorldServiceImpl**: This class extends `HelloWorldServiceGrpc.HelloWorldServiceImplBase`, implementing the service logic. When the server receives a "hello" request, this implementation is invoked. It constructs a greeting using the names provided in the request, wraps it in a response, and sends it back to the client. The method demonstrates handling of a unary gRPC call where the client sends a single request and waits for a single response.

