id:{6578B301-90E8-F7CF-FB34-7D4C0F280422}  
title:Open a Webpage in the Browser Application  
brief:This recipe shows how to launch a web page in the built-in browser application.  
samplecode:[Browse on GitHub](https://github.com/xamarin/recipes/tree/master/android/fundamentals/intent/open_a_webpage_in_the_browser_application)  
article:[Hello, Multiscreen Applications](/guides/android/getting_started/hello,_multi-screen_applications)  
sdk:[Invoking Google Applications on Android Devices](http://developer.android.com/guide/appendix/g-app-intents.html)  

<a name="Recipe" class="injected"></a>


# Recipe

 [ ![](Images/Browser.png)](Images/Browser.png)

1.  Create a new Xamarin.Android application. The project template will create a single activity named Activity1 (MainActivity.cs), which contains a button.
2.  From the `button.Click` handler in MainActivity.cs, create a `Uri` and an `Intent`.


```
intent.button.Click += delegate {
       var uri = Android.Net.Uri.Parse ("http://www.xamarin.com");
       var intent = new Intent (Intent.ActionView, uri);
       StartActivity (intent);
};
```

Calling `StartActivity` and passing it the `Intent` in the above code launches
the browser app.

 <a name="Additional_Information" class="injected"></a>


# Additional Information

Each screen in an application is represented by an activity. Using
asynchronous messages called intents, when created from a Uri, causes the system
to load an activity that can handle the Uri scheme. In this recipe a Uri
beginning with http:// loads an activity from the browser application to display
the page.