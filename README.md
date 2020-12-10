## Simple Android Boilerplate for Web Pages

1. Create a New Project in Android Studio

1. Add the following line to the _AndroidManifest.xml_: 


    ```xml
        <uses-permission android:name="android.permission.INTERNET" />
    ```

1. Add _android:usesCleartextTraffic="true"_ to the same file


    ```xml
        <application
            ...
            android:usesCleartextTraffic="true"
            ...

    ```

1. Add a webview to the _activity_main.xml_ file

    ```xml
        <WebView
            android:id="@+id/webView"
            android:layout_width="match_parent"
            android:layout_height="match_parent" />
    ```

1. Import the needed classes into the _MainActivity.java_ file

    ```java
        import android.webkit.WebSettings;
        import android.webkit.WebView;
        import android.webkit.WebViewClient;
    ```

2. Create  a webView in the _onCreate_ method of the _MainActivity_ class, enable the _JavaScript_ and type in your website's URL.

    ```java
        webView = (WebView)findViewById(R.id.webView);
            WebSettings webSettings = webView.getSettings();
            webSettings.setJavaScriptEnabled(true);
            webView.loadUrl("http://tatry.hu");
            webView.setWebViewClient(new WebViewClient());
    ```

3. You can also set up fullscreen mode for your app. For this import the _WindowManager_ interface

    ```java
        import android.view.WindowManager;
    ```

4. Add the following lines to the _onCreate_ method of the _MainActivity_ class too

    ```java
        requestWindowFeature(Window.FEATURE_NO_TITLE);

        getWindow().setFlags(WindowManager.LayoutParams.FLAG_FULLSCREEN, WindowManager.LayoutParams.FLAG_FULLSCREEN);
    ```

