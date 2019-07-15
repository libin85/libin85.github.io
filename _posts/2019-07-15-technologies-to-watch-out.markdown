---
title:  "Four emerging technologies for C# developers"
date:   2019-06-15 10:30:00
comments: true
categories: [Xamarin]
tags: [C#, Emerging, GRPC, WebAssembly]
---

As software developers, we are very fortunate to work on solutions that impact thousands of people, if not millions. The reach of technology has expanded to the length and breadth of this world and beyond over the last decade.  Its no more a luxury for the elite community, but a necessity for everyone. This growth has made it necessary to make further improvements to our existing tools, platforms and frameworks, and also have given way to few new great solutions.

As a developer who focus primarily on C#, I would like to share with you a few frameworks/technology  that I believe will have a big impact in our work in the next 2 years.

### Artificial Intelligence

Artificial intelligence or more commonly known as AI, has already made some major breakthrough around the world,and have become an integral part of many businesses and organisations.  This intelligence is applied on a wide range of applications from games to high precision medical diagnosis.  There are many sub-sections to AI, and one that is widely used across most solutions is Machine Learning. Two of the most popular ML frameworks are TensorFlow and PyTorch and they both are written in Python. TensorFlow was developed by Google and PyTorch by Facebook.

TensorFlow has 2 open source  C# binding libraries [TensorFlow.NET][tensorflownet] and [TensorFlowSharp][tensorflowSharp]. I recommend you to have a look into both of these and decide which one you feel more comfortable. I personally feel TensorFlow.Net is more upto date. But I am really keen to know what others think too.

Microsoft also offers an easy to use cloud solution under the Azure umbrella. Its main AI offerings are Azure Machine Learning Studio and Azure Cognitive Services. You could learn more about them at [Microsoft's AI School][aischool]

### Protocol Buffer

XML and Json has dominated our industry when it comes to data transfer between systems. Latter being more prominent in the last decade or so. Both of these are human readable and there are plenty of tools available to the aid of developers. While they serve its purpose, its not really optimised for this exact use case. The engineers in Google decided to take on the challenge, and they developed Protocol Buffer aka ProtoBuff.

ProtoBuff uses binary to transfer data. It is therefore faster and the payload size is much smaller. Almost all of the major programming languages supports protobuff. It is already in mainstream in some of the other languages, especially Golang. The dotnet team is currently doing a great job to accommodate protobuff to our current workflows. You could learn more about Protobuffs from [here][protobuff].

### GRPC

REST API's have done a great job when communicating between a server and browser, but we all know its not that ideal for service to service communication. That is where we traditionally had SDK's and client libraries. They were super easy to work with.  But in the world of microservices, things are different. Each service might be written in different language using different frameworks. And writing a client library for every possible language is not fun.

And hey, GRPC to our rescue.  Using GRPC, when we define our API's  in its structure and compile the code, the client libraries and server stubs are auto-generated for us. But things does not stop there. GRPC is build upon Http 2.0 and supports a  bi-directional streaming. Its uses Protobuff as a transport medium and hence its super efficient too. By using GRPC Gateway, we can also generate Http REST endpoints and swagger documentation as an added bonus.  Dotnet team is working to include GRPC in .NetCore 3.0

### Web Assembly

JavaScript has been the only language that we could use to write  logic for the web since the beginning. But as we all know, JavaScript was never made to work for our current web applications but rather website interactions and for gluing up the web components. Since its inception, there has been many changes and additions made to keep JavaScript on the front-foot to help us create beautiful web applications and websites.

In 2015, the major web browsers came together and formed a new technology that would allow the web to execute binary.  This is web assembly. We can use almost all of the major programming languages to write scripts for the web now. The web assembly code is compiled into WASM and it also utilizes the power of the client machine which means it gets the same performance of native apps.

Dotnet team has been working on blazor, a single page application framework that uses web assembly. Blazor is currently one of the most mature SPA web application frameworks, though there is a long way for it go ahead. It has borrowed some of the best practices from Angular and React and have implemented them on top of web assembly and dotnet goodness. You can find more about blazor [here][blazor].

I hope to soon share more about these topics with you all. And I look forward to hear if there are any other tools/frameworks that you believe will have positive impact on us.

[tensorflownet]: https://github.com/SciSharp/TensorFlow.NET
[tensorflowSharp]: https://github.com/migueldeicaza/TensorFlowSharp
[aischool]: https://aischool.microsoft.com
[protobuff]: https://developers.google.com/protocol-buffers/
[blazor]: https://dotnet.microsoft.com/apps/aspnet/web-apps/client
