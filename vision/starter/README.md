# Local setup 
https://codelabs.developers.google.com/codelabs/mlkit-android#0

local env (dev env is as encapsulated as it gets - so gradlew determine the version, java should be 11 or higher):
java 17 (supplied by android studio) 
gradle (7.6.1 or higher)
groovey 4.0.0 (installed via brew) /usr/local/Cellar/groovy/4.0.0

- build.gradle:
	- replace deprecated repository: jcenter()  with mavenCentral()
	- buildscript.classpath 'com.android.tools.build:gradle:7.4.2' (upgrade 3.4.0 to 7.4.2)
- app/build.gradle:
	- add: namespace "com.google.codelab.mlkit" (on older versions was on AndroidManifest.xml manifest tag, package attribute)
	- upgrade android.defaultConfig.targetSdkVersion and androig.compileSdkVersion to 31 (minimal version)
	- replace com.google.android.gms:play-services-mlkit-text-recognition with com.google.mlkit:text-recognition
- app/src/main/AndroidManifest.xml:
	- android:exported="true" (new mandatory attribute, allow to open this app from any other app)
	- remove deprecated package from manifest tag
- gradle/wrapper/gradle-wrapper.properties
	- upgrade: distributionUrl=https\://services.gradle.org/distributions/gradle-7.6.1-all.zip


