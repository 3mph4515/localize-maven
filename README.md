# localize-maven
Localize.io maven repositary

Localize usage:

1. Add repository url to your build.gradle file

`
maven {
        url 'https://raw.github.com/3mph4515/localize-maven/master/'
    }
`

2. Add dependency

`
    compile 'io.localize:localize:1.1.1'
`

3. Configure your MainActivity and Application classes
```
MainActivity->onCreate
        Localize.initialize(this);
ApplicationClass->onConfigurationChanged
        Localize.onConfigurationChanged(newConfig);
```
4. Get keys from localize.io and configure manifest

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

