## SideMenu
![](https://github.com/AndreiMisiukevich/SideMenu/blob/master/images/gif.gif?raw=true)

## Setup
* Available on NuGet: [SideMenu](http://www.nuget.org/packages/SideMenu) [![NuGet](https://img.shields.io/nuget/v/SideMenu.svg?label=NuGet)](https://www.nuget.org/packages/SideMenu)
* Add nuget package to your Xamarin.Forms .NETSTANDARD/PCL project and to your platform-specific projects
* Add (**AFTER** ```Forms.Init(...)```):
  - **SideMenuViewRenderer.Preserve()** AppDelegate in **FinishedLaunching** for **iOS** 
  - **SideMenuViewRenderer.Preserve()** MainActivity in **OnCreate** for **Android**

|Platform|Version|
| ------------------- | :-----------: |
|Xamarin.iOS|iOS 7+|
|Xamarin.Mac|All|
|Xamarin.Android|API 15+|
|Windows 10 UWP|10+|
|Tizen|4.0+|
|Gtk|All|
|WPF|.NET 4.5|
|.NET Standard|2.0+|


1) Create SideMenuView
2) Add children elements
3) Use **SideMenuView.Place** attached property for determining if an element is **MainView** (default value), **LeftMenu** or **RightMenu**.
4) Use **side:SideMenuView.MenuWidthPercentage** or **WidthRequest** for determining side menu size.
5) MainView element **must** have BackgroundColor set up (for example set **White**).
Look at Xaml for more info.

**XAML:**
```xaml
<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:side="clr-namespace:SideMenu;assembly=SideMenu"
             x:Name="Page"
             Title="SIDE MENU SAMPLE"
             x:Class="SideMenuSample.MainPage">

    <side:SideMenuView x:Name="SideMenu">
        <!--MainView with White Background Color-->
        <ContentView BackgroundColor="White">
          <!-- MainView Content -->
        </ContentView>

        <!-- Left Menu has 50% width of Main Content width-->
        <ScrollView side:SideMenuView.Place="LeftMenu"
                    side:SideMenuView.MenuWidthPercentage="0.5"
                    BackgroundColor="Orange">
            <!-- LeftMenu Content -->
        </ScrollView>

        <!-- Right Menu has 35% width of Main Content width-->
        <ContentView side:SideMenuView.Place="RightMenu"
                     side:SideMenuView.MenuWidthPercentage="0.35">
            <!-- RightMenu Content -->
        </ContentView> 

    </side:SideMenuView>

</ContentPage>
```

Sample: https://github.com/AndreiMisiukevich/SideMenu/blob/master/SideMenuSample/MainPage.xaml

## License
The MIT License (MIT) see [License file](LICENSE)

## Contribution
Feel free to create issues and PRs 😃

