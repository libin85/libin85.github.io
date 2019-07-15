---
title:  "A dive into Shell -Part 2"
date:   2019-07-04 10:30:00
comments: true
categories: [Xamarin]
tags: [Xamarin, Shell]
published: false
---

In the part 2 of this series, we will look a bit deeper into tabbed pages using Xamarin Forms Shell. To create a tabbed page in our Xamarin Forms application using Shell, we need to first create a new instance of the `AppShell` page and assign it to the `MainPage` property in the `App.xaml.cs` class.

```csharp
    public partial class App : Application
    {
        public App()
        {
            InitializeComponent();
            MainPage = new AppShell();
        }
    }
```

_Note: AppShell is just a normal Xaml file with a code behind, and can be named anything._


