---
title:  "Why am I excited about Microsoft Maui"
date:   2020-07-03 20:30:00
comments: true
categories: [Xamarin]
tags: [MAUI, XAMARIN, Mobile Development, MVU]
---

When Xamarin was introduced to the world in mid 2012, there was shere excitment among developers who used it. They knew they were using a product that will redefine mobile app development for the years to come, and it has lived upto its expectations. Years have passed and its 2021, many more exciting frameworks have come including the likes of React Native and Flutter that have made their presence felt. They have learned from one another and have been trying to outshine each other. In June 2019, I had written a [blog][myblog] in which I have expressed that its time for Microsoft to bring in a radical change to Xamarin to be more relevant in the industry. And today we are happy to see MAUI in action.

MAUI looks very promising and its again set to redefine the mobile development. Its not just another upgrade of Xamarin, its a complete rewrite of the framework from the ground up.The following things are what I believe that makes it revolutionary.

### Choice of architecture paradigms

When Xamarin introduced Forms, they decided to go with MVVM architecture. It is a great choice to write enterprise application and it also provides a great level of seperation of concerns. As community evolved around Xamarin, we soon saw that developers have created RxUI for xamarin which was a great choice for projects that use reactive programming. Other frameworks also have their choice of architecture style, for example React Native and flutter is build upon MVU principles. The team at Microsoft have done their homework and used their learnings from Xamarin to make sure that the core of MAUI is architecture agnostic - this means MAUI currently supports MVVM, MVU, RxUI, and even Blazor. It has the potential to support any new styles that can evolve in the future.

### Native UI controls vs 2D canvas UI

Xamarin and ReactNative allows us to create beautiful UI by providing wrapper around the respective native controls. This allowed developers to quickly create beuatiful apps in less time and be complaint with the platform requirements. But things have changed in the last few years, Apple definitely is much liberal about their UI guidelines now and the expectations of users have changed. People are now accepting the same UI style across both Android and iOS. Flutter has embraced this, and decided to use skia as canvas to draw controls that could be used on both the platforms.This definitely has big advantage in certain projects, where developers spend hours to customise UI on both platforms to get the desired look. But what if we could use both native and 2d canvas UI controls? Well, thats exactly what the team at microsoft is working towards. They are crafting beautiful canvas drawn control to work alongside the native controls. But unlike Flutter, Maui is not using skia cnavas but native graphics. Checkout this [repo][controlsrepo] for more information.

### Single Project experience

Its a tiring task for most Xamarin developers to manage resources such as fonts, images, splash screen etc for both the platforms. It can also be tricky and difficult for new developers to manage the communication between the forms project and the native projects. The .NET MAUI single project is an elegant solution to some of these problems. In MAUI we have a single project that uses a SDK-style project system, and the native dependencies are managed in the platform folder in the project. Though we dont have native projects in Maui, we still can access all native capabilities from MAUI project.

### Slim Renderers

Slim Renderers is poised to drastically improve the performance of rendering controls in our app. It uses a concept called Mapper to bind the properties with the native controls and trigger actions. Its very slim at its core and its supports all the architecture paradigms and unlike the current xamarin forms renderer, and its pretty easy to make modifications to the controls if needed.

[myblog]: http://libinjoseph.me/2019/a-retrospective-journey-on-xamarin/
[controlsrepo]: https://github.com/dotnet/Microsoft.Maui.Graphics.Controls
