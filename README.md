# PC Book - Go

This repository contains the Golang codes for the hands-on section of [The complete gRPC course](http://bit.ly/grpccourse) by [TECH SCHOOL](https://dev.to/techschoolguru).

## The PC book application

PC book is an application to manage and search laptop configurations. It provides 4 gRPC APIs:

1. Create a new laptop: [unary gRPC](https://youtu.be/LOE_tkVFtb0)

    This is a unary RPC API that allows client to create a new laptop with some specific configurations.

    The input of the API is a laptop, and it returns the unique ID of the created laptop.

    The laptop ID is a UUID, and can be set by the client, or randomly generated by the server if it's not provided.

2. Search laptops with some filtering conditions: [server-streaming gRPC](https://youtu.be/SBPjEbZcgf8)

    This is a server-streaming RPC API that allows client to search for laptops that satisfies some filtering conditions, such as the maximum price, minimum cores, minimum CPU frequency, and minimum RAM.

    The input of the API is the filtering conditions, and it returns a stream of laptops that satisfy the conditions.

3. Upload a laptop image file in chunks: [client-streaming gRPC](https://youtu.be/i9H3BaRGLEc)

   This is a client-streaming RPC API that allows client to upload 1 laptop image file to the server. The file will be split into multiple chunks of 1 KB, and they will be sent to the server as a stream.

   The input of the API is a stream of request, which can either be:
   - Metadata of the image (only the 1st request): which contains the laptop ID, and the image type (or file extension) such as `.jpg` or `.png`.
   - Or a binary data chunk of the image.

   The total size of the image should not exceed 1 MB.

   The API will returns a response that contains the uploaded image ID (random UUID generated by the server) and the total size of the image.

4. Rate multiple laptops and get back average rating for each of them: [bidirectional-streaming gRPC](https://youtu.be/hjTI35iKMyQ)

    This is a bidirectional-streaming RPC API that allows client to rate multiple laptops, each with a score between 1 to 10, and get back the average rating score for each of them.

    The input of the API is a stream of requests, each with a laptop ID and a score.

    The API will returns a stream of responses, each contains a laptop ID, the number of times that laptop was rated, and the average rated score.

## The complete gRPC course

If you're building APIs for your microservices or mobile applications, you definitely want to try gRPC. It is super-fast, strongly-typed, and you no longer need to write a lot of boilerplate codes for services communication. Thanks to awesome HTTP/2 and Protocol Buffer!

This is a 4-in-1 course, where you will learn not only gRPC, but also protocol-buffer and backend development with Go and Java. The codes in this course are production-grade, with well-organised structure and unit tests.

### What you’ll learn:

- What gRPC is, how it works, why we should use it, and where it is suitable to.
- The amazing HTTP/2 protocol that gRPC is built on.
- Compare gRPC with REST.
- Write and serialise protocol-buffer messages using Go + Java.
- Define gRPC services with protocol-buffer and generate Go + Java codes.
- Implement 4 types of gRPC using Go + Java: unary, server-streaming, client-streaming and bidirectional streaming.
- Handle context deadline, gRPC errors and status codes
Write production-grade application with interfaces and unit tests for gRPC services.

### Are there any course requirements or prerequisites?

- You only need to have basic programming skills in Go or Java.

## TECH SCHOOL - From noob to pro

At Tech School, we believe that everyone deserves a good and free education. The purpose of Tech School is to give everyone a chance to learn IT by giving free, high-quality tutorials and coding courses on Youtube.

New videos are uploaded every week. The video topics are wide-ranging, and suitable for many different levels of tech knowledge: from noob to pro. The most important thing is: all content created by Tech School is free and will always be free. 

If you like the videos and want to support us with this vision, please share, subscribe, or [donate to us](https://donorbox.org/techschool). That would give us a lot of motivation to make more useful stuffs for the community. Thank you!
