<img src="https://i.dlpng.com/static/png/6991256_preview.png"  width="300"><br>
# Dolly for SharedPreferences

**Dolly** is a library that combines 2 types of sharedPreferences in one place:<br>
[SharedPreferences](https://developer.android.com/reference/android/content/SharedPreferences) - Regular sharedPreferences <br>
[EncryptedSharedPreferences](https://developer.android.com/reference/androidx/security/crypto/EncryptedSharedPreferences) - AES256 encrypted key:value SharedPreferences <br>

**Dolly implements the logic for you, you just need to use it.**<br>

[![](https://jitpack.io/v/Amit7474/Dolly-SharedPreferences.svg)](https://jitpack.io/#Amit7474/Dolly-SharedPreferences)
[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-Dolly%20for%20SharedPreferences-blue.svg?style=flat)](https://android-arsenal.com/details/1/8189)

# Download
## Requirement
```
minSdkVersion 23
```
## Repository
Add this in your root `build.gradle` file (**not** your module `build.gradle` file):
```
allprojects {
	repositories {
		...
		maven { url "https://jitpack.io" }
	}
}
```
## Dependency
Add this to your module's `build.gradle` file (Note: version should match the jitpack badge above)
```
dependencies {
	implementation 'com.github.Amit7474:Dolly-SharedPreferences:1.0.0'
}
```
# Usage
Get the instance of Dolly:
```Java
Dolly dolly = Dolly.getInstance(context);
```
Start use Dolly:
```Java
dolly.getInt("age", 20, Type.ENCRYPT);
```

## API
**`putInt(key, value, type)`**

store Int values.<br/>
```Java
dolly.putInt("Age", 23, Type.ENCRYPT);
dolly.putInt("Age", 20, Type.NOT_ENCRYPT);
```
**`getInt(key, defaultValue, type)`**

get Int values.<br>
defaultValue is optional! in case that its not supplied and the key is missing will return `-1` <br/>
```Java
dolly.getInt("Age", 5, Type.ENCRYPT);
dolly.getInt("Age", Type.NOT_ENCRYPT);
```
**`putBoolean(key, value, type)`**

store boolean values.<br/>
```Java
dolly.putBoolean("isSingle", true, Type.ENCRYPT);
dolly.putBoolean("isSingle", true, Type.NOT_ENCRYPT);
```
**`getBoolean(key, defaultValue, type)`**

get Boolean values.<br>
defaultValue is optional! in case that its not supplied and the key is missing will return `false` <br/>
```Java
dolly.getBoolean("isSingle", Type.ENCRYPT);
dolly.getBoolean("isSingle", true, Type.NOT_ENCRYPT);
```
**`putFloat(key, value, type)`**

store float values.<br/>
```Java
dolly.putFloat("hight", 6, Type.ENCRYPT);
dolly.putFloat("hight", 8, Type.NOT_ENCRYPT);
```
**`getFloat(key, defaultValue, type)`**

get float values.<br>
defaultValue is optional! in case that its not supplied and the key is missing will return `-1` <br/>
```Java
dolly.getFloat("hight", 50, Type.ENCRYPT);
dolly.getFloat("hight", Type.NOT_ENCRYPT);
```
**`putLong(key, value, type)`**

store long values.<br/>
```Java
dolly.putLong("hight", 6, Type.ENCRYPT);
dolly.putLong("hight", 8, Type.NOT_ENCRYPT);
```
**`getLong(key, defaultValue, type)`**

get long values.<br>
defaultValue is optional! in case that its not supplied and the key is missing will return `-1` <br/>
```Java
dolly.getLong("hight", 50, Type.ENCRYPT);
dolly.getLong("hight", Type.NOT_ENCRYPT);
```
**`putDouble(key, value, type)`**

store double values.<br/>
```Java
dolly.putDouble("length", 6.5, Type.ENCRYPT);
dolly.putDouble("hight",10.0, Type.NOT_ENCRYPT);
```
**`getDouble(key, defaultValue, type)`**

get double values.<br>
defaultValue is optional! in case that its not supplied and the key is missing will return `-1` <br/>
```Java
dolly.getDouble("hight", 50, Type.ENCRYPT);
dolly.getDouble("hight", Type.NOT_ENCRYPT);
```
**`putString(key, value, type)`**

store string values.<br/>
```Java
dolly.putString("name", "Dani", Type.ENCRYPT);
dolly.putString("name","Dani", Type.NOT_ENCRYPT);
```
**`getString(key, defaultValue, type)`**

get string values.<br>
defaultValue is optional! in case that its not supplied and the key is missing will return `"null"` <br/>
```Java
dolly.getString("hight", "null", Type.ENCRYPT);
dolly.getString("hight", Type.NOT_ENCRYPT);
```
**`putStringSet(key, value, type)`**

store string set values.<br/>
```Java
Set<String> set = new Set();
dolly.putStringSet("set", set, Type.ENCRYPT);
dolly.putStringSet("set",set, Type.NOT_ENCRYPT);
```
**`getStringSet(key, defaultValue, type)`**

get string values.<br>
defaultValue is optional! in case that its not supplied and the key is missing will return `null` <br/>
```Java
dolly.getStringSet("set", null, Type.ENCRYPT);
dolly.getStringSet("set", Type.NOT_ENCRYPT);
```
**`putJsonObject(key, value, type)`**

store JSONObject values.<br/>
```Java
JSONObject obj = new JSONObject;
obj.put("name", "Dani");
dolly.putJsonObject("json", obj, Type.ENCRYPT);
dolly.putJsonObject("json",obj, Type.NOT_ENCRYPT);
```
**`getJsonObject(key, defaultValue, type)`**

get JSONObject values.<br>
defaultValue is optional! in case that its not supplied and the key is missing will return `null` <br/>
```Java
dolly.getJsonObject("json", null, Type.ENCRYPT);
dolly.getJsonObject("json", Type.NOT_ENCRYPT);
```
**`remove(key, type)`**

use this to remove a key:value pair from storage.<br/>
It will remove ONLY from the storage that you specify! (ENCRYPT/NPT_ENCRYPT)
```Java
dolly.remove("name", Type.ENCRYPT);
```
**`contains(key)`**

checks if a key is already stored in storage (BOTH encrypt/not encrypt) .<br>
```Java
dolly.contains("json");
```
**`removeAll()`**

Clears the entire storage (BOTH encrypt/not encrypt) .<br>
```Java
dolly.removeAll();
```
# License
```
Copyright (C) 2020, Amit kremer

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```

