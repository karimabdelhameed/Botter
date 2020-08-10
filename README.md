<img src="https://raw.githubusercontent.com/karimabdelhameed/Botter/master/.github/images/ic_botter.png" alt="Botter">

## Onboard, retain and support mobile users at scale
Engage customers with in‑app messages and support them with an integrated knowledge base and help desk.

## The Botter Messenger
The [Botter Messenger](https://botter.ai/) enables you to use it like a Messenger in your app, have conversations with your customers, send rich outbound messages, and track events.
The Botter SDK is the home for the conversations your customers have with you, and the place where they can self-serve for support or to learn more about your product.
You can open Botter from a persistent button that sits over your app’s UI, From there, your customer can  start a conversation, replies in both directions happen in real time.

## Installation
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

## Integration

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

## Customizations
if you want anytime at any screen hide the Botter chat icon, just write the below line inside <strong>onResume()</strong> method : 

```
Botter.client().setLauncherVisibility(Botter.Visibility.GONE);
```

and you can show it anytime using the below line at <strong>onResume()</strong> also :

```
Botter.client().setLauncherVisibility(Botter.Visibility.VISIBLE);
```

You can also change margins around the launcher button using : 

```
Botter.client().setLauncherMargin(left,top,right,bottom);
```

If you have your custom button , and want to show chat screen directly then you can use the below line:

```
Botter.client().openChatActivity();
```

You can customize Botter with your preferred settings, when you initialize Botter instance inside <strong>onCreate</strong> method of your Application class like below : 

```
Botter.initialize(this,
"Your API Key"
new BotterCustomization.Builder() .setLauncherGravity(BotterCustomization.LauncherGravity.LEFT) // set the launcher icon to the left/right of your screen.
.setLauncherIcon(R.drawable.) //set the launcher icon.
.setBotterLogo(R.drawable.) //set the chat logo.
.setBotterAccentColor(R.color.) //set the chat accent color.
.setBotterHeadlineText("") // set welcome screen headline text.
.setBotterHeadlineTextColor(R.color.) // set welcome screen headline text color.
.seBtotterWelcomeText("") // set welcome screen headline welcome message.
.setBotterWelcomeTextColor(R.color.) // set welcome screen headline welcome message color.
.setBotterChatHeaderTitle("") //set chat screen header title.              
.setBotterChatHeaderTitleColor(R.color.) // set chat screen header title color.
.setBotterChatBubbleColor(R.color.) // set botter bubble color.
.setBotterChatBubbleTextColor(R.color.) // set botter bubble text color.
.setSenderChatBubbleColor(R.color.) // set sender bubble color.
.setSenderChatBubbleTextColor(R.color.) // set sender bubble text color.
.setBotterRegularFontFamily(R.font.) // set chat primary font.
.setBotterSemiBoldFontFamily(R.font.) // set chat secondry font.
.setHasFAQs(true) // Determine if chat has FAQs or not.
.setAgentDefaultIcon(R.drawable.) // set the default icon for agent.
.build());
```

## Customization Parameters table:
| Name  | Description | Screenshot |
| ------------- | ------------- | ------------- |
| setLauncherGravity | To set the launcher to the right/left of the screen. | <img src="https://raw.githubusercontent.com/karimabdelhameed/Botter/master/.github/images/1.png" alt="Botter">

