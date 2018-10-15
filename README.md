# GoogleAdMob



<p>
Please Refer To the Links For Google AdMobs
<ul>
<li>Go to the Homepage To create a Account :https://www.google.com/admob/?gclid=EAIaIQobChMI6rnXu92I3gIVzuR3Ch1ttQ4HEAAYASAAEgJcJvD_BwE</li>
<li>Configure  Your AppManifest And Gradle : https://developers.google.com/ad-manager/mobile-ads-sdk/android/quick-start#update_your_androidmanifestxml</li>
<li>Add The Following Code Snippit On the MainThrea :


```
    MobileAds.initialize(this, "APPID GENERATED IN GOOLEADMOB COnsole");
        adView = (AdView) findViewById(R.id.adView);
        AdRequest adRequest = new AdRequest.Builder().build();
        adView.loadAd(adRequest);

        adView.setAdListener(new AdListener(){
            @Override
            public void onAdLoaded() {
                // Code to be executed when an ad finishes loading.
                Log.w("TAG","ON µADD LOADED");
            }

            @Override
            public void onAdFailedToLoad(int errorCode) {
                // Code to be executed when an ad request fails.
                Log.w("TAG","ON µADD LOADED FAILED");
            }

            @Override
            public void onAdOpened() {
                // Code to be executed when an ad opens an overlay that
                // covers the screen.
                Log.w("TAG","ON µADD LOADED ADD OPEN");
            }

            @Override
            public void onAdLeftApplication() {
                // Code to be executed when the user has left the app.
                Log.w("TAG","ON µADD LOADED ADD LEFT APPLICATION");
            }

            @Override
            public void onAdClosed() {
                // Code to be executed when when the user is about to return
                // to the app after tapping on an ad.
                Log.w("TAG","ON µADD LOADED ADD CLOSED");
            }
        });
    
  ```
</li>
<li>
Update Your Manifest .

  ```
     <meta-data
            android:name="com.google.android.gms.ads.AD_MANAGER_APP"
            android:value="true"/>
        <meta-data
            android:name="com.google.android.gms.ads.com.example.maturi.googleadmobs"
            android:value="ca-app-pub-7848862584025779/5831572805"/>
            
  ```
</li>
</ul>
</p>

# Known Isues:

<li>
If You are Using Firbase Avoid Using GoogleAdmobs Sdk Since Firebase is having it's Own SDK for Admobs.
</li>
<li>
If you forget to Initialize parametes/settings in your Manifest your application  will crash
with a message "The Google Mobile Ads SDK was initialized incorrectly."
</li>

