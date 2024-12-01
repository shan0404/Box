1.升级agp到8.7.2
2.升级sdk 到35
3.修复
Inconsistent JVM-target compatibility detected for tasks 'compileArm64GenericDebugJavaWithJavac'  (1.8) and 'kaptGenerateStubsArm64GenericDebugKotlin'  (17).
compileOptions {
sourceCompatibility = JavaVersion.VERSION_17 // Or JavaVersion.VERSION_1_8 if you prefer
targetCompatibility = JavaVersion.VERSION_17 // Or JavaVersion.VERSION_1_8 if you prefer
}
kotlinOptions {
jvmTarget = '17' // Or '1.8' if you prefer
}

4.优化
buildFeatures {
dataBinding = true
buildConfig=true
}


5.升级media3到1.5.0
6.升级nextlib到0.8.2


7.修复

Your project includes version 8.5.35 of R8, while Android Gradle Plugin was shipped with 8.7.18. This can lead to unexpected issues.

将
classpath("com.android.tools:r8:8.5.35")
更新为
classpath("com.android.tools:r8:8.7.18")


8.修复exo p2p播放
app/src/main/java/com/google/androidx/media3/exoplayer/ext/okhttp/HttpUtil.java
app/src/main/java/com/google/androidx/media3/exoplayer/ext/okhttp/OkHttpDataSource.java