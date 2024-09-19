# WebView Example Application

This repository contains a simple Android application that demonstrates how to use the `WebView` component to load external and local HTML pages. It also includes basic settings for controlling system UI visibility and JavaScript support.

## Features

- Loads a webpage (e.g., `https://google.com.tr`) in a `WebView`.
- Option to load local HTML content from the `assets` folder.
- JavaScript enabled for WebView.
- Mixed content allowed (HTTP and HTTPS).
- Automatically hides the status bar and navigation bar for an immersive full-screen experience.
- Supports auto-rotation based on sensor orientation.

## Installation

1. Clone this repository:
    ```bash
    git clone https://github.com/oguzhangozdogan/Fullscreen-Webview-Example.git
    ```
2. Open the project in Android Studio.
3. Build and run the application on an Android device or emulator.

## Usage

The app uses a `WebView` to display web content. By default, it loads `https://google.com.tr`, but you can change the URL or load local HTML files by modifying the following line in `MainActivity.java`:

```java
myWebView.loadUrl("https://google.com.tr");
//myWebView.loadUrl("file:///android_asset/index.html");
```

To enable full-screen mode and hide the system UI, the hideSystemUI method is called when the activity is created. This method also sets the screen orientation to sensor-based:
```java
private void hideSystemUI() {
    setRequestedOrientation(ActivityInfo.SCREEN_ORIENTATION_SENSOR);
    getWindow().addFlags(WindowManager.LayoutParams.FLAG_FULLSCREEN);

    getWindow().getDecorView().setSystemUiVisibility(
        View.SYSTEM_UI_FLAG_HIDE_NAVIGATION |
        View.SYSTEM_UI_FLAG_FULLSCREEN |
        View.SYSTEM_UI_FLAG_IMMERSIVE_STICKY
    );
}
```
