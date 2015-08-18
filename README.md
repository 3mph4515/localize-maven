# localize-maven
Localize.io maven repositary

Localize usage:

* Add repository url to your build.gradle file

```
maven {
        url 'https://raw.github.com/3mph4515/localize-maven/master/'
    }
```

* Add dependency

```
configurations {
    compile.exclude module: 'stax'
    compile.exclude module: 'stax-api'
    compile.exclude module: 'xpp3'
}
....

    compile 'io.localize:localize:1.1.1'
```

* Configure your MainActivity and Application classes
```
MainActivity->onCreate

        Localize.initialize(this);
        
ApplicationClass->onConfigurationChanged

        Localize.onConfigurationChanged(newConfig);
```
* Get keys from localize.io and configure manifest

```
        <meta-data
            android:name="localize_production_key"
            android:value="prod_xxx..xxx"/>
```

```
        <meta-data
            android:name="localize_development_key"
            android:value="dev_xxx..xxx"/>
```
* Localize your views with 

```
tvTextView.setText(Localize.getLocalizedString("key"));
```

* Android Studio SDK Plugin 

https://bitbucket.org/jerminal/localize-android-studio-plugin/src/c3c074cdc7d8?at=master

* Making screenshots and debug strings refreshing

Add this to turn on snapshot widget
```
Localize.addSnapshotWidget(this);
```
