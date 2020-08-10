<img src="https://raw.githubusercontent.com/karimabdelhameed/Botter/master/.github/images/ic_botter.png" alt="Botter">

## Onboard, retain and support mobile users at scale
Engage customers with in‑app messages and support them with an integrated knowledge base and help desk.

### The Botter Messenger
The [Botter Messenger](https://botter.ai/) enables you to use it like a Messenger in your app, have conversations with your customers, send rich outbound messages, and track events.
The Botter SDK is the home for the conversations your customers have with you, and the place where they can self-serve for support or to learn more about your product.
You can open Botter from a persistent button that sits over your app’s UI, From there, your customer can  start a conversation, replies in both directions happen in real time.

### Installation
Install Botter to see and talk to users of your Android app, Botter for Android supports API 23 and above.

<li>Add the below lines under <strong>all projects -> repositories</strong> in build.gradle <strong>(project level)</strong>.</li>

```
maven {
  url "from our support team"
     credentials {
       username = "*ask for your username*" //from our support team
       password = "*ask for your password*" //from our support team
    }
}
```
<li> Make sure that you suppoty java 8 by adding the below lines under <strong>android { </strong> in build.gradle <strong>(App level)</strong>
  
```
 compileOptions {
        sourceCompatibility JavaVersion.VERSION_1_8
        targetCompatibility JavaVersion.VERSION_1_8
    } 
```
<li> add Botter dependency under <strong>dependencies { </strong> section  
 
```
implementation "com.bluecrunch:botter:1.2.1"
```

### Integration

<p>First, you'll need to get your Botter Android API key. To find this, just contact our support team to get you one.
  Then, initialize Botter by calling the following in the <strong>onCreate()</strong> method of your application class</p>
  
```
Botter.initialize(this,"Your API Key",
new BotterCustomization.Builder().build());
```

<strong>Note:</strong> If you don't currently implement a custom application, you’ll need to create one. A custom application looks like this:

```
public class CustomApplication extends Application {
    @Override public void onCreate() {
        super.onCreate();
        Botter.initialize(this,"Your API Key",
new BotterCustomization.Builder().build());
   }
}
```

You’ll need to update your manifest to use your application:

```
<application
    android:name=".CustomApplication">
</application>
```

### Customizations
