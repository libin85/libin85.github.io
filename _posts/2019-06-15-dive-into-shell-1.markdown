---
title:  "A dive into Shell - Part 1"
date:   2019-06-15 10:30:00
comments: true
categories: [Xamarin]
tags: [Xamarin, Shell]
---

Xamarin has become the de-facto standard for building cross-platform mobile apps. In the last 8 years that we have been using xamarin, there has been a lot of big and small changes. And one that clearly stood-apart, and influenced most of us, was the introduction of Xamarin.Forms. Xamarin.Forms offers some great capabilities to mobile developers to re-use native UI across Android, iOS and UWP. This was something truly revolutionary. But inspite all the great features and goodness of Xamarin.Forms there was certainly some pain-points that the developer community raised in various forums. Xamarin.Forms Shell and Visual address most of these issues, and I truly believe this would be the next big change in the mobile developer world.

In this blog we will look into what shell is, and how it helps developers to better organise code and build mobile apps faster.

Shell is an opinionated way to describe the application's top-level heirarchy in a single page. It basically provides three navigational paradigms:

1. **Flyout (Hamburger menu)**
2. **Bottom Tabbar**
3. **Top Tabbar**

We can use either one of them, or a combintation of all three in the same application. The above navigational patterns can be customised using bindable properties and methods that comes out of box or we could further make changes to them using custom renderers inheriting  `ShellRenderer` class.

Though Shell's purpose is to provide a clean representation of the top level heirarchy of an app, it also comes with other great features that allow `URI-based navigation` to the inner pages while supporting `deep linking`.

Before we get into the _nuts and bolts_ of Shell, I like to make clear what top level navigation heirarchy is. To understand this, we will examine [Spotify][spotify], the popular digital music service app that gives us access to millions of songs.

![spotify screenshot image]({{ site.baseurl }}/images/spotify_image.png "spotify navigation structure")

The first layer of navigation heairarchy of spotify is a bottom tabbar that consists of four different tabs: `Home` , `Search` , `Your Library` and `Premium`. Each of these tabs have numerous links and buttons that takes us to various pages and views. But none of those are considered to be the top-level navigation and will not be included in the shell structure. If we move into the third tab `Your Library` within the app, there is a second layer of navigation hierarchy which is a top tabbar with two tabs `Music` and `Podcasts`, this is included.

_Note: Though both Music and Podcasts have a third layer of navigation hierarchy with 3 tabs each, shell currently does not support nested top tabbars at this stage._

So to put things precisely, we can tell that we only define either a flyout, bottom tabbar or top tabbar in the shell xaml. And other inner page navigation can be done using the existing navigation service or the newly introduced URI navigation. The above structure that we discussed can be defined in xaml as below.

```shell
<?xml version="1.0" encoding="UTF-8"?>
<Shell xmlns="http://xamarin.com/schemas/2014/forms"
       xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
       xmlns:d="http://xamarin.com/schemas/2014/forms/design"
       xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
       mc:Ignorable="d"
       xmlns:local="clr-namespace:LabOne.Views"
       Title="LabOne"
       x:Class="LabOne.AppShell">
    <TabBar Route="spotifyapp">
        <Tab Title="Home" Icon="tab_home.png">
            <ShellContent ContentTemplate="{DataTemplate local:HomePage}"/>
        </Tab>
        <Tab Title="Search" Icon="tab_search.png">
            <ShellContent ContentTemplate="{DataTemplate local:SearchPage}"/>
        </Tab>
        <Tab Title="Your Library" Icon="tab_library.png">
            <ShellContent Title="Music" ContentTemplate="{DataTemplate local:MusicPage}"/>
            <ShellContent Title="Podcast" ContentTemplate="{DataTemplate local:PodPage}"/>
        </Tab>
        <Tab Title="Premium" Icon="tab_premium.png">
            <ShellContent ContentTemplate="{DataTemplate local:PremiumPage}"/>
        </Tab>
    </TabBar>
</Shell>
```

For more detailed information about Shell, Please refer this [link][xamarinshelllink].

[spotify]: https://www.spotify.com/
[xamarinshelllink]: https://docs.microsoft.com/en-us/xamarin/xamarin-forms/app-fundamentals/shell/
