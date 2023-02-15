# Hi there <a href="https://saileshdahal.com.np"><img src="https://media.giphy.com/media/hvRJCLFzcasrR4ia7z/giphy.gif" width="5%"></a>

I am Sailesh Dahal from Nepal 🇳🇵, a full-stack developer passionate about Flutter, Dart, and Firebase.

## Currently

- 💻 I’m currently working on **Freelance Projects**
- 🌱 I’m currently learning **[TypeScript](https://www.typescriptlang.org/)**
- 👯 I’m looking to collaborate on **Flutter Projects**
- 🤔 I’m looking for help with **Native App Development**
- 💬 Ask me about **[Flutter](https://flutter.dev)**

## My weekly development breakdown 📊

<!--START_SECTION:waka-->
<!--END_SECTION:waka-->

## Blog Posts 📕

<!-- BLOG-POST-LIST:START -->
 - 🌮[🤳 Effortless Sharing: From external apps to your Flutter app in no time](https://saileshdahal.com.np/sharing-media-from-external-to-flutter-app) 
 - &lt;p&gt;Sharing things like files, pictures, videos, and texts from external apps can be difficult, especially when done without any external packages.&lt;/p&gt;
&lt;p&gt;Facilitating content sharing via external apps boosts user engagement, improves the user experience, and helps to spread the word about our app.&lt;/p&gt;
&lt;p&gt;In this article, we&#39;ll be taking advantage of the awesome &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/share_handler&quot;&gt;share_handler&lt;/a&gt; package to make sharing from external apps to our Flutter app really easy!&lt;/p&gt;
&lt;p&gt;We will be using a multi-flavored flutter app as our starting point for this tutorial. You can &lt;a target=&quot;_blank&quot; href=&quot;https://github.com/saileshbro/sharing_into_flutter_app.git&quot;&gt;find the repo &lt;strong&gt;here&lt;/strong&gt;&lt;/a&gt;&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;&lt;strong&gt;🥳 Sounds great, right?&lt;/strong&gt;&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;Let&#39;s get started by adding &lt;code&gt;share_handler&lt;/code&gt; as a dependency in &lt;code&gt;pubspec.yaml&lt;/code&gt;&lt;/p&gt;
&lt;h2 id=&quot;heading-android-setup&quot;&gt;Android setup 🤖&lt;/h2&gt;
&lt;p&gt;We will start with the easy setup. In our &lt;code&gt;android/app/src/main/AndroidManifest.xml&lt;/code&gt; file, we will add the intent filters and metadata for the media types we want to support.&lt;/p&gt;
&lt;p&gt;For text-only support&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-xml&quot;&gt;&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;intent-filter&lt;/span&gt;&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;action&lt;/span&gt; &lt;span class=&quot;hljs-attr&quot;&gt;android:name&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;android.intent.action.SEND&quot;&lt;/span&gt; /&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;category&lt;/span&gt; &lt;span class=&quot;hljs-attr&quot;&gt;android:name&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;android.intent.category.DEFAULT&quot;&lt;/span&gt; /&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;data&lt;/span&gt; &lt;span class=&quot;hljs-attr&quot;&gt;android:mimeType&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;text/*&quot;&lt;/span&gt; /&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;intent-filter&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;For image-only support&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-xml&quot;&gt;&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;intent-filter&lt;/span&gt;&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;action&lt;/span&gt; &lt;span class=&quot;hljs-attr&quot;&gt;android:name&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;android.intent.action.SEND&quot;&lt;/span&gt; /&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;category&lt;/span&gt; &lt;span class=&quot;hljs-attr&quot;&gt;android:name&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;android.intent.category.DEFAULT&quot;&lt;/span&gt; /&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;data&lt;/span&gt; &lt;span class=&quot;hljs-attr&quot;&gt;android:mimeType&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;image/*&quot;&lt;/span&gt; /&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;intent-filter&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;For video-only support&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-xml&quot;&gt;&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;intent-filter&lt;/span&gt;&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;action&lt;/span&gt; &lt;span class=&quot;hljs-attr&quot;&gt;android:name&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;android.intent.action.SEND&quot;&lt;/span&gt; /&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;category&lt;/span&gt; &lt;span class=&quot;hljs-attr&quot;&gt;android:name&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;android.intent.category.DEFAULT&quot;&lt;/span&gt; /&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;data&lt;/span&gt; &lt;span class=&quot;hljs-attr&quot;&gt;android:mimeType&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;video/*&quot;&lt;/span&gt; /&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;intent-filter&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;If you want to support any type of files&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-xml&quot;&gt;&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;intent-filter&lt;/span&gt;&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;action&lt;/span&gt; &lt;span class=&quot;hljs-attr&quot;&gt;android:name&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;android.intent.action.SEND&quot;&lt;/span&gt; /&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;category&lt;/span&gt; &lt;span class=&quot;hljs-attr&quot;&gt;android:name&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;android.intent.category.DEFAULT&quot;&lt;/span&gt; /&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;data&lt;/span&gt; &lt;span class=&quot;hljs-attr&quot;&gt;android:mimeType&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;**/*&quot;&lt;/span&gt; /&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;intent-filter&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;blockquote&gt;
&lt;p&gt;&lt;strong&gt;💡 Tip:&lt;/strong&gt; You can add &lt;code&gt;SHARE_MULTIPLE&lt;/code&gt; action, if you want to support more than one media sharing.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;pre&gt;&lt;code class=&quot;lang-xml&quot;&gt;&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;intent-filter&lt;/span&gt;&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;action&lt;/span&gt; &lt;span class=&quot;hljs-attr&quot;&gt;android:name&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;android.intent.action.SEND_MULTIPLE&quot;&lt;/span&gt; /&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;category&lt;/span&gt; &lt;span class=&quot;hljs-attr&quot;&gt;android:name&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;android.intent.category.DEFAULT&quot;&lt;/span&gt; /&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;data&lt;/span&gt; &lt;span class=&quot;hljs-attr&quot;&gt;android:mimeType&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;image/*&quot;&lt;/span&gt; /&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;intent-filter&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;intent-filter&lt;/span&gt;&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;action&lt;/span&gt; &lt;span class=&quot;hljs-attr&quot;&gt;android:name&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;android.intent.action.SEND_MULTIPLE&quot;&lt;/span&gt; /&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;category&lt;/span&gt; &lt;span class=&quot;hljs-attr&quot;&gt;android:name&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;android.intent.category.DEFAULT&quot;&lt;/span&gt; /&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;data&lt;/span&gt; &lt;span class=&quot;hljs-attr&quot;&gt;android:mimeType&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;video/*&quot;&lt;/span&gt; /&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;intent-filter&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;intent-filter&lt;/span&gt;&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;action&lt;/span&gt; &lt;span class=&quot;hljs-attr&quot;&gt;android:name&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;android.intent.action.SEND_MULTIPLE&quot;&lt;/span&gt; /&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;category&lt;/span&gt; &lt;span class=&quot;hljs-attr&quot;&gt;android:name&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;android.intent.category.DEFAULT&quot;&lt;/span&gt; /&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;data&lt;/span&gt; &lt;span class=&quot;hljs-attr&quot;&gt;android:mimeType&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;*/*&quot;&lt;/span&gt; /&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;intent-filter&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;blockquote&gt;
&lt;p&gt;&lt;strong&gt;💡Tip:&lt;/strong&gt; You can change the &lt;code&gt;android:mimeType&lt;/code&gt; accordingly for the file types.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;Also, if you want to prevent the incoming shares from opening a new activity each time, you can prevent this by changing &lt;code&gt;android:launchMode&lt;/code&gt; to &lt;code&gt;singleTask&lt;/code&gt;&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-xml&quot;&gt;&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;activity&lt;/span&gt;
&lt;span class=&quot;hljs-attr&quot;&gt;...&lt;/span&gt;
&lt;span class=&quot;hljs-attr&quot;&gt;android:lunchMode&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;singleTask&quot;&lt;/span&gt;
&lt;span class=&quot;hljs-attr&quot;&gt;...&lt;/span&gt;
&amp;gt;&lt;/span&gt;
...
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;activity&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;For adding our app in share suggestions and shortcuts, we can create a new file &lt;code&gt;share_targets.xml&lt;/code&gt; in &lt;code&gt;android/app/src/main/res/xml/share_targets.xml&lt;/code&gt;&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-xml&quot;&gt;&lt;span class=&quot;hljs-meta&quot;&gt;&amp;lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;shortcuts&lt;/span&gt; &lt;span class=&quot;hljs-attr&quot;&gt;xmlns:android&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;http://schemas.android.com/apk/res/android&quot;&lt;/span&gt;&amp;gt;&lt;/span&gt;
  &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;share-target&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;android:targetClass&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;@{&#39;np.com.saileshdahal.sharing&#39;+@strings/app_id_suffix+&#39;.dynamic_share_target&#39;}&quot;&lt;/span&gt;&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;data&lt;/span&gt; &lt;span class=&quot;hljs-attr&quot;&gt;android:mimeType&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;*/*&quot;&lt;/span&gt; /&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;category&lt;/span&gt;
      &lt;span class=&quot;hljs-attr&quot;&gt;android:name&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;@{&#39;np.com.saileshdahal.sharing&#39;+@strings/app_id_suffix+&#39;.dynamic_share_target&#39;}&quot;&lt;/span&gt; /&amp;gt;&lt;/span&gt;
  &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;share-target&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;shortcuts&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;blockquote&gt;
&lt;p&gt;&lt;strong&gt;💡 Tip:&lt;/strong&gt; Make sure you have &lt;code&gt;app_id_suffix&lt;/code&gt; resource string defined for each flavor.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;pre&gt;&lt;code class=&quot;lang-apache&quot;&gt;&lt;span class=&quot;hljs-attribute&quot;&gt;resValue&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&quot;string&quot;&lt;/span&gt;, &lt;span class=&quot;hljs-string&quot;&gt;&quot;app_id_suffix&quot;&lt;/span&gt;, applicationIdSuffix
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;If you are &lt;strong&gt;not using flavors&lt;/strong&gt;, you can define this in the following format.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-xml&quot;&gt;&lt;span class=&quot;hljs-meta&quot;&gt;&amp;lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;shortcuts&lt;/span&gt; &lt;span class=&quot;hljs-attr&quot;&gt;xmlns:android&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;http://schemas.android.com/apk/res/android&quot;&lt;/span&gt;&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;share-target&lt;/span&gt; &lt;span class=&quot;hljs-attr&quot;&gt;android:targetClass&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;{your.package.identifier}.MainActivity&quot;&lt;/span&gt;&amp;gt;&lt;/span&gt;
        &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;data&lt;/span&gt; &lt;span class=&quot;hljs-attr&quot;&gt;android:mimeType&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;*/*&quot;&lt;/span&gt; /&amp;gt;&lt;/span&gt;
        &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;category&lt;/span&gt; &lt;span class=&quot;hljs-attr&quot;&gt;android:name&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;{your.package.identifier}.dynamic_share_target&quot;&lt;/span&gt; /&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;share-target&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;shortcuts&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Now, we will add a metadata field in the &lt;code&gt;AndroidManifest.xml&lt;/code&gt; file.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-xml&quot;&gt;&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;meta-data&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;android:name&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;android.service.chooser.chooser_target_service&quot;&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;android:value&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;androidx.sharetarget.ChooserTargetServiceCompat&quot;&lt;/span&gt; /&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;meta-data&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;android:name&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;android.app.shortcuts&quot;&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;android:resource&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;@xml/share_targets&quot;&lt;/span&gt; /&amp;gt;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Once done, if you try to share something, you should see the app icon on the share page.&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1676289713546/0efdd6d6-d920-41e8-91a9-457f328656b3.png&quot; alt=&quot;App showing in share intent&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;hr /&gt;
&lt;h2 id=&quot;heading-ios-setup&quot;&gt;iOS setup 📱&lt;/h2&gt;
&lt;h3 id=&quot;heading-update-runner-infoplist&quot;&gt;Update Runner &lt;code&gt;Info.plist&lt;/code&gt;&lt;/h3&gt;
&lt;p&gt;For iOS, let&#39;s get started by editing our &lt;code&gt;Info.plist&lt;/code&gt; file. We will be registering a deep link that will be launched by Share Extension.&lt;/p&gt;
&lt;p&gt;For registering the deep link, add the following in your &lt;code&gt;Info.plist&lt;/code&gt;&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-xml&quot;&gt;&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;CFBundleURLTypes&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;array&lt;/span&gt;&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;dict&lt;/span&gt;&amp;gt;&lt;/span&gt;
        &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;CFBundleTypeRole&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
        &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;Editor&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;
        &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;CFBundleURLSchemes&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
        &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;array&lt;/span&gt;&amp;gt;&lt;/span&gt;
            &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;ShareMedia-$descriptionlpar;PRODUCT_BUNDLE_IDENTIFIER&rpar;&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;
        &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;array&lt;/span&gt;&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;dict&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;array&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;If you already have some entries for &lt;code&gt;CFBundleURLTypes&lt;/code&gt;, you can add a new entry like this.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-xml&quot;&gt;&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;CFBundleURLTypes&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;array&lt;/span&gt;&amp;gt;&lt;/span&gt;
    ...
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;dict&lt;/span&gt;&amp;gt;&lt;/span&gt;
        &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;CFBundleTypeRole&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
        &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;Editor&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;
        &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;CFBundleURLSchemes&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
        &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;array&lt;/span&gt;&amp;gt;&lt;/span&gt;
            &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;ShareMedia-$descriptionlpar;PRODUCT_BUNDLE_IDENTIFIER&rpar;&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;
        &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;array&lt;/span&gt;&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;dict&lt;/span&gt;&amp;gt;&lt;/span&gt;
    ...
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;array&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;blockquote&gt;
&lt;p&gt;&lt;strong&gt;💡 Tip:&lt;/strong&gt; Make sure you have a user-defined variable &lt;code&gt;PRODUCT_BUNDLE_IDENTIFIER&lt;/code&gt; for your iOS project.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;Make sure you have an entry for &lt;code&gt;NSPhotoLibraryUsageDescription&lt;/code&gt; if you are planning to share images.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-xml&quot;&gt;&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;NSPhotoLibraryUsageDescription&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;Photos can be shared to and used in this app&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;If you are planning to add &lt;code&gt;AirDrop&lt;/code&gt; support, add the following entry in &lt;code&gt;Info.plist&lt;/code&gt;.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-xml&quot;&gt;&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;LSSupportsOpeningDocumentsInPlace&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;No&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;CFBundleDocumentTypes&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;array&lt;/span&gt;&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;dict&lt;/span&gt;&amp;gt;&lt;/span&gt;
        &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;CFBundleTypeName&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
        &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;ShareHandler&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;
        &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;LSHandlerRank&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
        &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;Alternate&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;
        &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;LSItemContentTypes&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
        &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;array&lt;/span&gt;&amp;gt;&lt;/span&gt;
            &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;public.file-url&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;
            &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;public.image&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;
            &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;public.text&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;
            &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;public.movie&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;
            &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;public.url&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;
            &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;public.data&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;
        &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;array&lt;/span&gt;&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;dict&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;array&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;blockquote&gt;
&lt;p&gt;💡 You can modify &lt;code&gt;LSItemContentTypes&lt;/code&gt; array based on your need.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;h3 id=&quot;heading-share-extension-setup&quot;&gt;Share Extension setup&lt;/h3&gt;
&lt;p&gt;Now for this part, we will create a share extension from Xcode.&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;Open &lt;code&gt;ios&lt;/code&gt; folder of your flutter project in Xcode.&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;open ios/Runner.xcworkspace
&lt;/code&gt;&lt;/pre&gt;
&lt;ul&gt;
&lt;li&gt;Go to &lt;code&gt;File&lt;/code&gt; -&amp;gt; &lt;code&gt;New&lt;/code&gt; -&amp;gt; &lt;code&gt;Target&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1676289784911/315f2d44-700d-4c8f-b816-348a5bc99e74.png&quot; alt=&quot;Image showing how to create a new target&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;Search for &lt;code&gt;Share Extension&lt;/code&gt; and hit &lt;code&gt;Next&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1676289798585/fb9216af-8b17-4b2b-85f2-2aa3e53028e2.png&quot; alt=&quot;Image showing how to select a Share Extension&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;p&gt;Now create the extension with &lt;code&gt;ShareExtension&lt;/code&gt; name, and hit save. This will add a new target for your project.&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;&lt;strong&gt;🚨 Note:&lt;/strong&gt; Make sure the name is &lt;code&gt;ShareExtension&lt;/code&gt;&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1676289845846/c3d57abe-9d1a-4180-b745-ad8eaa6924a5.png&quot; alt=&quot;Create a new Share Extension Prompt&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;&lt;strong&gt;🚨 IMPORTANT:&lt;/strong&gt; Make sure the minimum deployment version of both targets is the same.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1676289961422/192e05e0-0731-4b0a-b919-0af9063176f2.png&quot; alt=&quot;Setting min deployment version to 14&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;p&gt;For &lt;code&gt;Target&lt;/code&gt; -&amp;gt; &lt;code&gt;Runner&lt;/code&gt;, set minimum deployment version to &lt;code&gt;14.0&lt;/code&gt;.&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1676289979648/2af298bf-0818-439f-ab10-bfd83df83f0d.png&quot; alt=&quot;Setting min deployment version to 14&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;p&gt;Similarly for &lt;code&gt;Target&lt;/code&gt;-&amp;gt; &lt;code&gt;ShareExtension&lt;/code&gt;, set minimum deployment version to &lt;code&gt;14.0&lt;/code&gt;&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1676289992228/c8a9c274-7260-42e2-b569-031d02cb8255.png&quot; alt=&quot;Setting min deployment version to 14&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;p&gt;Once this is done, open &lt;code&gt;ios/ShareExtension/ShareViewController.swift&lt;/code&gt; and replace everything with following&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-swift&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; share_handler_ios_models

&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;ShareViewController&lt;/span&gt;: &lt;span class=&quot;hljs-title&quot;&gt;ShareHandlerIosViewController&lt;/span&gt; &lt;/span&gt;{}
&lt;/code&gt;&lt;/pre&gt;
&lt;blockquote&gt;
&lt;p&gt;&lt;strong&gt;🚨 Note:&lt;/strong&gt; Make sure to run &lt;code&gt;flutter pub get&lt;/code&gt; and &lt;code&gt;pod install --repo-update&lt;/code&gt;&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;If you have multiple flavors set up then we will also have to create multiple flavors for our share extension. We will create 3 different schemes for share extension too.&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1676290018979/59d15593-eef5-433e-82ab-b741d3f14eb4.png&quot; alt=&quot;Manage scheme option&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;p&gt;Go to &lt;code&gt;Manage Scheme&lt;/code&gt;, and then we will duplicate and create 3 different schemes for &lt;code&gt;ShareExtension&lt;/code&gt; as &lt;code&gt;ShareExtension-production&lt;/code&gt;, &lt;code&gt;ShareExtension-development&lt;/code&gt; and &lt;code&gt;ShareExtension-staging&lt;/code&gt;.&lt;/p&gt;
&lt;p&gt;Rename &lt;code&gt;ShareExtension&lt;/code&gt; to &lt;code&gt;ShareExtension-production&lt;/code&gt; that will handle one scheme, and then for staging, we can duplicate &lt;code&gt;ShareExtension-production&lt;/code&gt; and rename it to &lt;code&gt;ShareExtension-staging&lt;/code&gt; and assign the correct configuration.&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1676290061564/62c12ca3-be04-4ddd-8d4c-ed45d3254211.jpeg&quot; alt=&quot;Create a new Share Extension scheme for staging&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;p&gt;Similarly, we will create one scheme for &lt;code&gt;ShareExtension-development&lt;/code&gt; as well.&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1676290073981/a45b3dde-0a31-4ebc-9b34-bc71bb3277a5.png&quot; alt=&quot;All final schemes&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;🚨 &lt;strong&gt;Note: You don&#39;t have to duplicate the schemes if you are not using flavors&lt;/strong&gt;.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;h3 id=&quot;heading-share-extension-infoplist-update&quot;&gt;Share Extension &lt;code&gt;Info.plist&lt;/code&gt; update&lt;/h3&gt;
&lt;p&gt;Once this is done, we will make some changes to &lt;code&gt;ios/ShareExtension/Info.plist&lt;/code&gt;&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-xml&quot;&gt;&lt;span class=&quot;hljs-meta&quot;&gt;&amp;lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-meta&quot;&gt;&amp;lt;!DOCTYPE &lt;span class=&quot;hljs-meta-keyword&quot;&gt;plist&lt;/span&gt; &lt;span class=&quot;hljs-meta-keyword&quot;&gt;PUBLIC&lt;/span&gt; &lt;span class=&quot;hljs-meta-string&quot;&gt;&quot;-//Apple//DTD PLIST 1.0//EN&quot;&lt;/span&gt; &lt;span class=&quot;hljs-meta-string&quot;&gt;&quot;http://www.apple.com/DTDs/PropertyList-1.0.dtd&quot;&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;plist&lt;/span&gt; &lt;span class=&quot;hljs-attr&quot;&gt;version&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;1.0&quot;&lt;/span&gt;&amp;gt;&lt;/span&gt;
  &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;dict&lt;/span&gt;&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;CFBundleVersion&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;$descriptionlpar;FLUTTER_BUILD_NUMBER&rpar;&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;NSExtension&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;dict&lt;/span&gt;&amp;gt;&lt;/span&gt;
      &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;NSExtensionAttributes&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
      &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;dict&lt;/span&gt;&amp;gt;&lt;/span&gt;
        &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;IntentsSupported&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
        &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;array&lt;/span&gt;&amp;gt;&lt;/span&gt;
          &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;INSendMessageIntent&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;
        &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;array&lt;/span&gt;&amp;gt;&lt;/span&gt;
        &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;NSExtensionActivationRule&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
        &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;dict&lt;/span&gt;&amp;gt;&lt;/span&gt;
          &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;NSExtensionActivationSupportsWebURLWithMaxCount&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
          &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;integer&lt;/span&gt;&amp;gt;&lt;/span&gt;999&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;integer&lt;/span&gt;&amp;gt;&lt;/span&gt;
          &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;NSExtensionActivationSupportsWebPageWithMaxCount&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
          &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;integer&lt;/span&gt;&amp;gt;&lt;/span&gt;999&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;integer&lt;/span&gt;&amp;gt;&lt;/span&gt;
          &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;NSExtensionActivationSupportsMovieWithMaxCount&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
          &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;integer&lt;/span&gt;&amp;gt;&lt;/span&gt;999&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;integer&lt;/span&gt;&amp;gt;&lt;/span&gt;
          &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;NSExtensionActivationSupportsImageWithMaxCount&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
          &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;integer&lt;/span&gt;&amp;gt;&lt;/span&gt;999&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;integer&lt;/span&gt;&amp;gt;&lt;/span&gt;
          &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;NSExtensionActivationSupportsFileWithMaxCount&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
          &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;integer&lt;/span&gt;&amp;gt;&lt;/span&gt;999&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;integer&lt;/span&gt;&amp;gt;&lt;/span&gt;
          &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;NSExtensionActivationSupportsAttachmentsWithMaxCount&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
          &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;integer&lt;/span&gt;&amp;gt;&lt;/span&gt;999&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;integer&lt;/span&gt;&amp;gt;&lt;/span&gt;
          &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;NSExtensionActivationSupportsText&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
          &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;true&lt;/span&gt; /&amp;gt;&lt;/span&gt;
        &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;dict&lt;/span&gt;&amp;gt;&lt;/span&gt;
        &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;PHSupportedMediaTypes&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
        &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;array&lt;/span&gt;&amp;gt;&lt;/span&gt;
          &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;Video&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;
          &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;Image&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;
        &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;array&lt;/span&gt;&amp;gt;&lt;/span&gt;
      &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;dict&lt;/span&gt;&amp;gt;&lt;/span&gt;
      &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;NSExtensionMainStoryboard&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
      &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;MainInterface&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;
      &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;NSExtensionPointIdentifier&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
      &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;com.apple.share-services&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;dict&lt;/span&gt;&amp;gt;&lt;/span&gt;
  &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;dict&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;plist&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Here you can make changes to the &lt;code&gt;NSExtensionActivationRule&lt;/code&gt; field based on your requirements.&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;Note: Here we have set the maximum file-sharing count to 999, but you can disable or enable them based on your requirements.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;Once this is done, make sure we have different bundle identifiers for each flavor and configuration for &lt;code&gt;Share Extension&lt;/code&gt;. If you click &lt;code&gt;Target&lt;/code&gt; -&amp;gt; &lt;code&gt;Share Extension&lt;/code&gt; -&amp;gt; &lt;code&gt;Singing &amp;amp; Capabilities&lt;/code&gt; -&amp;gt; &lt;code&gt;All&lt;/code&gt;&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1676290130000/678a49d8-2cef-4d4d-9218-fb118a2f387b.png&quot; alt=&quot;All bundle ids for share extension&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;&lt;strong&gt;🚨 Note:&lt;/strong&gt; Make sure the &lt;code&gt;ShareExtension&lt;/code&gt; bundle identifier for each config has a &lt;code&gt;.ShareExtension&lt;/code&gt; prefix compared to the &lt;code&gt;Runner&lt;/code&gt;.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;Once done, we need to assign both targets with a group identifier. For both &lt;code&gt;Runner&lt;/code&gt; and &lt;code&gt;ShareExtension&lt;/code&gt; target, go to &lt;code&gt;Signing &amp;amp; Capabilities&lt;/code&gt;.&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1676290144337/b32f39ad-7e5b-4e46-aa55-97644a3e2b34.png&quot; alt=&quot;Show how to add app group&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;p&gt;Now, for each flavor, we will add an app group.&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1676290163014/d90f88b6-7357-42f5-b16b-0a89a81ea540.png&quot; alt=&quot;Show how to add app group&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1676290176925/0b4f0856-0a10-43f2-aeae-b851091f53fa.png&quot; alt=&quot;Show how to add app group&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;🚨 Note: Make sure to add the group id as &lt;code&gt;group.&amp;lt;bundle identifier&amp;gt;&lt;/code&gt; for each flavor.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;For &lt;code&gt;Debug-production&lt;/code&gt;, &lt;code&gt;Release-production&lt;/code&gt;, and &lt;code&gt;Profile-production&lt;/code&gt;.&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1676290196245/04fb9de6-227c-4a9a-bf46-038303eddf60.png&quot; alt=&quot;add new group id for production&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;💡 Tip: For matching group, you can select the check box&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1676290267867/dac703ea-93d6-421a-8291-9545ce4dbef3.png&quot; alt=&quot;option showing the group id&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;p&gt;For &lt;code&gt;Debug-development&lt;/code&gt;, &lt;code&gt;Release-development&lt;/code&gt;, and &lt;code&gt;Profile-development&lt;/code&gt;.&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1676290276924/2b178b2b-1bb3-42f4-aab3-d09fbb44bd25.png&quot; alt=&quot;add new group id for development&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;p&gt;Similarly for &lt;code&gt;Debug-staging&lt;/code&gt;, &lt;code&gt;Release-staging&lt;/code&gt;, and &lt;code&gt;Profile-staging&lt;/code&gt;&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1676290291524/0f017a91-0600-46ec-8d4e-0eedb61cb93b.png&quot; alt=&quot;add new group id for staging&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;p&gt;If you click on &lt;code&gt;Target&lt;/code&gt; -&amp;gt; &lt;code&gt;Runner&lt;/code&gt; -&amp;gt; &lt;code&gt;Signing &amp;amp; Capabilities&lt;/code&gt; -&amp;gt; &lt;code&gt;All&lt;/code&gt;, you should see the following.&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1676290303653/04773b29-42fe-4a3a-8361-de3adb195cce.png&quot; alt=&quot;All app groups linked&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;p&gt;This will create &lt;code&gt;entitlements&lt;/code&gt; files for each configuration.&lt;/p&gt;
&lt;p&gt;Similarly for &lt;code&gt;ShareExtension&lt;/code&gt; we can quickly create &lt;code&gt;.entitlements&lt;/code&gt; files. In &lt;code&gt;ios/ShareExtension&lt;/code&gt; we will create an entitlements file for each config and each flavor. We will create 9 entitlements files for each flavor &lpar;&lt;code&gt;production&lt;/code&gt;, &lt;code&gt;development&lt;/code&gt;, and &lt;code&gt;staging&lt;/code&gt;&rpar;, and &lt;code&gt;Debug&lt;/code&gt;, &lt;code&gt;Release&lt;/code&gt;, and &lt;code&gt;Profile&lt;/code&gt; config.&lt;/p&gt;
&lt;p&gt;For &lt;code&gt;Debug&lt;/code&gt;, &lt;code&gt;Release&lt;/code&gt;, and &lt;code&gt;Profile&lt;/code&gt; configuration for &lt;code&gt;development&lt;/code&gt; flavor, we will create three files &lt;code&gt;ShareExtensionRelease-development.entitlements&lt;/code&gt;, &lt;code&gt;ShareExtensionDebug-development.entitlements&lt;/code&gt;, and &lt;code&gt;ShareExtensionProfile-development.entitlements&lt;/code&gt;, with the following contents.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-xml&quot;&gt;&lt;span class=&quot;hljs-meta&quot;&gt;&amp;lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-meta&quot;&gt;&amp;lt;!DOCTYPE &lt;span class=&quot;hljs-meta-keyword&quot;&gt;plist&lt;/span&gt; &lt;span class=&quot;hljs-meta-keyword&quot;&gt;PUBLIC&lt;/span&gt; &lt;span class=&quot;hljs-meta-string&quot;&gt;&quot;-//Apple//DTD PLIST 1.0//EN&quot;&lt;/span&gt; &lt;span class=&quot;hljs-meta-string&quot;&gt;&quot;http://www.apple.com/DTDs/PropertyList-1.0.dtd&quot;&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;plist&lt;/span&gt; &lt;span class=&quot;hljs-attr&quot;&gt;version&lt;/span&gt;=&lt;span class=&quot;hljs-string&quot;&gt;&quot;1.0&quot;&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;dict&lt;/span&gt;&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;com.apple.security.application-groups&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;array&lt;/span&gt;&amp;gt;&lt;/span&gt;
        &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;group.np.com.saileshdahal.sharing.dev&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;
    &lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;array&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;dict&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;plist&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Similarly, for each configuration of &lt;code&gt;production&lt;/code&gt; and &lt;code&gt;staging&lt;/code&gt; flavor, we will create three entitlements files.&lt;/p&gt;
&lt;p&gt;By the end, we will have the following files&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-apache&quot;&gt;&lt;span class=&quot;hljs-attribute&quot;&gt;ShareExtensionDebug&lt;/span&gt;-development.entitlements
&lt;span class=&quot;hljs-attribute&quot;&gt;ShareExtensionDebug&lt;/span&gt;-production.entitlements
&lt;span class=&quot;hljs-attribute&quot;&gt;ShareExtensionDebug&lt;/span&gt;-staging.entitlements
&lt;span class=&quot;hljs-attribute&quot;&gt;ShareExtensionProfile&lt;/span&gt;-development.entitlements
&lt;span class=&quot;hljs-attribute&quot;&gt;ShareExtensionProfile&lt;/span&gt;-production.entitlements
&lt;span class=&quot;hljs-attribute&quot;&gt;ShareExtensionProfile&lt;/span&gt;-staging.entitlements
&lt;span class=&quot;hljs-attribute&quot;&gt;ShareExtensionRelease&lt;/span&gt;-development.entitlements
&lt;span class=&quot;hljs-attribute&quot;&gt;ShareExtensionRelease&lt;/span&gt;-production.entitlements
&lt;span class=&quot;hljs-attribute&quot;&gt;ShareExtensionRelease&lt;/span&gt;-staging.entitlements
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Once this is done, link the entitlement files by clicking &lt;code&gt;+&lt;/code&gt; button for app group capabilities for each flavor.&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1676290359941/a5681d0c-2d34-4a64-9d15-657cc78085ea.png&quot; alt=&quot;reverify your entitlements file&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;&lt;strong&gt;💡Tip:&lt;/strong&gt; Make sure the entitlements files are correctly linked, else this may not work properly for each flavor.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;Make sure, we have all the entitlements files linked up correctly. If we do everything right we will see the following.&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1676290370952/47123d8c-caa9-4a75-9178-e2420c29dbb5.png&quot; alt=&quot;all linked group ids&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1676290380424/6dbfe44f-3a78-4b7e-a677-5c04999e3a55.png&quot; alt=&quot;final entitlement files&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;🚨 For iOS setup without flavors&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;All the setup above can be taken reference for the apps without flavors as well. The only difference here is, we can have single entitlements file for each target, that is &lt;code&gt;Runner.entitlements&lt;/code&gt; and &lt;code&gt;ShareExtension.entitlements&lt;/code&gt;.&lt;/p&gt;
&lt;p&gt;The bundle id for the &lt;code&gt;Share Extension&lt;/code&gt; will be &lt;code&gt;np.com.saileshdahal.sharing.ShareExtension&lt;/code&gt;, and the group bundle id will be &lt;code&gt;group.np.com.saileshdahal.sharing&lt;/code&gt;&lt;/p&gt;
&lt;p&gt;Now, for the final setup, we will make some changes in &lt;code&gt;Podfile&lt;/code&gt; and register the dependency.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-ruby&quot;&gt;target &lt;span class=&quot;hljs-string&quot;&gt;&#39;Runner&#39;&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;do&lt;/span&gt;
  use_frameworks!
  use_modular_headers!

  flutter_install_all_ios_pods File.dirname&lpar;File.realpath&lpar;__FILE_&lt;span class=&quot;hljs-number&quot;&gt;_&lt;/span&gt;&rpar;&rpar;

  &lt;span class=&quot;hljs-comment&quot;&gt;# Add this block&lt;/span&gt;
  target &lt;span class=&quot;hljs-string&quot;&gt;&#39;ShareExtension&#39;&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;do&lt;/span&gt;
    inherit! &lt;span class=&quot;hljs-symbol&quot;&gt;:search_paths&lt;/span&gt;
    pod &lt;span class=&quot;hljs-string&quot;&gt;&quot;share_handler_ios_models&quot;&lt;/span&gt;, &lt;span class=&quot;hljs-symbol&quot;&gt;:path&lt;/span&gt; =&amp;gt; &lt;span class=&quot;hljs-string&quot;&gt;&quot;.symlinks/plugins/share_handler_ios/ios/Models&quot;&lt;/span&gt;
  &lt;span class=&quot;hljs-keyword&quot;&gt;end&lt;/span&gt;
  &lt;span class=&quot;hljs-comment&quot;&gt;# End of block&lt;/span&gt;

&lt;span class=&quot;hljs-keyword&quot;&gt;end&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Once this is done, run &lt;code&gt;pod install --repo-update&lt;/code&gt; in &lt;code&gt;ios&lt;/code&gt; directory.&lt;/p&gt;
&lt;hr /&gt;
&lt;h2 id=&quot;heading-testing-time&quot;&gt;🧪 Testing time&lt;/h2&gt;
&lt;p&gt;Let&#39;s check if we can see our app when we share something.&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1676290414640/002962c1-c902-45e5-b31c-528e5ffbf932.png&quot; alt=&quot;app showing in share intent&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;p&gt;Here, we can see both flavors appear while we try to share images from photos.&lt;/p&gt;
&lt;hr /&gt;
&lt;h2 id=&quot;heading-getting-shared-media-in-flutter&quot;&gt;Getting shared media in Flutter&lt;/h2&gt;
&lt;p&gt;Now that we have both Android and iOS working, we can start implementing our share handler service to get the shared media.&lt;/p&gt;
&lt;p&gt;The package exposes a stream of &lt;code&gt;SharedMedia&lt;/code&gt;. We can subscribe to this stream and do side effects based on the shared media type.&lt;/p&gt;
&lt;p&gt;Also, the package has a method to get the initial shared media. This will be helpful if the app is in terminated state, and we open the app from the share page.&lt;/p&gt;
&lt;p&gt;I have added the code snippet from &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/share_handler&quot;&gt;&lt;code&gt;share_handler&lt;/code&gt;&lt;/a&gt;&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;HomePage&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;extends&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;StatefulWidget&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; HomePage&lpar;{&lt;span class=&quot;hljs-keyword&quot;&gt;super&lt;/span&gt;.key}&rpar;;

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  State&amp;lt;HomePage&amp;gt; createState&lpar;&rpar; =&amp;gt; _HomePageState&lpar;&rpar;;
}

&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;_HomePageState&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;extends&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;State&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-title&quot;&gt;HomePage&lt;/span&gt;&amp;gt; &lt;/span&gt;{
  StreamSubscription&amp;lt;SharedMedia&amp;gt;? _streamSubscription;
  SharedMedia? media;

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  &lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt; initState&lpar;&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;super&lt;/span&gt;.initState&lpar;&rpar;;
    initPlatformState&lpar;&rpar;;
  }

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  &lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt; dispose&lpar;&rpar; {
    _streamSubscription?.cancel&lpar;&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;super&lt;/span&gt;.dispose&lpar;&rpar;;
  }

  Future&amp;lt;&lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt;&amp;gt; initPlatformState&lpar;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; handler = ShareHandlerPlatform.instance;
    media = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; handler.getInitialSharedMedia&lpar;&rpar;;
    _streamSubscription = handler.sharedMediaStream.listen&lpar;&lpar;SharedMedia media&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;!mounted&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt;;
      setState&lpar;&lpar;&rpar; =&amp;gt; &lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;.media = media&rpar;;
    }&rpar;;
  }

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Widget build&lpar;BuildContext context&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Scaffold&lpar;
      appBar: AppBar&lpar;
        title: &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; Text&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;Share Handler&#39;&lt;/span&gt;&rpar;,
      &rpar;,
      body: ListView&lpar;
        padding: &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; EdgeInsets.all&lpar;&lt;span class=&quot;hljs-number&quot;&gt;16&lt;/span&gt;&rpar;,
        children: &amp;lt;Widget&amp;gt;[
          Text&lpar;
            &lt;span class=&quot;hljs-string&quot;&gt;&#39;Shared to conversation identifier: &lt;span class=&quot;hljs-subst&quot;&gt;${media?.conversationIdentifier}&lt;/span&gt;&#39;&lt;/span&gt;,
          &rpar;,
          &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; SizedBox&lpar;height: &lt;span class=&quot;hljs-number&quot;&gt;10&lt;/span&gt;&rpar;,
          Text&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;Shared text: &lt;span class=&quot;hljs-subst&quot;&gt;${media?.content}&lt;/span&gt;&#39;&lt;/span&gt;&rpar;,
          &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; SizedBox&lpar;height: &lt;span class=&quot;hljs-number&quot;&gt;10&lt;/span&gt;&rpar;,
          Text&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;Shared files: &lt;span class=&quot;hljs-subst&quot;&gt;${media?.attachments?.length}&lt;/span&gt;&#39;&lt;/span&gt;&rpar;,
          ...&lpar;media?.attachments ?? []&rpar;.map&lpar;&lpar;attachment&rpar; {
            &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; path = attachment?.path;
            &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;path != &lt;span class=&quot;hljs-keyword&quot;&gt;null&lt;/span&gt; &amp;amp;&amp;amp;
                attachment?.type == SharedAttachmentType.image&rpar; {
              &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Column&lpar;
                children: [
                  ElevatedButton&lpar;
                    onPressed: &lpar;&rpar; {
                      ShareHandlerPlatform.instance.recordSentMessage&lpar;
                        conversationIdentifier:
                            &lt;span class=&quot;hljs-string&quot;&gt;&#39;custom-conversation-identifier&#39;&lt;/span&gt;,
                        conversationName: &lt;span class=&quot;hljs-string&quot;&gt;&#39;John Doe&#39;&lt;/span&gt;,
                        conversationImageFilePath: path,
                        serviceName: &lt;span class=&quot;hljs-string&quot;&gt;&#39;custom-service-name&#39;&lt;/span&gt;,
                      &rpar;;
                    },
                    child: &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; Text&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;Record message&#39;&lt;/span&gt;&rpar;,
                  &rpar;,
                  &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; SizedBox&lpar;height: &lt;span class=&quot;hljs-number&quot;&gt;10&lt;/span&gt;&rpar;,
                  Image.file&lpar;File&lpar;path&rpar;&rpar;,
                ],
              &rpar;;
            }
            &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Text&lpar;
              &lt;span class=&quot;hljs-string&quot;&gt;&#39;&lt;span class=&quot;hljs-subst&quot;&gt;${attachment?.type}&lt;/span&gt; Attachment: &lt;span class=&quot;hljs-subst&quot;&gt;${attachment?.path}&lt;/span&gt;&#39;&lt;/span&gt;,
            &rpar;;
          }&rpar;,
        ],
      &rpar;,
    &rpar;;
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Now, if we run this code and try to share an image from Photos, we should see something like this 🥳.&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1676290453387/c35ad321-b438-4991-b90e-02fc03cff5af.gif&quot; alt=&quot;working demo of the gif&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;hr /&gt;
&lt;p&gt;🎉 Congratulations, we&#39;ve reached the end of this article on how to easily share content from external apps to your Flutter app using the share_handler package! 🚀 Hopefully, you found this tutorial helpful and have learned a lot about effortless sharing in Flutter.&lt;/p&gt;
&lt;p&gt;As always, the source code for this tutorial can be found on the GitHub repository at &lt;a target=&quot;_blank&quot; href=&quot;https://github.com/saileshbro/sharing_into_flutter_app&quot;&gt;&lt;code&gt;saileshbro/sharing_into_flutter_app&lt;/code&gt;&lt;/a&gt;. If you found this article useful, don&#39;t forget to leave a  and share it with others.&lt;/p&gt;
&lt;p&gt;And if you&#39;re interested in learning more about setting up flavors in Flutter, be sure to check out &lt;a target=&quot;_blank&quot; href=&quot;https://saileshdahal.com.np/flavor-setup-flutter&quot;&gt;&lt;strong&gt;🍰 Simplifying flavor setup in the existing Flutter app: A comprehensive guide&lt;/strong&gt;&lt;/a&gt; to learn how to add different flavors to your app with unique configurations and build targets.&lt;/p&gt;
&lt;p&gt;Thank you for joining me on this journey, and happy coding! 💻👨💻&lt;/p&gt;
&lt;h2 id=&quot;heading-references&quot;&gt;References&lt;/h2&gt;
&lt;ul&gt;
&lt;li&gt;&lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/share_handler&quot;&gt;&lt;code&gt;share_handler&lt;/code&gt;&lt;/a&gt;&lt;/li&gt;
&lt;/ul&gt;
 

 - 💯[🍰 Simplifying flavor setup in the existing Flutter app: A comprehensive guide](https://saileshdahal.com.np/flavor-setup-flutter) 
 - &lt;p&gt;Flavors are build configurations in Flutter apps that allow developers to create separate environments using the same code base. They allow for customization at runtime based on the defined compile-time configurations.&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;&lt;p&gt;Flavors allow efficient management of different development environments &lpar;development, staging, production&rpar;&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;Enables creation of multiple versions of the same app &lpar;free and paid versions, separate environments for feature development&rpar;&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;Simplifies setting different parameters &lpar;API endpoints, API keys, app icons&rpar; for each configuration&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;Makes it easier to manage different app versions&lt;/p&gt;
&lt;/li&gt;
&lt;/ul&gt;
&lt;blockquote&gt;
&lt;p&gt;Apps created using the &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/very_good_cli&quot;&gt;&lt;code&gt;very_good_cli&lt;/code&gt;&lt;/a&gt; comes with three flavors - &lt;code&gt;development&lt;/code&gt;, &lt;code&gt;staging&lt;/code&gt;, and &lt;code&gt;production&lt;/code&gt;.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;hr /&gt;
&lt;h1 id=&quot;heading-adding-flavors-to-an-existing-flutter-app&quot;&gt;Adding Flavors to an Existing Flutter App&lt;/h1&gt;
&lt;p&gt;When it comes to adding flavors to an existing Flutter app, there are packages available that promise to automate the process, such as &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/flutter_flavorizr&quot;&gt;&lt;code&gt;flutter_flavorizr&lt;/code&gt;&lt;/a&gt;.&lt;/p&gt;
&lt;p&gt;It&#39;s common for these solutions to encounter issues when the app has already made extensive use of native plugins and custom configurations.&lt;/p&gt;
&lt;p&gt;As a result, manually adding flavors to an app may be the best course of action. This process requires a bit of human touch, but it provides complete control over the configuration of your app&#39;s flavors.&lt;/p&gt;
&lt;hr /&gt;
&lt;h1 id=&quot;heading-setting-up-flavors&quot;&gt;Setting Up Flavors 🛠&lt;/h1&gt;
&lt;p&gt;To get a hands-on experience, we will be adding flavors to &lt;a target=&quot;_blank&quot; href=&quot;https://github.com/saileshbro/fitness_app_clone&quot;&gt;&lt;strong&gt;an existing app from here&lt;/strong&gt;&lt;/a&gt;&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;We will be setting up &lt;code&gt;development&lt;/code&gt;, &lt;code&gt;staging&lt;/code&gt; and &lt;code&gt;production&lt;/code&gt; flavors.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;h2 id=&quot;heading-create-target-files&quot;&gt;Create Target Files 💻&lt;/h2&gt;
&lt;p&gt;We will start by creating three main files for each flavor, &lt;code&gt;main_&amp;lt;flavor&amp;gt;.dart&lt;/code&gt; and create a &lt;code&gt;main&lt;/code&gt; function.&lt;/p&gt;
&lt;p&gt;We can replace the outdated &lt;code&gt;main.dart&lt;/code&gt; file with our new entry points. In the &lt;code&gt;bootstrap.dart file&lt;/code&gt;, we&#39;ll create a new function called &lt;code&gt;bootstrap&lt;/code&gt; which will accept the environment from each entry point and use it to launch the app.&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;&lt;code&gt;main_production.dart&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt; main&lpar;&rpar; =&amp;gt; bootstrap&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;production&#39;&lt;/span&gt;&rpar;;
&lt;/code&gt;&lt;/pre&gt;
&lt;ul&gt;
&lt;li&gt;&lt;code&gt;main_development.dart&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt; main&lpar;&rpar; =&amp;gt; bootstrap&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;development&#39;&lt;/span&gt;&rpar;;
&lt;/code&gt;&lt;/pre&gt;
&lt;ul&gt;
&lt;li&gt;&lt;code&gt;main_staging.dart&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt; main&lpar;&rpar; =&amp;gt; bootstrap&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;staging&#39;&lt;/span&gt;&rpar;;
&lt;/code&gt;&lt;/pre&gt;
&lt;ul&gt;
&lt;li&gt;&lt;code&gt;bootstrap.dart&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt; bootstrap&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; env&rpar; =&amp;gt; runApp&lpar;MyApp&lpar;env: env&rpar;&rpar;;

&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;MyApp&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;extends&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;StatelessWidget&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; MyApp&lpar;{&lt;span class=&quot;hljs-keyword&quot;&gt;super&lt;/span&gt;.key, &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;.env}&rpar;;
  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; env;

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Widget build&lpar;BuildContext context&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; MaterialApp&lpar;
      debugShowCheckedModeBanner: &lt;span class=&quot;hljs-keyword&quot;&gt;false&lt;/span&gt;,
      builder: &lpar;context, child&rpar; {
        &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;env == &lt;span class=&quot;hljs-string&quot;&gt;&#39;production&#39;&lt;/span&gt;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; child!;
        &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Banner&lpar;
          message: env.toUpperCase&lpar;&rpar;,
          location: BannerLocation.topEnd,
          child: child,
        &rpar;;
      },
      theme: ThemeData&lpar;
        fontFamily: &lt;span class=&quot;hljs-string&quot;&gt;&#39;Montserrat&#39;&lt;/span&gt;,
      &rpar;,
      home: &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; HomePage&lpar;&rpar;,
    &rpar;;
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Since setting up flavors in android is pretty straightforward, we will start with it so we can test it quickly.&lt;/p&gt;
&lt;h2 id=&quot;heading-using-flavors-in-android&quot;&gt;Using flavors in Android 🤖&lt;/h2&gt;
&lt;p&gt;To add &lt;code&gt;production&lt;/code&gt;, &lt;code&gt;staging&lt;/code&gt; and &lt;code&gt;development&lt;/code&gt; flavors, let&#39;s make some changes in the app level &lt;code&gt;build.gradle&lt;/code&gt; in &lt;code&gt;android/app/build.gradle&lt;/code&gt; file.&lt;/p&gt;
&lt;p&gt;Here, let&#39;s specify a &lt;code&gt;flavorDimensions&lt;/code&gt; and a &lt;code&gt;productFlavors&lt;/code&gt; object.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-apache&quot;&gt;    &lt;span class=&quot;hljs-attribute&quot;&gt;flavorDimensions&lt;/span&gt; &#39;default&#39;
    &lt;span class=&quot;hljs-attribute&quot;&gt;productFlavors&lt;/span&gt; {
        &lt;span class=&quot;hljs-attribute&quot;&gt;production&lt;/span&gt; {
            &lt;span class=&quot;hljs-attribute&quot;&gt;dimension&lt;/span&gt; &#39;default&#39;
            &lt;span class=&quot;hljs-attribute&quot;&gt;resValue&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&quot;string&quot;&lt;/span&gt;, &lt;span class=&quot;hljs-string&quot;&gt;&quot;app_name&quot;&lt;/span&gt;, &lt;span class=&quot;hljs-string&quot;&gt;&quot;FITNESS&quot;&lt;/span&gt;
        }
        &lt;span class=&quot;hljs-attribute&quot;&gt;development&lt;/span&gt; {
            &lt;span class=&quot;hljs-attribute&quot;&gt;dimension&lt;/span&gt; &#39;default&#39;
            &lt;span class=&quot;hljs-attribute&quot;&gt;applicationIdSuffix&lt;/span&gt; &#39;.dev&#39;
            &lt;span class=&quot;hljs-attribute&quot;&gt;versionNameSuffix&lt;/span&gt; &#39;.dev&#39;
            &lt;span class=&quot;hljs-attribute&quot;&gt;resValue&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&quot;string&quot;&lt;/span&gt;, &lt;span class=&quot;hljs-string&quot;&gt;&quot;app_name&quot;&lt;/span&gt;, &lt;span class=&quot;hljs-string&quot;&gt;&quot;FITNESS.DEV&quot;&lt;/span&gt;
        }

        &lt;span class=&quot;hljs-attribute&quot;&gt;staging&lt;/span&gt; {
            &lt;span class=&quot;hljs-attribute&quot;&gt;dimension&lt;/span&gt; &#39;default&#39;
            &lt;span class=&quot;hljs-attribute&quot;&gt;applicationIdSuffix&lt;/span&gt; &#39;.stg&#39;
            &lt;span class=&quot;hljs-attribute&quot;&gt;versionNameSuffix&lt;/span&gt; &#39;.stg&#39;
            &lt;span class=&quot;hljs-attribute&quot;&gt;resValue&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&quot;string&quot;&lt;/span&gt;, &lt;span class=&quot;hljs-string&quot;&gt;&quot;app_name&quot;&lt;/span&gt;, &lt;span class=&quot;hljs-string&quot;&gt;&quot;FITNESS.STG&quot;&lt;/span&gt;
        }
    }
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;The &lt;code&gt;flavorDimensions&lt;/code&gt; line defines the name of the flavor dimension, which is &lt;code&gt;default&lt;/code&gt; in this case. Each flavor is defined within the &lt;code&gt;productFlavors&lt;/code&gt; block. The &lt;code&gt;production&lt;/code&gt; flavor is the base flavor of the app.&lt;/p&gt;
&lt;p&gt;The &lt;code&gt;development&lt;/code&gt; and &lt;code&gt;staging&lt;/code&gt; flavors are similar, but with some differences. The &lt;code&gt;applicationIdSuffix&lt;/code&gt; and &lt;code&gt;versionNameSuffix&lt;/code&gt; lines add the &lt;code&gt;.dev&lt;/code&gt; or &lt;code&gt;.stg&lt;/code&gt; suffix to the application ID and version name, respectively. The &lt;code&gt;resValue&lt;/code&gt; line sets the name of the app to &lt;code&gt;FITNESS.DEV&lt;/code&gt; or &lt;code&gt;FITNESS.STG&lt;/code&gt;, respectively.&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;NOTE: Don&#39;t forget to add &lt;code&gt;android:label=&quot;@string/app_name&quot;&lt;/code&gt; to the &lt;code&gt;application&lt;/code&gt; tag in &lt;code&gt;AndroidManifest.xml&lt;/code&gt; file.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;hr /&gt;
&lt;h2 id=&quot;heading-lets-test&quot;&gt;Let&#39;s Test 🧪&lt;/h2&gt;
&lt;p&gt;Now, we can run the app using the following commands.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;flutter run --flavor development --target lib/main_development.dart
flutter run --flavor staging --target lib/main_staging.dart
flutter run --flavor production --target lib/production.dart
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Once done, you should have three different apps with different names, versions, and bundle identifiers.&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1675685697832/2b172457-0674-4066-89dc-cb6c1755d472.png&quot; alt=&quot;android flavors working&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;hr /&gt;
&lt;h2 id=&quot;heading-ios-schemas&quot;&gt;iOS Schemas&lt;/h2&gt;
&lt;p&gt;We will now be creating schemas for each flavor in Xcode. We already have a &lt;code&gt;Runner&lt;/code&gt; schema, which is the default schema. We will rename it to &lt;code&gt;production&lt;/code&gt; and create two new schemas, &lt;code&gt;development&lt;/code&gt; and &lt;code&gt;staging&lt;/code&gt;.&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;Open the ios folder in Xcode.&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;open ios/Runner.xcworkspace
&lt;/code&gt;&lt;/pre&gt;
&lt;ul&gt;
&lt;li&gt;Let&#39;s make some changes to our configuration.&lt;/li&gt;
&lt;/ul&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1675685767350/9193336b-1b16-4e9e-acde-158c3d3b3f1c.png&quot; alt=&quot;config-initial&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;In Project Runner, rename &lt;code&gt;Debug&lt;/code&gt;, &lt;code&gt;Release&lt;/code&gt;, and &lt;code&gt;Profile&lt;/code&gt; adding &lt;code&gt;-production&lt;/code&gt; suffixes to each.&lt;/li&gt;
&lt;/ul&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1675685793314/58f491d2-f3dd-4795-bf5f-2f5229f1f616.png&quot; alt=&quot;config-production&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;Once done, we will now create these 3 files for each &lt;code&gt;staging&lt;/code&gt; and &lt;code&gt;development&lt;/code&gt; as well. You can use duplicate.&lt;/li&gt;
&lt;/ul&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1675685814141/8854c543-13a8-4f36-b679-5f27b2dfcc3e.png&quot; alt=&quot;config-duplicate-button&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;Once done, we will have 9 configurations, 3 for each flavor.&lt;/li&gt;
&lt;/ul&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1675685828283/2c1b695b-5aa4-40e1-a916-3c585dbb1796.png&quot; alt=&quot;configuration&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;Select the Runner scheme and click the Manage Schemes button.&lt;/li&gt;
&lt;/ul&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1675685852673/f2be4c69-88ec-4bfa-aedd-257b327bd970.png&quot; alt=&quot;manage-scheme-button&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;Once, there rename &lt;code&gt;Runner&lt;/code&gt; scheme to &lt;code&gt;production&lt;/code&gt;, and duplicate &lt;code&gt;production&lt;/code&gt; to two new &lt;code&gt;development&lt;/code&gt; and &lt;code&gt;staging&lt;/code&gt;.&lt;/li&gt;
&lt;/ul&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1675685906070/131c1a60-3d98-411e-9b86-5db4fba1d6b9.png&quot; alt=&quot;duplicate-button&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;Make sure to add the correct configuration while duplicating.&lt;/li&gt;
&lt;/ul&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1675685935904/cf4fe682-11b5-458c-88aa-50cd3360cf29.jpeg&quot; alt=&quot;staging-scheme&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;p&gt;Similarly, create a &lt;code&gt;development&lt;/code&gt; scheme with the correct configuration.&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1675685963735/70050902-c61c-4920-b9bd-71bd11905135.png&quot; alt=&quot;development-scheme&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;p&gt;Once you are done with schemes, you will have something like this.&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1675685978858/81dc9e70-2888-47f3-b86a-2cb5c37d8b74.png&quot; alt=&quot;final-schemes&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;&lt;strong&gt;NOTE&lt;/strong&gt;: Make sure all three schemes have correct configuration, don&#39;t forget to recheck &lt;code&gt;production&lt;/code&gt; scheme configuration.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;ul&gt;
&lt;li&gt;Now, let&#39;s add the bundle identifier for each configuration. In &lt;code&gt;Target&lt;/code&gt;-&amp;gt; &lt;code&gt;Runner&lt;/code&gt;, click &lt;code&gt;Build Settings&lt;/code&gt; and search for &lt;code&gt;Product Bundle Identifier&lt;/code&gt;.&lt;/li&gt;
&lt;/ul&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1675685992723/f8b3b271-b6f6-49ef-93c7-14977e69f8ef.jpeg&quot; alt=&quot;bundle-identifier&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;Add the suffix as required.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1675686084412/1a9e836a-13fb-408b-9504-5032e7bf78b7.png&quot; alt=&quot;final-bundle-ids&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;p&gt;Once you are done, you will have something like this.&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;Finally, we will create a new &lt;code&gt;User Defined Variable&lt;/code&gt; called &lt;code&gt;APP_DISPLAY_NAME&lt;/code&gt; which will have a different name for each configuration.&lt;/li&gt;
&lt;/ul&gt;
&lt;p&gt;In same &lt;code&gt;Target&lt;/code&gt; -&amp;gt; &lt;code&gt;Runner&lt;/code&gt; -&amp;gt; &lt;code&gt;Build Settings&lt;/code&gt;, click on the &lt;code&gt;+&lt;/code&gt; button, and create a new user-defined variable.&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1675686104706/8d88f4d4-2ccb-4723-bd53-12c030d5b47f.png&quot; alt=&quot;user_defined_variable&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1675686120917/c0d571c2-5b53-49d0-86a3-a1bd0cdfd43f.png&quot; alt=&quot;APP_DISPLAY_NAME&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;p&gt;Once, you are done with the user-defined variable, you need to change the &lt;code&gt;Info.plist&lt;/code&gt; to use this variable.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-xml&quot;&gt;&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;CFBundleName&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;$descriptionlpar;APP_DISPLAY_NAME&rpar;&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;CFBundleDisplayName&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;key&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;$descriptionlpar;APP_DISPLAY_NAME&rpar;&lt;span class=&quot;hljs-tag&quot;&gt;&amp;lt;/&lt;span class=&quot;hljs-name&quot;&gt;string&lt;/span&gt;&amp;gt;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;hr /&gt;
&lt;h2 id=&quot;heading-lets-test-1&quot;&gt;Let&#39;s Test 🧪&lt;/h2&gt;
&lt;p&gt;Similar to android, we can test iOS by running the following commands.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;flutter run --flavor development --target lib/main_development.dart
flutter run --flavor staging --target lib/main_staging.dart
flutter run --flavor production --target lib/production.dart
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1675696750786/806598ad-33cc-4e3b-8c85-df0e578cf60b.png&quot; alt class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;hr /&gt;
&lt;h2 id=&quot;heading-app-icons-for-android-and-ios&quot;&gt;App Icons for Android and iOS 🎨&lt;/h2&gt;
&lt;blockquote&gt;
&lt;p&gt;🎆 Let&#39;s make it look pretty!&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;Now, let&#39;s have different icons based on the flavors. We will have 3 different icons for each flavor.&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1675686180483/ae0ed32b-1b2e-43c9-8d23-32194e23ad45.png&quot; alt=&quot;launch-icons&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;p&gt;We will use &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/flutter_launcher_icons&quot;&gt;&lt;code&gt;flutter_launcher_icons&lt;/code&gt;&lt;/a&gt; to generate the launch icons. Install it as a dev dependency.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;flutter pub add flutter_launcher_icons --dev
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Once this is done, we will create &lt;code&gt;flutter_launcher_icons-&amp;lt;flavor&amp;gt;.yaml&lt;/code&gt; files for each flavor.&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;&lt;code&gt;flutter_launcher_icons-development.yaml&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-yaml&quot;&gt;&lt;span class=&quot;hljs-attr&quot;&gt;flutter_icons:&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;android:&lt;/span&gt; &lt;span class=&quot;hljs-literal&quot;&gt;true&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;ios:&lt;/span&gt; &lt;span class=&quot;hljs-literal&quot;&gt;true&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;remove_alpha_ios:&lt;/span&gt; &lt;span class=&quot;hljs-literal&quot;&gt;true&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;image_path:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&quot;assets/icons/dev-icon.png&quot;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;ul&gt;
&lt;li&gt;&lt;code&gt;flutter_launcher_icons-staging.yaml&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-yaml&quot;&gt;&lt;span class=&quot;hljs-attr&quot;&gt;flutter_icons:&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;android:&lt;/span&gt; &lt;span class=&quot;hljs-literal&quot;&gt;true&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;ios:&lt;/span&gt; &lt;span class=&quot;hljs-literal&quot;&gt;true&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;remove_alpha_ios:&lt;/span&gt; &lt;span class=&quot;hljs-literal&quot;&gt;true&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;image_path:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&quot;assets/icons/stg-icon.png&quot;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;ul&gt;
&lt;li&gt;&lt;code&gt;flutter_launcher_icons-production.yaml&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-yaml&quot;&gt;&lt;span class=&quot;hljs-attr&quot;&gt;flutter_icons:&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;android:&lt;/span&gt; &lt;span class=&quot;hljs-literal&quot;&gt;true&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;ios:&lt;/span&gt; &lt;span class=&quot;hljs-literal&quot;&gt;true&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;remove_alpha_ios:&lt;/span&gt; &lt;span class=&quot;hljs-literal&quot;&gt;true&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;image_path:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&quot;assets/icons/prod-icon.png&quot;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Now to generate the launch icons we need to run&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;flutter pub run flutter_launcher_icons:main -f flutter_launcher_icons-*
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;This will generate all the icons.&lt;/p&gt;
&lt;p&gt;Finally, we will set the icons to be dynamic in Xcode.&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;In &lt;code&gt;Runner&lt;/code&gt; -&amp;gt; &lt;code&gt;Assets.xcassets&lt;/code&gt; we can see that we have all the required icons. We can remove the &lt;code&gt;AppIcon&lt;/code&gt; , which is unused.&lt;/li&gt;
&lt;/ul&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1675686204624/7b92cc30-14d2-46b1-8454-575049fa104d.png&quot; alt=&quot;app-icons&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;Now, in &lt;code&gt;Target&lt;/code&gt;-&amp;gt; &lt;code&gt;Runner&lt;/code&gt; -&amp;gt; &lt;code&gt;Build Settings&lt;/code&gt;, search for &lt;code&gt;primary app icon&lt;/code&gt;.&lt;/li&gt;
&lt;/ul&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1675686216871/01802647-e968-4bdb-9cfa-0cec4f07e1fa.png&quot; alt=&quot;app-icon-change&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;Now, set the corresponding suffix to each one.&lt;/li&gt;
&lt;/ul&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1675686232157/77259f1f-7b3f-4bef-93c1-0b488881e650.png&quot; alt=&quot;final-app-icon&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;hr /&gt;
&lt;h2 id=&quot;heading-final-result&quot;&gt;Final Result 🎉&lt;/h2&gt;
&lt;p&gt;Now, if we run the app, for all the flavors, we will have different icons, names, versions, and bundle identifiers.&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;NOTE: Make sure to uninstall the previous builds before running the app.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1675686316246/d5f7c534-ee4a-49dc-a990-bb1957ffbc8c.png&quot; alt=&quot;final-preview&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;hr /&gt;
&lt;h1 id=&quot;heading-bonus&quot;&gt;🎊 Bonus&lt;/h1&gt;
&lt;p&gt;For easy usage, we can create some launch configs for &lt;code&gt;Visual Studio Code&lt;/code&gt; and &lt;code&gt;Android Studio&lt;/code&gt;.&lt;/p&gt;
&lt;h2 id=&quot;heading-for-visual-studio-code&quot;&gt;For Visual Studio Code&lt;/h2&gt;
&lt;p&gt;Create a new file in &lt;code&gt;.vscode/launch.json&lt;/code&gt; with the following content.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-json&quot;&gt;{
  &lt;span class=&quot;hljs-attr&quot;&gt;&quot;version&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;0.2.0&quot;&lt;/span&gt;,
  &lt;span class=&quot;hljs-attr&quot;&gt;&quot;configurations&quot;&lt;/span&gt;: [
    {
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;name&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;DEV | DEBUG&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;request&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;launch&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;type&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;dart&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;program&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;lib/main_development.dart&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;args&quot;&lt;/span&gt;: [
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;--flavor&quot;&lt;/span&gt;,
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;development&quot;&lt;/span&gt;,
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;--target&quot;&lt;/span&gt;,
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;lib/main_development.dart&quot;&lt;/span&gt;
      ],
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;flutterMode&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;debug&quot;&lt;/span&gt;
    },
    {
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;name&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;DEV | RELEASE&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;request&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;launch&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;type&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;dart&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;program&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;lib/main_development.dart&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;args&quot;&lt;/span&gt;: [
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;--flavor&quot;&lt;/span&gt;,
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;development&quot;&lt;/span&gt;,
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;--target&quot;&lt;/span&gt;,
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;lib/main_development.dart&quot;&lt;/span&gt;
      ],
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;flutterMode&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;release&quot;&lt;/span&gt;
    },
    {
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;name&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;DEV | PROFILE&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;request&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;launch&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;type&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;dart&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;program&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;lib/main_development.dart&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;args&quot;&lt;/span&gt;: [
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;--flavor&quot;&lt;/span&gt;,
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;development&quot;&lt;/span&gt;,
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;--target&quot;&lt;/span&gt;,
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;lib/main_development.dart&quot;&lt;/span&gt;
      ],
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;flutterMode&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;profile&quot;&lt;/span&gt;
    },
    {
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;name&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;STG | DEBUG&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;request&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;launch&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;type&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;dart&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;program&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;lib/main_staging.dart&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;args&quot;&lt;/span&gt;: [
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;--flavor&quot;&lt;/span&gt;,
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;staging&quot;&lt;/span&gt;,
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;--target&quot;&lt;/span&gt;,
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;lib/main_staging.dart&quot;&lt;/span&gt;
      ],
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;flutterMode&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;debug&quot;&lt;/span&gt;
    },
    {
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;name&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;STG | RELEASE&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;request&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;launch&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;type&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;dart&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;program&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;lib/main_staging.dart&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;args&quot;&lt;/span&gt;: [
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;--flavor&quot;&lt;/span&gt;,
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;staging&quot;&lt;/span&gt;,
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;--target&quot;&lt;/span&gt;,
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;lib/main_staging.dart&quot;&lt;/span&gt;
      ],
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;flutterMode&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;release&quot;&lt;/span&gt;
    },
    {
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;name&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;STG | PROFILE&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;request&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;launch&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;type&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;dart&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;program&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;lib/main_staging.dart&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;args&quot;&lt;/span&gt;: [
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;--flavor&quot;&lt;/span&gt;,
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;staging&quot;&lt;/span&gt;,
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;--target&quot;&lt;/span&gt;,
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;lib/main_staging.dart&quot;&lt;/span&gt;
      ],
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;flutterMode&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;profile&quot;&lt;/span&gt;
    },
    {
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;name&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;PROD | DEBUG&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;request&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;launch&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;type&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;dart&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;program&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;lib/main_production.dart&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;args&quot;&lt;/span&gt;: [
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;--flavor&quot;&lt;/span&gt;,
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;production&quot;&lt;/span&gt;,
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;--target&quot;&lt;/span&gt;,
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;lib/main_production.dart&quot;&lt;/span&gt;
      ],
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;flutterMode&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;debug&quot;&lt;/span&gt;
    },
    {
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;name&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;PROD | RELEASE&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;request&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;launch&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;type&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;dart&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;program&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;lib/main_production.dart&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;args&quot;&lt;/span&gt;: [
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;--flavor&quot;&lt;/span&gt;,
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;production&quot;&lt;/span&gt;,
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;--target&quot;&lt;/span&gt;,
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;lib/main_production.dart&quot;&lt;/span&gt;
      ],
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;flutterMode&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;release&quot;&lt;/span&gt;
    },
    {
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;name&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;PROD | PROFILE&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;request&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;launch&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;type&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;dart&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;program&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;lib/main_production.dart&quot;&lt;/span&gt;,
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;args&quot;&lt;/span&gt;: [
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;--flavor&quot;&lt;/span&gt;,
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;production&quot;&lt;/span&gt;,
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;--target&quot;&lt;/span&gt;,
        &lt;span class=&quot;hljs-string&quot;&gt;&quot;lib/main_production.dart&quot;&lt;/span&gt;
      ],
      &lt;span class=&quot;hljs-attr&quot;&gt;&quot;flutterMode&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;profile&quot;&lt;/span&gt;
    },
  ]
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;This will create the launch config with all the args.&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1675686338649/11fa8f57-66cb-4452-8ba2-d7f8dfa74b98.png&quot; alt=&quot;vs-code-launch-settings&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;h2 id=&quot;heading-for-android-studio&quot;&gt;For Android Studio&lt;/h2&gt;
&lt;p&gt;For Android Studio, you can get the &lt;a target=&quot;_blank&quot; href=&quot;https://github.com/saileshbro/fitness_app_clone/tree/master/.idea/runConfigurations&quot;&gt;configuration files from here&lt;/a&gt;, for all the configs.&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1675686357238/a3b68a58-d26d-4eb6-bd59-c0ce6d6a42a5.png&quot; alt=&quot;android-studio-launch-settings&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;hr /&gt;
&lt;p&gt;🎉 Congrats! We&#39;ve made it to the end of our exploration of Flutter Flavors! 🚀 We&#39;ve successfully learned how to add different flavors to our flutter application, each with its own unique configurations and build targets.&lt;/p&gt;
&lt;p&gt;It&#39;s just the tip of the iceberg when it comes to the use cases of flavors in Flutter. For instance, you can inject dependencies based on the flavor you are using, which can entirely change the behavior of your app. The possibilities are endless!&lt;/p&gt;
&lt;p&gt;As always, you can refer back to the Github repository for this tutorial at &lt;a target=&quot;_blank&quot; href=&quot;https://github.com/saileshbro/fitness_app_clone&quot;&gt;https://github.com/saileshbro/fitness_app_clone&lt;/a&gt; if you need any help. Don&#39;t forget to give it a  and help spread the word about this amazing project. If you get stuck or need assistance, feel free to submit an issue or contribute a pull request.&lt;/p&gt;
&lt;p&gt;Thank you for joining me on this journey; let&#39;s create even more amazing applications together. Have fun coding! 💻👨💻&lt;/p&gt;
&lt;hr /&gt;
&lt;h2 id=&quot;heading-references&quot;&gt;References&lt;/h2&gt;
&lt;ul&gt;
&lt;li&gt;&lt;p&gt;&lt;a target=&quot;_blank&quot; href=&quot;https://www.youtube.com/watch?v=Vhm1Cv2uPko&quot;&gt;Flutter Flavors, App Icons, and Firebase Tutorial - Marcus Ng&lt;/a&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;a target=&quot;_blank&quot; href=&quot;https://docs.flutter.dev/deployment/flavors&quot;&gt;Creating flavors for Flutter&lt;/a&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;a target=&quot;_blank&quot; href=&quot;https://developer.android.com/studio/build/build-variants#flavor-dimensions&quot;&gt;Android Developers - Build Variants: Flavor Dimensions&lt;/a&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;/ul&gt;
 

 - 💯[🚀 Building a Fullstack App with dart_frog and Flutter in a Monorepo - Part 6](https://saileshdahal.com.np/building-a-fullstack-app-with-dartfrog-and-flutter-in-a-monorepo-part-6) 
 - &lt;p&gt;In earlier sections of this tutorial series, we covered the fundamental stages for creating a to-do application with Flutter and Dart.&lt;/p&gt;
&lt;p&gt;We&#39;ve covered everything from bootstrapping an empty &lt;a target=&quot;_blank&quot; href=&quot;https://flutter.dev&quot;&gt;Flutter&lt;/a&gt; project, importing necessary dependencies, setting up the folder structure, integrating the frontend with the backend, and implementing the Todo data sources, repositories, and view models.&lt;/p&gt;
&lt;p&gt;In this part, we&#39;ll show you how to utilize dart frog to establish user authentication with &lt;a target=&quot;_blank&quot; href=&quot;https://jwt.io&quot;&gt;JSON Web Tokens &lpar;JWT&rpar;&lt;/a&gt;. By the end of this article, we will be able to:&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;&lt;p&gt;Implement user login and register.&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;Create &lt;code&gt;User&lt;/code&gt; model.&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;Create and implement &lt;code&gt;UserRepository&lt;/code&gt; and &lt;code&gt;UserDataSource&lt;/code&gt;.&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;Handle &lt;code&gt;UnauthorizedException&lt;/code&gt;.&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;Create a new authorization middleware.&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;Implement user authentication using &lt;a target=&quot;_blank&quot; href=&quot;https://jwt.io&quot;&gt;JWT&lt;/a&gt;.&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;Secure routes with &lt;code&gt;Authorization&lt;/code&gt; headers.&lt;/p&gt;
&lt;/li&gt;
&lt;/ul&gt;
&lt;p&gt;Don&#39;t forget to check out the &lt;a target=&quot;_blank&quot; href=&quot;https://github.com/saileshbro/full_stack_todo_dart&quot;&gt;GitHub&lt;/a&gt; repo for this article if you need any assistance along the way.&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;Let&#39;s get started 🚀&lt;/p&gt;
&lt;/blockquote&gt;
&lt;hr /&gt;
&lt;h1 id=&quot;heading-overview&quot;&gt;Overview 🔍&lt;/h1&gt;
&lt;blockquote&gt;
&lt;p&gt;👀 Get a sneak peek of what&#39;s to come 🔮&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;When we&#39;re done, we should have an app that supports the following requests:&lt;/p&gt;
&lt;ol&gt;
&lt;li&gt;&lt;code&gt;/todos*&lt;/code&gt; - Guard all to-do routes with &lt;code&gt;Authorization&lt;/code&gt; header.&lt;/li&gt;
&lt;/ol&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;curl -s -L -X POST &lt;span class=&quot;hljs-string&quot;&gt;&#39;http://localhost:8080/todos&#39;&lt;/span&gt; -H &lt;span class=&quot;hljs-string&quot;&gt;&#39;Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY5ZWFkZTg3LWRhNWUtNDRjZC1iNTRlLTQ3NGE4NWQ4ZGVlNCIsIm5hbWUiOiJTYWlsZXNoIERhaGFsIiwiZW1haWwiOiJzYWlsZXNoYnJvQGdtYWlsLmNvbSIsImNyZWF0ZWRfYXQiOiIyMDIzLTAxLTIzVDIyOjU0OjM4Ljg2NDkxMloiLCJwYXNzd29yZCI6IiQyYSQxMCR6VjBTZlI3cUpHOHlCelJWWThtNkRlMWo0UUtHL2VRdXl6NzduQ1lBL1luZENtb1ZSbzB0RyIsImlhdCI6MTY3NDQ5Mzc3OX0.W36mHXKFrxZDhz0Hrxt0Cmrz3WNVexiAZe2KAjrWMaE&#39;&lt;/span&gt; -H &lt;span class=&quot;hljs-string&quot;&gt;&#39;Content-Type: application/json&#39;&lt;/span&gt; --data-raw &lt;span class=&quot;hljs-string&quot;&gt;&#39;{
    &quot;title&quot;:&quot;this is a title asdf&quot;,
    &quot;description&quot;:&quot;Not so great description asdf&quot;
}&#39;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;ol&gt;
&lt;li&gt;&lt;code&gt;/users/login&lt;/code&gt; - Login user&lt;/li&gt;
&lt;/ol&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;curl -s -L -X POST &lt;span class=&quot;hljs-string&quot;&gt;&#39;http://localhost:8080/users/login&#39;&lt;/span&gt; -H &lt;span class=&quot;hljs-string&quot;&gt;&#39;Content-Type: application/json&#39;&lt;/span&gt; --data-raw &lt;span class=&quot;hljs-string&quot;&gt;&#39;{
    &quot;email&quot;:&quot;saileshbro@gmail.com&quot;,
    &quot;password&quot;:&quot;6aMj@UBByu&quot;
}&#39;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;ol&gt;
&lt;li&gt;&lt;code&gt;/users/signup&lt;/code&gt; - Register new user&lt;/li&gt;
&lt;/ol&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;curl -s -L -X POST &lt;span class=&quot;hljs-string&quot;&gt;&#39;http://localhost:8080/users/signup&#39;&lt;/span&gt; -H &lt;span class=&quot;hljs-string&quot;&gt;&#39;Content-Type: application/json&#39;&lt;/span&gt; --data-raw &lt;span class=&quot;hljs-string&quot;&gt;&#39;{
    &quot;email&quot;:&quot;saileshbro@gmail.com&quot;,
    &quot;name&quot;:&quot;Sailesh Dahal&quot;,
    &quot;password&quot;:&quot;6aMj@UBByu%7BzN^C9tMe#Te4b!4cJrXwwFi#HgKrQ&amp;amp;g&amp;amp;&quot;
}&#39;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;hr /&gt;
&lt;h1 id=&quot;heading-updating-database&quot;&gt;Updating Database 🛠&lt;/h1&gt;
&lt;blockquote&gt;
&lt;p&gt;💾 Upgrading our database to its full potential 🚀&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;To begin, we will create a new table called &lt;code&gt;users&lt;/code&gt; and add a &lt;a target=&quot;_blank&quot; href=&quot;https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-foreign-key/&quot;&gt;&lt;code&gt;foreign key&lt;/code&gt;&lt;/a&gt; to our current &lt;code&gt;todos&lt;/code&gt; table. This ensures that each to-do item is associated with a single user, and that data is accessible only to that person.&lt;/p&gt;
&lt;h2 id=&quot;heading-create-users-table&quot;&gt;Create &lt;code&gt;users&lt;/code&gt; table&lt;/h2&gt;
&lt;p&gt;We will create a new &lt;code&gt;users&lt;/code&gt; table with the following columns.&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;&lt;p&gt;&lt;code&gt;id&lt;/code&gt; : unique &lt;code&gt;uuid&lt;/code&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;code&gt;name&lt;/code&gt; : name of the user&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;code&gt;email&lt;/code&gt; : email of the user&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;code&gt;password&lt;/code&gt; : hashed password of the user&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;code&gt;created_at&lt;/code&gt; : timestamp of when the user was created&lt;/p&gt;
&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-sql&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;CREATE&lt;/span&gt; EXTENSION &lt;span class=&quot;hljs-keyword&quot;&gt;IF&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;NOT&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;EXISTS&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&quot;uuid-ossp&quot;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;CREATE&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;TABLE&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;users&lt;/span&gt;&lpar;
    &lt;span class=&quot;hljs-keyword&quot;&gt;id&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;uuid&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;DEFAULT&lt;/span&gt; uuid_generate_v4&lpar;&rpar; PRIMARY &lt;span class=&quot;hljs-keyword&quot;&gt;KEY&lt;/span&gt;,
    &lt;span class=&quot;hljs-keyword&quot;&gt;name&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;VARCHAR&lt;/span&gt;&lpar;&lt;span class=&quot;hljs-number&quot;&gt;255&lt;/span&gt;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;NOT&lt;/span&gt; &lt;span class=&quot;hljs-literal&quot;&gt;NULL&lt;/span&gt;,
    email &lt;span class=&quot;hljs-built_in&quot;&gt;TEXT&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;NOT&lt;/span&gt; &lt;span class=&quot;hljs-literal&quot;&gt;NULL&lt;/span&gt;,
      &lt;span class=&quot;hljs-keyword&quot;&gt;password&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;TEXT&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;NOT&lt;/span&gt; &lt;span class=&quot;hljs-literal&quot;&gt;NULL&lt;/span&gt;,
    created_at &lt;span class=&quot;hljs-built_in&quot;&gt;timestamp&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;default&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;current_timestamp&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;NOT&lt;/span&gt; &lt;span class=&quot;hljs-literal&quot;&gt;NULL&lt;/span&gt;
&rpar;;
&lt;/code&gt;&lt;/pre&gt;
&lt;blockquote&gt;
&lt;p&gt;The &lt;a target=&quot;_blank&quot; href=&quot;https://www.postgresql.org/docs/10/uuid-ossp.html&quot;&gt;&lt;code&gt;uuid-ossp&lt;/code&gt;&lt;/a&gt; extension is used to generate unique IDs for each user.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;h2 id=&quot;heading-updating-todos-table&quot;&gt;Updating &lt;code&gt;todos&lt;/code&gt; table&lt;/h2&gt;
&lt;p&gt;We will update the &lt;code&gt;todos&lt;/code&gt; table to include a foreign key to the &lt;code&gt;users&lt;/code&gt; table.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-sql&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;TRUNCATE&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;TABLE&lt;/span&gt; todos;
&lt;span class=&quot;hljs-keyword&quot;&gt;ALTER&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;TABLE&lt;/span&gt; todos
    &lt;span class=&quot;hljs-keyword&quot;&gt;ADD&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;COLUMN&lt;/span&gt; user_id &lt;span class=&quot;hljs-keyword&quot;&gt;uuid&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;NOT&lt;/span&gt; &lt;span class=&quot;hljs-literal&quot;&gt;NULL&lt;/span&gt;,
    &lt;span class=&quot;hljs-keyword&quot;&gt;ADD&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;CONSTRAINT&lt;/span&gt; constraint_fk
        &lt;span class=&quot;hljs-keyword&quot;&gt;FOREIGN&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;KEY&lt;/span&gt; &lpar;user_id&rpar;
            &lt;span class=&quot;hljs-keyword&quot;&gt;REFERENCES&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;users&lt;/span&gt; &lpar;&lt;span class=&quot;hljs-keyword&quot;&gt;id&lt;/span&gt;&rpar;
            &lt;span class=&quot;hljs-keyword&quot;&gt;ON&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;DELETE&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;CASCADE&lt;/span&gt;;
&lt;/code&gt;&lt;/pre&gt;
&lt;blockquote&gt;
&lt;p&gt;The &lt;a target=&quot;_blank&quot; href=&quot;https://www.commandprompt.com/education/postgresql-delete-cascade-with-examples/&quot;&gt;&lt;code&gt;ON DELETE CASCADE&lt;/code&gt;&lt;/a&gt; clause ensures that when a user is deleted, all their to-do items will be deleted.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;Once we are done with the changes, we can proceed to create a user schema in our &lt;code&gt;models&lt;/code&gt; package.&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;More about &lt;a target=&quot;_blank&quot; href=&quot;https://www.postgresql.org/docs/current/ddl-constraints.html&quot;&gt;&lt;code&gt;CONSTRAINTS&lt;/code&gt;&lt;/a&gt; here.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;hr /&gt;
&lt;h1 id=&quot;heading-create-user-model&quot;&gt;Create &lt;code&gt;User&lt;/code&gt; model&lt;/h1&gt;
&lt;blockquote&gt;
&lt;p&gt;🧑💼 Defining our User Model 📝&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;We will start by creating a &lt;code&gt;UserId&lt;/code&gt; in our &lt;code&gt;typedefs&lt;/code&gt; package.&lt;/p&gt;
&lt;h2 id=&quot;heading-create-userid-type&quot;&gt;Create &lt;code&gt;UserId&lt;/code&gt; type&lt;/h2&gt;
&lt;p&gt;In &lt;code&gt;typedefs&lt;/code&gt; package, we will make some changes. We will rename the older &lt;code&gt;src/typedefs.dart&lt;/code&gt; file to &lt;code&gt;src/todo_types.dart&lt;/code&gt; and create a new &lt;code&gt;src/user_types.dart&lt;/code&gt; file.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;typedef&lt;/span&gt; UserId = &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;;
&lt;/code&gt;&lt;/pre&gt;
&lt;blockquote&gt;
&lt;p&gt;💡 Make sure to update the exports.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;library&lt;/span&gt; typedefs;

&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;src/todo_types.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;src/user_types.dart&#39;&lt;/span&gt;;
&lt;/code&gt;&lt;/pre&gt;
&lt;h2 id=&quot;heading-update-folder-structure&quot;&gt;Update folder structure&lt;/h2&gt;
&lt;p&gt;In &lt;code&gt;models&lt;/code&gt; package, we will create a new &lt;code&gt;user.dart&lt;/code&gt; file. Since we are creating models for a different feature, we will mode the todo specific models to a new &lt;code&gt;todo&lt;/code&gt; folder.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-apache&quot;&gt;.
 &lt;span class=&quot;hljs-attribute&quot;&gt;create_todo_dto&lt;/span&gt;
    &lt;span class=&quot;hljs-attribute&quot;&gt;create_todo_dto&lt;/span&gt;.dart
 &lt;span class=&quot;hljs-attribute&quot;&gt;todo&lt;/span&gt;.dart
 &lt;span class=&quot;hljs-attribute&quot;&gt;update_todo_dto&lt;/span&gt;
     &lt;span class=&quot;hljs-attribute&quot;&gt;update_todo_dto&lt;/span&gt;.dart
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Also, make sure to export &lt;code&gt;create_todo_dto&lt;/code&gt; and &lt;code&gt;update_todo_dto&lt;/code&gt; from &lt;code&gt;todo.dart&lt;/code&gt;&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:freezed_annotation/freezed_annotation.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:models/src/serializers/date_time_converter.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:typedefs/typedefs.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;./create_todo_dto/create_todo_dto.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;./update_todo_dto/update_todo_dto.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;part&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;todo.freezed.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;part&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;todo.g.dart&#39;&lt;/span&gt;;
&lt;/code&gt;&lt;/pre&gt;
&lt;h2 id=&quot;heading-create-user-model-1&quot;&gt;Create &lt;code&gt;User&lt;/code&gt; model&lt;/h2&gt;
&lt;p&gt;Now, we will create a &lt;code&gt;User&lt;/code&gt; model in &lt;code&gt;src/user/user.dart&lt;/code&gt; file.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:freezed_annotation/freezed_annotation.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:models/src/serializers/date_time_converter.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:typedefs/typedefs.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;part&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;user.freezed.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;part&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;user.g.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-meta&quot;&gt;@freezed&lt;/span&gt;
&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;User&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;with&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;_&lt;/span&gt;$descriptionlt;span class=&quot;hljs-title&quot;&gt;User&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;factory&lt;/span&gt; User&lpar;{
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; UserId id,
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; name,
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; email,
    &lt;span class=&quot;hljs-meta&quot;&gt;@DateTimeConverter&lt;/span&gt;&lpar;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;DateTime&lt;/span&gt; createdAt,
    &lt;span class=&quot;hljs-meta&quot;&gt;@Default&lt;/span&gt;&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;&#39;&lt;/span&gt;&rpar; &lt;span class=&quot;hljs-meta&quot;&gt;@JsonKey&lt;/span&gt;&lpar;includeToJson: &lt;span class=&quot;hljs-keyword&quot;&gt;false&lt;/span&gt;&rpar; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; password,
  }&rpar; = _User;

  &lt;span class=&quot;hljs-keyword&quot;&gt;factory&lt;/span&gt; User.fromJson&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;dynamic&lt;/span&gt;&amp;gt; json&rpar; =&amp;gt; _$UserFromJson&lpar;json&rpar;;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;blockquote&gt;
&lt;p&gt;We are ignoring the &lt;code&gt;password&lt;/code&gt; field when serializing the model to JSON. This is because we don&#39;t want to send the password to the client.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;Similarly, we will create &lt;code&gt;CreateUserDto&lt;/code&gt; and &lt;code&gt;LoginUserDto&lt;/code&gt; for creating and logging in users.&lt;/p&gt;
&lt;p&gt;In &lt;code&gt;src/user/create_user_dto/create_user_dto.dart&lt;/code&gt; file,&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:either_dart/either.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:exceptions/exceptions.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:failures/failures.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:freezed_annotation/freezed_annotation.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;part&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;create_user_dto.freezed.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;part&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;create_user_dto.g.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-meta&quot;&gt;@freezed&lt;/span&gt;
&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;CreateUserDto&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;with&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;_&lt;/span&gt;$descriptionlt;span class=&quot;hljs-title&quot;&gt;CreateUserDto&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;factory&lt;/span&gt; CreateUserDto&lpar;{
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; name,
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; email,
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; password,
  }&rpar; = _CreateUserDto;

  &lt;span class=&quot;hljs-keyword&quot;&gt;factory&lt;/span&gt; CreateUserDto.fromJson&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;dynamic&lt;/span&gt;&amp;gt; json&rpar; =&amp;gt;
      _$CreateUserDtoFromJson&lpar;json&rpar;;

  &lt;span class=&quot;hljs-keyword&quot;&gt;static&lt;/span&gt; Either&amp;lt;ValidationFailure, CreateUserDto&amp;gt; validated&lpar;
    &lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;dynamic&lt;/span&gt;&amp;gt; json,
  &rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;try&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; errors = &amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;&amp;gt;&amp;gt;{};
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; name = json[&lt;span class=&quot;hljs-string&quot;&gt;&#39;name&#39;&lt;/span&gt;] &lt;span class=&quot;hljs-keyword&quot;&gt;as&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String?&lt;/span&gt; ?? &lt;span class=&quot;hljs-string&quot;&gt;&#39;&#39;&lt;/span&gt;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; email = json[&lt;span class=&quot;hljs-string&quot;&gt;&#39;email&#39;&lt;/span&gt;] &lt;span class=&quot;hljs-keyword&quot;&gt;as&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String?&lt;/span&gt; ?? &lt;span class=&quot;hljs-string&quot;&gt;&#39;&#39;&lt;/span&gt;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; password = json[&lt;span class=&quot;hljs-string&quot;&gt;&#39;password&#39;&lt;/span&gt;] &lt;span class=&quot;hljs-keyword&quot;&gt;as&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String?&lt;/span&gt; ?? &lt;span class=&quot;hljs-string&quot;&gt;&#39;&#39;&lt;/span&gt;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;name.isEmpty&rpar; {
        errors[&lt;span class=&quot;hljs-string&quot;&gt;&#39;name&#39;&lt;/span&gt;] = [&lt;span class=&quot;hljs-string&quot;&gt;&#39;Name is required&#39;&lt;/span&gt;];
      }
      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;email.isEmpty&rpar; {
        errors[&lt;span class=&quot;hljs-string&quot;&gt;&#39;email&#39;&lt;/span&gt;] = [&lt;span class=&quot;hljs-string&quot;&gt;&#39;Email is required&#39;&lt;/span&gt;];
      }
      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;!email.contains&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;@&#39;&lt;/span&gt;&rpar;&rpar; {
        errors[&lt;span class=&quot;hljs-string&quot;&gt;&#39;email&#39;&lt;/span&gt;] = [&lt;span class=&quot;hljs-string&quot;&gt;&#39;Email is invalid&#39;&lt;/span&gt;];
      }
      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;password.isEmpty&rpar; {
        errors[&lt;span class=&quot;hljs-string&quot;&gt;&#39;password&#39;&lt;/span&gt;] = [&lt;span class=&quot;hljs-string&quot;&gt;&#39;Password is required&#39;&lt;/span&gt;];
      }
      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;password.length &amp;lt; &lt;span class=&quot;hljs-number&quot;&gt;6&lt;/span&gt;&rpar; {
        errors[&lt;span class=&quot;hljs-string&quot;&gt;&#39;password&#39;&lt;/span&gt;] = [&lt;span class=&quot;hljs-string&quot;&gt;&#39;Password must be at least 6 characters&#39;&lt;/span&gt;];
      }

      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;errors.isEmpty&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Right&lpar;CreateUserDto.fromJson&lpar;json&rpar;&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; BadRequestException&lpar;
        message: &lt;span class=&quot;hljs-string&quot;&gt;&#39;Validation failed&#39;&lt;/span&gt;,
        errors: errors,
      &rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;on&lt;/span&gt; BadRequestException &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Left&lpar;
        ValidationFailure&lpar;
          message: e.message,
          errors: e.errors,
          statusCode: e.statusCode,
        &rpar;,
      &rpar;;
    }
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Similarly, we will create a new &lt;code&gt;login_user_dto&lt;/code&gt;.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:either_dart/either.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:exceptions/exceptions.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:failures/failures.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:freezed_annotation/freezed_annotation.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;part&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;login_user_dto.freezed.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;part&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;login_user_dto.g.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-meta&quot;&gt;@freezed&lt;/span&gt;
&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;LoginUserDto&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;with&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;_&lt;/span&gt;$descriptionlt;span class=&quot;hljs-title&quot;&gt;LoginUserDto&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;factory&lt;/span&gt; LoginUserDto&lpar;{
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; email,
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; password,
  }&rpar; = _LoginUserDto;

  &lt;span class=&quot;hljs-keyword&quot;&gt;factory&lt;/span&gt; LoginUserDto.fromJson&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;dynamic&lt;/span&gt;&amp;gt; json&rpar; =&amp;gt;
      _$LoginUserDtoFromJson&lpar;json&rpar;;

  &lt;span class=&quot;hljs-keyword&quot;&gt;static&lt;/span&gt; Either&amp;lt;ValidationFailure, LoginUserDto&amp;gt; validated&lpar;
    &lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;dynamic&lt;/span&gt;&amp;gt; json,
  &rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;try&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; errors = &amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;&amp;gt;&amp;gt;{};
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; email = json[&lt;span class=&quot;hljs-string&quot;&gt;&#39;email&#39;&lt;/span&gt;] &lt;span class=&quot;hljs-keyword&quot;&gt;as&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String?&lt;/span&gt; ?? &lt;span class=&quot;hljs-string&quot;&gt;&#39;&#39;&lt;/span&gt;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; password = json[&lt;span class=&quot;hljs-string&quot;&gt;&#39;password&#39;&lt;/span&gt;] &lt;span class=&quot;hljs-keyword&quot;&gt;as&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String?&lt;/span&gt; ?? &lt;span class=&quot;hljs-string&quot;&gt;&#39;&#39;&lt;/span&gt;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;email.isEmpty&rpar; {
        errors[&lt;span class=&quot;hljs-string&quot;&gt;&#39;email&#39;&lt;/span&gt;] = [&lt;span class=&quot;hljs-string&quot;&gt;&#39;Email is required&#39;&lt;/span&gt;];
      }
      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;password.isEmpty&rpar; {
        errors[&lt;span class=&quot;hljs-string&quot;&gt;&#39;password&#39;&lt;/span&gt;] = [&lt;span class=&quot;hljs-string&quot;&gt;&#39;Password is required&#39;&lt;/span&gt;];
      }
      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;errors.isEmpty&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Right&lpar;LoginUserDto.fromJson&lpar;json&rpar;&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; BadRequestException&lpar;
        message: &lt;span class=&quot;hljs-string&quot;&gt;&#39;Validation failed&#39;&lt;/span&gt;,
        errors: errors,
      &rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;on&lt;/span&gt; BadRequestException &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Left&lpar;
        ValidationFailure&lpar;
          message: e.message,
          errors: e.errors,
          statusCode: e.statusCode,
        &rpar;,
      &rpar;;
    }
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;These data transfer objects will be used to send, receive and validate data from the client in the backend.&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;💡 Make sure to export &lt;code&gt;create_user_dto&lt;/code&gt; and &lt;code&gt;login_user_dto&lt;/code&gt; from &lt;code&gt;user.dart&lt;/code&gt;, and &lt;code&gt;user.dart&lt;/code&gt; from &lt;code&gt;models.dart&lt;/code&gt;&lt;/p&gt;
&lt;/blockquote&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:freezed_annotation/freezed_annotation.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:models/src/serializers/date_time_converter.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:typedefs/typedefs.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;./create_user_dto/create_user_dto.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;./login_user_dto/login_user_dto.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;part&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;user.freezed.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;part&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;user.g.dart&#39;&lt;/span&gt;;
&lt;/code&gt;&lt;/pre&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;library&lt;/span&gt; models;

&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;src/todo/todo.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;src/user/user.dart&#39;&lt;/span&gt;;
&lt;/code&gt;&lt;/pre&gt;
&lt;blockquote&gt;
&lt;p&gt;💡 Make sure to run &lt;code&gt;flutter pub run build_runner build&lt;/code&gt; to generate new files.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;hr /&gt;
&lt;h1 id=&quot;heading-creating-userdatasource&quot;&gt;Creating &lt;code&gt;UserDataSource&lt;/code&gt;&lt;/h1&gt;
&lt;blockquote&gt;
&lt;p&gt;📊 Building the foundation for user management with &lt;code&gt;UserDataSource&lt;/code&gt; 🛠&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;In &lt;code&gt;data_source&lt;/code&gt; package, we will create a new interface called &lt;code&gt;UserDataSource&lt;/code&gt; in &lt;code&gt;data_source/lib/src/user_data_source.dart&lt;/code&gt;&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:models/models.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:typedefs/typedefs.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;abstract&lt;/span&gt; &lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;UserDataSource&lt;/span&gt; &lt;/span&gt;{
  Future&amp;lt;User&amp;gt; getUserById&lpar;UserId id&rpar;;

  Future&amp;lt;User&amp;gt; createUser&lpar;CreateUserDto user&rpar;;

  Future&amp;lt;User&amp;gt; getUserByEmail&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; email&rpar;;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;We will have methods to query and create users. We will do the implementation in our &lt;code&gt;backend&lt;/code&gt;.&lt;/p&gt;
&lt;hr /&gt;
&lt;h1 id=&quot;heading-creating-userrepository&quot;&gt;Creating &lt;code&gt;UserRepository&lt;/code&gt;&lt;/h1&gt;
&lt;blockquote&gt;
&lt;p&gt;🔍 Designing our User Management System with UserRepository 🛠&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;We will also create an interface called &lt;code&gt;UserRepository&lt;/code&gt; which will return either a failure or valid data making use of &lt;code&gt;UserDataSource&lt;/code&gt;.&lt;/p&gt;
&lt;p&gt;In &lt;code&gt;repository&lt;/code&gt; package, we will create a new interface called &lt;code&gt;UserRepository&lt;/code&gt; in &lt;code&gt;repository/lib/src/user_repository.dart&lt;/code&gt;&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:either_dart/either.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:failures/failures.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:models/models.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:typedefs/typedefs.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;abstract&lt;/span&gt; &lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;UserRepository&lt;/span&gt; &lt;/span&gt;{
  Future&amp;lt;Either&amp;lt;Failure, User&amp;gt;&amp;gt; getUserById&lpar;UserId id&rpar;;

  Future&amp;lt;Either&amp;lt;Failure, User&amp;gt;&amp;gt; createUser&lpar;CreateUserDto createUserDto&rpar;;

  Future&amp;lt;Either&amp;lt;Failure, User&amp;gt;&amp;gt; loginUser&lpar;LoginUserDto loginUserDto&rpar;;

  Future&amp;lt;Either&amp;lt;Failure, User&amp;gt;&amp;gt; getUserByEmail&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; email&rpar;;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;We will have all the methods we need to create, query and login users. We will do the implementation in our backend.&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;💡 Make sure to export &lt;code&gt;UserRepository&lt;/code&gt; from &lt;code&gt;repository.dart&lt;/code&gt;&lt;/p&gt;
&lt;/blockquote&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;library&lt;/span&gt; repository;

&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;src/todo_repository.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;src/user_repository.dart&#39;&lt;/span&gt;;
&lt;/code&gt;&lt;/pre&gt;
&lt;hr /&gt;
&lt;h1 id=&quot;heading-implementing-userdatasource&quot;&gt;Implementing &lt;code&gt;UserDataSource&lt;/code&gt;&lt;/h1&gt;
&lt;blockquote&gt;
&lt;p&gt;💻 Bringing &lt;code&gt;UserDataSource&lt;/code&gt; to life 🔧&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;Now, we will implement &lt;code&gt;UserDataSource&lt;/code&gt; in our backend. In &lt;code&gt;backend/lib/user/data_source/user_data_source_impl.dart&lt;/code&gt;, we will create a new class called &lt;code&gt;UserDataSourceImpl&lt;/code&gt; which will implement &lt;code&gt;UserDataSource&lt;/code&gt;.&lt;/p&gt;
&lt;p&gt;This is how an empty implementation of &lt;code&gt;UserDataSourceImpl&lt;/code&gt; will look like.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:data_source/data_source.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:models/models.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:typedefs/typedefs.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;UserDataSourceImpl&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;implements&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;UserDataSource&lt;/span&gt; &lt;/span&gt;{
  UserDataSourceImpl&lpar;&lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;._databaseConnection&rpar;;

  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; DatabaseConnection _databaseConnection;
  Future&amp;lt;User&amp;gt; createUser&lpar;CreateUserDto user&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; UnimplementedError&lpar;&rpar;;
  }

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;User&amp;gt; getUserByEmail&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; email&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; UnimplementedError&lpar;&rpar;;
  }

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;User&amp;gt; getUserById&lpar;UserId id&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; UnimplementedError&lpar;&rpar;;
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;h2 id=&quot;heading-implementing-createuser-method&quot;&gt;Implementing &lt;code&gt;createUser&lt;/code&gt; method&lt;/h2&gt;
&lt;p&gt;Now, we will implement &lt;code&gt;createUser&lt;/code&gt; method. We will use &lt;code&gt;DatabaseConnection&lt;/code&gt; to connect to our database and create a new user from the dto we received.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;User&amp;gt; createUser&lpar;CreateUserDto user&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;try&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _databaseConnection.connect&lpar;&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; result = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _databaseConnection.db.query&lpar;
        &lt;span class=&quot;hljs-string&quot;&gt;&#39;&#39;&#39;
        INSERT INTO users &lpar;name, email, password&rpar;
        VALUES &lpar;@name, @email, @password&rpar; RETURNING *
        &#39;&#39;&#39;&lt;/span&gt;,
        substitutionValues: user.toJson&lpar;&rpar;,
      &rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;result.affectedRowCount == &lt;span class=&quot;hljs-number&quot;&gt;0&lt;/span&gt;&rpar; {
        &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; ServerException&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;Failed to create todo&#39;&lt;/span&gt;&rpar;;
      }
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; userMap = result.first.toColumnMap&lpar;&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; User.fromJson&lpar;userMap&rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;on&lt;/span&gt; PostgreSQLException &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; ServerException&lpar;e.message ?? &lt;span class=&quot;hljs-string&quot;&gt;&#39;Unexpected error&#39;&lt;/span&gt;&rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;finally&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _databaseConnection.close&lpar;&rpar;;
    }
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;We will validate the DTO in the repository before passing it to the data source. The database will then be queried to generate a new user. We will throw a &lt;code&gt;ServerException&lt;/code&gt; if the user is not created, else, we will return the user that was created.&lt;/p&gt;
&lt;h2 id=&quot;heading-implementing-getuserbyemail-method&quot;&gt;Implementing &lt;code&gt;getUserByEmail&lt;/code&gt; method&lt;/h2&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;User&amp;gt; getUserByEmail&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; email&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;try&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _databaseConnection.connect&lpar;&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; result = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _databaseConnection.db.query&lpar;
        &lt;span class=&quot;hljs-string&quot;&gt;&#39;&#39;&#39;
        SELECT id, name, email, password, created_at
        FROM users WHERE email = @email
        &#39;&#39;&#39;&lt;/span&gt;,
        substitutionValues: {&lt;span class=&quot;hljs-string&quot;&gt;&#39;email&#39;&lt;/span&gt;: email},
      &rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;result.isEmpty&rpar; {
        &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; NotFoundException&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;User not found&#39;&lt;/span&gt;&rpar;;
      }
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; User.fromJson&lpar;result.first.toColumnMap&lpar;&rpar;&rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;on&lt;/span&gt; PostgreSQLException &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; ServerException&lpar;e.message ?? &lt;span class=&quot;hljs-string&quot;&gt;&#39;Unexpected error&#39;&lt;/span&gt;&rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;finally&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _databaseConnection.close&lpar;&rpar;;
    }
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Here, we will query the database for the user with the given email. If the user is not found, we will throw a &lt;code&gt;NotFoundException&lt;/code&gt;. We will handle this exception in the &lt;code&gt;UserController&lt;/code&gt; and return a &lt;code&gt;404&lt;/code&gt; response.&lt;/p&gt;
&lt;h2 id=&quot;heading-implementing-getuserbyid-method&quot;&gt;Implementing &lt;code&gt;getUserById&lt;/code&gt; method&lt;/h2&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;User&amp;gt; getUserById&lpar;UserId id&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;try&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _databaseConnection.connect&lpar;&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; result = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _databaseConnection.db.query&lpar;
        &lt;span class=&quot;hljs-string&quot;&gt;&#39;SELECT id, name, email, created_at FROM users WHERE id = @id&#39;&lt;/span&gt;,
        substitutionValues: {&lt;span class=&quot;hljs-string&quot;&gt;&#39;id&#39;&lt;/span&gt;: id},
      &rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;result.isEmpty&rpar; {
        &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; NotFoundException&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;User not found&#39;&lt;/span&gt;&rpar;;
      }
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; User.fromJson&lpar;result.first.toColumnMap&lpar;&rpar;&rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;on&lt;/span&gt; PostgreSQLException &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; ServerException&lpar;e.message ?? &lt;span class=&quot;hljs-string&quot;&gt;&#39;Unexpected error&#39;&lt;/span&gt;&rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;finally&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _databaseConnection.close&lpar;&rpar;;
    }
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;We will query the database for the user with the given id. If the user is not found, we will throw a &lt;code&gt;NotFoundException&lt;/code&gt;. We will handle this exception in the &lt;code&gt;UserController&lt;/code&gt; and return a &lt;code&gt;404&lt;/code&gt; response.&lt;/p&gt;
&lt;hr /&gt;
&lt;h1 id=&quot;heading-creating-passwordhasherservice&quot;&gt;Creating &lt;code&gt;PasswordHasherService&lt;/code&gt;&lt;/h1&gt;
&lt;blockquote&gt;
&lt;p&gt;🔑 Keeping user passwords safe with &lt;code&gt;PasswordHasherService&lt;/code&gt; 🔒&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;We will create a new service to hash and validate hashed passwords before going on to the &lt;code&gt;UserRepository&lt;/code&gt; implementation. The &lt;code&gt;CreateUserDto&lt;/code&gt; with the hashed password will be passed to the &lt;code&gt;UserRepository&lt;/code&gt;.&lt;/p&gt;
&lt;p&gt;In &lt;code&gt;backend/lib/services/password_hasher_service.dart&lt;/code&gt;, we will create a new class called &lt;code&gt;PasswordHasherService&lt;/code&gt;.&lt;/p&gt;
&lt;p&gt;We will use &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/bcrypt&quot;&gt;&lt;code&gt;bcrypt&lt;/code&gt;&lt;/a&gt; package to hash and verify the password.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;flutter pub add bcrypt
&lt;/code&gt;&lt;/pre&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:bcrypt/bcrypt.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;PasswordHasherService&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; PasswordHasherService&lpar;&rpar;;

  &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; hashPassword&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; password&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; BCrypt.hashpw&lpar;password, BCrypt.gensalt&lpar;&rpar;&rpar;;
  }

  &lt;span class=&quot;hljs-built_in&quot;&gt;bool&lt;/span&gt; checkPassword&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; password, &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; hashedPassword&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; BCrypt.checkpw&lpar;password, hashedPassword&rpar;;
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Now, we can pass this service as a dependency to &lt;code&gt;UserRepository&lt;/code&gt; when we implement our repository.&lt;/p&gt;
&lt;hr /&gt;
&lt;h1 id=&quot;heading-implementing-userrepository&quot;&gt;Implementing &lt;code&gt;UserRepository&lt;/code&gt;&lt;/h1&gt;
&lt;blockquote&gt;
&lt;p&gt;💻 Bringing &lt;code&gt;UserRepository&lt;/code&gt; to life 🔧&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;Now, we will implement &lt;code&gt;UserRepository&lt;/code&gt; in our backend. In &lt;code&gt;backend/lib/user/repository/user_repository_impl.dart&lt;/code&gt;, we will create a new class called &lt;code&gt;UserRepositoryImpl&lt;/code&gt; which will implement &lt;code&gt;UserRepository&lt;/code&gt;.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/services/password_hasher_service.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:data_source/data_source.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:either_dart/either.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:failures/failures.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:models/models.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:repository/repository.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:typedefs/typedefs.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;UserRepositoryImpl&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;implements&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;UserRepository&lt;/span&gt; &lt;/span&gt;{
  UserRepositoryImpl&lpar;&lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;.dataSource, &lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;.passwordHasherService&rpar;;

  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; UserDataSource dataSource;
  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; PasswordHasherService passwordHasherService;

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Either&amp;lt;Failure, User&amp;gt;&amp;gt; createUser&lpar;CreateUserDto createUserDto&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; UnimplementedError&lpar;&rpar;;
  }

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Either&amp;lt;Failure, User&amp;gt;&amp;gt; getUserByEmail&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; email&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; UnimplementedError&lpar;&rpar;;
  }

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Either&amp;lt;Failure, User&amp;gt;&amp;gt; getUserById&lpar;UserId id&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; UnimplementedError&lpar;&rpar;;
  }

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Either&amp;lt;Failure, User&amp;gt;&amp;gt; loginUser&lpar;LoginUserDto loginUserDto&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; UnimplementedError&lpar;&rpar;;
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;h2 id=&quot;heading-implementing-getuserbyemail-method-1&quot;&gt;Implementing &lt;code&gt;getUserByEmail&lt;/code&gt; method&lt;/h2&gt;
&lt;p&gt;We will start by implementing &lt;code&gt;getUserByEmail&lt;/code&gt;. We will use the data source&#39;s &lt;code&gt;dataSource.getUserByEmail&lt;/code&gt; method to see if we get a &lt;code&gt;User&lt;/code&gt; object. If we get a &lt;code&gt;User&lt;/code&gt; object, we shall wrap it in a &lt;code&gt;Right&lt;/code&gt; object and return it. If an error occurs, we will return a &lt;code&gt;Left&lt;/code&gt; object along with a &lt;code&gt;ServerFailure&lt;/code&gt; object.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Either&amp;lt;Failure, User&amp;gt;&amp;gt; getUserByEmail&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; email&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;try&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; user = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; dataSource.getUserByEmail&lpar;email&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Right&lpar;user&rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
      log&lpar;e.toString&lpar;&rpar;&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; Left&lpar;
        ServerFailure&lpar;
          message: &lt;span class=&quot;hljs-string&quot;&gt;&#39;User with this email does not exist&#39;&lt;/span&gt;,
          statusCode: HttpStatus.notFound,
        &rpar;,
      &rpar;;
    }
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;h2 id=&quot;heading-implementing-getuserbyid-method-1&quot;&gt;Implementing &lt;code&gt;getUserById&lt;/code&gt; method&lt;/h2&gt;
&lt;p&gt;Similarly, we will call &lt;code&gt;dataSource.getUserById&lt;/code&gt; method and see whether we get a &lt;code&gt;User&lt;/code&gt; object. If we get a &lt;code&gt;User&lt;/code&gt; object, we shall wrap it in a &lt;code&gt;Right&lt;/code&gt; object and return it. If an error occurs, we will return a &lt;code&gt;Left&lt;/code&gt; object along with a &lt;code&gt;ServerFailure&lt;/code&gt; object.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Either&amp;lt;Failure, User&amp;gt;&amp;gt; getUserById&lpar;UserId id&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;try&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; res = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; dataSource.getUserById&lpar;id&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Right&lpar;res&rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;on&lt;/span&gt; NotFoundException &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
      log&lpar;e.message&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Left&lpar;
        ServerFailure&lpar;
          message: e.message,
          statusCode: e.statusCode,
        &rpar;,
      &rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;on&lt;/span&gt; ServerException &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
      log&lpar;e.message&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Left&lpar;
        ServerFailure&lpar;message: e.message&rpar;,
      &rpar;;
    }
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;h2 id=&quot;heading-implementing-loginuser-method&quot;&gt;Implementing &lt;code&gt;loginUser&lt;/code&gt; method&lt;/h2&gt;
&lt;p&gt;Now, we will implement &lt;code&gt;loginUser&lt;/code&gt;. We will check if the user with the given email exists. If the user exists, we will check the password with &lt;code&gt;PasswordHasherService&lt;/code&gt;. If they do not match, we will return a failure, else we will return the logged in user.&lt;/p&gt;
&lt;p&gt;This method will be used by the &lt;code&gt;UserController&lt;/code&gt; to create an access token for the user.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Either&amp;lt;Failure, User&amp;gt;&amp;gt; loginUser&lpar;LoginUserDto loginUserDto&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;try&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; email = loginUserDto.email;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; userExists = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; getUserByEmail&lpar;email&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;userExists.isLeft&rpar; {
        &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; ServerException&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;Invalid email or password&#39;&lt;/span&gt;&rpar;;
      }
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; user = userExists.right;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; password = loginUserDto.password;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; isPasswordCorrect =
          passwordHasherService.checkPassword&lpar;password, user.password&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;!isPasswordCorrect&rpar; {
        &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; ServerException&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;Invalid email or password&#39;&lt;/span&gt;&rpar;;
      }
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Right&lpar;user&rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
      log&lpar;e.toString&lpar;&rpar;&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; Left&lpar;
        ServerFailure&lpar;
          message: &lt;span class=&quot;hljs-string&quot;&gt;&#39;Invalid email or password&#39;&lt;/span&gt;,
          statusCode: HttpStatus.unauthorized,
        &rpar;,
      &rpar;;
    }
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;h2 id=&quot;heading-implementing-createuser-method-1&quot;&gt;Implementing &lt;code&gt;createUser&lt;/code&gt; method&lt;/h2&gt;
&lt;p&gt;Similarly, we will implement &lt;code&gt;createUser&lt;/code&gt;. We will check if the user with the given email exists. If the user exists, we will return an failure, else we will create the user and return it.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Either&amp;lt;Failure, User&amp;gt;&amp;gt; createUser&lpar;CreateUserDto createUserDto&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;try&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; userExists = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; getUserByEmail&lpar;createUserDto.email&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;userExists.isRight&rpar; {
        &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; ServerException&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;Email already in use&#39;&lt;/span&gt;&rpar;;
      }
      &lt;span class=&quot;hljs-comment&quot;&gt;// dto is already validated in the controller&lt;/span&gt;
      &lt;span class=&quot;hljs-comment&quot;&gt;// we will hash the password here&lt;/span&gt;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; hashedPassword = passwordHasherService.hashPassword&lpar;
        createUserDto.password,
      &rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; user = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; dataSource.createUser&lpar;
        createUserDto.copyWith&lpar;
          password: hashedPassword,
        &rpar;,
      &rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Right&lpar;user&rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;on&lt;/span&gt; ServerException &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
      log&lpar;e.message&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Left&lpar;
        ServerFailure&lpar;message: e.message&rpar;,
      &rpar;;
    }
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;hr /&gt;
&lt;h1 id=&quot;heading-implementing-jwtservice&quot;&gt;Implementing &lt;code&gt;JwtService&lt;/code&gt;&lt;/h1&gt;
&lt;blockquote&gt;
&lt;p&gt;🔐 Securing User Login with JWT 🔒&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;Now, once we have all the necessary implementation of the repository and the data source, we will implement &lt;code&gt;JwtService&lt;/code&gt; before implementing our &lt;code&gt;UserController&lt;/code&gt;. This service will be used to create a JWT token for the user when they log in or signup.&lt;/p&gt;
&lt;p&gt;In &lt;code&gt;backend/lib/user/service/jwt_service.dart&lt;/code&gt;, we will create a new class called &lt;code&gt;JwtService&lt;/code&gt;. We will use &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/dart_jsonwebtoken&quot;&gt;&lt;code&gt;dart_jsonwebtoken&lt;/code&gt;&lt;/a&gt; package to create and verify JWT tokens.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;flutter pub add dart_jsonwebtoken
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Now, we will implement the &lt;code&gt;JwtService&lt;/code&gt; class.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dart_jsonwebtoken/dart_jsonwebtoken.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dotenv/dotenv.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;JWTService&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; JWTService&lpar;&lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;._env&rpar;;

  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; DotEnv _env;

  &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; sign&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;dynamic&lt;/span&gt;&amp;gt; payload&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; secret = _env[&lt;span class=&quot;hljs-string&quot;&gt;&#39;JWT_SECRET&#39;&lt;/span&gt;]!;
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; jwt = JWT&lpar;payload&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; jwt.sign&lpar;SecretKey&lpar;secret&rpar;&rpar;;
  }

  &lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;dynamic&lt;/span&gt;&amp;gt; verify&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; token&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; secret = _env[&lt;span class=&quot;hljs-string&quot;&gt;&#39;JWT_SECRET&#39;&lt;/span&gt;]!;
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; jwt = JWT.verify&lpar;token, SecretKey&lpar;secret&rpar;&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; jwt.payload &lt;span class=&quot;hljs-keyword&quot;&gt;as&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;dynamic&lt;/span&gt;&amp;gt;;
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;blockquote&gt;
&lt;p&gt;💡 NOTE: We are using &lt;code&gt;dotenv&lt;/code&gt; package to get the &lt;code&gt;JWT_SECRET&lt;/code&gt; from the &lt;code&gt;.env&lt;/code&gt; file. 💡 Make sure you have added the &lt;code&gt;JWT_SECRET&lt;/code&gt; to the &lt;code&gt;.env&lt;/code&gt; file.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;pre&gt;&lt;code class=&quot;lang-apache&quot;&gt;...
&lt;span class=&quot;hljs-attribute&quot;&gt;JWT_SECRET&lt;/span&gt;=verycomplexsupersecret
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Once this is done, we will implement the &lt;code&gt;UserController&lt;/code&gt;.&lt;/p&gt;
&lt;hr /&gt;
&lt;h1 id=&quot;heading-tidy-up-time&quot;&gt;Tidy Up Time 🧹&lt;/h1&gt;
&lt;blockquote&gt;
&lt;p&gt;Make Room for Improvement 🧠&lt;/p&gt;
&lt;/blockquote&gt;
&lt;h2 id=&quot;heading-remove-duplicates&quot;&gt;Remove duplicates&lt;/h2&gt;
&lt;p&gt;We have multiple routes that are not implemented and are returning the same response. We will remove these routes and create a new &lt;code&gt;Handler&lt;/code&gt; to handle these requests.&lt;/p&gt;
&lt;p&gt;We will create a new &lt;code&gt;Handler&lt;/code&gt; called &lt;code&gt;notAllowedRequestHandler&lt;/code&gt; in &lt;code&gt;backend/lib/request_handlers/not_allowed_request_handler.dart&lt;/code&gt; to handle these requests.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;Future&amp;lt;Response&amp;gt; notAllowedRequestHandler&lpar;RequestContext context&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
  &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Response.json&lpar;
    body: {&lt;span class=&quot;hljs-string&quot;&gt;&#39;error&#39;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&#39;👀 Looks like you are lost 🔦&#39;&lt;/span&gt;},
    statusCode: HttpStatus.methodNotAllowed,
  &rpar;;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Then, we will replace the routes with this handler.&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;&lt;code&gt;backend/routes/index.dart&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/request_handlers/not_allowed_request_handler.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dart_frog/dart_frog.dart&#39;&lt;/span&gt;;

Handler onRequest = notAllowedRequestHandler;
&lt;/code&gt;&lt;/pre&gt;
&lt;ul&gt;
&lt;li&gt;&lt;p&gt;&lt;code&gt;backend/routes/todos/index.dart&lt;/code&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;code&gt;backend/routes/todos/[id].dart&lt;/code&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-diff&quot;&gt;&lt;span class=&quot;hljs-addition&quot;&gt;+     return notAllowedRequestHandler&lpar;context&rpar;;&lt;/span&gt;
&lt;span class=&quot;hljs-deletion&quot;&gt;-     return Response.json&lpar;&lt;/span&gt;
&lt;span class=&quot;hljs-deletion&quot;&gt;-       body: {&#39;error&#39;: &#39;👀 Looks like you are lost 🔦&#39;},&lt;/span&gt;
&lt;span class=&quot;hljs-deletion&quot;&gt;-       statusCode: HttpStatus.methodNotAllowed,&lt;/span&gt;
&lt;span class=&quot;hljs-deletion&quot;&gt;-     &rpar;;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;h2 id=&quot;heading-refactor-httpcontroller&quot;&gt;Refactor &lt;code&gt;HttpController&lt;/code&gt;&lt;/h2&gt;
&lt;p&gt;Right now, if we have to implement &lt;code&gt;HttpController&lt;/code&gt;, we will have to override all the methods. We will refactor the &lt;code&gt;HttpController&lt;/code&gt; to make it optional to override all the methods.&lt;/p&gt;
&lt;p&gt;we will create a new handler called &lt;code&gt;unimplementedHandler&lt;/code&gt; in &lt;code&gt;backend/lib/request_handlers/unimplemented_handler.dart&lt;/code&gt; to handle the unimplemented methods.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;dart:io&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dart_frog/dart_frog.dart&#39;&lt;/span&gt;;

Future&amp;lt;Response&amp;gt; unimplementedHandler&lpar;[RequestContext? context]&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
  &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Response.json&lpar;
    body: {&lt;span class=&quot;hljs-string&quot;&gt;&#39;error&#39;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&#39;👀 Not implemented yet&#39;&lt;/span&gt;},
    statusCode: HttpStatus.notImplemented,
  &rpar;;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Then, we will refactor the &lt;code&gt;HttpController&lt;/code&gt; to use this handler. In &lt;code&gt;backend/lib/controller/http_controller.dart&lt;/code&gt;, we will change the methods to call and return &lt;code&gt;unimplementedHandler&lt;/code&gt;.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;abstract&lt;/span&gt; &lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;HttpController&lt;/span&gt; &lt;/span&gt;{
  FutureOr&amp;lt;Response&amp;gt; index&lpar;Request request&rpar; =&amp;gt; unimplementedHandler&lpar;&rpar;;

  FutureOr&amp;lt;Response&amp;gt; store&lpar;Request request&rpar; =&amp;gt; unimplementedHandler&lpar;&rpar;;

  FutureOr&amp;lt;Response&amp;gt; &lt;span class=&quot;hljs-keyword&quot;&gt;show&lt;/span&gt;&lpar;Request request, &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; id&rpar; =&amp;gt; unimplementedHandler&lpar;&rpar;;

  FutureOr&amp;lt;Response&amp;gt; update&lpar;Request request, &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; id&rpar; =&amp;gt;
      unimplementedHandler&lpar;&rpar;;

  FutureOr&amp;lt;Response&amp;gt; destroy&lpar;Request request, &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; id&rpar; =&amp;gt;
      unimplementedHandler&lpar;&rpar;;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;hr /&gt;
&lt;h1 id=&quot;heading-implementing-usercontroller&quot;&gt;Implementing &lt;code&gt;UserController&lt;/code&gt;&lt;/h1&gt;
&lt;blockquote&gt;
&lt;p&gt;Adding magic with &lt;code&gt;UserController&lt;/code&gt; Implementation 🧙&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;Now, we will implement &lt;code&gt;UserController&lt;/code&gt; in &lt;code&gt;user/controller/user_controller.dart&lt;/code&gt;.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;dart:async&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/controller/http_controller.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/services/jwt_service.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dart_frog/dart_frog.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:repository/repository.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;UserController&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;extends&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;HttpController&lt;/span&gt; &lt;/span&gt;{
  UserController&lpar;&lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;._repo, &lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;._jwtService&rpar;;

  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; UserRepository _repo;
  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; JWTService _jwtService;

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  FutureOr&amp;lt;Response&amp;gt; store&lpar;Request request&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; UnimplementedError&lpar;&rpar;;
  }

  FutureOr&amp;lt;Response&amp;gt; login&lpar;Request request&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; UnimplementedError&lpar;&rpar;;
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;We will override &lt;code&gt;store&lt;/code&gt; method, which will responsible for creating and storing the user, and then another &lt;code&gt;login&lt;/code&gt; method, to log in the user.&lt;/p&gt;
&lt;p&gt;Also, we will create a new private method called &lt;code&gt;_signAndSendToken&lt;/code&gt; which will take the user, and then sign and send the user along with the JWT token.&lt;/p&gt;
&lt;h2 id=&quot;heading-implement-signandsendtoken-method&quot;&gt;Implement &lt;code&gt;_signAndSendToken&lt;/code&gt; method&lt;/h2&gt;
&lt;p&gt;We will use this method once &lt;code&gt;login&lt;/code&gt; and &lt;code&gt;store&lt;/code&gt; method are successful and when we want to send a response to the user.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  Response _signAndSendToken&lpar;User user, [&lt;span class=&quot;hljs-built_in&quot;&gt;int?&lt;/span&gt; httpStatus]&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; token = _jwtService.sign&lpar;user.toJson&lpar;&rpar;&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Response.json&lpar;
      body: {
        &lt;span class=&quot;hljs-string&quot;&gt;&#39;token&#39;&lt;/span&gt;: token,
        &lt;span class=&quot;hljs-string&quot;&gt;&#39;user&#39;&lt;/span&gt;: user.toJson&lpar;&rpar;..remove&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;password&#39;&lt;/span&gt;&rpar;,
      },
      statusCode: httpStatus ?? HttpStatus.ok,
    &rpar;;
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;h2 id=&quot;heading-implement-store-method&quot;&gt;Implement &lt;code&gt;store&lt;/code&gt; method&lt;/h2&gt;
&lt;p&gt;We will parse the JSON body, and validate the body with &lt;code&gt;CreateUserDto&lt;/code&gt;. Once validated, we will call &lt;code&gt;repository.createUser&lt;/code&gt; which will hash the password and create a new user if not already there.&lt;/p&gt;
&lt;p&gt;Once this is done, we will call &lt;code&gt;_signAndSendToken&lt;/code&gt; and return with &lt;code&gt;201&lt;/code&gt; status code.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  FutureOr&amp;lt;Response&amp;gt; store&lpar;Request request&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; parsedBody = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; parseJson&lpar;request&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;parsedBody.isLeft&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Response.json&lpar;
        body: {&lt;span class=&quot;hljs-string&quot;&gt;&#39;message&#39;&lt;/span&gt;: parsedBody.left.message},
        statusCode: parsedBody.left.statusCode,
      &rpar;;
    }
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; json = parsedBody.right;
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; createTodoDto = CreateUserDto.validated&lpar;json&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;createTodoDto.isLeft&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Response.json&lpar;
        body: {
          &lt;span class=&quot;hljs-string&quot;&gt;&#39;message&#39;&lt;/span&gt;: createTodoDto.left.message,
          &lt;span class=&quot;hljs-string&quot;&gt;&#39;errors&#39;&lt;/span&gt;: createTodoDto.left.errors,
        },
        statusCode: createTodoDto.left.statusCode,
      &rpar;;
    }
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; res = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _repo.createUser&lpar;createTodoDto.right&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; res.fold&lpar;
      &lpar;left&rpar; =&amp;gt; Response.json&lpar;
        body: {&lt;span class=&quot;hljs-string&quot;&gt;&#39;message&#39;&lt;/span&gt;: left.message},
        statusCode: left.statusCode,
      &rpar;,
      &lpar;right&rpar; =&amp;gt; _signAndSendToken&lpar;right, HttpStatus.created&rpar;,
    &rpar;;
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;h2 id=&quot;heading-implement-login&quot;&gt;Implement &lt;code&gt;login&lt;/code&gt;&lt;/h2&gt;
&lt;p&gt;Similar to &lt;code&gt;store&lt;/code&gt;, we will parse and verify &lt;code&gt;LoginUserDto&lt;/code&gt;, and call &lt;code&gt;repository.loginUser&lt;/code&gt; which will verify the password and return the user.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  FutureOr&amp;lt;Response&amp;gt; login&lpar;Request request&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; parsedBody = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; parseJson&lpar;request&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;parsedBody.isLeft&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Response.json&lpar;
        body: {&lt;span class=&quot;hljs-string&quot;&gt;&#39;message&#39;&lt;/span&gt;: parsedBody.left.message},
        statusCode: parsedBody.left.statusCode,
      &rpar;;
    }
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; json = parsedBody.right;
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; loginUserDto = LoginUserDto.validated&lpar;json&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;loginUserDto.isLeft&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Response.json&lpar;
        body: {
          &lt;span class=&quot;hljs-string&quot;&gt;&#39;message&#39;&lt;/span&gt;: loginUserDto.left.message,
          &lt;span class=&quot;hljs-string&quot;&gt;&#39;errors&#39;&lt;/span&gt;: loginUserDto.left.errors,
        },
        statusCode: loginUserDto.left.statusCode,
      &rpar;;
    }
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; res = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _repo.loginUser&lpar;loginUserDto.right&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; res.fold&lpar;
      &lpar;left&rpar; =&amp;gt; Response.json&lpar;
        body: {&lt;span class=&quot;hljs-string&quot;&gt;&#39;message&#39;&lt;/span&gt;: left.message},
        statusCode: left.statusCode,
      &rpar;,
      _signAndSendToken,
    &rpar;;
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;hr /&gt;
&lt;h1 id=&quot;heading-adding-dependency-injections&quot;&gt;Adding Dependency Injections 🧰&lt;/h1&gt;
&lt;blockquote&gt;
&lt;p&gt;Making sure our ducks are in a row 🦆&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;In our global middleware &lt;code&gt;backend/routes/_middleware.dart&lt;/code&gt;, we will register the dependencies.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/db/database_connection.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/services/jwt_service.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/services/password_hasher_service.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/user/controller/user_controller.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/user/data_source/user_data_source_impl.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/user/repositories/user_repository_impl.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dart_frog/dart_frog.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:data_source/data_source.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dotenv/dotenv.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:repository/repository.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; env = DotEnv&lpar;&rpar;..load&lpar;&rpar;;
&lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; _db = DatabaseConnection&lpar;env&rpar;;
&lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; _userDs = UserDataSourceImpl&lpar;_db&rpar;;
&lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; _passwordHasher = PasswordHasherService&lpar;&rpar;;
&lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; _userRepo = UserRepositoryImpl&lpar;_userDs, _passwordHasher&rpar;;
&lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; _jwtService = JWTService&lpar;env&rpar;;
&lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; _userController = UserController&lpar;_userRepo, _jwtService&rpar;;

Handler middleware&lpar;Handler handler&rpar; {
  &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; handler
      .use&lpar;requestLogger&lpar;&rpar;&rpar;
      .use&lpar;provider&amp;lt;DatabaseConnection&amp;gt;&lpar;&lpar;_&rpar; =&amp;gt; _db&rpar;&rpar;
      .use&lpar;provider&amp;lt;JWTService&amp;gt;&lpar;&lpar;_&rpar; =&amp;gt; _jwtService&rpar;&rpar;
      .use&lpar;provider&amp;lt;UserDataSource&amp;gt;&lpar;&lpar;_&rpar; =&amp;gt; _userDs&rpar;&rpar;
      .use&lpar;provider&amp;lt;UserRepository&amp;gt;&lpar;&lpar;_&rpar; =&amp;gt; _userRepo&rpar;&rpar;
      .use&lpar;provider&amp;lt;UserController&amp;gt;&lpar;&lpar;_&rpar; =&amp;gt; _userController&rpar;&rpar;
      .use&lpar;provider&amp;lt;PasswordHasherService&amp;gt;&lpar;&lpar;_&rpar; =&amp;gt; _passwordHasher&rpar;&rpar;;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;hr /&gt;
&lt;h1 id=&quot;heading-setting-up-routes&quot;&gt;Setting up routes&lt;/h1&gt;
&lt;blockquote&gt;
&lt;p&gt;Connecting the dots 🔗 - defining API endpoints&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;We will now setup the routes for &lt;code&gt;UserController&lt;/code&gt; in &lt;code&gt;backend/routes/user&lt;/code&gt; we will create three new files &lt;code&gt;index.dart&lt;/code&gt;, &lt;code&gt;login.dart&lt;/code&gt;, and &lt;code&gt;signup.dart&lt;/code&gt;.&lt;/p&gt;
&lt;p&gt;Doing this we will have three different routes:&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;&lt;p&gt;&lt;code&gt;/user&lt;/code&gt; - &lt;code&gt;index.dart&lt;/code&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;code&gt;/user/login&lt;/code&gt; - &lt;code&gt;login.dart&lt;/code&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;code&gt;/user/signup&lt;/code&gt; - &lt;code&gt;signup.dart&lt;/code&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;/ul&gt;
&lt;h2 id=&quot;heading-indexdart&quot;&gt;&lt;code&gt;index.dart&lt;/code&gt;&lt;/h2&gt;
&lt;p&gt;This route does nothing. We will just return &lt;code&gt;unimplementedHandler&lt;/code&gt;.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/request_handlers/not_allowed_request_handler.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dart_frog/dart_frog.dart&#39;&lt;/span&gt;;

Handler onRequest = notAllowedRequestHandler;
&lt;/code&gt;&lt;/pre&gt;
&lt;h2 id=&quot;heading-logindart&quot;&gt;&lt;code&gt;login.dart&lt;/code&gt;&lt;/h2&gt;
&lt;p&gt;We will get the &lt;code&gt;UserController&lt;/code&gt; from the &lt;code&gt;RequestContext&lt;/code&gt; and call &lt;code&gt;login&lt;/code&gt; method for &lt;code&gt;POST&lt;/code&gt; requests.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;dart:async&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/request_handlers/not_allowed_request_handler.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/user/controller/user_controller.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dart_frog/dart_frog.dart&#39;&lt;/span&gt;;

FutureOr&amp;lt;Response&amp;gt; onRequest&lpar;RequestContext context&rpar; {
  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; userController = context.read&amp;lt;UserController&amp;gt;&lpar;&rpar;;
  &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;context.request.method != HttpMethod.post&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; notAllowedRequestHandler&lpar;context&rpar;;
  }
  &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; userController.login&lpar;context.request&rpar;;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;h2 id=&quot;heading-signupdart&quot;&gt;&lt;code&gt;signup.dart&lt;/code&gt;&lt;/h2&gt;
&lt;p&gt;Similar to &lt;code&gt;login.dart&lt;/code&gt;, we will get the &lt;code&gt;UserController&lt;/code&gt; from the &lt;code&gt;RequestContext&lt;/code&gt; and call &lt;code&gt;store&lt;/code&gt; method for &lt;code&gt;POST&lt;/code&gt; requests.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;dart:async&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/request_handlers/not_allowed_request_handler.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/user/controller/user_controller.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dart_frog/dart_frog.dart&#39;&lt;/span&gt;;

FutureOr&amp;lt;Response&amp;gt; onRequest&lpar;RequestContext context&rpar; {
  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; userController = context.read&amp;lt;UserController&amp;gt;&lpar;&rpar;;
  &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;context.request.method != HttpMethod.post&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; notAllowedRequestHandler&lpar;context&rpar;;
  }
  &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; userController.store&lpar;context.request&rpar;;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;blockquote&gt;
&lt;p&gt;💡 NOTE: Recheck your &lt;code&gt;.env&lt;/code&gt; file before testing the routes.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;hr /&gt;
&lt;h1 id=&quot;heading-testing-routes&quot;&gt;Testing routes&lt;/h1&gt;
&lt;blockquote&gt;
&lt;p&gt;Testing Time 🧪 - Verify Your Routes!&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;Once we have set up the routes, we can test them using &lt;code&gt;curl&lt;/code&gt; or &lt;code&gt;postman&lt;/code&gt;.&lt;/p&gt;
&lt;h2 id=&quot;heading-userslogin&quot;&gt;&lt;code&gt;/users/login&lt;/code&gt;&lt;/h2&gt;
&lt;h3 id=&quot;heading-when-the-email-and-password-match&quot;&gt;When the email and password match&lt;/h3&gt;
&lt;ul&gt;
&lt;li&gt;&lt;code&gt;REQUEST&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;curl -s -L -X POST &lt;span class=&quot;hljs-string&quot;&gt;&#39;http://localhost:8080/users/login&#39;&lt;/span&gt; -H &lt;span class=&quot;hljs-string&quot;&gt;&#39;Content-Type: application/json&#39;&lt;/span&gt; --data-raw &lt;span class=&quot;hljs-string&quot;&gt;&#39;{
    &quot;email&quot;:&quot;saileshbro@gmail.com&quot;,
    &quot;password&quot;:&quot;6aMj@UBByu%7BzN^C9tMe#Te4b!4cJrXwwFi#HgKrQ&amp;amp;g&amp;amp;ddNN6eHQ94vd5SuJtEc%7^H6L^xews8soG@R7GnW*RvfJVMaKEuBXNtVtbP5!3^qs*n!Z%87q8eRJmKFUHg&quot;
}&#39;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;ul&gt;
&lt;li&gt;&lt;code&gt;RESPONSE&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-json&quot;&gt;{
  &lt;span class=&quot;hljs-attr&quot;&gt;&quot;token&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjQ4ODY5Yjc4LWEwMjgtNGMwNS1hN2QzLTQ5OTQ2Mzk4NDI2NSIsIm5hbWUiOiJTYWlsZXNoIERhaGFsIiwiZW1haWwiOiJzYWlsZXNoQGdtYWlsLmNvbSIsImNyZWF0ZWRfYXQiOiIyMDIzLTAxLTMwVDA5OjU3OjQ5LjExODM2MVoiLCJwYXNzd29yZCI6IiQyYSQxMCRGSDVDc2N1Y0VuLlNwWlZmSWFtRGwuZzRMaDFhd2ltbVRMS05yU2NORW1qT25lSFZHOE4wLiIsImlhdCI6MTY3NTA2MDA0MH0.qvzLWgAEphlYqZztoBf7Bvag6hO1qkp44hUwl78CMVo&quot;&lt;/span&gt;,
  &lt;span class=&quot;hljs-attr&quot;&gt;&quot;user&quot;&lt;/span&gt;: {
    &lt;span class=&quot;hljs-attr&quot;&gt;&quot;id&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;48869b78-a028-4c05-a7d3-499463984265&quot;&lt;/span&gt;,
    &lt;span class=&quot;hljs-attr&quot;&gt;&quot;name&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;Sailesh Dahal&quot;&lt;/span&gt;,
    &lt;span class=&quot;hljs-attr&quot;&gt;&quot;email&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;saileshbro@gmail.com&quot;&lt;/span&gt;,
    &lt;span class=&quot;hljs-attr&quot;&gt;&quot;created_at&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;2023-01-30T09:57:49.118361Z&quot;&lt;/span&gt;
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;h3 id=&quot;heading-when-the-email-or-password-does-not-match&quot;&gt;When the email or password does not match.&lt;/h3&gt;
&lt;ul&gt;
&lt;li&gt;&lt;code&gt;REQUEST&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;curl -s -L -X POST &lt;span class=&quot;hljs-string&quot;&gt;&#39;http://localhost:8080/users/login&#39;&lt;/span&gt; -H &lt;span class=&quot;hljs-string&quot;&gt;&#39;Content-Type: application/json&#39;&lt;/span&gt; --data-raw &lt;span class=&quot;hljs-string&quot;&gt;&#39;{
    &quot;email&quot;:&quot;sa@gmail.com&quot;,
    &quot;name&quot;:&quot;Sailesh Dahal&quot;,
    &quot;password&quot;:&quot;6aMj@UBByu%7BzN^C9tMe#Te4b!4cJrXwwFi#HgKrQ&amp;amp;g&amp;amp;ddNN6eHQ94vd5SuJtEc%7^H6L^xews8soG@R7GnW*RvfJVMaKEuBXNtVtbP5!3^qs*n!Z%87q8eRJmKFUHg&quot;
}&#39;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;ul&gt;
&lt;li&gt;&lt;code&gt;RESPONSE&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-json&quot;&gt;{ &lt;span class=&quot;hljs-attr&quot;&gt;&quot;message&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;Invalid email or password&quot;&lt;/span&gt; }
&lt;/code&gt;&lt;/pre&gt;
&lt;h2 id=&quot;heading-userssignup&quot;&gt;&lt;code&gt;/users/signup&lt;/code&gt;&lt;/h2&gt;
&lt;h3 id=&quot;heading-when-the-data-is-not-valid&quot;&gt;When the data is not valid&lt;/h3&gt;
&lt;ul&gt;
&lt;li&gt;&lt;code&gt;REQUEST&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;curl -s -L -X POST &lt;span class=&quot;hljs-string&quot;&gt;&#39;http://localhost:8080/users/signup&#39;&lt;/span&gt; -H &lt;span class=&quot;hljs-string&quot;&gt;&#39;Content-Type: application/json&#39;&lt;/span&gt; --data-raw &lt;span class=&quot;hljs-string&quot;&gt;&#39;{
    &quot;email&quot;:&quot;sailes@gmail.com&quot;,
    &quot;password&quot;:&quot;6aMj@UBByu&quot;
}&#39;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;ul&gt;
&lt;li&gt;&lt;code&gt;RESPONSE&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-json&quot;&gt;{
  &lt;span class=&quot;hljs-attr&quot;&gt;&quot;message&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;Validation failed&quot;&lt;/span&gt;,
  &lt;span class=&quot;hljs-attr&quot;&gt;&quot;errors&quot;&lt;/span&gt;: {
    &lt;span class=&quot;hljs-attr&quot;&gt;&quot;name&quot;&lt;/span&gt;: [&lt;span class=&quot;hljs-string&quot;&gt;&quot;Name is required&quot;&lt;/span&gt;]
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;h3 id=&quot;heading-when-there-is-no-user-with-the-given-email-it-will-create-a-new-user-and-return-the-same-response-as-userslogin&quot;&gt;When there is no user with the given email, it will create a new user and return the same response as &lt;code&gt;/users/login&lt;/code&gt;.&lt;/h3&gt;
&lt;ul&gt;
&lt;li&gt;&lt;code&gt;REQUEST&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;curl -s -L -X POST &lt;span class=&quot;hljs-string&quot;&gt;&#39;http://localhost:8080/users/signup&#39;&lt;/span&gt; -H &lt;span class=&quot;hljs-string&quot;&gt;&#39;Content-Type: application/json&#39;&lt;/span&gt; --data-raw &lt;span class=&quot;hljs-string&quot;&gt;&#39;{
    &quot;email&quot;:&quot;sailesh12@gmail.com&quot;,
    &quot;name&quot;:&quot;Sailesh Dahal&quot;,
    &quot;password&quot;:&quot;6aMj123&quot;
}&#39;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;ul&gt;
&lt;li&gt;&lt;code&gt;RESPONSE&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-json&quot;&gt;{
  &lt;span class=&quot;hljs-attr&quot;&gt;&quot;token&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImM1ODE2YWQ0LTNkODctNDUzZC1hZmFkLTUwMzljY2YxZjdjNyIsIm5hbWUiOiJTYWlsZXNoIERhaGFsIiwiZW1haWwiOiJzYWlsZXNoMTJAZ21haWwuY29tIiwiY3JlYXRlZF9hdCI6IjIwMjMtMDEtMzBUMDY6Mjg6MzUuMzkyMjM4WiIsInBhc3N3b3JkIjoiJDJhJDEwJHRuTllGM3FHQmlPT1dKeHVacm1MaU91SHhBMU1HQlNMcmoxYS5ndHY2TTNCMHpmRW5Dc1dLIiwiaWF0IjoxNjc1MDYwMTE0fQ.aUpo9HXTFmdmkTsfGoTp0mcK0OJ_fFuwZArqyNFpKvQ&quot;&lt;/span&gt;,
  &lt;span class=&quot;hljs-attr&quot;&gt;&quot;user&quot;&lt;/span&gt;: {
    &lt;span class=&quot;hljs-attr&quot;&gt;&quot;id&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;c5816ad4-3d87-453d-afad-5039ccf1f7c7&quot;&lt;/span&gt;,
    &lt;span class=&quot;hljs-attr&quot;&gt;&quot;name&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;Sailesh Dahal&quot;&lt;/span&gt;,
    &lt;span class=&quot;hljs-attr&quot;&gt;&quot;email&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;sailesh12@gmail.com&quot;&lt;/span&gt;,
    &lt;span class=&quot;hljs-attr&quot;&gt;&quot;created_at&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;2023-01-30T06:28:35.392238Z&quot;&lt;/span&gt;
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;h3 id=&quot;heading-when-there-is-a-user-with-the-given-email-it-will-return-the-following-response&quot;&gt;When there is a user with the given email, it will return the following response.&lt;/h3&gt;
&lt;ul&gt;
&lt;li&gt;&lt;code&gt;REQUEST&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;curl -s -L -X POST &lt;span class=&quot;hljs-string&quot;&gt;&#39;http://localhost:8080/users/signup&#39;&lt;/span&gt; -H &lt;span class=&quot;hljs-string&quot;&gt;&#39;Content-Type: application/json&#39;&lt;/span&gt; --data-raw &lt;span class=&quot;hljs-string&quot;&gt;&#39;{
    &quot;email&quot;:&quot;sailesh12@gmail.com&quot;,
    &quot;name&quot;:&quot;Sailesh Dahal&quot;,
    &quot;password&quot;:&quot;6aMj123&quot;
}&#39;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;ul&gt;
&lt;li&gt;&lt;code&gt;RESPONSE&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-json&quot;&gt;{
  &lt;span class=&quot;hljs-attr&quot;&gt;&quot;message&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;Email already in use&quot;&lt;/span&gt;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;hr /&gt;
&lt;h1 id=&quot;heading-protecting-routes&quot;&gt;Protecting Routes&lt;/h1&gt;
&lt;blockquote&gt;
&lt;p&gt;Locking Down: Secure Your Endpoints 🔒&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;Now, we can protect our routes by adding middleware to the routes. We will check for the &lt;code&gt;Authorization&lt;/code&gt; header and verify the token. We can intercept all the requests going to &lt;code&gt;/todos/*&lt;/code&gt; and check for the token.&lt;/p&gt;
&lt;p&gt;We can do this by creating a new authorization middleware. We will create a new file &lt;code&gt;backend/lib/middlewares/authorization_middleware.dart&lt;/code&gt;. Before that, let&#39;s create a new exception for unauthorized requests.&lt;/p&gt;
&lt;h2 id=&quot;heading-creating-unauthorizedexception&quot;&gt;Creating &lt;code&gt;UnauthorizedException&lt;/code&gt;&lt;/h2&gt;
&lt;p&gt;When the token is not valid, we will throw an &lt;code&gt;UnauthorizedException&lt;/code&gt; which will be handled by the &lt;code&gt;ExceptionHandlerMiddleware&lt;/code&gt;.&lt;/p&gt;
&lt;p&gt;In &lt;code&gt;exceptions&lt;/code&gt; package, we will create a new exception called &lt;code&gt;UnauthorizedException&lt;/code&gt; in &lt;code&gt;exceptions/lib/src/http_exception/unauthorized_exception.dart&lt;/code&gt;&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;dart:io&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:exceptions/src/http_exception/http_exception.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;UnauthorizedException&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;extends&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;HttpException&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; UnauthorizedException&lpar;{
    &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; message = &lt;span class=&quot;hljs-string&quot;&gt;&#39;Unauthorized&#39;&lt;/span&gt;,
    &lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;.errors = &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; {},
  }&rpar; : &lt;span class=&quot;hljs-keyword&quot;&gt;super&lt;/span&gt;&lpar;message, HttpStatus.unauthorized&rpar;;

  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;&amp;gt;&amp;gt; errors;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;blockquote&gt;
&lt;p&gt;💡 Make sure to export the exception in &lt;code&gt;http_exception.dart&lt;/code&gt; file.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;./bad_request_exception.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;./not_found_exception.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;./unauthorized_exception.dart&#39;&lt;/span&gt;;
&lt;/code&gt;&lt;/pre&gt;
&lt;blockquote&gt;
&lt;p&gt;💡 Make sure to run &lt;code&gt;flutter pub run build_runner build&lt;/code&gt; to generate the code.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;h2 id=&quot;heading-creating-authorizationmiddleware&quot;&gt;Creating &lt;code&gt;AuthorizationMiddleware&lt;/code&gt;&lt;/h2&gt;
&lt;blockquote&gt;
&lt;p&gt;🔒 Securing Endpoints with AuthorizationMiddleware 🛡&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;Now, we can create the &lt;code&gt;AuthorizationMiddleware&lt;/code&gt; in &lt;code&gt;backend/lib/middlewares/authorization_middleware.dart&lt;/code&gt;.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;dart:io&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/db/database_connection.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/services/jwt_service.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/todo/controller/todo_controller.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/todo/data_source/todo_data_source_impl.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/todo/repositories/todo_repository_impl.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dart_frog/dart_frog.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:data_source/data_source.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:exceptions/exceptions.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:models/models.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:repository/repository.dart&#39;&lt;/span&gt;;

Handler authorizationMiddleware&lpar;Handler handler&rpar; {
  &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; &lpar;context&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;try&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; request = context.request;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; authHeader = request.headers[HttpHeaders.authorizationHeader] ?? &lt;span class=&quot;hljs-string&quot;&gt;&#39;&#39;&lt;/span&gt;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; token = authHeader.replaceFirst&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;Bearer &#39;&lt;/span&gt;, &lt;span class=&quot;hljs-string&quot;&gt;&#39;&#39;&lt;/span&gt;&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;token.isEmpty&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; UnauthorizedException&lpar;&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; jwtService = context.read&amp;lt;JWTService&amp;gt;&lpar;&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; decoded = jwtService.verify&lpar;token&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; decodedUser = User.fromJson&lpar;decoded&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; userRepo = context.read&amp;lt;UserRepository&amp;gt;&lpar;&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; user = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; userRepo.getUserById&lpar;decodedUser.id&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;user.isLeft&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; UnauthorizedException&lpar;&rpar;;
      context = _handleAuthDependencies&lpar;context, user.right&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; handler&lpar;context&rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;on&lt;/span&gt; UnauthorizedException &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Response.json&lpar;
        body: {&lt;span class=&quot;hljs-string&quot;&gt;&#39;message&#39;&lt;/span&gt;: e.message},
        statusCode: e.statusCode,
      &rpar;;
    }
  };
}

RequestContext _handleAuthDependencies&lpar;
  RequestContext context,
  User user,
&rpar; {
  &lt;span class=&quot;hljs-keyword&quot;&gt;late&lt;/span&gt; RequestContext updatedContext;
  updatedContext = context.provide&amp;lt;User&amp;gt;&lpar;&lpar;&rpar; =&amp;gt; user&rpar;;
  &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; updatedContext;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Here, we are checking for the &lt;code&gt;Authorization&lt;/code&gt; header and verifying the token. If the token is valid, we are adding the &lt;code&gt;User&lt;/code&gt; object to the context, so that we can get the logged-in user later from the provider.&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;If the token is invalid, we will return a &lt;code&gt;401&lt;/code&gt; response.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;h2 id=&quot;heading-updating-auth-dependencies&quot;&gt;Updating auth dependencies&lt;/h2&gt;
&lt;p&gt;Now, since we will have to add a &lt;code&gt;user_id&lt;/code&gt; whenever, we will create a todo, we will have to pass the logged-in user to the TodoDataSource. We will update the &lt;code&gt;TodoDataSourceImpl&lt;/code&gt; to accept the &lt;code&gt;User&lt;/code&gt; object from the constructor.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;TodoDataSourceImpl&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;implements&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;TodoDataSource&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-comment&quot;&gt;/// &lt;span class=&quot;markdown&quot;&gt;{@macro todo&lt;span class=&quot;hljs-emphasis&quot;&gt;_data_&lt;/span&gt;source&lt;span class=&quot;hljs-emphasis&quot;&gt;_impl}&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;
  &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; TodoDataSourceImpl&lpar;&lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;._databaseConnection, &lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;.user&rpar;;
  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; DatabaseConnection _databaseConnection;

  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; User user;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Also, we will update &lt;code&gt;createTodo&lt;/code&gt; and &lt;code&gt;updateTodo&lt;/code&gt; methods to add the &lt;code&gt;user_id&lt;/code&gt;.&lt;/p&gt;
&lt;h3 id=&quot;heading-update-createtodo-method&quot;&gt;Update &lt;code&gt;createTodo&lt;/code&gt; method&lt;/h3&gt;
&lt;pre&gt;&lt;code class=&quot;lang-diff&quot;&gt;  @override
  Future&amp;lt;Todo&amp;gt; createTodo&lpar;CreateTodoDto todo&rpar; async {
    try {
      await _databaseConnection.connect&lpar;&rpar;;
      final result = await _databaseConnection.db.query&lpar;
        &#39;&#39;&#39;
&lt;span class=&quot;hljs-deletion&quot;&gt;-       INSERT INTO todos &lpar;title, description, completed&rpar;&lt;/span&gt;
&lt;span class=&quot;hljs-addition&quot;&gt;+       INSERT INTO todos &lpar;title, description, completed, user_id&rpar;&lt;/span&gt;
&lt;span class=&quot;hljs-deletion&quot;&gt;-       VALUES &lpar;@title, @description, @completed&rpar; RETURNING *&lt;/span&gt;
&lt;span class=&quot;hljs-addition&quot;&gt;+       VALUES &lpar;@title, @description, @completed, @user_id&rpar; RETURNING *&lt;/span&gt;
        &#39;&#39;&#39;,
        substitutionValues: {
          &#39;title&#39;: todo.title,
          &#39;description&#39;: todo.description,
          &#39;completed&#39;: false,
&lt;span class=&quot;hljs-addition&quot;&gt;+         &#39;user_id&#39;: _user.id,&lt;/span&gt;
        },
      &rpar;;
      if &lpar;result.affectedRowCount == 0&rpar; {
        throw const ServerException&lpar;&#39;Failed to create todo&#39;&rpar;;
      }
      final todoMap = result.first.toColumnMap&lpar;&rpar;;
      return Todo&lpar;
        id: todoMap[&#39;id&#39;] as int,
&lt;span class=&quot;hljs-addition&quot;&gt;+       userId: todoMap[&#39;user_id&#39;] as String,&lt;/span&gt;
        title: todoMap[&#39;title&#39;] as String,
        description: todoMap[&#39;description&#39;] as String,
        createdAt: todoMap[&#39;created_at&#39;] as DateTime,
      &rpar;;
    } on PostgreSQLException catch &lpar;e&rpar; {
      throw ServerException&lpar;e.message ?? &#39;Unexpected error&#39;&rpar;;
    } finally {
      await _databaseConnection.close&lpar;&rpar;;
    }
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;h3 id=&quot;heading-update-updatetodo-method&quot;&gt;Update &lt;code&gt;updateTodo&lt;/code&gt; method&lt;/h3&gt;
&lt;pre&gt;&lt;code class=&quot;lang-diff&quot;&gt;      final result = await _databaseConnection.db.query&lpar;
        &#39;&#39;&#39;
        UPDATE todos
        SET title = COALESCE&lpar;@new_title, title&rpar;,
            description = COALESCE&lpar;@new_description, description&rpar;,
            completed = COALESCE&lpar;@new_completed, completed&rpar;,
            updated_at = current_timestamp
        WHERE id = @id
&lt;span class=&quot;hljs-addition&quot;&gt;+       AND user_id = @user_id&lt;/span&gt;
        RETURNING *
        &#39;&#39;&#39;,
        substitutionValues: {
          &#39;id&#39;: id,
&lt;span class=&quot;hljs-addition&quot;&gt;+         &#39;user_id&#39;: _user.id,&lt;/span&gt;
          &#39;new_title&#39;: todo.title,
          &#39;new_description&#39;: todo.description,
          &#39;new_completed&#39;: todo.completed,
        },
      &rpar;;
&lt;/code&gt;&lt;/pre&gt;
&lt;h3 id=&quot;heading-update-todo-model-to-add-userid&quot;&gt;Update &lt;code&gt;Todo&lt;/code&gt; model to add &lt;code&gt;userId&lt;/code&gt;&lt;/h3&gt;
&lt;p&gt;We will also add the missing &lt;code&gt;userId&lt;/code&gt; from &lt;code&gt;Todo&lt;/code&gt; model.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-diff&quot;&gt;  factory Todo&lpar;{
    required TodoId id,
&lt;span class=&quot;hljs-addition&quot;&gt;+   required UserId userId,&lt;/span&gt;
    required String title,
    @Default&lpar;&#39;&#39;&rpar; String description,
    @Default&lpar;false&rpar; bool completed,
    @DateTimeConverter&lpar;&rpar; required DateTime createdAt,
    @DateTimeConverterNullable&lpar;&rpar; DateTime? updatedAt,
  }&rpar; = _Todo;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Now, once this is done, we will update the &lt;code&gt;_handleAuthDependencies&lt;/code&gt; method in &lt;code&gt;authorization_middleware.dart&lt;/code&gt; as&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;RequestContext _handleAuthDependencies&lpar;
  RequestContext context,
  User user,
&rpar; {
  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; db = context.read&amp;lt;DatabaseConnection&amp;gt;&lpar;&rpar;;
  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; todoDs = TodoDataSourceImpl&lpar;db, user&rpar;;
  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; todoRepo = TodoRepositoryImpl&lpar;todoDs&rpar;;
  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; todoController = TodoController&lpar;todoRepo&rpar;;
  &lt;span class=&quot;hljs-keyword&quot;&gt;late&lt;/span&gt; RequestContext updatedContext;
  updatedContext = context.provide&amp;lt;User&amp;gt;&lpar;&lpar;&rpar; =&amp;gt; user&rpar;;
  updatedContext = updatedContext.provide&amp;lt;TodoController&amp;gt;&lpar;&lpar;&rpar; =&amp;gt; todoController&rpar;;
  updatedContext = updatedContext.provide&amp;lt;TodoRepository&amp;gt;&lpar;&lpar;&rpar; =&amp;gt; todoRepo&rpar;;
  updatedContext = updatedContext.provide&amp;lt;TodoDataSource&amp;gt;&lpar;&lpar;&rpar; =&amp;gt; todoDs&rpar;;
  &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; updatedContext;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;h2 id=&quot;heading-using-authorizationmiddleware&quot;&gt;Using &lt;code&gt;AuthorizationMiddleware&lt;/code&gt;&lt;/h2&gt;
&lt;blockquote&gt;
&lt;p&gt;Applying &lt;code&gt;AuthorizationMiddleware&lt;/code&gt; to routes&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;Let&#39;s create a new middleware in &lt;code&gt;backend/routes/todos/_middleware.dart&lt;/code&gt; and add the following code.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/middlewares/authorization_middleware.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dart_frog/dart_frog.dart&#39;&lt;/span&gt;;

Handler middleware&lpar;Handler handler&rpar; =&amp;gt; authorizationMiddleware&lpar;handler&rpar;;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Since this middleware lies inside &lt;code&gt;routes/todos&lt;/code&gt;, all the &lt;code&gt;/todos/*&lt;/code&gt; routes will be intercepted by this middleware. This means that all the &lt;code&gt;/todos/*&lt;/code&gt; routes will be protected and if the user tries to access these routes without a valid token, it will return a &lt;code&gt;401&lt;/code&gt; response.&lt;/p&gt;
&lt;hr /&gt;
&lt;h1 id=&quot;heading-testing-protected-todos-routes&quot;&gt;Testing protected &lt;code&gt;/todos/*&lt;/code&gt; routes&lt;/h1&gt;
&lt;blockquote&gt;
&lt;p&gt;Putting updated routes to the Test 🧪&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;If we try to access the &lt;code&gt;/todos/*&lt;/code&gt; routes without a valid token, it will return a &lt;code&gt;401&lt;/code&gt; response. We can test this by running the following command.&lt;/p&gt;
&lt;h2 id=&quot;heading-get-todos&quot;&gt;GET /todos&lt;/h2&gt;
&lt;ul&gt;
&lt;li&gt;&lt;code&gt;REQUEST&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;curl -s -L -X GET &lt;span class=&quot;hljs-string&quot;&gt;&#39;http://localhost:8080/todos&#39;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;ul&gt;
&lt;li&gt;&lt;code&gt;RESPONSE&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-json&quot;&gt;{
  &lt;span class=&quot;hljs-attr&quot;&gt;&quot;message&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;Unauthorized&quot;&lt;/span&gt;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;ul&gt;
&lt;li&gt;&lt;code&gt;REQUEST&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;curl -s -L -X GET &lt;span class=&quot;hljs-string&quot;&gt;&#39;http://localhost:8080/todos&#39;&lt;/span&gt; -H &lt;span class=&quot;hljs-string&quot;&gt;&#39;Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY5ZWFkZTg3LWRhNWUtNDRjZC1iNTRlLTQ3NGE4NWQ4ZGVlNCIsIm5hbWUiOiJTYWlsZXNoIERhaGFsIiwiZW1haWwiOiJzYWlsZXNoYnJvQGdtYWlsLmNvbSIsImNyZWF0ZWRfYXQiOiIyMDIzLTAxLTIzVDIyOjU0OjM4Ljg2NDkxMloiLCJwYXNzd29yZCI6IiQyYSQxMCR6VjBTZlI3cUpHOHlCelJWWThtNkRlMWo0UUtHL2VRdXl6NzduQ1lBL1luZENtb1ZSbzB0RyIsImlhdCI6MTY3NDQ5Mzc3OX0.W36mHXKFrxZDhz0Hrxt0Cmrz3WNVexiAZe2KAjrWMaE&#39;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;ul&gt;
&lt;li&gt;&lt;code&gt;RESPONSE&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-json&quot;&gt;[
  {
    &lt;span class=&quot;hljs-attr&quot;&gt;&quot;id&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-number&quot;&gt;76&lt;/span&gt;,
    &lt;span class=&quot;hljs-attr&quot;&gt;&quot;user_id&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;69eade87-da5e-44cd-b54e-474a85d8dee4&quot;&lt;/span&gt;,
    &lt;span class=&quot;hljs-attr&quot;&gt;&quot;title&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;this is a title asdf&quot;&lt;/span&gt;,
    &lt;span class=&quot;hljs-attr&quot;&gt;&quot;description&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;Not so great description asdf&quot;&lt;/span&gt;,
    &lt;span class=&quot;hljs-attr&quot;&gt;&quot;completed&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-literal&quot;&gt;false&lt;/span&gt;,
    &lt;span class=&quot;hljs-attr&quot;&gt;&quot;created_at&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;2023-01-23T22:56:31.686023Z&quot;&lt;/span&gt;,
    &lt;span class=&quot;hljs-attr&quot;&gt;&quot;updated_at&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;2023-01-30T04:08:06.349549Z&quot;&lt;/span&gt;
  }
]
&lt;/code&gt;&lt;/pre&gt;
&lt;h2 id=&quot;heading-post-todos&quot;&gt;POST /todos&lt;/h2&gt;
&lt;ul&gt;
&lt;li&gt;&lt;code&gt;REQUEST&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;curl -s -L -X POST &lt;span class=&quot;hljs-string&quot;&gt;&#39;http://localhost:8080/todos&#39;&lt;/span&gt; -H &lt;span class=&quot;hljs-string&quot;&gt;&#39;Content-Type: application/json&#39;&lt;/span&gt; --data-raw &lt;span class=&quot;hljs-string&quot;&gt;&#39;{
    &quot;title&quot;:&quot;this is a title asdf&quot;,
    &quot;description&quot;:&quot;Not so great description asdf&quot;
}&#39;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;ul&gt;
&lt;li&gt;&lt;code&gt;RESPONSE&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-json&quot;&gt;{
  &lt;span class=&quot;hljs-attr&quot;&gt;&quot;message&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;Unauthorized&quot;&lt;/span&gt;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;ul&gt;
&lt;li&gt;&lt;code&gt;REQUEST&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;curl -s -L -X POST &lt;span class=&quot;hljs-string&quot;&gt;&#39;http://localhost:8080/todos&#39;&lt;/span&gt; -H &lt;span class=&quot;hljs-string&quot;&gt;&#39;Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY5ZWFkZTg3LWRhNWUtNDRjZC1iNTRlLTQ3NGE4NWQ4ZGVlNCIsIm5hbWUiOiJTYWlsZXNoIERhaGFsIiwiZW1haWwiOiJzYWlsZXNoYnJvQGdtYWlsLmNvbSIsImNyZWF0ZWRfYXQiOiIyMDIzLTAxLTIzVDIyOjU0OjM4Ljg2NDkxMloiLCJwYXNzd29yZCI6IiQyYSQxMCR6VjBTZlI3cUpHOHlCelJWWThtNkRlMWo0UUtHL2VRdXl6NzduQ1lBL1luZENtb1ZSbzB0RyIsImlhdCI6MTY3NDQ5Mzc3OX0.W36mHXKFrxZDhz0Hrxt0Cmrz3WNVexiAZe2KAjrWMaE&#39;&lt;/span&gt; -H &lt;span class=&quot;hljs-string&quot;&gt;&#39;Content-Type: application/json&#39;&lt;/span&gt; --data-raw &lt;span class=&quot;hljs-string&quot;&gt;&#39;{
    &quot;title&quot;:&quot;this is a title asdf&quot;,
    &quot;description&quot;:&quot;Not so great description asdf&quot;
}&#39;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;ul&gt;
&lt;li&gt;&lt;code&gt;RESPONSE&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;pre&gt;&lt;code class=&quot;lang-json&quot;&gt;{
  &lt;span class=&quot;hljs-attr&quot;&gt;&quot;id&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-number&quot;&gt;79&lt;/span&gt;,
  &lt;span class=&quot;hljs-attr&quot;&gt;&quot;user_id&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;69eade87-da5e-44cd-b54e-474a85d8dee4&quot;&lt;/span&gt;,
  &lt;span class=&quot;hljs-attr&quot;&gt;&quot;title&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;this is a title asdf&quot;&lt;/span&gt;,
  &lt;span class=&quot;hljs-attr&quot;&gt;&quot;description&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;Not so great description asdf&quot;&lt;/span&gt;,
  &lt;span class=&quot;hljs-attr&quot;&gt;&quot;completed&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-literal&quot;&gt;false&lt;/span&gt;,
  &lt;span class=&quot;hljs-attr&quot;&gt;&quot;created_at&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&quot;2023-01-30T07:10:10.102358Z&quot;&lt;/span&gt;,
  &lt;span class=&quot;hljs-attr&quot;&gt;&quot;updated_at&quot;&lt;/span&gt;: &lt;span class=&quot;hljs-literal&quot;&gt;null&lt;/span&gt;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Similarly, we can test the other routes as well 🥳&lt;/p&gt;
&lt;hr /&gt;
&lt;p&gt;🎉 Congrats, we&#39;ve made it to the end of Part 6! 🚀 We&#39;ve successfully added user authentication with JWT to our &lt;a target=&quot;_blank&quot; href=&quot;https://dartfrog.vgv.dev/&quot;&gt;dart_frog&lt;/a&gt; backend.&lt;/p&gt;
&lt;p&gt;It&#39;s been an incredible adventure, and we&#39;ve gone a long way since Part 1. Using Dart and Flutter, we created a full-stack to-do application. But our task does not end there. We haven&#39;t addressed testing yet in this course, but it&#39;s an important aspect of developing any program. Let us know in the comments if you&#39;d want to learn more about testing your code in all of the modules we&#39;ve written in this series.&lt;/p&gt;
&lt;p&gt;As always, you can refer back to the GitHub repo for this tutorial at &lt;a target=&quot;_blank&quot; href=&quot;https://github.com/saileshbro/full_stack_todo_dart&quot;&gt;https://github.com/saileshbro/full_stack_todo_dart&lt;/a&gt; if you need any help. Don&#39;t forget to give it a  and help spread the word about the initiative. Also, if you get stuck or want assistance, please submit an issue or, better yet, contribute a pull request.&lt;/p&gt;
&lt;p&gt;Thank you for joining me on this journey; let&#39;s create even more wonderful applications together. Have fun coding! 💻&lt;/p&gt;
 

 - 🌮[🚀 Building a Fullstack App with dart_frog and Flutter in a Monorepo - Part 5](https://saileshdahal.com.np/building-a-fullstack-app-with-dartfrog-and-flutter-in-a-monorepo-part-5) 
 - &lt;p&gt;In the previous part of this series, we set up the foundation for our full-stack to-do application by creating models, data sources, repositories, exceptions and handling failures. In this part, we will take it to the next level by:&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;&lt;p&gt;Scaffolding an empty &lt;a target=&quot;_blank&quot; href=&quot;https://flutter.dev&quot;&gt;&lt;code&gt;flutter&lt;/code&gt;&lt;/a&gt; project&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;Importing necessary dependencies&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;Creating a folder structure&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;Connecting our front end with the backend using &lt;code&gt;TodosHttpClient&lt;/code&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;Setting up dependency injection using &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/injectable&quot;&gt;&lt;code&gt;injectable&lt;/code&gt;&lt;/a&gt; and &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/get_it&quot;&gt;&lt;code&gt;get_it&lt;/code&gt;&lt;/a&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;Implementing &lt;code&gt;TodosRemoteDataSource&lt;/code&gt; and &lt;code&gt;TodoRepository&lt;/code&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;Handling errors as &lt;code&gt;NetworkFailure&lt;/code&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;Creating &lt;code&gt;NetworkException&lt;/code&gt; and &lt;code&gt;DioNetworkException&lt;/code&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;Creating &lt;code&gt;NetworkErrorInterceptor&lt;/code&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;Creating &lt;code&gt;ShowTodosView&lt;/code&gt; and &lt;code&gt;ShowTodosViewModel&lt;/code&gt; to show the fetched todos&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;Creating &lt;code&gt;MaintainTodoView&lt;/code&gt; and &lt;code&gt;MaintainTodoViewModel&lt;/code&gt; to maintain the todos&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;Adding linting with &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/very_good_analysis&quot;&gt;&lt;code&gt;very_good_analysis&lt;/code&gt;&lt;/a&gt; to make sure our code is clean.&lt;/p&gt;
&lt;/li&gt;
&lt;/ul&gt;
&lt;p&gt;We will be diving deeper into the world of flutter making use of the best practices, packages and libraries available for flutter. And by the end of this part, we will have a fully functional front end for our to-do application.&lt;/p&gt;
&lt;div class=&quot;embed-wrapper&quot;&gt;&lt;div class=&quot;embed-loading&quot;&gt;&lt;div class=&quot;loadingRow&quot;&gt;&lt;/div&gt;&lt;div class=&quot;loadingRow&quot;&gt;&lt;/div&gt;&lt;/div&gt;&lt;a class=&quot;embed-card&quot; href=&quot;https://www.youtube.com/shorts/7XJHrpCpzUo?feature=share&quot;&gt;https://www.youtube.com/shorts/7XJHrpCpzUo?feature=share&lt;/a&gt;&lt;/div&gt;
&lt;p&gt; &lt;/p&gt;
&lt;p&gt;Don&#39;t forget to check the GitHub repo for this tutorial at &lt;a target=&quot;_blank&quot; href=&quot;https://github.com/saileshbro/full_stack_todo_dart&quot;&gt;GitHub&lt;/a&gt; if you need a little help along the way. Let&#39;s get started 🚀&lt;/p&gt;
&lt;h1 id=&quot;heading-scaffolding-frontend&quot;&gt;🚀 Scaffolding Frontend&lt;/h1&gt;
&lt;blockquote&gt;
&lt;p&gt;🌟 Frontend is about to shine.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;We will begin by scaffolding an empty Flutter project using the command:&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;flutter create --project-name fullstack_todo --org np.com.saileshdahal frontend
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;This will create an empty flutter project in &lt;code&gt;frontend&lt;/code&gt; directory. We will then do some initial setup, and add some dependencies.&lt;/p&gt;
&lt;h2 id=&quot;heading-importing-necessary-dependencies&quot;&gt;Importing necessary dependencies 📦&lt;/h2&gt;
&lt;blockquote&gt;
&lt;p&gt;Time to bring in the big guns! 💪 Let&#39;s import those dependencies&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;We will import the necessary dependencies in the &lt;code&gt;pubspec.yaml&lt;/code&gt; file. The dependencies that we are using are as follows.&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;&lt;p&gt;&lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/dio&quot;&gt;&lt;code&gt;dio&lt;/code&gt;&lt;/a&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/either_dart&quot;&gt;&lt;code&gt;either_dart&lt;/code&gt;&lt;/a&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/flutter_hooks&quot;&gt;&lt;code&gt;flutter_hooks&lt;/code&gt;&lt;/a&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/get_it&quot;&gt;&lt;code&gt;get_it&lt;/code&gt;&lt;/a&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/injectable&quot;&gt;&lt;code&gt;injectable&lt;/code&gt;&lt;/a&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/stacked&quot;&gt;&lt;code&gt;stacked&lt;/code&gt;&lt;/a&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/stacked_services&quot;&gt;&lt;code&gt;stacked_services&lt;/code&gt;&lt;/a&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/build_runner&quot;&gt;&lt;code&gt;build_runner&lt;/code&gt;&lt;/a&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/very_good_analysis&quot;&gt;&lt;code&gt;very_good_analysis&lt;/code&gt;&lt;/a&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/retrofit&quot;&gt;&lt;code&gt;retrofit&lt;/code&gt;&lt;/a&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;/ul&gt;
&lt;p&gt;These dependencies will allow us to easily handle communication with the backend, handle state management, and implement a clean and maintainable codebase for our application.&lt;/p&gt;
&lt;p&gt;To install you can use the following command:&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;flutter pub add dio either_dart flutter_hooks get_it injectable stacked stacked_services retrofit

flutter pub add --dev build_runner very_good_analysis stacked_generator injectable_generator retrofit_generator
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;We will also include the packages that we have built, once done &lt;code&gt;pubspec.yaml&lt;/code&gt; should look something like this.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-yaml&quot;&gt;&lt;span class=&quot;hljs-attr&quot;&gt;dependencies:&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;data_source:&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;path:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;../data_source&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;dio:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^4.0.6&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;either_dart:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^0.3.0&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;exceptions:&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;path:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;../exceptions&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;failures:&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;path:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;../failures&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;flutter:&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;sdk:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;flutter&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;flutter_hooks:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^0.18.5+1&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;get_it:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^7.2.0&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;injectable:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^2.1.0&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;models:&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;path:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;../models&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;repository:&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;path:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;../repository&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;retrofit:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^3.3.1&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;stacked:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^3.0.1&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;stacked_services:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^0.9.9&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;typedefs:&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;path:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;../typedefs&lt;/span&gt;

&lt;span class=&quot;hljs-attr&quot;&gt;dev_dependencies:&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;build_runner:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^2.3.3&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;flutter_test:&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;sdk:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;flutter&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;injectable_generator:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^2.1.3&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;integration_test:&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;sdk:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;flutter&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;mockito:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^5.3.2&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;retrofit_generator:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^4.2.0&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;stacked_generator:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^0.8.3&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;very_good_analysis:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^3.1.0&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;h2 id=&quot;heading-folder-structure&quot;&gt;Folder Structure 📂&lt;/h2&gt;
&lt;p&gt;This is how we will architect our folder structures.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-apache&quot;&gt;.
 &lt;span class=&quot;hljs-attribute&quot;&gt;constants&lt;/span&gt;
 &lt;span class=&quot;hljs-attribute&quot;&gt;core&lt;/span&gt;
    &lt;span class=&quot;hljs-attribute&quot;&gt;app&lt;/span&gt;
    &lt;span class=&quot;hljs-attribute&quot;&gt;di&lt;/span&gt;
    &lt;span class=&quot;hljs-attribute&quot;&gt;network&lt;/span&gt;
        &lt;span class=&quot;hljs-attribute&quot;&gt;exceptions&lt;/span&gt;
        &lt;span class=&quot;hljs-attribute&quot;&gt;interceptors&lt;/span&gt;
 &lt;span class=&quot;hljs-attribute&quot;&gt;data&lt;/span&gt;
    &lt;span class=&quot;hljs-attribute&quot;&gt;data_source&lt;/span&gt;
       &lt;span class=&quot;hljs-attribute&quot;&gt;todo_http_client&lt;/span&gt;
       &lt;span class=&quot;hljs-attribute&quot;&gt;todo_remote_data_source&lt;/span&gt;
    &lt;span class=&quot;hljs-attribute&quot;&gt;repositories&lt;/span&gt;
 &lt;span class=&quot;hljs-attribute&quot;&gt;data_services&lt;/span&gt;
 &lt;span class=&quot;hljs-attribute&quot;&gt;presentation&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;ul&gt;
&lt;li&gt;&lt;p&gt;&lt;code&gt;constants&lt;/code&gt;: This folder will include all the hard-coded constants in our project, such as API endpoints or keys.&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;code&gt;core&lt;/code&gt;: This directory will include all the core functionalities of our app, which are common for all the features. This includes routing, dependency injection, and network interceptors.&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;code&gt;data&lt;/code&gt;: This directory will include all the implementations related to data sources and repositories.&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;code&gt;data_services&lt;/code&gt;: This will include the implementation of services that will be shared across different view models.&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;code&gt;presentation&lt;/code&gt;: This will include the views and view models for creating and listing&lt;/p&gt;
&lt;/li&gt;
&lt;/ul&gt;
&lt;p&gt;The &lt;code&gt;data_source&lt;/code&gt; and &lt;code&gt;repositories&lt;/code&gt; folders contain the implementation of the abstract contracts defined in the &lt;code&gt;data_sources&lt;/code&gt; and &lt;code&gt;repository&lt;/code&gt; packages, respectively. This allows for the separation of concerns and easier maintenance of the codebase.&lt;/p&gt;
&lt;h1 id=&quot;heading-connecting-with-the-backend&quot;&gt;Connecting with the backend 🔌&lt;/h1&gt;
&lt;blockquote&gt;
&lt;p&gt;Let&#39;s get this party started 🎉&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;Let&#39;s start by connecting with the &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/dart_frog&quot;&gt;dart_frog&lt;/a&gt; backend using &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/dio&quot;&gt;dio&lt;/a&gt;. For this, we will create a new class &lt;code&gt;TodosHttpClient&lt;/code&gt;&lt;/p&gt;
&lt;h2 id=&quot;heading-create-todoshttpclient&quot;&gt;Create &lt;code&gt;TodosHttpClient&lt;/code&gt;&lt;/h2&gt;
&lt;p&gt;&lt;code&gt;TodosHttpClient&lt;/code&gt; will be responsible for calling our backend. We will be using &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/retrofit&quot;&gt;&lt;code&gt;retrofit&lt;/code&gt;&lt;/a&gt; to generate the necessary codes to call the backend.&lt;/p&gt;
&lt;p&gt;Retrofit allows us to define our API endpoints as interfaces with annotated methods, and it will automatically generate the necessary code to handle the network requests and convert the JSON responses to Dart objects.&lt;/p&gt;
&lt;p&gt;We will create a new file in &lt;code&gt;data/data_source/todo_http_client/todos_http_client.dart&lt;/code&gt; with the following code.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dio/dio.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:injectable/injectable.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:models/models.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:retrofit/retrofit.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:typedefs/typedefs.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;part&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;todos_http_client.g.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-meta&quot;&gt;@RestApi&lt;/span&gt;&lpar;&rpar;
&lt;span class=&quot;hljs-meta&quot;&gt;@lazySingleton&lt;/span&gt;
&lt;span class=&quot;hljs-keyword&quot;&gt;abstract&lt;/span&gt; &lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;TodosHttpClient&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-meta&quot;&gt;@factoryMethod&lt;/span&gt;
  &lt;span class=&quot;hljs-keyword&quot;&gt;factory&lt;/span&gt; TodosHttpClient&lpar;Dio _dio&rpar; = _TodosHttpClient;

  &lt;span class=&quot;hljs-meta&quot;&gt;@GET&lt;/span&gt;&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;/todos&#39;&lt;/span&gt;&rpar;
  Future&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&amp;lt;Todo&amp;gt;&amp;gt; getAllTodo&lpar;&rpar;;
  &lt;span class=&quot;hljs-meta&quot;&gt;@GET&lt;/span&gt;&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;/todos/{id}&#39;&lt;/span&gt;&rpar;
  Future&amp;lt;Todo&amp;gt; getTodoById&lpar;&lt;span class=&quot;hljs-meta&quot;&gt;@Path&lt;/span&gt;&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;id&#39;&lt;/span&gt;&rpar; TodoId id&rpar;;
  &lt;span class=&quot;hljs-meta&quot;&gt;@POST&lt;/span&gt;&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;/todos&#39;&lt;/span&gt;&rpar;
  Future&amp;lt;Todo&amp;gt; createTodo&lpar;&lt;span class=&quot;hljs-meta&quot;&gt;@Body&lt;/span&gt;&lpar;&rpar; CreateTodoDto todo&rpar;;
  &lt;span class=&quot;hljs-meta&quot;&gt;@PATCH&lt;/span&gt;&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;/todos/{id}&#39;&lt;/span&gt;&rpar;
  Future&amp;lt;Todo&amp;gt; updateTodo&lpar;&lt;span class=&quot;hljs-meta&quot;&gt;@Path&lt;/span&gt;&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;id&#39;&lt;/span&gt;&rpar; TodoId id, &lt;span class=&quot;hljs-meta&quot;&gt;@Body&lt;/span&gt;&lpar;&rpar; UpdateTodoDto todo&rpar;;
  &lt;span class=&quot;hljs-meta&quot;&gt;@DELETE&lt;/span&gt;&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;/todos/{id}&#39;&lt;/span&gt;&rpar;
  Future&amp;lt;&lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt;&amp;gt; deleteTodoById&lpar;&lt;span class=&quot;hljs-meta&quot;&gt;@Path&lt;/span&gt;&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;id&#39;&lt;/span&gt;&rpar; TodoId id&rpar;;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;After completing the steps, we will execute &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/build_runner&quot;&gt;&lt;code&gt;build_runner&lt;/code&gt;&lt;/a&gt; to generate the necessary code. This will create an implementation of &lt;code&gt;TodosHttpClient&lt;/code&gt; and we will link the generated &lt;code&gt;_TodosHttpClient&lt;/code&gt; to the factory method of this abstract class. The Dio object will be passed as a dependency through the constructor. Since we are using &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/get_it&quot;&gt;&lt;code&gt;get_it&lt;/code&gt;&lt;/a&gt; and &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/injectable&quot;&gt;&lt;code&gt;injectable&lt;/code&gt;&lt;/a&gt;, it will be necessary to manage the injection of this dependency.&lt;/p&gt;
&lt;h2 id=&quot;heading-setup-injectable&quot;&gt;Setup &lt;code&gt;injectable&lt;/code&gt; 🔧&lt;/h2&gt;
&lt;p&gt;Injectable is a package for Dart that allows for dependency injection in our application. It provides a simple and easy-to-use API for managing dependencies and injecting them into our classes. By using Injectable, we can easily swap out dependencies for different environments, like testing, and make our code more modular and testable.&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;👉 Read more about &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/injectable#registering-third-party-types&quot;&gt;&lt;code&gt;injectable&lt;/code&gt;&lt;/a&gt;.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;To handle how we inject the &lt;code&gt;Dio&lt;/code&gt; instance, we will create some files to inject third-party modules. In the &lt;code&gt;core&lt;/code&gt; directory, we will create a new directory called &lt;code&gt;di&lt;/code&gt;, short for Dependency Injection.&lt;/p&gt;
&lt;p&gt;Here, create a new file called &lt;code&gt;locator.dart&lt;/code&gt;, and add the following code.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:fullstack_todo/core/di/locator.config.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:get_it/get_it.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:injectable/injectable.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; locator = GetIt.instance;

&lt;span class=&quot;hljs-meta&quot;&gt;@injectableInit&lt;/span&gt;
&lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt; setupLocator&lpar;&rpar; =&amp;gt; locator.init&lpar;&rpar;;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Now, we will create another file called &lt;code&gt;third_party_modules.dart&lt;/code&gt;, this file will have a getter which will resolve the instance of &lt;code&gt;Dio&lt;/code&gt;.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dio/dio.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:injectable/injectable.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-meta&quot;&gt;@module&lt;/span&gt;
&lt;span class=&quot;hljs-keyword&quot;&gt;abstract&lt;/span&gt; &lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;ThirdPartyModules&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-meta&quot;&gt;@lazySingleton&lt;/span&gt;
  Dio &lt;span class=&quot;hljs-keyword&quot;&gt;get&lt;/span&gt; dio =&amp;gt; Dio&lpar;BaseOptions&lpar;baseUrl: kBaseUrl&rpar;&rpar;;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Then, we will create the missing &lt;code&gt;kBaseUrl&lt;/code&gt; constant in &lt;code&gt;constants/constants.dart&lt;/code&gt; file.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; kBaseUrl = &lt;span class=&quot;hljs-string&quot;&gt;&#39;http://localhost:8080&#39;&lt;/span&gt;;
&lt;/code&gt;&lt;/pre&gt;
&lt;blockquote&gt;
&lt;p&gt;Note: The port for you may be different, please check what port your backend will run by running &lt;code&gt;dart_frog dev&lt;/code&gt; in the &lt;code&gt;backend&lt;/code&gt; folder.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;If you check the generated code in &lt;code&gt;locator.config.dart&lt;/code&gt;, it creates the instance of &lt;code&gt;dio&lt;/code&gt; and passes it to our &lt;code&gt;TodosHttpClient&lt;/code&gt;.&lt;/p&gt;
&lt;h2 id=&quot;heading-implement-todosremotedatasource&quot;&gt;Implement &lt;code&gt;TodosRemoteDataSource&lt;/code&gt; 💻&lt;/h2&gt;
&lt;p&gt;We will now use &lt;code&gt;TodosHttpClient&lt;/code&gt; to implement our &lt;code&gt;TodosDataSource&lt;/code&gt;. For this, we will create &lt;code&gt;data_source/todos_remote_data_source.dart&lt;/code&gt; file, and we will implement &lt;code&gt;TodosDataSource&lt;/code&gt; as follows.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:data_source/data_source.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:fullstack_todo/data/data_source/todos_http_client/todos_http_client.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:injectable/injectable.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:models/models.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:typedefs/typedefs.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-meta&quot;&gt;@LazySingleton&lt;/span&gt;&lpar;&lt;span class=&quot;hljs-keyword&quot;&gt;as&lt;/span&gt;: TodoDataSource&rpar;
&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;TodosRemoteDataSource&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;implements&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;TodoDataSource&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; TodosRemoteDataSource&lpar;&lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;.httpClient&rpar;;

  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; TodosHttpClient httpClient;

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Todo&amp;gt; createTodo&lpar;CreateTodoDto todo&rpar; =&amp;gt; httpClient.createTodo&lpar;todo&rpar;;

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;&lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt;&amp;gt; deleteTodoById&lpar;TodoId id&rpar; =&amp;gt; httpClient.deleteTodoById&lpar;id&rpar;;

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&amp;lt;Todo&amp;gt;&amp;gt; getAllTodo&lpar;&rpar; =&amp;gt; httpClient.getAllTodo&lpar;&rpar;;

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Todo&amp;gt; getTodoById&lpar;TodoId id&rpar; =&amp;gt; httpClient.getTodoById&lpar;id&rpar;;

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Todo&amp;gt; updateTodo&lpar;{&lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; TodoId id, &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; UpdateTodoDto todo}&rpar; =&amp;gt;
      httpClient.updateTodo&lpar;id, todo&rpar;;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Here, we are passing the &lt;code&gt;TodosHttpClient&lt;/code&gt; as a dependency. This will help us to test the implementation by passing a mock implementation of &lt;code&gt;HttpClient&lt;/code&gt; to the data source implementation.&lt;/p&gt;
&lt;h2 id=&quot;heading-handling-errors-as-networkfailure&quot;&gt;Handling errors as &lt;code&gt;NetworkFailure&lt;/code&gt; 🛑&lt;/h2&gt;
&lt;p&gt;We need to handle the errors that we send from the backend as failures, and other possible errors as well. One possible way to do this is, when we implement our &lt;code&gt;TodoRepository&lt;/code&gt;, we will catch all the exceptions as &lt;code&gt;NetworkException&lt;/code&gt;, and then resolve the exception to the &lt;code&gt;Failure&lt;/code&gt; and handle the failures in the UI.&lt;/p&gt;
&lt;p&gt;The way we do this is can create an &lt;code&gt;interceptor&lt;/code&gt;, that we can plug into our &lt;code&gt;dio&lt;/code&gt; instance, and then handle the errors from there.&lt;/p&gt;
&lt;p&gt;By creating a new &lt;code&gt;NetworkException&lt;/code&gt; class in our &lt;code&gt;exceptions&lt;/code&gt; package, we will be able to effectively handle network errors that may occur while communicating with the backend. This is especially important when implementing the &lt;code&gt;TodoRepository&lt;/code&gt; class in the front end, as it ensures that any network errors that occur are caught and handled in a consistent and efficient manner.&lt;/p&gt;
&lt;p&gt;However, it is important to note that when working with APIs, we will encounter errors that are returned in the form of &lt;code&gt;DioError&lt;/code&gt;. To handle these errors, we will use an &lt;code&gt;ErrorInterceptorHandler&lt;/code&gt; to continue the Dio request-response cycle, while also rejecting any errors that occur.&lt;/p&gt;
&lt;p&gt;To ensure that we are able to catch &lt;code&gt;NetworkException&lt;/code&gt; in the repository, we will create a new class called &lt;code&gt;DioNetworkException&lt;/code&gt; which extends &lt;code&gt;DioError&lt;/code&gt; and implements &lt;code&gt;NetworkException&lt;/code&gt;. This allows us to create a new instance of &lt;code&gt;DioNetworkException&lt;/code&gt; and reject it from the handler.&lt;/p&gt;
&lt;h2 id=&quot;heading-create-networkexception&quot;&gt;Create &lt;code&gt;NetworkException&lt;/code&gt; 🌐&lt;/h2&gt;
&lt;p&gt;In our &lt;code&gt;exceptions&lt;/code&gt; package, we will create a new exception called &lt;code&gt;NetworkExeption&lt;/code&gt;. We are doing this because we don&#39;t want any external dependencies on our packages, as much as we can. Let&#39;s create a new file &lt;code&gt;exceptions/lib/src/network_exception/network_exception.dart&lt;/code&gt; in &lt;code&gt;exceptions&lt;/code&gt; package with the following contents.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;NetworkException&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;implements&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;Exception&lt;/span&gt; &lt;/span&gt;{
  NetworkException&lpar;{
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;.message,
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;.statusCode,
    &lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;.errors = &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; {},
  }&rpar;;

  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; message;

  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;int&lt;/span&gt; statusCode;

  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;&amp;gt;&amp;gt; errors;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;blockquote&gt;
&lt;p&gt;👉 Make sure to export this from &lt;code&gt;exceptions.dart&lt;/code&gt; library.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;library&lt;/span&gt; exceptions;

&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;src/http_exception/http_exception.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;src/network_exception/network_exception.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;src/server_exception/server_exception.dart&#39;&lt;/span&gt;;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Once this is done, let&#39;s come back to &lt;code&gt;frontend&lt;/code&gt; and create a new class called &lt;code&gt;DioNetworkException&lt;/code&gt;.&lt;/p&gt;
&lt;h2 id=&quot;heading-create-dionetworkexception&quot;&gt;Create &lt;code&gt;DioNetworkException&lt;/code&gt;&lt;/h2&gt;
&lt;p&gt;Let&#39;s create a new file in &lt;code&gt;lib/core/network/exceptions/dio_network_exception.dart&lt;/code&gt; in the &lt;code&gt;frontend&lt;/code&gt; package.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dio/dio.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:exceptions/exceptions.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;DioNetworkException&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;extends&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;DioError&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;implements&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;NetworkException&lt;/span&gt; &lt;/span&gt;{
  DioNetworkException&lpar;{
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;.message,
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;.statusCode,
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;.errors,
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;super&lt;/span&gt;.requestOptions,
  }&rpar;;

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;int&lt;/span&gt; statusCode;
  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; message;
  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;&amp;gt;&amp;gt; errors;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;This exception is created to convert the &lt;code&gt;DioError&lt;/code&gt; we get while implementing the error interceptor, to our &lt;code&gt;NetworkException&lt;/code&gt; so that we only care about the &lt;code&gt;NetworkException&lt;/code&gt; we implemented in our package, and catch it.&lt;/p&gt;
&lt;h2 id=&quot;heading-create-networkerrorinterceptor&quot;&gt;Create &lt;code&gt;NetworkErrorInterceptor&lt;/code&gt; 🔒&lt;/h2&gt;
&lt;p&gt;We will now implement &lt;code&gt;NetworkErrorInterceptor&lt;/code&gt; extending &lt;code&gt;Interceptor&lt;/code&gt; from &lt;code&gt;dio&lt;/code&gt;. Here we will have to override &lt;code&gt;onError&lt;/code&gt; method, which will give us &lt;code&gt;DioError&lt;/code&gt; object and a handler.&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;👉 Read more &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/dio#interceptors&quot;&gt;about interceptors&lt;/a&gt; from here.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;Create a new file &lt;code&gt;frontend/lib/core/network/interceptors/dio_error_interceptor.dart&lt;/code&gt;&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dio/dio.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:failures/failures.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:fullstack_todo/core/network/exceptions/dio_network_exception.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;NetworkErrorInterceptor&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;extends&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;Interceptor&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  &lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt; onError&lpar;DioError err, ErrorInterceptorHandler handler&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; genericInternetIssue =
        &lt;span class=&quot;hljs-string&quot;&gt;&#39;Please check your internet connection and try again&#39;&lt;/span&gt;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;try&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;err.response == &lt;span class=&quot;hljs-keyword&quot;&gt;null&lt;/span&gt;&rpar; {
        &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; DioNetworkException&lpar;
          message: genericInternetIssue,
          statusCode: &lt;span class=&quot;hljs-number&quot;&gt;500&lt;/span&gt;,
          requestOptions: err.requestOptions,
          errors: {},
        &rpar;;
      }
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; errorJson = err.response!.data &lt;span class=&quot;hljs-keyword&quot;&gt;as&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;dynamic&lt;/span&gt;&amp;gt;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; failureFromServer = NetworkFailure.fromJson&lpar;
        {
          ...errorJson,
          &lt;span class=&quot;hljs-string&quot;&gt;&#39;status_code&#39;&lt;/span&gt;: err.response!.statusCode,
        },
      &rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; DioNetworkException&lpar;
        message: failureFromServer.message,
        statusCode: err.response!.statusCode ?? failureFromServer.statusCode,
        errors: failureFromServer.errors,
        requestOptions: err.requestOptions,
      &rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;on&lt;/span&gt; DioNetworkException &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
      handler.reject&lpar;e&rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
      handler.reject&lpar;
        DioNetworkException&lpar;
          message: genericInternetIssue,
          statusCode: &lt;span class=&quot;hljs-number&quot;&gt;500&lt;/span&gt;,
          requestOptions: err.requestOptions,
          errors: {},
        &rpar;,
      &rpar;;
    }
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;blockquote&gt;
&lt;p&gt;Note: we may need to make a small change to our &lt;code&gt;NetworkFailure&lt;/code&gt; class and run &lt;code&gt;build_runner&lt;/code&gt;&lt;/p&gt;
&lt;/blockquote&gt;
&lt;pre&gt;&lt;code class=&quot;lang-diff&quot;&gt;  const factory NetworkFailure&lpar;{
    required String message,
    required int statusCode,
&lt;span class=&quot;hljs-deletion&quot;&gt;-   @Default&lpar;[]&rpar; List&amp;lt;String&amp;gt; errors,&lt;/span&gt;
&lt;span class=&quot;hljs-addition&quot;&gt;+   @Default&lpar;{}&rpar; Map&amp;lt;String, List&amp;lt;String&amp;gt;&amp;gt; errors,&lt;/span&gt;
  }&rpar; = _NetworkFailure;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Now once, we have implemented the &lt;code&gt;NetworkErrorInterceptor&lt;/code&gt;, we will attach this interceptor to our dio object.&lt;/p&gt;
&lt;p&gt;Open &lt;code&gt;third_party_modules.dart&lt;/code&gt; and add the following line.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-diff&quot;&gt;abstract class ThirdPartyModules {
  @lazySingleton
  Dio get dio =&amp;gt; Dio&lpar;BaseOptions&lpar;baseUrl: kBaseUrl&rpar;&rpar;;
&lt;span class=&quot;hljs-addition&quot;&gt;+    ..interceptors.add&lpar;NetworkErrorInterceptor&lpar;&rpar;&rpar;;&lt;/span&gt;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;h2 id=&quot;heading-implement-todorepository&quot;&gt;Implement &lt;code&gt;TodoRepository&lt;/code&gt; 📚&lt;/h2&gt;
&lt;p&gt;Now we will implement the todo repository at &lt;code&gt;lib/data/repositories/todo_repository_impl.dart&lt;/code&gt; in the following way.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:data_source/data_source.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:either_dart/either.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:exceptions/exceptions.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:failures/failures.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:injectable/injectable.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:models/models.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:repository/repository.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:typedefs/typedefs.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-meta&quot;&gt;@LazySingleton&lt;/span&gt;&lpar;&lt;span class=&quot;hljs-keyword&quot;&gt;as&lt;/span&gt;: TodoRepository&rpar;
&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;TodoRepositoryImpl&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;implements&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;TodoRepository&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; TodoRepositoryImpl&lpar;&lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;._todoDataSource&rpar;;
  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; TodoDataSource _todoDataSource;

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Either&amp;lt;Failure, Todo&amp;gt;&amp;gt; createTodo&lpar;CreateTodoDto createTodoDto&rpar; =&amp;gt;
      handleError&lpar;&lpar;&rpar; =&amp;gt; _todoDataSource.createTodo&lpar;createTodoDto&rpar;&rpar;;

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Either&amp;lt;Failure, &lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt;&amp;gt;&amp;gt; deleteTodo&lpar;TodoId id&rpar; =&amp;gt;
      handleError&lpar;&lpar;&rpar; =&amp;gt; _todoDataSource.deleteTodoById&lpar;id&rpar;&rpar;;

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Either&amp;lt;Failure, Todo&amp;gt;&amp;gt; getTodoById&lpar;TodoId id&rpar; =&amp;gt;
      handleError&lpar;&lpar;&rpar; =&amp;gt; _todoDataSource.getTodoById&lpar;id&rpar;&rpar;;

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Either&amp;lt;Failure, &lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&amp;lt;Todo&amp;gt;&amp;gt;&amp;gt; getTodos&lpar;&rpar; =&amp;gt;
      handleError&lpar;_todoDataSource.getAllTodo&rpar;;

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Either&amp;lt;Failure, Todo&amp;gt;&amp;gt; updateTodo&lpar;{
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; TodoId id,
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; UpdateTodoDto updateTodoDto,
  }&rpar; =&amp;gt;
      handleError&lpar;
        &lpar;&rpar; =&amp;gt; _todoDataSource.updateTodo&lpar;id: id, todo: updateTodoDto&rpar;,
      &rpar;;

  Future&amp;lt;Either&amp;lt;Failure, T&amp;gt;&amp;gt; handleError&amp;lt;T&amp;gt;&lpar;
    Future&amp;lt;T&amp;gt; &lt;span class=&quot;hljs-built_in&quot;&gt;Function&lt;/span&gt;&lpar;&rpar; callback,
  &rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;try&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; res = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; callback&lpar;&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Right&lpar;res&rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;on&lt;/span&gt; NetworkException &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Left&lpar;
        NetworkFailure&lpar;
          message: e.message,
          statusCode: e.statusCode,
          errors: e.errors,
        &rpar;,
      &rpar;;
    }
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Here, we are passing the data source as a dependency and calling methods from the data source for each implementation. In addition to that, we have created a &lt;code&gt;handleError&lt;/code&gt; generic method, which takes a caller method, and checks if there is a &lt;code&gt;NetworkException&lt;/code&gt;.&lt;/p&gt;
&lt;p&gt;The &lt;code&gt;NetworkException&lt;/code&gt; will be caught here which was thrown from the interceptor as &lt;code&gt;DioNetworkException&lt;/code&gt;.&lt;/p&gt;
&lt;p&gt;Now, let&#39;s do some UI, and connect our view model to the repository.&lt;/p&gt;
&lt;h1 id=&quot;heading-creating-showtodosview&quot;&gt;Creating &lt;code&gt;ShowTodosView&lt;/code&gt; 📋&lt;/h1&gt;
&lt;p&gt;Next, we will move on to creating the user interface and retrieving data from our repositories. To do this, we will perform some initial setup. We will be utilizing &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/stacked&quot;&gt;stacked&lt;/a&gt; to implement a Model-View-ViewModel &lpar;MVVM&rpar; architecture. The necessary dependencies have already been imported. Let&#39;s begin by creating the views and adding them to the routes.&lt;/p&gt;
&lt;h2 id=&quot;heading-create-showtodosview-and-showtodosviewmodel&quot;&gt;Create &lt;code&gt;ShowTodosView&lt;/code&gt; and &lt;code&gt;ShowTodosViewModel&lt;/code&gt;&lt;/h2&gt;
&lt;p&gt;In &lt;code&gt;lib/presentation//show_todos&lt;/code&gt; we will create two new files called &lt;code&gt;show_todos_view.dart&lt;/code&gt; and &lt;code&gt;show_todos_viewmodel.dart&lt;/code&gt;.&lt;/p&gt;
&lt;p&gt;We will begin by creating an empty implementation of the view and view model.&lt;/p&gt;
&lt;p&gt;In &lt;code&gt;show_todos_viewmodel.dart&lt;/code&gt;&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:stacked/stacked.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:injectable/injectable.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-meta&quot;&gt;@injectable&lt;/span&gt;
&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;ShowTodosViewModel&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;extends&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;BaseViewModel&lt;/span&gt; &lt;/span&gt;{}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Similarly in &lt;code&gt;show_todos_view.dart&lt;/code&gt;.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:flutter/material.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:fullstack_todo/core/di/locator.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:fullstack_todo/presentation/show_todos/show_todos_viewmodel.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:stacked/stacked.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;ShowTodosView&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;extends&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;StatelessWidget&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; ShowTodosView&lpar;{Key? key}&rpar; : &lt;span class=&quot;hljs-keyword&quot;&gt;super&lt;/span&gt;&lpar;key: key&rpar;;

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Widget build&lpar;BuildContext context&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; ViewModelBuilder&amp;lt;ShowTodosViewModel&amp;gt;.nonReactive&lpar;
      viewModelBuilder: &lpar;&rpar; =&amp;gt; locator&amp;lt;ShowTodosViewModel&amp;gt;&lpar;&rpar;,
      builder: &lpar;
        BuildContext context,
        ShowTodosViewModel model,
        Widget? child,
      &rpar; {
        &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Scaffold&lpar;
          body: Center&lpar;
            child: Text&lpar;
              &lt;span class=&quot;hljs-string&quot;&gt;&#39;ShowTodosView&#39;&lt;/span&gt;,
            &rpar;,
          &rpar;,
        &rpar;;
      },
    &rpar;;
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;We will also take advantage of the routing system provided by &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/stacked&quot;&gt;&lt;code&gt;stacked&lt;/code&gt;&lt;/a&gt;. This system uses context-less routing, allowing us to easily navigate within our application from the view model.&lt;/p&gt;
&lt;p&gt;We will create a &lt;code&gt;NavigationService&lt;/code&gt; that can be injected as a dependency, which will enable us to handle routing in a consistent and efficient manner.&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;👉 Read &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/stacked_services#navigation-service&quot;&gt;more about &lt;code&gt;NavigationService&lt;/code&gt;&lt;/a&gt; from here.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;Let&#39;s create a new &lt;code&gt;core/app/routes.dart&lt;/code&gt; file with the following contents.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:fullstack_todo/presentation/show_todos/show_todos_view.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:stacked/stacked_annotations.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-meta&quot;&gt;@StackedApp&lt;/span&gt;&lpar;
  routes: routes,
&rpar;
&lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&amp;lt;StackedRoute&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;dynamic&lt;/span&gt;&amp;gt;&amp;gt; routes = [
  AdaptiveRoute&lpar;page: ShowTodosView, initial: &lt;span class=&quot;hljs-keyword&quot;&gt;true&lt;/span&gt;&rpar;,
];
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Here, the &lt;code&gt;@StackedApp&lt;/code&gt; decorator does the magic. Once this is done, we run &lt;code&gt;build_runner&lt;/code&gt; to run code generation. We will get a new file &lt;code&gt;routes.router.dart&lt;/code&gt;&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;👉 Read more &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/stacked#router&quot;&gt;about &lt;code&gt;@StackedApp&lt;/code&gt;&lt;/a&gt;&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;Now, in &lt;code&gt;main.dart&lt;/code&gt; file, let&#39;s remove all the comments and make these changes.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:flutter/material.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:fullstack_todo/core/app/routes.router.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:fullstack_todo/core/di/locator.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:stacked_services/stacked_services.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt; main&lpar;&rpar; {
  setupLocator&lpar;&rpar;;
  runApp&lpar;&lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; MyApp&lpar;&rpar;&rpar;;
}

&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;MyApp&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;extends&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;StatelessWidget&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; MyApp&lpar;{&lt;span class=&quot;hljs-keyword&quot;&gt;super&lt;/span&gt;.key}&rpar;;

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Widget build&lpar;BuildContext context&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; MaterialApp&lpar;
      title: &lt;span class=&quot;hljs-string&quot;&gt;&#39;Fullstack Todo App&#39;&lt;/span&gt;,
      theme: ThemeData&lpar;
        primarySwatch: Colors.blue,
      &rpar;,
      navigatorKey: StackedService.navigatorKey,
      onGenerateRoute: StackedRouter&lpar;&rpar;.onGenerateRoute,
    &rpar;;
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Before calling &lt;code&gt;runApp&lpar;&rpar;&lt;/code&gt;, we are invoking &lt;code&gt;setupLocator&lpar;&rpar;&lt;/code&gt; from &lt;code&gt;locator.dart&lt;/code&gt;. This function will handle all the logic related to dependency injection. We are also providing &lt;code&gt;navigatorKey&lt;/code&gt; and &lt;code&gt;onGenerateRoute&lt;/code&gt; parameters, which come from &lt;code&gt;stacked&lt;/code&gt; and &lt;code&gt;routes.router.dart&lt;/code&gt;, respectively.&lt;/p&gt;
&lt;p&gt;We also need to take an extra step, which is to manage the injection of the &lt;code&gt;NavigationService&lt;/code&gt;. For this, we need to add a getter to the &lt;code&gt;third_party_modules.dart&lt;/code&gt; file.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-meta&quot;&gt;@module&lt;/span&gt;
&lt;span class=&quot;hljs-keyword&quot;&gt;abstract&lt;/span&gt; &lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;ThirdPartyModules&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-meta&quot;&gt;@lazySingleton&lt;/span&gt;
  Dio &lt;span class=&quot;hljs-keyword&quot;&gt;get&lt;/span&gt; dio =&amp;gt; Dio&lpar;BaseOptions&lpar;baseUrl: kBaseUrl&rpar;&rpar;
    ..interceptors.add&lpar;NetworkErrorInterceptor&lpar;&rpar;&rpar;;

  &lt;span class=&quot;hljs-meta&quot;&gt;@lazySingleton&lt;/span&gt;
  NavigationService &lt;span class=&quot;hljs-keyword&quot;&gt;get&lt;/span&gt; navigationService;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Once this is done, if you build the app you should see the first visual output.&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1673539321212/c86ca5ee-3d5c-4c22-881d-249da562025b.png&quot; alt class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;h3 id=&quot;heading-implement-showtodosviewmodel&quot;&gt;Implement &lt;code&gt;ShowTodosViewModel&lt;/code&gt;&lt;/h3&gt;
&lt;p&gt;This view model will utilize the &lt;code&gt;TodoRepository&lt;/code&gt; to retrieve data from the backend.&lt;/p&gt;
&lt;p&gt;Similar to &lt;code&gt;initState&lt;/code&gt; method used when working with &lt;code&gt;StatefulWidgets&lt;/code&gt;, we can create a new method in our ViewModel called &lt;code&gt;init&lt;/code&gt; to handle initialization logic.&lt;/p&gt;
&lt;p&gt;Within this method, we can call the repository to fetch all the todos. We will also create a &lt;code&gt;refresh&lt;/code&gt; method to handle pull-to-refresh functionality.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-meta&quot;&gt;@injectable&lt;/span&gt;
&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;ShowTodosViewModel&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;extends&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;BaseViewModel&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; TodoRepository _todoRepository;

  ShowTodosViewModel&lpar;&lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;._todoRepository&rpar;;

  &lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt; handleFailure&lpar;Failure failure&rpar; {
    setError&lpar;failure.message&rpar;;
    log&lpar;failure.message&rpar;;
  }

  &lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt; init&lpar;&rpar; =&amp;gt; runBusyFuture&lpar;refresh&lpar;&rpar;&rpar;;

  Future&amp;lt;&lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt;&amp;gt; refresh&lpar;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; response = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _todoRepository.getTodos&lpar;&rpar;;
    response.fold&lpar;handleFailure, &lt;span class=&quot;hljs-built_in&quot;&gt;print&lt;/span&gt;&rpar;;
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Here, we have three methods, &lt;code&gt;init&lt;/code&gt; &lt;code&gt;refresh&lt;/code&gt; and &lt;code&gt;handleFailure&lt;/code&gt;.&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;&lt;p&gt;&lt;code&gt;init&lt;/code&gt; This method is ideally run on &lt;code&gt;initState&lt;/code&gt; state. This will call the &lt;code&gt;refresh&lt;/code&gt; method, but in addition to that, this will mark the ViewModel as &lt;code&gt;busy&lt;/code&gt; before calling the method. This will be helpful when we want to show a loading indicator when we first fetch the todos.&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;code&gt;refresh&lt;/code&gt; This method will call the &lt;code&gt;TodoRepository&lt;/code&gt; and than handle re response accordingly.&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;code&gt;handleFailure&lt;/code&gt; Ideally, this is the place where we would handle the failure and show the UI accordingly. The &lt;code&gt;setError&lt;/code&gt; is storing the failure message in the view model, which will be accessible by &lt;code&gt;modelError&lt;/code&gt; getter from &lt;code&gt;BaseViewModel&lt;/code&gt;.&lt;/p&gt;
&lt;/li&gt;
&lt;/ul&gt;
&lt;p&gt;Now we are getting the todos from the backend. We will also be marking todos as completed and deleting the todo from this same view model.&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;Where should we put the todos once we fetch them?&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;We will also have another view called &lt;code&gt;MaintainTodoView&lt;/code&gt; which will be responsible for creating and updating the todos. We will come across a problem, where we will have to update the state of the created and updated todo. We can do this by passing the todo down the routes once it is created or updated.&lt;/p&gt;
&lt;p&gt;Another way to do this is by creating a data service, which will be shared across different view models. This service will be reactive, meaning if the data changes, it will rebuild all the view models listening to this data. This will help us avoid passing down the problem of the route.&lt;/p&gt;
&lt;h3 id=&quot;heading-implement-todosdataservice&quot;&gt;Implement &lt;code&gt;TodosDataService&lt;/code&gt;&lt;/h3&gt;
&lt;p&gt;We will create a &lt;code&gt;TodosDataService&lt;/code&gt; which will be shared across the view models. This will have some helper methods that will be used to maintain the state of all the todos. We will create a new file &lt;code&gt;lib/data_services/todos_data_service.dart&lt;/code&gt;&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:flutter/material.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:injectable/injectable.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:models/models.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:stacked/stacked.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-meta&quot;&gt;@lazySingleton&lt;/span&gt;
&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;TodosDataService&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;with&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;ReactiveServiceMixin&lt;/span&gt; &lt;/span&gt;{
  TodosDataService&lpar;&rpar; {
    listenToReactiveValues&lpar;[_todos]&rpar;;
  }
  &lt;span class=&quot;hljs-keyword&quot;&gt;late&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; ReactiveValue&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&amp;lt;Todo&amp;gt;&amp;gt; _todos = ReactiveValue&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&amp;lt;Todo&amp;gt;&amp;gt;&lpar;[]&rpar;;

  &lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&amp;lt;Todo&amp;gt; &lt;span class=&quot;hljs-keyword&quot;&gt;get&lt;/span&gt; todos =&amp;gt; _todos.value;

  &lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt; add&lpar;Todo todo&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; index = _todos.value.indexWhere&lpar;&lpar;element&rpar; =&amp;gt; element.id == todo.id&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;index == &lt;span class=&quot;hljs-number&quot;&gt;-1&lt;/span&gt;&rpar; {
      _todos.value.insert&lpar;&lt;span class=&quot;hljs-number&quot;&gt;0&lt;/span&gt;, todo&rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;else&lt;/span&gt; {
      _todos.value[index] = todo;
    }
    notifyListeners&lpar;&rpar;;
  }

  &lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt; addAll&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&amp;lt;Todo&amp;gt; todos&rpar; {
    _todos.value
      ..clear&lpar;&rpar;
      ..insertAll&lpar;&lt;span class=&quot;hljs-number&quot;&gt;0&lt;/span&gt;, todos&rpar;;
    notifyListeners&lpar;&rpar;;
  }

  &lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt; remove&lpar;Todo todo&rpar; {
    _todos.value.removeWhere&lpar;&lpar;element&rpar; =&amp;gt; element.id == todo.id&rpar;;
    notifyListeners&lpar;&rpar;;
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Here, we are using &lt;code&gt;ReactiveServiceMixin&lt;/code&gt; and &lt;code&gt;ReactiveValue&lt;/code&gt; objects. When we call &lt;code&gt;add&lt;/code&gt; method, it checks if the todo is present already, if so, it will update the existing one, or else it will add it to the top, so that we can see the latest one at the top.&lt;/p&gt;
&lt;p&gt;Similarly, there is &lt;code&gt;addAll&lt;/code&gt; which will clear all todos and then add them to the top.&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;👉 Read more about &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/stacked#reactivity&quot;&gt;reactivity in stacked&lt;/a&gt; from here.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;h3 id=&quot;heading-updating-showtodosviewmodel&quot;&gt;Updating &lt;code&gt;ShowTodosViewModel&lt;/code&gt;&lt;/h3&gt;
&lt;p&gt;Now we will inject &lt;code&gt;TodosDataService&lt;/code&gt; from the constructor and make some changes to the view model to handle reactivity.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-meta&quot;&gt;@injectable&lt;/span&gt;
&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;ShowTodosViewModel&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;extends&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;ReactiveViewModel&lt;/span&gt; &lt;/span&gt;{
  ShowTodosViewModel&lpar;
    &lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;._todoRepository,
    &lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;._todosDataService,
  &rpar;;

  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; TodoRepository _todoRepository;
  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; TodosDataService _todosDataService;
  &lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&amp;lt;Todo&amp;gt; &lt;span class=&quot;hljs-keyword&quot;&gt;get&lt;/span&gt; todos =&amp;gt; _todosDataService.todos;

  Future&amp;lt;&lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt;&amp;gt; init&lpar;&rpar; =&amp;gt; runBusyFuture&lpar;refresh&lpar;&rpar;&rpar;;

  &lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt; handleFailure&lpar;Failure failure&rpar; {
    setError&lpar;failure.message&rpar;;
    log&lpar;failure.message&rpar;;
  }

  Future&amp;lt;&lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt;&amp;gt; refresh&lpar;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; response = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _todoRepository.getTodos&lpar;&rpar;;
    response.fold&lpar;handleFailure, _todosDataService.addAll&rpar;;
  }

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  &lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&amp;lt;ReactiveServiceMixin&amp;gt; &lt;span class=&quot;hljs-keyword&quot;&gt;get&lt;/span&gt; reactiveServices =&amp;gt; [_todosDataService];
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;If you noticed, we are extending from &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/stacked#reactiveviewmodel&quot;&gt;&lt;code&gt;ReactiveViewModel&lt;/code&gt;&lt;/a&gt; and also overriding &lt;code&gt;reactiveServices&lt;/code&gt;. We are listening to the &lt;code&gt;_todosDataService&lt;/code&gt; and will be reflecting the UI whenever the data is changed in the reactive service.&lt;/p&gt;
&lt;h3 id=&quot;heading-update-showtodosview-to-show-fetched-todos&quot;&gt;Update &lt;code&gt;ShowTodosView&lt;/code&gt; to show fetched todos&lt;/h3&gt;
&lt;p&gt;Now we can update the &lt;code&gt;show_todos_view.dart&lt;/code&gt; to show the fetched todos.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;ShowTodosView&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;extends&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;StatelessWidget&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; ShowTodosView&lpar;{&lt;span class=&quot;hljs-keyword&quot;&gt;super&lt;/span&gt;.key}&rpar;;

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Widget build&lpar;BuildContext context&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; ViewModelBuilder&amp;lt;ShowTodosViewModel&amp;gt;.reactive&lpar;
      viewModelBuilder: locator,
      onModelReady: &lpar;model&rpar; =&amp;gt; model.init&lpar;&rpar;,
      builder: &lpar;
        BuildContext context,
        ShowTodosViewModel model,
        Widget? child,
      &rpar; {
        &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Scaffold&lpar;
          appBar: AppBar&lpar;
            title: &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; Text&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;Todos&#39;&lt;/span&gt;&rpar;,
          &rpar;,
          floatingActionButton: FloatingActionButton&lpar;
            onPressed: &lpar;&rpar; {},
            child: &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; Icon&lpar;Icons.add&rpar;,
          &rpar;,
          body: Builder&lpar;
            builder: &lpar;context&rpar; {
              &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;model.isBusy&rpar; {
                &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; Center&lpar;child: CircularProgressIndicator&lpar;&rpar;&rpar;;
              }
              &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;model.hasError&rpar; {
                &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Center&lpar;child: Text&lpar;model.modelError.toString&lpar;&rpar;&rpar;&rpar;;
              }
              &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;model.todos.isEmpty&rpar; {
                &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Center&lpar;
                  child: Text&lpar;
                    &lt;span class=&quot;hljs-string&quot;&gt;&#39;No todos found!&#39;&lt;/span&gt;,
                    style: Theme.of&lpar;context&rpar;.textTheme.titleLarge,
                  &rpar;,
                &rpar;;
              }
              &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; RefreshIndicator&lpar;
                onRefresh: model.refresh,
                child: ListView.builder&lpar;
                  physics: &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; AlwaysScrollableScrollPhysics&lpar;&rpar;,
                  itemCount: model.todos.length,
                  itemBuilder: &lpar;context, index&rpar; {
                    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; todo = model.todos[index];
                    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; ListTile&lpar;
                      title: Text&lpar;todo.title&rpar;,
                      subtitle: Text&lpar;todo.description&rpar;,
                      leading: Checkbox&lpar;
                        value: todo.completed,
                        onChanged: &lpar;val&rpar; {},
                      &rpar;,
                      trailing: Row&lpar;
                        mainAxisSize: MainAxisSize.min,
                        children: [
                          IconButton&lpar;
                            icon: &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; Icon&lpar;
                              Icons.edit,
                              color: Colors.blue,
                            &rpar;,
                            onPressed: &lpar;&rpar; {},
                          &rpar;,
                          IconButton&lpar;
                            icon: &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; Icon&lpar;
                              Icons.delete,
                              color: Colors.red,
                            &rpar;,
                            onPressed: &lpar;&rpar; {},
                          &rpar;,
                        ],
                      &rpar;,
                    &rpar;;
                  },
                &rpar;,
              &rpar;;
            },
          &rpar;,
        &rpar;;
      },
    &rpar;;
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;This view will get all the lists from the view model with &lt;code&gt;init&lt;/code&gt; method.&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;Notice the &lt;code&gt;onModelReady&lt;/code&gt; in the &lt;code&gt;ViewModelBuilder&lt;/code&gt; where we are calling &lt;code&gt;init&lt;/code&gt; method from the view model.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;We are using the &lt;code&gt;Builder&lt;/code&gt; to check the different states of the view model and show the UI accordingly.&lt;/p&gt;
&lt;p&gt;We show a &lt;code&gt;CircularProgressIndicator&lt;/code&gt; when the view model is &lt;code&gt;isBusy&lt;/code&gt;. This value is set by &lt;code&gt;runBusyFuture&lt;/code&gt; method in the view model.&lt;/p&gt;
&lt;p&gt;Also if the model has an error, we can check &lt;code&gt;hasError&lt;/code&gt; and show the error message accordingly. We will also show the todos with a &lt;code&gt;ListView.builder&lt;/code&gt;, when there are todos, and an empty message as well.&lt;/p&gt;
&lt;p&gt;Now let&#39;s build the app, and check out the progress.&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;Tip: If you are using macOS, make sure to allow &lt;a target=&quot;_blank&quot; href=&quot;https://stackoverflow.com/a/61201109/9611399&quot;&gt;network access in the entitlements file&lt;/a&gt;.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1673539368493/53546965-2fb3-42cf-859c-718611e45739.png&quot; alt class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;p&gt;And, if you create one using postman, you should see something like this.&lt;/p&gt;
&lt;div class=&quot;embed-wrapper&quot;&gt;&lt;div class=&quot;embed-loading&quot;&gt;&lt;div class=&quot;loadingRow&quot;&gt;&lt;/div&gt;&lt;div class=&quot;loadingRow&quot;&gt;&lt;/div&gt;&lt;/div&gt;&lt;a class=&quot;embed-card&quot; href=&quot;https://youtube.com/shorts/hcz457pUcZ0?feature=share&quot;&gt;https://youtube.com/shorts/hcz457pUcZ0?feature=share&lt;/a&gt;&lt;/div&gt;
&lt;p&gt; &lt;/p&gt;
&lt;h3 id=&quot;heading-create-todolisttile&quot;&gt;Create &lt;code&gt;TodoListTile&lt;/code&gt;&lt;/h3&gt;
&lt;p&gt;Once this is done, let&#39;s do some refactoring. We can create a &lt;code&gt;TodoListTile&lt;/code&gt; widget as a separate stateless widget in &lt;code&gt;show_todos/widgets/todo_list_tile.dart&lt;/code&gt;&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;TodoListTile&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;extends&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;ViewModelWidget&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-title&quot;&gt;ShowTodosViewModel&lt;/span&gt;&amp;gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; TodoListTile&lpar;{
    &lt;span class=&quot;hljs-keyword&quot;&gt;super&lt;/span&gt;.key,
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;.todo,
  }&rpar;;

  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; Todo todo;

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Widget build&lpar;BuildContext context, ShowTodosViewModel viewModel&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; ListTile&lpar;
      title: Text&lpar;todo.title&rpar;,
      subtitle: Text&lpar;todo.description&rpar;,
      leading: Checkbox&lpar;
        value: todo.completed,
        onChanged: &lpar;val&rpar; =&amp;gt; viewModel.markCompleted&lpar;todo&rpar;,
      &rpar;,
      trailing: Row&lpar;
        mainAxisSize: MainAxisSize.min,
        children: [
          IconButton&lpar;
            icon: &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; Icon&lpar;
              Icons.edit,
              color: Colors.blue,
            &rpar;,
            onPressed: &lpar;&rpar; =&amp;gt; viewModel.handleTodo&lpar;todo&rpar;,
          &rpar;,
          IconButton&lpar;
            icon: &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; Icon&lpar;
              Icons.delete,
              color: Colors.red,
            &rpar;,
            onPressed: &lpar;&rpar; =&amp;gt; viewModel.deleteTodo&lpar;todo&rpar;,
          &rpar;,
        ],
      &rpar;,
    &rpar;;
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Here, we have missing view model methods, which we will implement later. Also, we are not using a &lt;code&gt;StatelessWidget&lt;/code&gt; here, but it&#39;s a &lt;code&gt;ViewModelWidget&lt;/code&gt;. This is a wrapper around &lt;code&gt;StatelessWidget&lt;/code&gt; which will also provide us with the view model. This works with &lt;code&gt;Provider&lt;/code&gt; under the hood.&lt;/p&gt;
&lt;p&gt;Let&#39;s use this &lt;code&gt;TodoListTile&lt;/code&gt; widget in &lt;code&gt;ShowTodosView&lt;/code&gt;. We can update the &lt;code&gt;ListView.builder&lt;/code&gt; as follows.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;ListView.builder&lpar;
  physics: &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; AlwaysScrollableScrollPhysics&lpar;&rpar;,
  itemCount: model.todos.length,
  itemBuilder: &lpar;context, index&rpar; =&amp;gt;
      TodoListTile&lpar;todo: model.todos[index]&rpar;,
&rpar;,
&lt;/code&gt;&lt;/pre&gt;
&lt;h3 id=&quot;heading-implement-delete-and-markcompleted-methods&quot;&gt;Implement &lt;code&gt;delete&lt;/code&gt; and &lt;code&gt;markCompleted&lt;/code&gt; methods.&lt;/h3&gt;
&lt;p&gt;We will now implement &lt;code&gt;deleteTodo&lt;/code&gt; and &lt;code&gt;markCompleted&lt;/code&gt; methods as follows.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  Future&amp;lt;&lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt;&amp;gt; deleteTodo&lpar;Todo todo&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; response = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _todoRepository.deleteTodo&lpar;todo.id&rpar;;
    response.fold&lpar;
      handleFailure,
      &lpar;_&rpar; =&amp;gt; _todosDataService.remove&lpar;todo&rpar;,
    &rpar;;
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Here, we are calling the &lt;code&gt;deleteTodo&lt;/code&gt; method from the repository, and if it&#39;s successful, we will remove the todo from the data service, that in turn will remove it from the UI.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  Future&amp;lt;&lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt;&amp;gt; markCompleted&lpar;Todo todo&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;busy&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;updating&#39;&lt;/span&gt;&rpar;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; completed = !todo.completed;
    _todosDataService.add&lpar;todo.copyWith&lpar;completed: completed&rpar;&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; updateDto = UpdateTodoDto&lpar;
      completed: !todo.completed,
    &rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; update = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; runBusyFuture&lpar;
      _todoRepository.updateTodo&lpar;id: todo.id, updateTodoDto: updateDto&rpar;,
      busyObject: &lt;span class=&quot;hljs-string&quot;&gt;&#39;updating&#39;&lt;/span&gt;,
    &rpar;;
    update.fold&lpar;
      &lpar;failure&rpar; {
        _todosDataService.add&lpar;todo.copyWith&lpar;completed: !completed&rpar;&rpar;;
        handleFailure&lpar;failure&rpar;;
      },
      &lpar;_&rpar; {},
    &rpar;;
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Here, in &lt;code&gt;markCompleted&lt;/code&gt; method, we are first negating the state, and then adding it to the data service, and then calling the API. This is to show the update in an instantaneous manner. If the update fails, we will revert the checkbox state.&lt;/p&gt;
&lt;p&gt;We will add an empty implementation for the &lt;code&gt;handleTodo&lt;/code&gt; method as follows.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  Future&amp;lt;&lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt;&amp;gt;? handleTodo&lpar;[Todo? todo]&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;null&lt;/span&gt;;
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;This method will take an optional Todo object, and we will pass it to &lt;code&gt;MaintainTodoView&lt;/code&gt;, which will create or update the todo based on the value provided.&lt;/p&gt;
&lt;p&gt;Once these methods are completed, we will have these functionalities.&lt;/p&gt;
&lt;div class=&quot;embed-wrapper&quot;&gt;&lt;div class=&quot;embed-loading&quot;&gt;&lt;div class=&quot;loadingRow&quot;&gt;&lt;/div&gt;&lt;div class=&quot;loadingRow&quot;&gt;&lt;/div&gt;&lt;/div&gt;&lt;a class=&quot;embed-card&quot; href=&quot;https://www.youtube.com/shorts/sY-5NN8GC8I?feature=share&quot;&gt;https://www.youtube.com/shorts/sY-5NN8GC8I?feature=share&lt;/a&gt;&lt;/div&gt;
&lt;p&gt; &lt;/p&gt;
&lt;h1 id=&quot;heading-creating-maintaintodoview&quot;&gt;Creating &lt;code&gt;MaintainTodoView&lt;/code&gt;📝&lt;/h1&gt;
&lt;p&gt;This view will be able to create and update the todos. We will create the view and the view model. Also, we will create a route for this, and implement &lt;code&gt;handleTodo&lt;/code&gt; method in &lt;code&gt;ShowTodosViewModel&lt;/code&gt;.&lt;/p&gt;
&lt;p&gt;We will create &lt;code&gt;maintain_todo_view.dart&lt;/code&gt; and &lt;code&gt;maintain_todo_viewmomdel.dart&lt;/code&gt; in &lt;code&gt;presentstion/main_todo&lt;/code&gt; directory.&lt;/p&gt;
&lt;p&gt;We will create the view model as follows.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-meta&quot;&gt;@injectable&lt;/span&gt;
&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;MaintainTodoViewModel&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;extends&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;ReactiveViewModel&lt;/span&gt; &lt;/span&gt;{
  MaintainTodoViewModel&lpar;&lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;._todosDataService&rpar;;
  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; TodosDataService _todosDataService;

  Todo? _todo;
  &lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt; init&lpar;Todo? todo&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;todo == &lt;span class=&quot;hljs-keyword&quot;&gt;null&lt;/span&gt;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt;;
    _todo = todo;
  }

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  &lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&amp;lt;ReactiveServiceMixin&amp;gt; &lt;span class=&quot;hljs-keyword&quot;&gt;get&lt;/span&gt; reactiveServices =&amp;gt; [_todosDataService];
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Similarly, we will create an empty view, as follows&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;MaintainTodoView&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;extends&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;StatelessWidget&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; MaintainTodoView&lpar;&lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;.todo, {&lt;span class=&quot;hljs-keyword&quot;&gt;super&lt;/span&gt;.key}&rpar;;
  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; Todo? todo;
  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Widget build&lpar;BuildContext context&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; ViewModelBuilder&amp;lt;MaintainTodoViewModel&amp;gt;.nonReactive&lpar;
      onModelReady: &lpar;model&rpar; =&amp;gt; model.init&lpar;todo&rpar;,
      viewModelBuilder: &lpar;&rpar; =&amp;gt; locator&amp;lt;MaintainTodoViewModel&amp;gt;&lpar;&rpar;,
      builder: &lpar;
        BuildContext context,
        MaintainTodoViewModel model,
        Widget? child,
      &rpar; {
        &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Scaffold&lpar;
          body: Center&lpar;
            child: Text&lpar;
              &lt;span class=&quot;hljs-string&quot;&gt;&#39;MaintainTodoView&#39;&lt;/span&gt;,
            &rpar;,
          &rpar;,
        &rpar;;
      },
    &rpar;;
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Now, we can add this view to the route, and handle routing from &lt;code&gt;ShowTodosViewModel&lt;/code&gt;. In &lt;code&gt;lib/core/app/routes.dart&lt;/code&gt; add the following route entry:&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&amp;lt;StackedRoute&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;dynamic&lt;/span&gt;&amp;gt;&amp;gt; routes = [
  AdaptiveRoute&lpar;page: ShowTodosView, initial: &lt;span class=&quot;hljs-keyword&quot;&gt;true&lt;/span&gt;&rpar;,
  AdaptiveRoute&lpar;page: MaintainTodoView&rpar;,
];
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Once you run the &lt;code&gt;build_runner&lt;/code&gt;, open the &lt;code&gt;ShowTodosViewModel&lt;/code&gt;, and make the following change.&lt;/p&gt;
&lt;p&gt;We will have to register &lt;code&gt;NavigationService&lt;/code&gt; in our third-party modules as follows.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-meta&quot;&gt;@module&lt;/span&gt;
&lt;span class=&quot;hljs-keyword&quot;&gt;abstract&lt;/span&gt; &lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;ThirdPartyModules&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-meta&quot;&gt;@lazySingleton&lt;/span&gt;
  Dio &lt;span class=&quot;hljs-keyword&quot;&gt;get&lt;/span&gt; dio =&amp;gt; Dio&lpar;BaseOptions&lpar;baseUrl: kBaseUrl&rpar;&rpar;;

  &lt;span class=&quot;hljs-meta&quot;&gt;@lazySingleton&lt;/span&gt;
  NavigationService &lt;span class=&quot;hljs-keyword&quot;&gt;get&lt;/span&gt; navigationService;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Now, we will inject the &lt;code&gt;NavigationService&lt;/code&gt; from the &lt;code&gt;ShowTodosViewModel&lt;/code&gt; constructor and implement the &lt;code&gt;handleTodo&lt;/code&gt; as follows.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-diff&quot;&gt;  ShowTodosViewModel&lpar;
    this._todoRepository,
    this._todosDataService,
&lt;span class=&quot;hljs-addition&quot;&gt;+   this._navigationService,&lt;/span&gt;
  &rpar;;

  final TodoRepository _todoRepository;
  final TodosDataService _todosDataService;
&lt;span class=&quot;hljs-addition&quot;&gt;+ final NavigationService _navigationService;&lt;/span&gt;

  Future&amp;lt;void&amp;gt;? handleTodo&lpar;[Todo? todo]&rpar; {
&lt;span class=&quot;hljs-addition&quot;&gt;+   return _navigationService.navigateTo&amp;lt;void&amp;gt;&lpar;&lt;/span&gt;
&lt;span class=&quot;hljs-addition&quot;&gt;+     Routes.maintainTodoView,&lt;/span&gt;
&lt;span class=&quot;hljs-addition&quot;&gt;+     arguments: MaintainTodoViewArguments&lpar;todo: todo&rpar;,&lt;/span&gt;
&lt;span class=&quot;hljs-addition&quot;&gt;+   &rpar;;&lt;/span&gt;
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;blockquote&gt;
&lt;p&gt;Make sure to run &lt;code&gt;build_runner&lt;/code&gt;.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;Now, you should be able to navigate to &lt;code&gt;MaintainTodoView&lt;/code&gt;.&lt;/p&gt;
&lt;div class=&quot;embed-wrapper&quot;&gt;&lt;div class=&quot;embed-loading&quot;&gt;&lt;div class=&quot;loadingRow&quot;&gt;&lt;/div&gt;&lt;div class=&quot;loadingRow&quot;&gt;&lt;/div&gt;&lt;/div&gt;&lt;a class=&quot;embed-card&quot; href=&quot;https://www.youtube.com/shorts/Ua27jp70j2s?feature=share&quot;&gt;https://www.youtube.com/shorts/Ua27jp70j2s?feature=share&lt;/a&gt;&lt;/div&gt;
&lt;p&gt; &lt;/p&gt;
&lt;h2 id=&quot;heading-implementing-maintaintodoviewmodel&quot;&gt;Implementing &lt;code&gt;MaintainTodoViewModel&lt;/code&gt;&lt;/h2&gt;
&lt;p&gt;We will create three state variables for handling &lt;code&gt;title&lt;/code&gt;, &lt;code&gt;description&lt;/code&gt;, and &lt;code&gt;completed&lt;/code&gt; value. We will also expose the getters for these variables. Also, we will create &lt;code&gt;onChanged&lt;/code&gt; methods for these variables.&lt;/p&gt;
&lt;p&gt;We will also create an &lt;code&gt;init&lt;/code&gt; method, which will take an optional &lt;code&gt;Todo&lt;/code&gt; object and populate these state variables. Here if we pass this optional todo, we will be updating that todo.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-meta&quot;&gt;@injectable&lt;/span&gt;
&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;MaintainTodoViewModel&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;extends&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;BaseViewModel&lt;/span&gt; &lt;/span&gt;{
  MaintainTodoViewModel&lpar;
    &lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;._todosDataService,
    &lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;._repository,
    &lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;._navigationService,
  &rpar;;

  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; TodosDataService _todosDataService;
  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; TodoRepository _repository;
  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; NavigationService _navigationService;
  &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; _title = &lt;span class=&quot;hljs-string&quot;&gt;&#39;&#39;&lt;/span&gt;;
  &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;get&lt;/span&gt; title =&amp;gt; _title;

  &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; _description = &lt;span class=&quot;hljs-string&quot;&gt;&#39;&#39;&lt;/span&gt;;
  &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;get&lt;/span&gt; description =&amp;gt; _description;

  &lt;span class=&quot;hljs-built_in&quot;&gt;bool&lt;/span&gt; _completed = &lt;span class=&quot;hljs-keyword&quot;&gt;false&lt;/span&gt;;
  &lt;span class=&quot;hljs-built_in&quot;&gt;bool&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;get&lt;/span&gt; completed =&amp;gt; _completed;

  &lt;span class=&quot;hljs-built_in&quot;&gt;bool&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;get&lt;/span&gt; isValidated {
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; empty = _title.isEmpty || _description.isEmpty;
    &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;empty&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;false&lt;/span&gt;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; errors = error&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;title&#39;&lt;/span&gt;&rpar; != &lt;span class=&quot;hljs-keyword&quot;&gt;null&lt;/span&gt; || error&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;description&#39;&lt;/span&gt;&rpar; != &lt;span class=&quot;hljs-keyword&quot;&gt;null&lt;/span&gt;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;errors&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;false&lt;/span&gt;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;true&lt;/span&gt;;
  }

  &lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt; onTitleChanged&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; value&rpar; {
    _title = value;
    &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;value.isEmpty&rpar; {
      setErrorForObject&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;title&#39;&lt;/span&gt;, &lt;span class=&quot;hljs-string&quot;&gt;&#39;Title is required&#39;&lt;/span&gt;&rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;else&lt;/span&gt; {
      setErrorForObject&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;title&#39;&lt;/span&gt;, &lt;span class=&quot;hljs-keyword&quot;&gt;null&lt;/span&gt;&rpar;;
    }
    notifyListeners&lpar;&rpar;;
  }

  &lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt; onDescriptionChanged&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; value&rpar; {
    _description = value;
    &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;value.isEmpty&rpar; {
      setErrorForObject&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;description&#39;&lt;/span&gt;, &lt;span class=&quot;hljs-string&quot;&gt;&#39;Description is required&#39;&lt;/span&gt;&rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;else&lt;/span&gt; {
      setErrorForObject&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;description&#39;&lt;/span&gt;, &lt;span class=&quot;hljs-keyword&quot;&gt;null&lt;/span&gt;&rpar;;
    }
    notifyListeners&lpar;&rpar;;
  }

  Todo? _todo;
  &lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt; init&lpar;Todo? todo&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;todo == &lt;span class=&quot;hljs-keyword&quot;&gt;null&lt;/span&gt;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt;;
    _title = todo.title;
    _description = todo.description;
    _todo = todo;
    _completed = todo.completed;
  }

  &lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt; onCompletedChanged&lpar;{&lt;span class=&quot;hljs-built_in&quot;&gt;bool?&lt;/span&gt; value}&rpar; {
    _completed = value ?? &lt;span class=&quot;hljs-keyword&quot;&gt;false&lt;/span&gt;;
    notifyListeners&lpar;&rpar;;
  }

  &lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt; handleTodo&lpar;&rpar; {}
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;In change handlers, we are also validating the values, and setting the errors for each state on change, and then we have a &lt;code&gt;isValidated&lt;/code&gt; getter which would return if the values are validated or not.&lt;/p&gt;
&lt;h2 id=&quot;heading-implementing-maintaintodoview&quot;&gt;Implementing &lt;code&gt;MaintainTodoView&lt;/code&gt;&lt;/h2&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;MaintainTodoView&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;extends&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;HookWidget&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; MaintainTodoView&lpar;&lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;.todo, {&lt;span class=&quot;hljs-keyword&quot;&gt;super&lt;/span&gt;.key}&rpar;;
  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; Todo? todo;

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Widget build&lpar;BuildContext context&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; titleController = useTextEditingController&lpar;text: todo?.title&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; descriptionController =
        useTextEditingController&lpar;text: todo?.description&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; titleFocusNode = useFocusNode&lpar;&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; descriptionFocusNode = useFocusNode&lpar;&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; checkBoxFocusNode = useFocusNode&lpar;&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; buttonFocusNode = useFocusNode&lpar;&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; ViewModelBuilder&amp;lt;MaintainTodoViewModel&amp;gt;.nonReactive&lpar;
      onModelReady: &lpar;model&rpar; =&amp;gt; model.init&lpar;todo&rpar;,
      viewModelBuilder: locator,
      builder: &lpar;
        BuildContext context,
        MaintainTodoViewModel model,
        Widget? child,
      &rpar; {
        &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Scaffold&lpar;
          appBar: AppBar&lpar;
            title: Text&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;&lt;span class=&quot;hljs-subst&quot;&gt;${todo == &lt;span class=&quot;hljs-keyword&quot;&gt;null&lt;/span&gt; ? &lt;span class=&quot;hljs-string&quot;&gt;&#39;Create&#39;&lt;/span&gt; : &lt;span class=&quot;hljs-string&quot;&gt;&#39;Edit&#39;&lt;/span&gt;}&lt;/span&gt; Todo&#39;&lt;/span&gt;&rpar;,
          &rpar;,
          body: Padding&lpar;
            padding: &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; EdgeInsets.all&lpar;&lt;span class=&quot;hljs-number&quot;&gt;16&lt;/span&gt;&rpar;,
            child: Column&lpar;
              crossAxisAlignment: CrossAxisAlignment.stretch,
              children: [
                TextFormField&lpar;
                  controller: titleController,
                  focusNode: titleFocusNode,
                  decoration: &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; InputDecoration&lpar;
                    hintText: &lt;span class=&quot;hljs-string&quot;&gt;&#39;Title&#39;&lt;/span&gt;,
                    border: OutlineInputBorder&lpar;&rpar;,
                  &rpar;,
                  onChanged: model.onTitleChanged,
                  onEditingComplete: descriptionFocusNode.requestFocus,
                &rpar;,
                &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; SizedBox&lpar;height: &lt;span class=&quot;hljs-number&quot;&gt;14&lt;/span&gt;&rpar;,
                TextFormField&lpar;
                  controller: descriptionController,
                  focusNode: descriptionFocusNode,
                  decoration: &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; InputDecoration&lpar;
                    hintText: &lt;span class=&quot;hljs-string&quot;&gt;&#39;Description&#39;&lt;/span&gt;,
                    border: OutlineInputBorder&lpar;&rpar;,
                  &rpar;,
                  onChanged: model.onDescriptionChanged,
                  onEditingComplete: checkBoxFocusNode.requestFocus,
                &rpar;,
                &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;todo != &lt;span class=&quot;hljs-keyword&quot;&gt;null&lt;/span&gt;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; SizedBox&lpar;height: &lt;span class=&quot;hljs-number&quot;&gt;14&lt;/span&gt;&rpar;,
                &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;todo != &lt;span class=&quot;hljs-keyword&quot;&gt;null&lt;/span&gt;&rpar;
                  SelectorViewModelBuilder&amp;lt;MaintainTodoViewModel, &lt;span class=&quot;hljs-built_in&quot;&gt;bool&lt;/span&gt;&amp;gt;&lpar;
                    selector: &lpar;model&rpar; =&amp;gt; model.completed,
                    builder: &lpar;context, val, _&rpar; {
                      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; CheckboxListTile&lpar;
                        focusNode: checkBoxFocusNode,
                        contentPadding: EdgeInsets.zero,
                        title: &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; Text&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;Mark Completed&#39;&lt;/span&gt;&rpar;,
                        value: val,
                        onChanged: &lpar;v&rpar; =&amp;gt; model.onCompletedChanged&lpar;value: v&rpar;,
                      &rpar;;
                    },
                  &rpar;,
                &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; Spacer&lpar;&rpar;,
                SelectorViewModelBuilder&amp;lt;MaintainTodoViewModel, &lt;span class=&quot;hljs-built_in&quot;&gt;bool&lt;/span&gt;&amp;gt;&lpar;
                  selector: &lpar;model&rpar; =&amp;gt; model.isValidated,
                  builder: &lpar;context, validated, child&rpar; {
                    &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;validated&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; child!;
                    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; SizedBox.shrink&lpar;&rpar;;
                  },
                  child: SizedBox&lpar;
                    height: &lt;span class=&quot;hljs-number&quot;&gt;50&lt;/span&gt;,
                    child: ElevatedButton&lpar;
                      focusNode: buttonFocusNode,
                      onPressed: model.handleTodo,
                      child:
                          SelectorViewModelBuilder&amp;lt;MaintainTodoViewModel, &lt;span class=&quot;hljs-built_in&quot;&gt;bool&lt;/span&gt;&amp;gt;&lpar;
                        selector: &lpar;model&rpar; =&amp;gt; model.isBusy,
                        builder: &lpar;context, isBusy, child&rpar; {
                          &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;isBusy&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; child!;
                          &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Row&lpar;
                            mainAxisSize: MainAxisSize.min,
                            children: &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; [
                              Icon&lpar;
                                Icons.save,
                                size: &lt;span class=&quot;hljs-number&quot;&gt;30&lt;/span&gt;,
                              &rpar;,
                              SizedBox&lpar;width: &lt;span class=&quot;hljs-number&quot;&gt;10&lt;/span&gt;&rpar;,
                              Text&lpar;
                                &lt;span class=&quot;hljs-string&quot;&gt;&#39;Save&#39;&lt;/span&gt;,
                                style: TextStyle&lpar;
                                  fontSize: &lt;span class=&quot;hljs-number&quot;&gt;20&lt;/span&gt;,
                                &rpar;,
                              &rpar;,
                            ],
                          &rpar;;
                        },
                        child: &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; CircularProgressIndicator&lpar;
                          valueColor:
                              AlwaysStoppedAnimation&amp;lt;Color&amp;gt;&lpar;Colors.white&rpar;,
                        &rpar;,
                      &rpar;,
                    &rpar;,
                  &rpar;,
                &rpar;
              ],
            &rpar;,
          &rpar;,
        &rpar;;
      },
    &rpar;;
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;This form includes crucial text fields for the &lt;code&gt;title&lt;/code&gt; and &lt;code&gt;description&lt;/code&gt; of the to-do task. The optional check box is displayed only when an existing to-do task is provided for updating. If a to-do task is provided, the form will be populated with the previous values and the check box will be visible for updating.&lt;/p&gt;
&lt;p&gt;To handle the form&#39;s input, we utilize the &lt;code&gt;flutter_hooks&lt;/code&gt; library for managing &lt;code&gt;TextEditingControllers&lt;/code&gt; and &lt;code&gt;FocusNodes&lt;/code&gt;. The &lt;code&gt;ElevatedButton&lt;/code&gt; takes care of the create/update action.&lt;/p&gt;
&lt;p&gt;We are also using &lt;code&gt;SelectorViewModelBuilder&lt;/code&gt; with a &lt;code&gt;selector&lt;/code&gt; to rebuild only when the value returned from the selector is changed, resulting in partial rebuilds. For example, we are only showing the &lt;code&gt;ElevatedButton&lt;/code&gt; when the form is validated.&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;👉 Read &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/stacked#selectorviewmodelbuilder&quot;&gt;more about &lt;code&gt;SelectorViewModelBuilder&lt;/code&gt;&lt;/a&gt;&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;With this, we have a functional form UI something like this.&lt;/p&gt;
&lt;div class=&quot;embed-wrapper&quot;&gt;&lt;div class=&quot;embed-loading&quot;&gt;&lt;div class=&quot;loadingRow&quot;&gt;&lt;/div&gt;&lt;div class=&quot;loadingRow&quot;&gt;&lt;/div&gt;&lt;/div&gt;&lt;a class=&quot;embed-card&quot; href=&quot;https://www.youtube.com/shorts/SOUH1t2RdbY?feature=share&quot;&gt;https://www.youtube.com/shorts/SOUH1t2RdbY?feature=share&lt;/a&gt;&lt;/div&gt;
&lt;p&gt; &lt;/p&gt;
&lt;p&gt;In the final part, let&#39;s implement &lt;code&gt;handleTodo&lt;/code&gt; method in &lt;code&gt;MaintainTodoViewmodel&lt;/code&gt; like this.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  Future&amp;lt;&lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt;&amp;gt; handleTodo&lpar;&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;!isValidated&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Future.value&lpar;&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;_todo == &lt;span class=&quot;hljs-keyword&quot;&gt;null&lt;/span&gt;&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; _createTodo&lpar;&rpar;;
    }
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; _updateTodo&lpar;&rpar;;
  }

  Future&amp;lt;&lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt;&amp;gt; _createTodo&lpar;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; dto = CreateTodoDto&lpar;title: title, description: description&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; response = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; runBusyFuture&lpar;_repository.createTodo&lpar;dto&rpar;&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; response.fold&lpar;
      &lpar;failure&rpar; {
        setError&lpar;failure.message&rpar;;
      },
      &lpar;todo&rpar; {
        _todosDataService.add&lpar;todo&rpar;;
        _navigationService.back&amp;lt;&lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt;&amp;gt;&lpar;&rpar;;
      },
    &rpar;;
  }

  Future&amp;lt;&lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt;&amp;gt; _updateTodo&lpar;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;_todo == &lt;span class=&quot;hljs-keyword&quot;&gt;null&lt;/span&gt;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; dto = UpdateTodoDto&lpar;
      title: title,
      description: description,
      completed: completed,
    &rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; response = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; runBusyFuture&lpar;
      _repository.updateTodo&lpar;id: _todo!.id, updateTodoDto: dto&rpar;,
    &rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; response.fold&lpar;
      &lpar;failure&rpar; {
        setError&lpar;failure.message&rpar;;
      },
      &lpar;todo&rpar; {
        _todosDataService.add&lpar;todo&rpar;;
        _navigationService.back&amp;lt;&lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt;&amp;gt;&lpar;&rpar;;
      },
    &rpar;;
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;The &lt;code&gt;handleTodo&lt;/code&gt; method is responsible for creating or updating a to-do task based on the optional &lt;code&gt;Todo&lt;/code&gt; provided in the &lt;code&gt;init&lt;/code&gt; method.&lt;/p&gt;
&lt;p&gt;It calls the private methods &lt;code&gt;_createTodo&lt;/code&gt; and &lt;code&gt;_updateTodo&lt;/code&gt; internally. &lt;code&gt;_createTodo&lt;/code&gt; creates a data transfer object, passes it to the repository, and navigates back upon successful creation.&lt;/p&gt;
&lt;p&gt;Similarly, &lt;code&gt;_updateTodo&lt;/code&gt; updates the provided to-do task and navigates back upon successful update.&lt;/p&gt;
&lt;p&gt;Finally, we have a fully functional app.&lt;/p&gt;
&lt;div class=&quot;embed-wrapper&quot;&gt;&lt;div class=&quot;embed-loading&quot;&gt;&lt;div class=&quot;loadingRow&quot;&gt;&lt;/div&gt;&lt;div class=&quot;loadingRow&quot;&gt;&lt;/div&gt;&lt;/div&gt;&lt;a class=&quot;embed-card&quot; href=&quot;https://www.youtube.com/shorts/oy4_PN1cbyI?feature=share&quot;&gt;https://www.youtube.com/shorts/oy4_PN1cbyI?feature=share&lt;/a&gt;&lt;/div&gt;
&lt;p&gt; &lt;/p&gt;
&lt;hr /&gt;
&lt;h1 id=&quot;heading-bonus&quot;&gt;Bonus 🎉&lt;/h1&gt;
&lt;p&gt;To ensure our code follows best practices and is consistent throughout our project, let&#39;s add some linting with &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/very_good_analysis&quot;&gt;very_good_analysis&lt;/a&gt; in &lt;code&gt;analysis_options.yaml&lt;/code&gt;.&lt;/p&gt;
&lt;p&gt;Linting is an important step in the development process as it helps catch potential errors and enforces a set of coding standards. This results in more readable and maintainable code, making it easier for both you and other developers to understand and work with the codebase.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-yaml&quot;&gt;&lt;span class=&quot;hljs-attr&quot;&gt;include:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;package:very_good_analysis/analysis_options.yaml&lt;/span&gt;
&lt;span class=&quot;hljs-attr&quot;&gt;analyzer:&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;exclude:&lt;/span&gt;
    &lt;span class=&quot;hljs-bullet&quot;&gt;-&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;**/*.router.dart&#39;&lt;/span&gt;
    &lt;span class=&quot;hljs-bullet&quot;&gt;-&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;**/*.locator.dart&#39;&lt;/span&gt;
    &lt;span class=&quot;hljs-bullet&quot;&gt;-&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;**/*.config.dart&#39;&lt;/span&gt;
    &lt;span class=&quot;hljs-bullet&quot;&gt;-&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;**/*.g.dart&#39;&lt;/span&gt;
&lt;span class=&quot;hljs-attr&quot;&gt;linter:&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;rules:&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;public_member_api_docs:&lt;/span&gt; &lt;span class=&quot;hljs-literal&quot;&gt;false&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;hr /&gt;
&lt;p&gt;🎉 Congrats, we&#39;ve made it to the end of Part 5! 🚀 We&#39;ve successfully built the front end of our full-stack to-do application using Flutter. From importing necessary dependencies to connecting with the backend, we&#39;ve covered it all. We&#39;ve even implemented features such as creating and updating todos, handling errors and creating a reactive data service.&lt;/p&gt;
&lt;p&gt;It&#39;s been an amazing journey, and we&#39;ve come a long way since Part 1. We&#39;ve built a complete full-stack to-do application using Dart and Flutter. But our work doesn&#39;t stop here. In this series, we haven&#39;t covered testing yet, but it&#39;s a crucial part of building any application. If you&#39;re interested in learning more about testing your code in all the modules we&#39;ve built in this series, let us know in the comments.&lt;/p&gt;
&lt;p&gt;As always, you can refer back to the GitHub repo for this tutorial at &lt;a target=&quot;_blank&quot; href=&quot;https://github.com/saileshbro/full_stack_todo_dart&quot;&gt;https://github.com/saileshbro/full_stack_todo_dart&lt;/a&gt; if you need any help. Don&#39;t forget to give it a  and spread the love for the project. Also, if you&#39;re stuck or need help, feel free to open an issue or better yet, send a pull request.&lt;/p&gt;
&lt;p&gt;Thank you for joining me in this adventure, let&#39;s make more amazing apps together. Happy coding! 💻&lt;/p&gt;
 

 - 💯[🚀 Building a Fullstack App with dart_frog and Flutter in a Monorepo - Part 4](https://saileshdahal.com.np/building-a-fullstack-app-with-dartfrog-and-flutter-in-a-monorepo-part-4) 
 - &lt;p&gt;In the previous part, we set up models, data sources, repositories, exceptions and failures for the full-stack to-do application. We also made some changes to our packages. In this part, we will:&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;&lt;p&gt;Connect to a &lt;a target=&quot;_blank&quot; href=&quot;https://www.postgresql.org/&quot;&gt;Postgres&lt;/a&gt; database&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;Complete the backend routes&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;Add a new controller to handle HTTP requests&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;Add necessary failures and exceptions&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;Fully implement CRUD operations for the to-do application&lt;/p&gt;
&lt;/li&gt;
&lt;/ul&gt;
&lt;h1 id=&quot;heading-implementing-the-backend&quot;&gt;🚀 Implementing the Backend&lt;/h1&gt;
&lt;p&gt;It&#39;s time to tackle the backend of our to-do app! 💪 Let&#39;s get coding! 💻&lt;/p&gt;
&lt;h2 id=&quot;heading-importing-necessary-dependencies&quot;&gt;Importing necessary dependencies 📦&lt;/h2&gt;
&lt;blockquote&gt;
&lt;p&gt;Time to bring in the big guns! 💪 Let&#39;s import those dependencies&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;We will import all the necessary dependencies in the &lt;code&gt;pubspec.yaml&lt;/code&gt; file.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-yaml&quot;&gt;&lt;span class=&quot;hljs-attr&quot;&gt;dependencies:&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;dart_frog:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^0.3.0&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;data_source:&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;path:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;../data_source&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;dotenv:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^4.0.1&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;either_dart:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^0.3.0&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;exceptions:&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;path:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;../exceptions&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;failures:&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;path:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;../failures&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;http:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^0.13.5&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;models:&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;path:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;../models&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;postgres:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^2.5.2&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;repository:&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;path:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;../repository&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;typedefs:&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;path:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;../typedefs&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;h2 id=&quot;heading-setting-up-the-postgres-database&quot;&gt;🛠 Setting up the Postgres database&lt;/h2&gt;
&lt;blockquote&gt;
&lt;p&gt;💾 Let&#39;s create a database&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;We will be using the &lt;a target=&quot;_blank&quot; href=&quot;https://www.postgresql.org/&quot;&gt;PostgreSQL&lt;/a&gt; database for this tutorial. To use the &lt;a target=&quot;_blank&quot; href=&quot;https://www.postgresql.org/&quot;&gt;PostgreSQL&lt;/a&gt; database for this tutorial, we can set up a test database on &lt;a target=&quot;_blank&quot; href=&quot;http://elephantsql.com&quot;&gt;elephantsql.com&lt;/a&gt;. Simply sign up on the website and click on the option to create a new instance. You should see something similar to this.&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1672567276279/aed8bde3-4e4f-4be1-8870-249f1ccacf4f.png&quot; alt=&quot;Elephant SQL New DB&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;p&gt;Once you add a name, you will be prompted to choose a name for your instance and a region that is nearest to you. I have selected the &lt;code&gt;AP-East-1&lt;/code&gt; region, but you can choose any region that you prefer.&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1672567316874/4a5d9897-4fad-44a7-8aba-97aac2734568.png&quot; alt=&quot;Elephant SQL Select Region&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;p&gt;Once you have chosen a name and selected a region, click the &lt;code&gt;Create Instance&lt;/code&gt; button. This will redirect you to a dashboard where you can click on the instance name to access the credentials for the database you have just created. The credentials should look similar to this.&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1672567334246/aba373d5-7eb6-417b-872e-70e3c7a53b70.png&quot; alt=&quot;Elephant SQL Creds&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;h2 id=&quot;heading-connecting-to-the-database&quot;&gt;Connecting to the Database 🔌&lt;/h2&gt;
&lt;blockquote&gt;
&lt;p&gt;💻 Setting up our database connection like a boss&lt;/p&gt;
&lt;/blockquote&gt;
&lt;h3 id=&quot;heading-setting-up-environment&quot;&gt;Setting up environment 🌿&lt;/h3&gt;
&lt;p&gt;Now that we have created a database, we can connect to it from our application. To do this, we will create a new file &lt;code&gt;.env&lt;/code&gt; at the root of the &lt;code&gt;backend&lt;/code&gt; directory. This file will contain the credentials for the database that we have just created. The &lt;code&gt;.env&lt;/code&gt; file should look similar to this.&lt;/p&gt;
&lt;p&gt;Once this is done, we will use the &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/dotenv&quot;&gt;dotenv&lt;/a&gt; package to load the environment variables from the &lt;code&gt;.env&lt;/code&gt; file. We will also use the &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/postgres&quot;&gt;postgres&lt;/a&gt; package to connect to the database. You can run the following command in the backend directory to add the necessary dependencies.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;dart pub add dotenv postgres
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;This is how &lt;code&gt;.env&lt;/code&gt; file should look. Make sure to use your database credentials&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-apache&quot;&gt;&lt;span class=&quot;hljs-attribute&quot;&gt;DB_HOST&lt;/span&gt;=tiny.db.elephantsql.com
&lt;span class=&quot;hljs-attribute&quot;&gt;DB_PORT&lt;/span&gt;=&lt;span class=&quot;hljs-number&quot;&gt;5432&lt;/span&gt;
&lt;span class=&quot;hljs-attribute&quot;&gt;DB_DATABASE&lt;/span&gt;=asztgqfq
&lt;span class=&quot;hljs-attribute&quot;&gt;DB_USERNAME&lt;/span&gt;=asztgqfq
&lt;span class=&quot;hljs-attribute&quot;&gt;DB_PASSWORD&lt;/span&gt;=PcIXbvXQLwpEON&lt;span class=&quot;hljs-number&quot;&gt;61&lt;/span&gt;GVPzqs&lt;span class=&quot;hljs-number&quot;&gt;0&lt;/span&gt;zHyzHyHZc
&lt;/code&gt;&lt;/pre&gt;
&lt;h3 id=&quot;heading-creating-database-connection&quot;&gt;Creating database connection 🔗&lt;/h3&gt;
&lt;p&gt;Now, create a &lt;code&gt;backend/lib/db/database_connection.dart&lt;/code&gt; file and add the following code.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;dart:developer&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dotenv/dotenv.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:postgres/postgres.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;DatabaseConnection&lt;/span&gt; &lt;/span&gt;{
  DatabaseConnection&lpar;&lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;._dotEnv&rpar; {
    _host = _dotEnv[&lt;span class=&quot;hljs-string&quot;&gt;&#39;DB_HOST&#39;&lt;/span&gt;] ?? &lt;span class=&quot;hljs-string&quot;&gt;&#39;localhost&#39;&lt;/span&gt;;
    _port = &lt;span class=&quot;hljs-built_in&quot;&gt;int&lt;/span&gt;.tryParse&lpar;_dotEnv[&lt;span class=&quot;hljs-string&quot;&gt;&#39;DB_PORT&#39;&lt;/span&gt;] ?? &lt;span class=&quot;hljs-string&quot;&gt;&#39;&#39;&lt;/span&gt;&rpar; ?? &lt;span class=&quot;hljs-number&quot;&gt;5432&lt;/span&gt;;
    _database = _dotEnv[&lt;span class=&quot;hljs-string&quot;&gt;&#39;DB_DATABASE&#39;&lt;/span&gt;] ?? &lt;span class=&quot;hljs-string&quot;&gt;&#39;test&#39;&lt;/span&gt;;
    _username = _dotEnv[&lt;span class=&quot;hljs-string&quot;&gt;&#39;DB_USERNAME&#39;&lt;/span&gt;] ?? &lt;span class=&quot;hljs-string&quot;&gt;&#39;test&#39;&lt;/span&gt;;
    _password = _dotEnv[&lt;span class=&quot;hljs-string&quot;&gt;&#39;DB_PASSWORD&#39;&lt;/span&gt;] ?? &lt;span class=&quot;hljs-string&quot;&gt;&#39;test&#39;&lt;/span&gt;;
  }

  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; DotEnv _dotEnv;
  &lt;span class=&quot;hljs-keyword&quot;&gt;late&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; _host;
  &lt;span class=&quot;hljs-keyword&quot;&gt;late&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;int&lt;/span&gt; _port;
  &lt;span class=&quot;hljs-keyword&quot;&gt;late&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; _database;
  &lt;span class=&quot;hljs-keyword&quot;&gt;late&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; _username;
  &lt;span class=&quot;hljs-keyword&quot;&gt;late&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; _password;
  PostgreSQLConnection? _connection;

  PostgreSQLConnection &lt;span class=&quot;hljs-keyword&quot;&gt;get&lt;/span&gt; db =&amp;gt;
      _connection ??= &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; Exception&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;Database connection not initialized&#39;&lt;/span&gt;&rpar;;

  Future&amp;lt;&lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt;&amp;gt; connect&lpar;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;try&lt;/span&gt; {
      _connection = PostgreSQLConnection&lpar;
        _host,
        _port,
        _database,
        username: _username,
        password: _password,
      &rpar;;
      log&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;Database connection successful&#39;&lt;/span&gt;&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; _connection!.open&lpar;&rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
      log&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;Database connection failed: &lt;span class=&quot;hljs-subst&quot;&gt;$e&lt;/span&gt;&#39;&lt;/span&gt;&rpar;;
    }
  }

  Future&amp;lt;&lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt;&amp;gt; close&lpar;&rpar; =&amp;gt; _connection!.close&lpar;&rpar;;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Whenever we want to query, we will open a connection to the database and close it once we are done. This will ensure that we are not keeping the connection open for too long.&lt;/p&gt;
&lt;h3 id=&quot;heading-injecting-databaseconnection-through-provider&quot;&gt;💉Injecting &lt;code&gt;DatabaseConnection&lt;/code&gt; through &lt;code&gt;provider&lt;/code&gt;&lt;/h3&gt;
&lt;p&gt;Create a new file &lt;code&gt;routes/_middleware.dart&lt;/code&gt; and add the following code.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/db/database_connection.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dart_frog/dart_frog.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dotenv/dotenv.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; env = DotEnv&lpar;&rpar;..load&lpar;&rpar;;
&lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; _db = DatabaseConnection&lpar;env&rpar;;

Handler middleware&lpar;Handler handler&rpar; {
  &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; handler.use&lpar;provider&amp;lt;DatabaseConnection&amp;gt;&lpar;&lpar;_&rpar; =&amp;gt; _db&rpar;&rpar;;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;This middleware is used to provide the &lt;code&gt;DatabaseConnection&lt;/code&gt; instance to other parts of the application through a &lt;code&gt;provider&lt;/code&gt;.&lt;/p&gt;
&lt;h3 id=&quot;heading-fetching-databaseconnection-from-provider&quot;&gt;Fetching &lt;code&gt;DatabaseConnection&lt;/code&gt; from &lt;code&gt;provider&lt;/code&gt; 🔍&lt;/h3&gt;
&lt;p&gt;Now in &lt;code&gt;routes/index.dart&lt;/code&gt; you can get this &lt;code&gt;DatabaseConnection&lt;/code&gt; from &lt;code&gt;RequestContext&lt;/code&gt; and use it to query the database.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/db/database_connection.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dart_frog/dart_frog.dart&#39;&lt;/span&gt;;

Future&amp;lt;Response&amp;gt; onRequest&lpar;RequestContext context&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; connection = context.read&amp;lt;DatabaseConnection&amp;gt;&lpar;&rpar;;
  &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; connection.connect&lpar;&rpar;;
  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; response =
      &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; connection.db.query&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;select * from information_schema.tables&#39;&lt;/span&gt;&rpar;;
  &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; connection.close&lpar;&rpar;;
  &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Response.json&lpar;body: response.map&lpar;&lpar;e&rpar; =&amp;gt; e.toColumnMap&lpar;&rpar;&rpar;.toList&lpar;&rpar;&rpar;;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;If you run &lt;code&gt;dart_frog dev&lt;/code&gt;, then you should be able to open &lt;code&gt;http://localhost:8080&lt;/code&gt; and see the following output.&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1672567384241/52a4d34e-c9b0-4237-bf5c-c399941321f9.png&quot; alt=&quot;Database Connection Successful&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;p&gt;We have successfully connected to the database.&lt;/p&gt;
&lt;h3 id=&quot;heading-create-database-table&quot;&gt;Create Database Table 📝&lt;/h3&gt;
&lt;blockquote&gt;
&lt;p&gt;🗃 Let&#39;s build our database table&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;Before implementing the &lt;code&gt;TodoDataSource&lt;/code&gt;, we will need to create the table in the database. To do this, open the &lt;a target=&quot;_blank&quot; href=&quot;elephantsql.com&quot;&gt;elephantsql.com&lt;/a&gt; dashboard and click on the &lt;code&gt;BROWSER&lt;/code&gt; tab.&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1672567429967/334dd3bf-3d31-49fd-abc2-d2235d7865b4.png&quot; alt=&quot;Elephant SQL Query Execution&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;p&gt;Then, execute the following query:&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-sql&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;CREATE&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;TABLE&lt;/span&gt; todos&lpar;
    &lt;span class=&quot;hljs-keyword&quot;&gt;id&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;SERIAL&lt;/span&gt; PRIMARY &lt;span class=&quot;hljs-keyword&quot;&gt;KEY&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;NOT&lt;/span&gt; &lt;span class=&quot;hljs-literal&quot;&gt;NULL&lt;/span&gt;,
    title &lt;span class=&quot;hljs-built_in&quot;&gt;VARCHAR&lt;/span&gt;&lpar;&lt;span class=&quot;hljs-number&quot;&gt;255&lt;/span&gt;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;NOT&lt;/span&gt; &lt;span class=&quot;hljs-literal&quot;&gt;NULL&lt;/span&gt;,
    description &lt;span class=&quot;hljs-built_in&quot;&gt;TEXT&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;NOT&lt;/span&gt; &lt;span class=&quot;hljs-literal&quot;&gt;NULL&lt;/span&gt;,
    completed &lt;span class=&quot;hljs-built_in&quot;&gt;BOOL&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;DEFAULT&lt;/span&gt; &lt;span class=&quot;hljs-literal&quot;&gt;FALSE&lt;/span&gt;,
    created_at &lt;span class=&quot;hljs-built_in&quot;&gt;timestamp&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;default&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;current_timestamp&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;NOT&lt;/span&gt; &lt;span class=&quot;hljs-literal&quot;&gt;NULL&lt;/span&gt;,
    updated_at &lt;span class=&quot;hljs-built_in&quot;&gt;timestamp&lt;/span&gt; &lt;span class=&quot;hljs-literal&quot;&gt;null&lt;/span&gt;
&rpar;;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;This &lt;a target=&quot;_blank&quot; href=&quot;https://www.tutorialspoint.com/postgresql/postgresql_create_table.htm&quot;&gt;PostgreSQL query&lt;/a&gt; creates a new table called todos with the following columns:&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;&lt;p&gt;&lt;code&gt;id&lt;/code&gt;: an integer column that is the table&#39;s primary key and is generated automatically by the database &lpar;using the &lt;a target=&quot;_blank&quot; href=&quot;https://www.educba.com/postgresql-serial/&quot;&gt;&lt;code&gt;SERIAL&lt;/code&gt;&lt;/a&gt; type&rpar;. The &lt;a target=&quot;_blank&quot; href=&quot;https://www.tutorialspoint.com/postgresql/postgresql_constraints.htm&quot;&gt;&lt;code&gt;NOT NULL&lt;/code&gt;&lt;/a&gt; constraint ensures that this column cannot contain a &lt;code&gt;NULL&lt;/code&gt; value.&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;code&gt;title&lt;/code&gt;: a string column with a maximum length of 255 characters. The &lt;a target=&quot;_blank&quot; href=&quot;https://www.tutorialspoint.com/postgresql/postgresql_constraints.htm&quot;&gt;&lt;code&gt;NOT NULL&lt;/code&gt;&lt;/a&gt; constraint ensures that this column cannot contain a &lt;code&gt;NULL&lt;/code&gt; value.&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;code&gt;description&lt;/code&gt;: a text column. The &lt;code&gt;NOT NULL&lt;/code&gt; constraint ensures that this column cannot contain a &lt;code&gt;NULL&lt;/code&gt; value.&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;code&gt;completed&lt;/code&gt;: a boolean column with a default value of &lt;code&gt;FALSE&lt;/code&gt;.&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;code&gt;created_at&lt;/code&gt;: a &lt;a target=&quot;_blank&quot; href=&quot;https://www.educba.com/postgresql-timestamp/&quot;&gt;&lt;code&gt;timestamp&lt;/code&gt;&lt;/a&gt; column with a default value of the current timestamp. The &lt;code&gt;NOT NULL&lt;/code&gt; constraint ensures that this column cannot contain a &lt;code&gt;NULL&lt;/code&gt; value.&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;code&gt;updated_at&lt;/code&gt;: a &lt;a target=&quot;_blank&quot; href=&quot;https://www.educba.com/postgresql-timestamp/&quot;&gt;&lt;code&gt;timestamp&lt;/code&gt;&lt;/a&gt; column that can contain a &lt;code&gt;NULL&lt;/code&gt; value.&lt;/p&gt;
&lt;/li&gt;
&lt;/ul&gt;
&lt;p&gt;The &lt;code&gt;todos&lt;/code&gt; table will be used to store the to-do items in our application. Each row in the table represents a single to-do item, and the table&#39;s columns store the data for that to-do item.&lt;/p&gt;
&lt;p&gt;Once you run the query, you should see a toast message at the top.&lt;/p&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1672567447946/08dd1b1d-1c5b-4f4d-bd8b-7562dc7ffc3f.png&quot; alt=&quot;Elephant SQL Query Success&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;h2 id=&quot;heading-implementing-tododatasource&quot;&gt;Implementing &lt;code&gt;TodoDataSource&lt;/code&gt; 💪&lt;/h2&gt;
&lt;blockquote&gt;
&lt;p&gt;Cooking up some &lt;code&gt;TodoDataSource&lt;/code&gt; magic 🔮&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;We will implement the todo data source in &lt;code&gt;backend/lib/todo/data_source/todo_data_source_impl.dart&lt;/code&gt;. This file will contain the implementation of the &lt;code&gt;TodoDataSource&lt;/code&gt; interface. We will pass a &lt;code&gt;DatabaseConnection&lt;/code&gt; as a dependency to this class.&lt;/p&gt;
&lt;p&gt;Create &lt;code&gt;TodoDataSourceImpl&lt;/code&gt; and implement &lt;code&gt;TodoDataSource&lt;/code&gt; interface, and override necessary methods. The empty implementation should look like this.&lt;/p&gt;
&lt;h3 id=&quot;heading-empty-tododatasource-implementation&quot;&gt;Empty &lt;code&gt;TodoDataSource&lt;/code&gt; implementation&lt;/h3&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/db/database_connection.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:data_source/data_source.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:models/models.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:typedefs/typedefs.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;TodoDataSourceImpl&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;implements&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;TodoDataSource&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; TodoDataSourceImpl&lpar;&lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;._databaseConnection&rpar;;
  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; DatabaseConnection _databaseConnection;

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Todo&amp;gt; createTodo&lpar;CreateTodoDto todo&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; UnimplementedError&lpar;&rpar;;
  }

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;&lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt;&amp;gt; deleteTodoById&lpar;TodoId id&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; UnimplementedError&lpar;&rpar;;
  }

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&amp;lt;Todo&amp;gt;&amp;gt; getAllTodo&lpar;&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; UnimplementedError&lpar;&rpar;;
  }

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Todo&amp;gt; getTodoById&lpar;TodoId id&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; UnimplementedError&lpar;&rpar;;
  }

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Todo&amp;gt; updateTodo&lpar;{&lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; TodoId id, &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; UpdateTodoDto todo}&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; UnimplementedError&lpar;&rpar;;
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;h3 id=&quot;heading-injecting-tododatasource-through-provider&quot;&gt;💉Injecting &lt;code&gt;TodoDataSource&lt;/code&gt; through &lt;code&gt;provider&lt;/code&gt;&lt;/h3&gt;
&lt;blockquote&gt;
&lt;p&gt;Let&#39;s add this to our global middleware in &lt;code&gt;routes/_middleware.dart&lt;/code&gt; file&lt;/p&gt;
&lt;/blockquote&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/db/database_connection.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/todo/data_source/todo_data_source_impl.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dart_frog/dart_frog.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dotenv/dotenv.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; env = DotEnv&lpar;&rpar;..load&lpar;&rpar;;
&lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; _db = DatabaseConnection&lpar;env&rpar;;
&lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; _ds = TodoDataSourceImpl&lpar;_db&rpar;;

Handler middleware&lpar;Handler handler&rpar; {
  &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; handler
      .use&lpar;requestLogger&lpar;&rpar;&rpar;
      .use&lpar;provider&amp;lt;DatabaseConnection&amp;gt;&lpar;&lpar;_&rpar; =&amp;gt; _db&rpar;&rpar;
      .use&lpar;provider&amp;lt;TodoDataSource&amp;gt;&lpar;&lpar;_&rpar; =&amp;gt; _ds&rpar;&rpar;;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;h3 id=&quot;heading-createtodo-implementation&quot;&gt;&lt;code&gt;createTodo&lt;/code&gt; implementation&lt;/h3&gt;
&lt;p&gt;Now we will implement the &lt;code&gt;createTodo&lt;/code&gt; method.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Todo&amp;gt; createTodo&lpar;CreateTodoDto todo&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;try&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _databaseConnection.connect&lpar;&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; result = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _databaseConnection.db.query&lpar;
        &lt;span class=&quot;hljs-string&quot;&gt;&#39;&#39;&#39;
        INSERT INTO todos &lpar;title, description, completed, created_at&rpar;
        VALUES &lpar;@title, @description, @completed, @created_at&rpar; RETURNING *
        &#39;&#39;&#39;&lt;/span&gt;,
        substitutionValues: {
          &lt;span class=&quot;hljs-string&quot;&gt;&#39;title&#39;&lt;/span&gt;: todo.title,
          &lt;span class=&quot;hljs-string&quot;&gt;&#39;description&#39;&lt;/span&gt;: todo.description,
          &lt;span class=&quot;hljs-string&quot;&gt;&#39;completed&#39;&lt;/span&gt;: &lt;span class=&quot;hljs-keyword&quot;&gt;false&lt;/span&gt;,
          &lt;span class=&quot;hljs-string&quot;&gt;&#39;created_at&#39;&lt;/span&gt;: &lt;span class=&quot;hljs-built_in&quot;&gt;DateTime&lt;/span&gt;.now&lpar;&rpar;,
        },
      &rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;result.affectedRowCount == &lt;span class=&quot;hljs-number&quot;&gt;0&lt;/span&gt;&rpar; {
        &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; ServerException&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;Failed to create todo&#39;&lt;/span&gt;&rpar;;
      }
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; todoMap = result.first.toColumnMap&lpar;&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Todo&lpar;
        id: todoMap[&lt;span class=&quot;hljs-string&quot;&gt;&#39;id&#39;&lt;/span&gt;] &lt;span class=&quot;hljs-keyword&quot;&gt;as&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;int&lt;/span&gt;,
        title: todoMap[&lt;span class=&quot;hljs-string&quot;&gt;&#39;title&#39;&lt;/span&gt;] &lt;span class=&quot;hljs-keyword&quot;&gt;as&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;,
        description: todoMap[&lt;span class=&quot;hljs-string&quot;&gt;&#39;description&#39;&lt;/span&gt;] &lt;span class=&quot;hljs-keyword&quot;&gt;as&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;,
        createdAt: todoMap[&lt;span class=&quot;hljs-string&quot;&gt;&#39;created_at&#39;&lt;/span&gt;] &lt;span class=&quot;hljs-keyword&quot;&gt;as&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;DateTime&lt;/span&gt;,
      &rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;on&lt;/span&gt; PostgreSQLException &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; ServerException&lpar;e.message ?? &lt;span class=&quot;hljs-string&quot;&gt;&#39;Unexpected error&#39;&lt;/span&gt;&rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;finally&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _databaseConnection.close&lpar;&rpar;;
    }
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;First, the method establishes a connection to the database using the &lt;code&gt;_databaseConnection&lt;/code&gt; object. Then, it uses the query method on the &lt;code&gt;db&lt;/code&gt; object to execute an &lt;code&gt;INSERT&lt;/code&gt; statement The &lt;code&gt;substitutionValues&lt;/code&gt; parameter is used to bind the values from the &lt;code&gt;CreateTodoDto&lt;/code&gt; .&lt;/p&gt;
&lt;p&gt;If the &lt;code&gt;INSERT&lt;/code&gt; statement is successful, the method retrieves the inserted row from the database using the &lt;code&gt;RETURNING *&lt;/code&gt; clause and converts it to a map using the &lt;code&gt;toColumnMap&lt;/code&gt; method. The method then uses this map to create and return a new &lt;code&gt;Todo&lt;/code&gt; object.&lt;/p&gt;
&lt;h3 id=&quot;heading-getalltodo-implementation&quot;&gt;&lt;code&gt;getAllTodo&lt;/code&gt; implementation&lt;/h3&gt;
&lt;p&gt;Now we will implement the &lt;code&gt;getAllTodo&lt;/code&gt; method.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&amp;lt;Todo&amp;gt;&amp;gt; getAllTodo&lpar;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;try&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _databaseConnection.connect&lpar;&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; result = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _databaseConnection.db.query&lpar;
        &lt;span class=&quot;hljs-string&quot;&gt;&#39;SELECT * FROM todos&#39;&lt;/span&gt;,
      &rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; data =
          result.map&lpar;&lpar;e&rpar; =&amp;gt; e.toColumnMap&lpar;&rpar;&rpar;.map&lpar;Todo.fromJson&rpar;.toList&lpar;&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; data;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;on&lt;/span&gt; PostgreSQLException &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; ServerException&lpar;e.message ?? &lt;span class=&quot;hljs-string&quot;&gt;&#39;Unexpected error&#39;&lt;/span&gt;&rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;finally&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _databaseConnection.close&lpar;&rpar;;
    }
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;This &lt;code&gt;getAllTodo&lt;/code&gt; method is used to retrieve a list of all the to-do items stored in the database. This executes a &lt;code&gt;SELECT&lt;/code&gt; query to retrieve all rows from the &lt;code&gt;todos&lt;/code&gt; table, maps each row to a &lt;code&gt;Todo&lt;/code&gt; object using the &lt;code&gt;Todo.fromJson&lt;/code&gt; function, and returns the list of &lt;code&gt;Todo&lt;/code&gt; objects.&lt;/p&gt;
&lt;h3 id=&quot;heading-gettodobyid-implementation&quot;&gt;&lt;code&gt;getTodoById&lt;/code&gt; implementation 🔍&lt;/h3&gt;
&lt;p&gt;Now we will implement the &lt;code&gt;getTodoById&lt;/code&gt; method.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
Future&amp;lt;Todo&amp;gt; getTodoById&lpar;TodoId id&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
  &lt;span class=&quot;hljs-keyword&quot;&gt;try&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _databaseConnection.connect&lpar;&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; result = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _databaseConnection.db.query&lpar;
      &lt;span class=&quot;hljs-string&quot;&gt;&#39;SELECT * FROM todos WHERE id = @id&#39;&lt;/span&gt;,
      substitutionValues: {&lt;span class=&quot;hljs-string&quot;&gt;&#39;id&#39;&lt;/span&gt;: id},
    &rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;result.isEmpty&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; NotFoundException&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;Todo not found&#39;&lt;/span&gt;&rpar;;
    }
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Todo.fromJson&lpar;result.first.toColumnMap&lpar;&rpar;&rpar;;
  } &lt;span class=&quot;hljs-keyword&quot;&gt;on&lt;/span&gt; PostgreSQLException &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; ServerException&lpar;e.message ?? &lt;span class=&quot;hljs-string&quot;&gt;&#39;Unexpected error&#39;&lt;/span&gt;&rpar;;
  } &lt;span class=&quot;hljs-keyword&quot;&gt;finally&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _databaseConnection.close&lpar;&rpar;;
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;We execute a &lt;code&gt;SELECT&lt;/code&gt; query that selects from &lt;code&gt;todos&lt;/code&gt; table where the id equals the provided id. If the query returns an empty result set, we throw a &lt;code&gt;NotFoundException&lt;/code&gt;, indicating that the requested to-do item could not be found, else it returns the mapped todo object.&lt;/p&gt;
&lt;h3 id=&quot;heading-updatetodo-implementation&quot;&gt;&lt;code&gt;updateTodo&lt;/code&gt; implementation 🔧&lt;/h3&gt;
&lt;p&gt;Here is the implementation of the &lt;code&gt;updateTodo&lt;/code&gt; method.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Todo&amp;gt; updateTodo&lpar;{
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; TodoId id,
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; UpdateTodoDto todo,
  }&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;try&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _databaseConnection.connect&lpar;&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; result = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _databaseConnection.db.query&lpar;
        &lt;span class=&quot;hljs-string&quot;&gt;&#39;&#39;&#39;
        UPDATE todos
        SET title = COALESCE&lpar;@new_title, title&rpar;,
            description = COALESCE&lpar;@new_description, description&rpar;,
            completed = COALESCE&lpar;@new_completed, completed&rpar;,
            updated_at = current_timestamp
        WHERE id = @id
        RETURNING *
        &#39;&#39;&#39;&lt;/span&gt;,
        substitutionValues: {
          &lt;span class=&quot;hljs-string&quot;&gt;&#39;id&#39;&lt;/span&gt;: id,
          &lt;span class=&quot;hljs-string&quot;&gt;&#39;new_title&#39;&lt;/span&gt;: todo.title,
          &lt;span class=&quot;hljs-string&quot;&gt;&#39;new_description&#39;&lt;/span&gt;: todo.description,
          &lt;span class=&quot;hljs-string&quot;&gt;&#39;new_completed&#39;&lt;/span&gt;: todo.completed,
        },
      &rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;result.isEmpty&rpar; {
        &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; NotFoundException&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;Todo not found&#39;&lt;/span&gt;&rpar;;
      }
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Todo.fromJson&lpar;result.first.toColumnMap&lpar;&rpar;&rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;on&lt;/span&gt; PostgreSQLException &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; ServerException&lpar;e.message ?? &lt;span class=&quot;hljs-string&quot;&gt;&#39;Unexpected error&#39;&lt;/span&gt;&rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;finally&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _databaseConnection.close&lpar;&rpar;;
    }
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;It executes an &lt;code&gt;UPDATE&lt;/code&gt; query on the todos table. If no value is provided for a column, then the &lt;code&gt;COALESCE&lt;/code&gt; function is used to keep the existing value in the database unchanged. The &lt;code&gt;updated_at&lt;/code&gt; column is set to the &lt;code&gt;current_timestamp&lt;/code&gt;. If the result set is empty, it means that no row with the given id was found, so a &lt;code&gt;NotFoundException&lt;/code&gt; is thrown.&lt;/p&gt;
&lt;h3 id=&quot;heading-deletetodobyid-implementation&quot;&gt;&lt;code&gt;deleteTodoById&lt;/code&gt; implementation 🗑&lt;/h3&gt;
&lt;p&gt;Now, we will implement the &lt;code&gt;deleteTodoById&lt;/code&gt; method.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;&lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt;&amp;gt; deleteTodoById&lpar;TodoId id&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;try&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _databaseConnection.connect&lpar;&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _databaseConnection.db.query&lpar;
        &lt;span class=&quot;hljs-string&quot;&gt;&#39;&#39;&#39;
        DELETE FROM todos
        WHERE id = @id
        &#39;&#39;&#39;&lt;/span&gt;,
        substitutionValues: {&lt;span class=&quot;hljs-string&quot;&gt;&#39;id&#39;&lt;/span&gt;: id},
      &rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;on&lt;/span&gt; PostgreSQLException &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; ServerException&lpar;e.message ?? &lt;span class=&quot;hljs-string&quot;&gt;&#39;Unexpected error&#39;&lt;/span&gt;&rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;finally&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _databaseConnection.close&lpar;&rpar;;
    }
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;If the delete statement is successful, the method does not return anything.&lt;/p&gt;
&lt;h3 id=&quot;heading-postgressqlexception-handling&quot;&gt;&lt;code&gt;PostgresSQLException&lt;/code&gt; handling 🚨&lt;/h3&gt;
&lt;p&gt;In all of the methods above, if there is an exception while querying, like &lt;code&gt;PostgresSQLException&lt;/code&gt;, it is caught and a &lt;code&gt;ServerException&lt;/code&gt; is thrown with a more general error message. Finally, the database connection is closed before the method finishes executing.&lt;/p&gt;
&lt;h2 id=&quot;heading-implementing-todorepository&quot;&gt;Implementing &lt;code&gt;TodoRepository&lt;/code&gt; 💪&lt;/h2&gt;
&lt;blockquote&gt;
&lt;p&gt;💪 Time to make that &lt;code&gt;TodoRepository&lt;/code&gt; do some work!&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;We will implement the todo repository in &lt;code&gt;backend/lib/todo/repositories/todo_repository_impl.dart&lt;/code&gt;. This file will contain the implementation of the &lt;code&gt;TodoRepository&lt;/code&gt; interface. We will pass a &lt;code&gt;TodoDataSource&lt;/code&gt; as a dependency to this class.&lt;/p&gt;
&lt;h3 id=&quot;heading-empty-todorepository-implementation&quot;&gt;Empty &lt;code&gt;TodoRepository&lt;/code&gt; implementation&lt;/h3&gt;
&lt;p&gt;Create &lt;code&gt;TodoRepositoryImpl&lt;/code&gt; and implement &lt;code&gt;TodoRepository&lt;/code&gt; interface, and override necessary methods. The empty implementation should look like this.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:data_source/data_source.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:either_dart/either.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:failures/failures.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:models/models.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:repository/repository.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:typedefs/src/typedefs.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;TodoRepositoryImpl&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;implements&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;TodoRepository&lt;/span&gt; &lt;/span&gt;{
  TodoRepositoryImpl&lpar;&lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;.dataSource&rpar;;

  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; TodoDataSource dataSource;

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Either&amp;lt;Failure, Todo&amp;gt;&amp;gt; createTodo&lpar;CreateTodoDto createTodoDto&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; UnimplementedError&lpar;&rpar;;
  }

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Either&amp;lt;Failure, &lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt;&amp;gt;&amp;gt; deleteTodo&lpar;TodoId id&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; UnimplementedError&lpar;&rpar;;
  }

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Either&amp;lt;Failure, Todo&amp;gt;&amp;gt; getTodoById&lpar;TodoId id&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; UnimplementedError&lpar;&rpar;;
  }

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Either&amp;lt;Failure, &lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&amp;lt;Todo&amp;gt;&amp;gt;&amp;gt; getTodos&lpar;&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; UnimplementedError&lpar;&rpar;;
  }

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Either&amp;lt;Failure, Todo&amp;gt;&amp;gt; updateTodo&lpar;{
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; TodoId id,
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; UpdateTodoDto updateTodoDto,
  }&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; UnimplementedError&lpar;&rpar;;
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;h3 id=&quot;heading-injecting-todorepository-through-provider&quot;&gt;💉Injecting &lt;code&gt;TodoRepository&lt;/code&gt; through &lt;code&gt;provider&lt;/code&gt;&lt;/h3&gt;
&lt;p&gt;Before implementing the methods of &lt;code&gt;TodoRepository&lt;/code&gt;, we will add it to our global middleware so that we can access it from our routes.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/db/database_connection.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/todo/data_source/todo_data_source_impl.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/todo/repositories/todo_repository_impl.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dart_frog/dart_frog.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:data_source/data_source.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dotenv/dotenv.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:repository/repository.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; env = DotEnv&lpar;&rpar;..load&lpar;&rpar;;
&lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; _db = DatabaseConnection&lpar;env&rpar;;
&lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; _ds = TodoDataSourceImpl&lpar;_db&rpar;;
&lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; _repo = TodoRepositoryImpl&lpar;_ds&rpar;;

Handler middleware&lpar;Handler handler&rpar; {
  &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; handler
      .use&lpar;requestLogger&lpar;&rpar;&rpar;
      .use&lpar;provider&amp;lt;DatabaseConnection&amp;gt;&lpar;&lpar;_&rpar; =&amp;gt; _db&rpar;&rpar;
      .use&lpar;provider&amp;lt;TodoDataSource&amp;gt;&lpar;&lpar;_&rpar; =&amp;gt; _ds&rpar;&rpar;
      .use&lpar;provider&amp;lt;TodoRepository&amp;gt;&lpar;&lpar;_&rpar; =&amp;gt; _repo&rpar;&rpar;;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;h3 id=&quot;heading-createtodo-implementation-1&quot;&gt;&lt;code&gt;createTodo&lt;/code&gt; implementation&lt;/h3&gt;
&lt;p&gt;Now we will implement the &lt;code&gt;createTodo&lt;/code&gt; method.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Either&amp;lt;Failure, Todo&amp;gt;&amp;gt; createTodo&lpar;CreateTodoDto createTodoDto&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;try&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; todo = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; dataSource.createTodo&lpar;createTodoDto&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Right&lpar;todo&rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;on&lt;/span&gt; ServerException &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
      log&lpar;e.message&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Left&lpar;
        ServerFailure&lpar;message: e.message&rpar;,
      &rpar;;
    }
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;In this code, we are implementing the &lt;code&gt;createTodo&lt;/code&gt; method which is part of the &lt;code&gt;TodoRepository&lt;/code&gt; interface using &lt;code&gt;dataSource.createTodo&lt;/code&gt; method. The &lt;code&gt;dataSource.createTodo&lt;/code&gt; method is responsible for inserting the todo into the database. If the insertion is successful, it returns the todo object.&lt;/p&gt;
&lt;h3 id=&quot;heading-gettodobyid-implementation-1&quot;&gt;&lt;code&gt;getTodoById&lt;/code&gt; implementation&lt;/h3&gt;
&lt;p&gt;Now we will implement the &lt;code&gt;getTodoById&lt;/code&gt; method.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Either&amp;lt;Failure, Todo&amp;gt;&amp;gt; getTodoById&lpar;TodoId id&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;try&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; res = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; dataSource.getTodoById&lpar;id&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Right&lpar;res&rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;on&lt;/span&gt; NotFoundException &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
      log&lpar;e.message&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Left&lpar;
        ServerFailure&lpar;
          message: e.message,
          statusCode: e.statusCode,
        &rpar;,
      &rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;on&lt;/span&gt; ServerException &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
      log&lpar;e.message&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Left&lpar;
        ServerFailure&lpar;message: e.message&rpar;,
      &rpar;;
    }
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;The method calls the &lt;code&gt;dataSource.getTodoById&lt;/code&gt; method, which is responsible for querying the database and returning the todo object. If the todo is found, it returns the value. A &lt;code&gt;NotFoundException&lt;/code&gt; is thrown when the todo with the given id is not found in the database.&lt;/p&gt;
&lt;h3 id=&quot;heading-gettodos-implementation&quot;&gt;&lt;code&gt;getTodos&lt;/code&gt; implementation&lt;/h3&gt;
&lt;p&gt;Here, we will implement the &lt;code&gt;getTodos&lt;/code&gt; method.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Either&amp;lt;Failure, &lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&amp;lt;Todo&amp;gt;&amp;gt;&amp;gt; getTodos&lpar;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;try&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Right&lpar;&lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; dataSource.getAllTodo&lpar;&rpar;&rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;on&lt;/span&gt; ServerException &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
      log&lpar;e.message&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Left&lpar;
        ServerFailure&lpar;message: e.message&rpar;,
      &rpar;;
    }
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;We call the &lt;code&gt;dataSource.getAllTodo&lt;/code&gt; method. If the method execution is successful, we return the list of todo items.&lt;/p&gt;
&lt;h3 id=&quot;heading-updatetodo-implementation-1&quot;&gt;&lt;code&gt;updateTodo&lt;/code&gt; implementation 🔧&lt;/h3&gt;
&lt;p&gt;Now we will implement the &lt;code&gt;updateTodo&lt;/code&gt; method.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Either&amp;lt;Failure, Todo&amp;gt;&amp;gt; updateTodo&lpar;{
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; TodoId id,
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; UpdateTodoDto updateTodoDto,
  }&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;try&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Right&lpar;
        &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; dataSource.updateTodo&lpar;
          id: id,
          todo: updateTodoDto,
        &rpar;,
      &rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;on&lt;/span&gt; NotFoundException &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
      log&lpar;e.message&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Left&lpar;
        ServerFailure&lpar;
          message: e.message,
          statusCode: e.statusCode,
        &rpar;,
      &rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;on&lt;/span&gt; ServerException &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
      log&lpar;e.message&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Left&lpar;
        ServerFailure&lpar;message: e.message&rpar;,
      &rpar;;
    }
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;The method updates the todo using the &lt;code&gt;dataSource.updateTodo&lt;/code&gt; method. If the update is successful, it returns the updated todo. If the update fails and a &lt;code&gt;NotFoundException&lt;/code&gt; is thrown, it logs the error message and returns a &lt;code&gt;ServerFailure&lt;/code&gt; object with the appropriate status code.&lt;/p&gt;
&lt;h3 id=&quot;heading-deletetodo-implementation&quot;&gt;&lt;code&gt;deleteTodo&lt;/code&gt; implementation&lt;/h3&gt;
&lt;p&gt;Finally, we will implement the &lt;code&gt;deleteTodo&lt;/code&gt; method.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  Future&amp;lt;Either&amp;lt;Failure, &lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt;&amp;gt;&amp;gt; deleteTodo&lpar;TodoId id&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;try&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; exists = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; getTodoById&lpar;id&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;exists.isLeft&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; exists;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; todo = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; dataSource.deleteTodoById&lpar;id&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Right&lpar;todo&rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;on&lt;/span&gt; ServerException &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
      log&lpar;e.message&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Left&lpar;
        ServerFailure&lpar;message: e.message&rpar;,
      &rpar;;
    }
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;We check if a todo exists by calling the &lt;code&gt;this.getTodoById&lt;/code&gt; method. If it does not exist, we return a &lt;code&gt;Failure&lt;/code&gt;. If the todo does exist, we delete it by calling the &lt;code&gt;dataSource.deleteTodoById&lt;/code&gt;.&lt;/p&gt;
&lt;h3 id=&quot;heading-handling-exception&quot;&gt;Handling &lt;code&gt;Exception&lt;/code&gt; 🛑&lt;/h3&gt;
&lt;p&gt;The &lt;code&gt;dataSource&lt;/code&gt; methods throw exceptions like &lt;code&gt;ServerException&lt;/code&gt; and &lt;code&gt;NotFoundException&lt;/code&gt;. We catch these exceptions and log the error message. We then return a &lt;code&gt;Left&lt;/code&gt; object containing a &lt;code&gt;ServerFailure&lt;/code&gt; object. The &lt;code&gt;ServerFailure&lt;/code&gt; object is a custom failure type that we can use to indicate that a server error occurred.&lt;/p&gt;
&lt;h2 id=&quot;heading-building-the-todocontroller&quot;&gt;Building the &lt;code&gt;TodoController&lt;/code&gt; 🔨&lt;/h2&gt;
&lt;blockquote&gt;
&lt;p&gt;Bringing it all together with our fancy new controller 🎉&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;The controller will be responsible for handling HTTP requests and sending back the appropriate response. We will implement five methods in the controller:&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;&lt;p&gt;&lt;strong&gt;index&lt;/strong&gt; &lt;code&gt;GET /resource&lt;/code&gt; 🔍&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;strong&gt;show&lt;/strong&gt; &lt;code&gt;GET /resource/{id}&lt;/code&gt; 📖&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;strong&gt;store&lt;/strong&gt; &lt;code&gt;POST /resource&lt;/code&gt; 📤&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;strong&gt;update&lt;/strong&gt; &lt;code&gt;PUT/PATCH /resource/{id}&lt;/code&gt; 🔗&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;strong&gt;delete&lt;/strong&gt; &lt;code&gt;DELETE /resource/{id}&lt;/code&gt; 🗑&lt;/p&gt;
&lt;/li&gt;
&lt;/ul&gt;
&lt;p&gt;These methods will correspond to the standard HTTP methods for retrieving, creating, updating, and deleting data. By using these methods, we can keep our code clean and organized. This approach is inspired by the &lt;a target=&quot;_blank&quot; href=&quot;https://laravel.com/docs/9.x/controllers&quot;&gt;Laravel framework&#39;s API controller&lt;/a&gt; methods.&lt;/p&gt;
&lt;h3 id=&quot;heading-abstract-httpcontroller&quot;&gt;Abstract &lt;code&gt;HttpController&lt;/code&gt; 🔮&lt;/h3&gt;
&lt;p&gt;We will create a new abstract class in the &lt;code&gt;backend/lib/controller/http_controller.dart&lt;/code&gt; called &lt;code&gt;HttpController&lt;/code&gt; and which will have five methods.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;dart:async&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dart_frog/dart_frog.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;abstract&lt;/span&gt; &lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;HttpController&lt;/span&gt; &lt;/span&gt;{
  FutureOr&amp;lt;Response&amp;gt; index&lpar;Request request&rpar;;

  FutureOr&amp;lt;Response&amp;gt; store&lpar;Request request&rpar;;

  FutureOr&amp;lt;Response&amp;gt; &lt;span class=&quot;hljs-keyword&quot;&gt;show&lt;/span&gt;&lpar;Request request, &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; id&rpar;;

  FutureOr&amp;lt;Response&amp;gt; update&lpar;Request request, &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; id&rpar;;

  FutureOr&amp;lt;Response&amp;gt; destroy&lpar;Request request, &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; id&rpar;;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;h3 id=&quot;heading-empty-todocontroller-implementation&quot;&gt;Empty &lt;code&gt;TodoController&lt;/code&gt; implementation&lt;/h3&gt;
&lt;p&gt;Now for the implementation of this contract, we will create a new class &lt;code&gt;TodoController&lt;/code&gt; in the &lt;code&gt;backend/lib/controller/todo_controller.dart&lt;/code&gt; file. We will implement each method in the &lt;code&gt;TodoController&lt;/code&gt; class.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;dart:async&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;dart:convert&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;dart:io&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/controller/http_controller.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dart_frog/dart_frog.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:either_dart/either.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:exceptions/exceptions.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:failures/failures.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:models/models.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:repository/repository.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:typedefs/typedefs.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;TodoController&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;extends&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;HttpController&lt;/span&gt; &lt;/span&gt;{
  TodoController&lpar;&lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;._repo&rpar;;

  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; TodoRepository _repo;
  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  FutureOr&amp;lt;Response&amp;gt; index&lpar;Request request&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; UnimplementedError&lpar;&rpar;;
  }

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  FutureOr&amp;lt;Response&amp;gt; &lt;span class=&quot;hljs-keyword&quot;&gt;show&lt;/span&gt;&lpar;Request request, &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; id&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; UnimplementedError&lpar;&rpar;;
  }

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  FutureOr&amp;lt;Response&amp;gt; destroy&lpar;Request request, &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; id&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; UnimplementedError&lpar;&rpar;;
  }

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  FutureOr&amp;lt;Response&amp;gt; store&lpar;Request request&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; UnimplementedError&lpar;&rpar;;
  }

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  FutureOr&amp;lt;Response&amp;gt; update&lpar;Request request, &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; id&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; UnimplementedError&lpar;&rpar;;
  }

  Future&amp;lt;Either&amp;lt;Failure, &lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;dynamic&lt;/span&gt;&amp;gt;&amp;gt;&amp;gt; parseJson&lpar;
    Request request,
  &rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; UnimplementedError&lpar;&rpar;;
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;h3 id=&quot;heading-parse-request-body&quot;&gt;Parse request body 🔬&lt;/h3&gt;
&lt;p&gt;Before we implement the methods, we will create a new helper method in &lt;code&gt;HttpController&lt;/code&gt; which will be responsible to parse the request body.&lt;/p&gt;
&lt;p&gt;If the request body is not a valid JSON, it will return a &lt;code&gt;Left&lt;/code&gt; object containing a &lt;code&gt;BadRequestFailure&lt;/code&gt; object. If the request body is a valid JSON, it will return a &lt;code&gt;Right&lt;/code&gt; object containing the parsed JSON.&lt;/p&gt;
&lt;p&gt;Add the following method to the &lt;code&gt;HttpController&lt;/code&gt; class.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  Future&amp;lt;Either&amp;lt;Failure, &lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;dynamic&lt;/span&gt;&amp;gt;&amp;gt;&amp;gt; parseJson&lpar;
    Request request,
  &rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;try&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; body = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; request.body&lpar;&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;body.isEmpty&rpar; {
        &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; BadRequestException&lpar;message: &lt;span class=&quot;hljs-string&quot;&gt;&#39;Invalid body&#39;&lt;/span&gt;&rpar;;
      }
      &lt;span class=&quot;hljs-keyword&quot;&gt;late&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;dynamic&lt;/span&gt;&amp;gt; json;
      &lt;span class=&quot;hljs-keyword&quot;&gt;try&lt;/span&gt; {
        json = jsonDecode&lpar;body&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;as&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;dynamic&lt;/span&gt;&amp;gt;;
        &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Right&lpar;json&rpar;;
      } &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
        &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; BadRequestException&lpar;message: &lt;span class=&quot;hljs-string&quot;&gt;&#39;Invalid body&#39;&lt;/span&gt;&rpar;;
      }
    } &lt;span class=&quot;hljs-keyword&quot;&gt;on&lt;/span&gt; BadRequestException &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Left&lpar;
        ValidationFailure&lpar;
          message: e.message,
          errors: {},
        &rpar;,
      &rpar;;
    }
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;h3 id=&quot;heading-injecting-todocontroller-through-provider&quot;&gt;💉Injecting &lt;code&gt;TodoController&lt;/code&gt; through &lt;code&gt;provider&lt;/code&gt;&lt;/h3&gt;
&lt;blockquote&gt;
&lt;p&gt;Let&#39;s add this to our global middleware &lt;code&gt;routes/_middleware.dart&lt;/code&gt; file.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/db/database_connection.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/todo/controller/todo_controller.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/todo/data_source/todo_data_source_impl.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/todo/repositories/todo_repository_impl.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dart_frog/dart_frog.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:data_source/data_source.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dotenv/dotenv.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:repository/repository.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; env = DotEnv&lpar;&rpar;..load&lpar;&rpar;;
&lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; _db = DatabaseConnection&lpar;env&rpar;;
&lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; _ds = TodoDataSourceImpl&lpar;_db&rpar;;
&lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; _repo = TodoRepositoryImpl&lpar;_ds&rpar;;
&lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; _todoController = TodoController&lpar;_repo&rpar;;

Handler middleware&lpar;Handler handler&rpar; {
  &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; handler
      .use&lpar;requestLogger&lpar;&rpar;&rpar;
      .use&lpar;provider&amp;lt;DatabaseConnection&amp;gt;&lpar;&lpar;_&rpar; =&amp;gt; _db&rpar;&rpar;
      .use&lpar;provider&amp;lt;TodoDataSource&amp;gt;&lpar;&lpar;_&rpar; =&amp;gt; _ds&rpar;&rpar;
      .use&lpar;provider&amp;lt;TodoRepository&amp;gt;&lpar;&lpar;_&rpar; =&amp;gt; _repo&rpar;&rpar;
      .use&lpar;provider&amp;lt;TodoController&amp;gt;&lpar;&lpar;_&rpar; =&amp;gt; _todoController&rpar;&rpar;;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;blockquote&gt;
&lt;p&gt;Note: We are using &lt;code&gt;requestLogger&lt;/code&gt; middleware to log the request and response.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;h2 id=&quot;heading-implementing-todocontroller&quot;&gt;Implementing &lt;code&gt;TodoController&lt;/code&gt; 🚀&lt;/h2&gt;
&lt;p&gt;We will implement the &lt;code&gt;TodoController&lt;/code&gt; methods as follows:&lt;/p&gt;
&lt;h3 id=&quot;heading-index-implementation&quot;&gt;&lt;code&gt;index&lt;/code&gt; implementation&lt;/h3&gt;
&lt;p&gt;The &lt;code&gt;index&lt;/code&gt; method will be responsible for retrieving all todo items from the database. We will implement it as follows:&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  FutureOr&amp;lt;Response&amp;gt; index&lpar;Request request&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; res = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _repo.getTodos&lpar;&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; res.fold&lpar;
      &lpar;left&rpar; =&amp;gt; Response.json&lpar;
        body: {&lt;span class=&quot;hljs-string&quot;&gt;&#39;message&#39;&lt;/span&gt;: left.message},
        statusCode: left.statusCode,
      &rpar;,
      &lpar;right&rpar; =&amp;gt; Response.json&lpar;
        body: right.map&lpar;&lpar;e&rpar; =&amp;gt; e.toJson&lpar;&rpar;&rpar;.toList&lpar;&rpar;,
      &rpar;,
    &rpar;;
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;We will call the &lt;code&gt;getTodos&lt;/code&gt; method and map the response. If the failure case is returned, we will return a response with an error status code and the error message. Else, we will return a &lt;code&gt;200&lt;/code&gt; status code and the list of todos.&lt;/p&gt;
&lt;h3 id=&quot;heading-show-implementation&quot;&gt;&lt;code&gt;show&lt;/code&gt; implementation&lt;/h3&gt;
&lt;p&gt;&lt;code&gt;show&lt;/code&gt; method will be responsible for retrieving a single to-do item from the database. We will implement it as follows:&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  FutureOr&amp;lt;Response&amp;gt; &lt;span class=&quot;hljs-keyword&quot;&gt;show&lt;/span&gt;&lpar;Request request, &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; id&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; todoId = mapTodoId&lpar;id&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;todoId.isLeft&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Response.json&lpar;
        body: {&lt;span class=&quot;hljs-string&quot;&gt;&#39;message&#39;&lt;/span&gt;: todoId.left.message},
        statusCode: todoId.left.statusCode,
      &rpar;;
    }
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; res = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _repo.getTodoById&lpar;todoId.right&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; res.fold&lpar;
      &lpar;left&rpar; =&amp;gt; Response.json&lpar;
        body: {&lt;span class=&quot;hljs-string&quot;&gt;&#39;message&#39;&lt;/span&gt;: left.message},
        statusCode: left.statusCode,
      &rpar;,
      &lpar;right&rpar; =&amp;gt; Response.json&lpar;
        body: right.toJson&lpar;&rpar;,
      &rpar;,
    &rpar;;
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;We will first call &lt;code&gt;mapTodoId&lt;/code&gt; method to validate the &lt;code&gt;id&lt;/code&gt; parameter. If it returns a failure, we will return a failure response with the status code. Then we will get the todo item from the repository and return the todo item if it is found. Else, we will return a failure response with the status code.&lt;/p&gt;
&lt;h3 id=&quot;heading-store-implementation&quot;&gt;&lt;code&gt;store&lt;/code&gt; implementation&lt;/h3&gt;
&lt;p&gt;&lt;code&gt;store&lt;/code&gt; method is as follows&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  FutureOr&amp;lt;Response&amp;gt; store&lpar;Request request&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; parsedBody = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; parseJson&lpar;request&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;parsedBody.isLeft&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Response.json&lpar;
        body: {&lt;span class=&quot;hljs-string&quot;&gt;&#39;message&#39;&lt;/span&gt;: parsedBody.left.message},
        statusCode: parsedBody.left.statusCode,
      &rpar;;
    }
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; json = parsedBody.right;
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; createTodoDto = CreateTodoDto.validated&lpar;json&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;createTodoDto.isLeft&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Response.json&lpar;
        body: {
          &lt;span class=&quot;hljs-string&quot;&gt;&#39;message&#39;&lt;/span&gt;: createTodoDto.left.message,
          &lt;span class=&quot;hljs-string&quot;&gt;&#39;errors&#39;&lt;/span&gt;: createTodoDto.left.errors,
        },
        statusCode: createTodoDto.left.statusCode,
      &rpar;;
    }
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; res = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _repo.createTodo&lpar;createTodoDto.right&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; res.fold&lpar;
      &lpar;left&rpar; =&amp;gt; Response.json&lpar;
        body: {&lt;span class=&quot;hljs-string&quot;&gt;&#39;message&#39;&lt;/span&gt;: left.message},
        statusCode: left.statusCode,
      &rpar;,
      &lpar;right&rpar; =&amp;gt; Response.json&lpar;
        body: right.toJson&lpar;&rpar;,
        statusCode: HttpStatus.created,
      &rpar;,
    &rpar;;
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;If &lt;code&gt;parseJson&lt;/code&gt; resolves to a failure, we will return a response with an error status code and message.&lt;/p&gt;
&lt;p&gt;We will pass the JSON object to the &lt;code&gt;CreateTodoDto.validated&lt;/code&gt; method. If this returns a failure, we will return a response with an error status code and message, here it will be &lt;code&gt;ValidationFailure&lt;/code&gt;.&lt;/p&gt;
&lt;p&gt;We will pass the DTO to &lt;code&gt;createTodo&lt;/code&gt; method of the &lt;code&gt;TodoRepository&lt;/code&gt;. If creating fails we will return a response with an error status code and message.&lt;/p&gt;
&lt;p&gt;If everything goes right, we will return a response with a &lt;code&gt;201&lt;/code&gt; status code and the to-do item.&lt;/p&gt;
&lt;h3 id=&quot;heading-destroy-implementation&quot;&gt;&lt;code&gt;destroy&lt;/code&gt; implementation&lt;/h3&gt;
&lt;p&gt;&lt;code&gt;destroy&lt;/code&gt; method is as follows&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  FutureOr&amp;lt;Response&amp;gt; destroy&lpar;Request request, &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; id&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; todoId = mapTodoId&lpar;id&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;todoId.isLeft&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Response.json&lpar;
        body: {&lt;span class=&quot;hljs-string&quot;&gt;&#39;message&#39;&lt;/span&gt;: todoId.left.message},
        statusCode: todoId.left.statusCode,
      &rpar;;
    }
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; res = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _repo.deleteTodo&lpar;todoId.right&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; res.fold&lpar;
      &lpar;left&rpar; =&amp;gt; Response.json&lpar;
        body: {&lt;span class=&quot;hljs-string&quot;&gt;&#39;message&#39;&lt;/span&gt;: left.message},
        statusCode: left.statusCode,
      &rpar;,
      &lpar;right&rpar; =&amp;gt; Response.json&lpar;body: {&lt;span class=&quot;hljs-string&quot;&gt;&#39;message&#39;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&#39;OK&#39;&lt;/span&gt;}&rpar;,
    &rpar;;
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;We will first call &lt;code&gt;mapTodoId&lt;/code&gt; method to validate the &lt;code&gt;id&lt;/code&gt; parameter. If it returns a failure, we will return a failure response with the status code. Then we will get the delete todo item from the repository and return OK with 200 status code if. If there is a failure, we will return a failure response with the status code.&lt;/p&gt;
&lt;h3 id=&quot;heading-update-implementation&quot;&gt;&lt;code&gt;update&lt;/code&gt; implementation&lt;/h3&gt;
&lt;p&gt;&lt;code&gt;update&lt;/code&gt; method will be responsible for updating a single to-do item from the database. We will implement it as follows:&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  FutureOr&amp;lt;Response&amp;gt; update&lpar;Request request, &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; id&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; parsedBody = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; parseJson&lpar;request&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; todoId = mapTodoId&lpar;id&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;todoId.isLeft&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Response.json&lpar;
        body: {&lt;span class=&quot;hljs-string&quot;&gt;&#39;message&#39;&lt;/span&gt;: todoId.left.message},
        statusCode: todoId.left.statusCode,
      &rpar;;
    }
    &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;parsedBody.isLeft&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Response.json&lpar;
        body: {&lt;span class=&quot;hljs-string&quot;&gt;&#39;message&#39;&lt;/span&gt;: parsedBody.left.message},
        statusCode: parsedBody.left.statusCode,
      &rpar;;
    }

    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; json = parsedBody.right;
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; updateTodoDto = UpdateTodoDto.validated&lpar;json&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;updateTodoDto.isLeft&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Response.json&lpar;
        body: {
          &lt;span class=&quot;hljs-string&quot;&gt;&#39;message&#39;&lt;/span&gt;: updateTodoDto.left.message,
          &lt;span class=&quot;hljs-string&quot;&gt;&#39;errors&#39;&lt;/span&gt;: updateTodoDto.left.errors,
        },
        statusCode: updateTodoDto.left.statusCode,
      &rpar;;
    }
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; res = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; _repo.updateTodo&lpar;
      id: todoId.right,
      updateTodoDto: updateTodoDto.right,
    &rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; res.fold&lpar;
      &lpar;left&rpar; =&amp;gt; Response.json&lpar;
        body: {&lt;span class=&quot;hljs-string&quot;&gt;&#39;message&#39;&lt;/span&gt;: left.message},
        statusCode: left.statusCode,
      &rpar;,
      &lpar;right&rpar; =&amp;gt; Response.json&lpar;
        body: right.toJson&lpar;&rpar;,
      &rpar;,
    &rpar;;
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;This method is similar to the &lt;code&gt;store&lt;/code&gt; method. We will first validate the &lt;code&gt;id&lt;/code&gt; parameter and then the JSON body. If both are valid, we will call the &lt;code&gt;updateTodo&lt;/code&gt; method of the &lt;code&gt;TodoRepository&lt;/code&gt; and then resolve the failure or the updated value.&lt;/p&gt;
&lt;h2 id=&quot;heading-implementing-routes&quot;&gt;Implementing Routes 🛣&lt;/h2&gt;
&lt;p&gt;We will now implement the routes. These are the routes that we will have&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;&lt;p&gt;&lt;strong&gt;GET&lt;/strong&gt; &lt;code&gt;/todos&lt;/code&gt; - Get all todos&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;strong&gt;GET&lt;/strong&gt; &lt;code&gt;/todos/:id&lt;/code&gt; - Get a single todo&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;strong&gt;POST&lt;/strong&gt; &lt;code&gt;/todos&lt;/code&gt; - Create a todo&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;strong&gt;PUT&lt;/strong&gt; &lt;code&gt;/todos/:id&lt;/code&gt; - Update a todo&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;strong&gt;PATCH&lt;/strong&gt; &lt;code&gt;/todos/:id&lt;/code&gt; - Update a todo&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;strong&gt;DELETE&lt;/strong&gt; &lt;code&gt;/todos/:id&lt;/code&gt; - Delete a todo&lt;/p&gt;
&lt;/li&gt;
&lt;/ul&gt;
&lt;p&gt;&lt;code&gt;dart_frog&lt;/code&gt; has a file system routing. For example, let&#39;s say we need to create &lt;code&gt;todos/1&lt;/code&gt; route. We will create a file &lt;code&gt;routes/todos/[id].dart&lt;/code&gt; and it will be mapped to &lt;code&gt;todos/1&lt;/code&gt; route.&lt;/p&gt;
&lt;h3 id=&quot;heading-implementing-todos-route&quot;&gt;Implementing &lt;code&gt;todos/&lt;/code&gt; route&lt;/h3&gt;
&lt;p&gt;To implement all the HTTP methods related to &lt;code&gt;todos/&lt;/code&gt; route, we will create a new file &lt;code&gt;routes/todos/index.dart&lt;/code&gt;.&lt;/p&gt;
&lt;p&gt;We will create a file &lt;code&gt;routes/todos/index.dart&lt;/code&gt; and implement the routes as follows:&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;dart:io&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/todo/controller/todo_controller.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dart_frog/dart_frog.dart&#39;&lt;/span&gt;;

Future&amp;lt;Response&amp;gt; onRequest&lpar;RequestContext context&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; controller = context.read&amp;lt;TodoController&amp;gt;&lpar;&rpar;;
  &lt;span class=&quot;hljs-keyword&quot;&gt;switch&lt;/span&gt; &lpar;context.request.method&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;case&lt;/span&gt; HttpMethod.&lt;span class=&quot;hljs-keyword&quot;&gt;get&lt;/span&gt;:
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; controller.index&lpar;context.request&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;case&lt;/span&gt; HttpMethod.post:
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; controller.store&lpar;context.request&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;case&lt;/span&gt; HttpMethod.put:
    &lt;span class=&quot;hljs-keyword&quot;&gt;case&lt;/span&gt; HttpMethod.patch:
    &lt;span class=&quot;hljs-keyword&quot;&gt;case&lt;/span&gt; HttpMethod.delete:
    &lt;span class=&quot;hljs-keyword&quot;&gt;case&lt;/span&gt; HttpMethod.head:
    &lt;span class=&quot;hljs-keyword&quot;&gt;case&lt;/span&gt; HttpMethod.options:
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Response.json&lpar;
        body: {&lt;span class=&quot;hljs-string&quot;&gt;&#39;error&#39;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&#39;👀 Looks like you are lost 🔦&#39;&lt;/span&gt;},
        statusCode: HttpStatus.methodNotAllowed,
      &rpar;;
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Here, we are getting the &lt;code&gt;TodoController&lt;/code&gt; from the &lt;code&gt;context&lt;/code&gt; and mapping the respective HTTP method to the controller method. We are also handling cases when the HTTP method is not allowed.&lt;/p&gt;
&lt;h3 id=&quot;heading-implementing-todosid-route&quot;&gt;Implementing &lt;code&gt;todos/:id&lt;/code&gt; route&lt;/h3&gt;
&lt;p&gt;Similarly, we will create a file &lt;code&gt;routes/todos/[id].dart&lt;/code&gt; and implement the routes as follows:&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;dart:io&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:backend/todo/controller/todo_controller.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dart_frog/dart_frog.dart&#39;&lt;/span&gt;;

Future&amp;lt;Response&amp;gt; onRequest&lpar;RequestContext context, &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; id&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; todoController = context.read&amp;lt;TodoController&amp;gt;&lpar;&rpar;;
  &lt;span class=&quot;hljs-keyword&quot;&gt;switch&lt;/span&gt; &lpar;context.request.method&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;case&lt;/span&gt; HttpMethod.&lt;span class=&quot;hljs-keyword&quot;&gt;get&lt;/span&gt;:
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; todoController.&lt;span class=&quot;hljs-keyword&quot;&gt;show&lt;/span&gt;&lpar;context.request, id&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;case&lt;/span&gt; HttpMethod.put:
    &lt;span class=&quot;hljs-keyword&quot;&gt;case&lt;/span&gt; HttpMethod.patch:
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; todoController.update&lpar;context.request, id&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;case&lt;/span&gt; HttpMethod.delete:
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; todoController.destroy&lpar;context.request, id&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;case&lt;/span&gt; HttpMethod.head:
    &lt;span class=&quot;hljs-keyword&quot;&gt;case&lt;/span&gt; HttpMethod.options:
    &lt;span class=&quot;hljs-keyword&quot;&gt;case&lt;/span&gt; HttpMethod.post:
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Response.json&lpar;
        body: {&lt;span class=&quot;hljs-string&quot;&gt;&#39;error&#39;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&#39;👀 Looks like you are lost 🔦&#39;&lt;/span&gt;},
        statusCode: HttpStatus.methodNotAllowed,
      &rpar;;
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Here, we will get the &lt;code&gt;id&lt;/code&gt; parameter from the route as a second parameter in &lt;code&gt;onRequest&lt;/code&gt; method as a string. This can be anything. This explains the use of &lt;code&gt;mapTodoId&lt;/code&gt; function in &lt;code&gt;typedefs&lt;/code&gt; package.&lt;/p&gt;
&lt;p&gt;We will pass the &lt;code&gt;id&lt;/code&gt; parameter to the controller methods. We will also handle the case when the HTTP method is not allowed.&lt;/p&gt;
&lt;h3 id=&quot;heading-implementing-route&quot;&gt;Implementing &lt;code&gt;/&lt;/code&gt; route&lt;/h3&gt;
&lt;p&gt;Finally, we will update &lt;code&gt;routes/index.dart&lt;/code&gt; file to return &lt;code&gt;methodNotAllowed&lt;/code&gt; response. This is our &lt;code&gt;/&lt;/code&gt; route, which will be handled as follows:&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;dart:io&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:dart_frog/dart_frog.dart&#39;&lt;/span&gt;;

Future&amp;lt;Response&amp;gt; onRequest&lpar;RequestContext context&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
  &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Response.json&lpar;
    body: {&lt;span class=&quot;hljs-string&quot;&gt;&#39;error&#39;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&#39;👀 Looks like you are lost 🔦&#39;&lt;/span&gt;},
    statusCode: HttpStatus.methodNotAllowed,
  &rpar;;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;h1 id=&quot;heading-testing-backend&quot;&gt;🧪 Testing backend&lt;/h1&gt;
&lt;blockquote&gt;
&lt;p&gt;Time to put our backend to the test! 🔍&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;We will run some e2e tests, to verify the backend works fine. create a file &lt;code&gt;backend/e2e/routes_test.dart&lt;/code&gt; and implement the tests as follows:&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;dart:convert&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;dart:io&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:http/http.dart&#39;&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;as&lt;/span&gt; http;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:models/models.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:test/test.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt; main&lpar;&rpar; {
  &lt;span class=&quot;hljs-keyword&quot;&gt;late&lt;/span&gt; Todo createdTodo;
  tearDownAll&lpar;&lpar;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; response = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; http.&lt;span class=&quot;hljs-keyword&quot;&gt;get&lt;/span&gt;&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;Uri&lt;/span&gt;.parse&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;http://localhost:8080/todos&#39;&lt;/span&gt;&rpar;&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; todos = &lpar;jsonDecode&lpar;response.body&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;as&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&rpar;
        .map&lpar;&lpar;e&rpar; =&amp;gt; Todo.fromJson&lpar;e &lt;span class=&quot;hljs-keyword&quot;&gt;as&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;dynamic&lt;/span&gt;&amp;gt;&rpar;&rpar;
        .toList&lpar;&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;for&lt;/span&gt; &lpar;&lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; todo &lt;span class=&quot;hljs-keyword&quot;&gt;in&lt;/span&gt; todos&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; http.delete&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;Uri&lt;/span&gt;.parse&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;http://localhost:8080/todos/&lt;span class=&quot;hljs-subst&quot;&gt;${todo.id}&lt;/span&gt;&#39;&lt;/span&gt;&rpar;&rpar;;
    }
  }&rpar;;
  group&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;E2E -&#39;&lt;/span&gt;, &lpar;&rpar; {
    test&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;GET /todos returns empty list of todos&#39;&lt;/span&gt;, &lpar;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; response = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; http.&lt;span class=&quot;hljs-keyword&quot;&gt;get&lt;/span&gt;&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;Uri&lt;/span&gt;.parse&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;http://localhost:8080/todos&#39;&lt;/span&gt;&rpar;&rpar;;
      expect&lpar;response.statusCode, HttpStatus.ok&rpar;;
      expect&lpar;response.body, equals&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;[]&#39;&lt;/span&gt;&rpar;&rpar;;
    }&rpar;;

    test&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;POST /todos to create a new todo&#39;&lt;/span&gt;, &lpar;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; response = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; http.post&lpar;
        &lt;span class=&quot;hljs-built_in&quot;&gt;Uri&lt;/span&gt;.parse&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;http://localhost:8080/todos&#39;&lt;/span&gt;&rpar;,
        headers: {
          &lt;span class=&quot;hljs-string&quot;&gt;&#39;Content-Type&#39;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&#39;application/json&#39;&lt;/span&gt;,
        },
        body: jsonEncode&lpar;_createTodoDto.toJson&lpar;&rpar;&rpar;,
      &rpar;;
      expect&lpar;response.statusCode, HttpStatus.created&rpar;;
      createdTodo =
          Todo.fromJson&lpar;jsonDecode&lpar;response.body&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;as&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;dynamic&lt;/span&gt;&amp;gt;&rpar;;
      expect&lpar;createdTodo.title, equals&lpar;_createTodoDto.title&rpar;&rpar;;
      expect&lpar;createdTodo.description, equals&lpar;_createTodoDto.description&rpar;&rpar;;
    }&rpar;;

    test&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;GET /todos returns list of todos with one todo&#39;&lt;/span&gt;, &lpar;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; response = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; http.&lt;span class=&quot;hljs-keyword&quot;&gt;get&lt;/span&gt;&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;Uri&lt;/span&gt;.parse&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;http://localhost:8080/todos&#39;&lt;/span&gt;&rpar;&rpar;;
      expect&lpar;response.statusCode, HttpStatus.ok&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; todos = &lpar;jsonDecode&lpar;response.body&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;as&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&rpar;
          .map&lpar;&lpar;e&rpar; =&amp;gt; Todo.fromJson&lpar;e &lt;span class=&quot;hljs-keyword&quot;&gt;as&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;dynamic&lt;/span&gt;&amp;gt;&rpar;&rpar;
          .toList&lpar;&rpar;;
      expect&lpar;todos.length, equals&lpar;&lt;span class=&quot;hljs-number&quot;&gt;1&lt;/span&gt;&rpar;&rpar;;
      expect&lpar;todos.first, equals&lpar;createdTodo&rpar;&rpar;;
    }&rpar;;

    test&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;GET /todos/:id returns the created todo&#39;&lt;/span&gt;, &lpar;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; response = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; http.&lt;span class=&quot;hljs-keyword&quot;&gt;get&lt;/span&gt;&lpar;
        &lt;span class=&quot;hljs-built_in&quot;&gt;Uri&lt;/span&gt;.parse&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;http://localhost:8080/todos/&lt;span class=&quot;hljs-subst&quot;&gt;${createdTodo.id}&lt;/span&gt;&#39;&lt;/span&gt;&rpar;,
      &rpar;;
      expect&lpar;response.statusCode, HttpStatus.ok&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; todo =
          Todo.fromJson&lpar;jsonDecode&lpar;response.body&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;as&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;dynamic&lt;/span&gt;&amp;gt;&rpar;;
      expect&lpar;todo, equals&lpar;createdTodo&rpar;&rpar;;
    }&rpar;;

    test&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;PUT /todos/:id to update the created todo&#39;&lt;/span&gt;, &lpar;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; updateTodoDto = UpdateTodoDto&lpar;
        title: &lt;span class=&quot;hljs-string&quot;&gt;&#39;updated title&#39;&lt;/span&gt;,
        description: &lt;span class=&quot;hljs-string&quot;&gt;&#39;updated description&#39;&lt;/span&gt;,
      &rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; response = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; http.put&lpar;
        &lt;span class=&quot;hljs-built_in&quot;&gt;Uri&lt;/span&gt;.parse&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;http://localhost:8080/todos/&lt;span class=&quot;hljs-subst&quot;&gt;${createdTodo.id}&lt;/span&gt;&#39;&lt;/span&gt;&rpar;,
        headers: {
          &lt;span class=&quot;hljs-string&quot;&gt;&#39;Content-Type&#39;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&#39;application/json&#39;&lt;/span&gt;,
        },
        body: jsonEncode&lpar;updateTodoDto.toJson&lpar;&rpar;&rpar;,
      &rpar;;
      expect&lpar;response.statusCode, HttpStatus.ok&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; todo =
          Todo.fromJson&lpar;jsonDecode&lpar;response.body&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;as&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;dynamic&lt;/span&gt;&amp;gt;&rpar;;
      expect&lpar;todo.title, equals&lpar;updateTodoDto.title&rpar;&rpar;;
      expect&lpar;todo.description, equals&lpar;updateTodoDto.description&rpar;&rpar;;
    }&rpar;;

    test&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;PATCH /todos/:id to update the created todo&#39;&lt;/span&gt;, &lpar;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; updateTodoDto = UpdateTodoDto&lpar;
        title: &lt;span class=&quot;hljs-string&quot;&gt;&#39;UPDATED TITLE&#39;&lt;/span&gt;,
        description: &lt;span class=&quot;hljs-string&quot;&gt;&#39;UPDATED DESCRIPTION&#39;&lt;/span&gt;,
      &rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; response = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; http.patch&lpar;
        &lt;span class=&quot;hljs-built_in&quot;&gt;Uri&lt;/span&gt;.parse&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;http://localhost:8080/todos/&lt;span class=&quot;hljs-subst&quot;&gt;${createdTodo.id}&lt;/span&gt;&#39;&lt;/span&gt;&rpar;,
        headers: {
          &lt;span class=&quot;hljs-string&quot;&gt;&#39;Content-Type&#39;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&#39;application/json&#39;&lt;/span&gt;,
        },
        body: jsonEncode&lpar;updateTodoDto.toJson&lpar;&rpar;&rpar;,
      &rpar;;
      expect&lpar;response.statusCode, HttpStatus.ok&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; todo =
          Todo.fromJson&lpar;jsonDecode&lpar;response.body&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;as&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;dynamic&lt;/span&gt;&amp;gt;&rpar;;
      expect&lpar;todo.title, equals&lpar;updateTodoDto.title&rpar;&rpar;;
      expect&lpar;todo.description, equals&lpar;updateTodoDto.description&rpar;&rpar;;
    }&rpar;;

    test&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;DELETE /todos/:id to delete the created todo&#39;&lt;/span&gt;, &lpar;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; response = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; http.delete&lpar;
        &lt;span class=&quot;hljs-built_in&quot;&gt;Uri&lt;/span&gt;.parse&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;http://localhost:8080/todos/&lt;span class=&quot;hljs-subst&quot;&gt;${createdTodo.id}&lt;/span&gt;&#39;&lt;/span&gt;&rpar;,
      &rpar;;
      expect&lpar;response.statusCode, HttpStatus.ok&rpar;;
      expect&lpar;response.body, jsonEncode&lpar;{&lt;span class=&quot;hljs-string&quot;&gt;&#39;message&#39;&lt;/span&gt;: &lt;span class=&quot;hljs-string&quot;&gt;&#39;OK&#39;&lt;/span&gt;}&rpar;&rpar;;
    }&rpar;;
    test&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;GET /todos returns empty list of todos&#39;&lt;/span&gt;, &lpar;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;async&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; response = &lt;span class=&quot;hljs-keyword&quot;&gt;await&lt;/span&gt; http.&lt;span class=&quot;hljs-keyword&quot;&gt;get&lt;/span&gt;&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;Uri&lt;/span&gt;.parse&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;http://localhost:8080/todos&#39;&lt;/span&gt;&rpar;&rpar;;
      expect&lpar;response.statusCode, HttpStatus.ok&rpar;;
      expect&lpar;response.body, equals&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;[]&#39;&lt;/span&gt;&rpar;&rpar;;
    }&rpar;;
  }&rpar;;
}

&lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; _createTodoDto = CreateTodoDto&lpar;
  title: &lt;span class=&quot;hljs-string&quot;&gt;&#39;title&#39;&lt;/span&gt;,
  description: &lt;span class=&quot;hljs-string&quot;&gt;&#39;description&#39;&lt;/span&gt;,
&rpar;;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;To run the tests, first, start the backend server by running the following command:&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;dart_frog dev
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;And then on a new terminal run the tests:&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;dart &lt;span class=&quot;hljs-built_in&quot;&gt;test&lt;/span&gt; e2e/routes_test.dart
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;&lt;img src=&quot;https://cdn.hashnode.com/res/hashnode/image/upload/v1672567494374/49437eba-3aac-4eda-af60-fe4bd0850487.png&quot; alt=&quot;Tests Passing fine&quot; class=&quot;image--center mx-auto&quot; /&gt;&lt;/p&gt;
&lt;hr /&gt;
&lt;p&gt;Wow, we&#39;ve made it to the end of part 4! 🎉 It&#39;s been a wild ride, but we&#39;ve finally completed the backend of our full-stack to-do application. We connected to a Postgres database, completed all our backend routes, and fully implemented CRUD operations. We even tested our backend to make sure everything is running smoothly.&lt;/p&gt;
&lt;p&gt;But we&#39;re not done yet! In the final part of this tutorial, we&#39;ll be building the front end of our to-do app using Flutter. It&#39;s going to be a blast! 💻&lt;/p&gt;
&lt;p&gt;Don&#39;t forget, you can always refer back to the GitHub repo for this tutorial at &lt;a target=&quot;_blank&quot; href=&quot;https://github.com/saileshbro/full_stack_todo_dart&quot;&gt;https://github.com/saileshbro/full_stack_todo_dart&lt;/a&gt; if you need a little help along the way.&lt;/p&gt;
&lt;p&gt;Until next time, happy coding! 😄&lt;/p&gt;
 

 - 🚀[🚀 Building a Fullstack App with dart_frog and Flutter in a Monorepo - Part 3](https://saileshdahal.com.np/building-a-fullstack-app-with-dartfrog-and-flutter-in-a-monorepo-part-3) 
 - &lt;p&gt;In the previous part, we set up models, data sources, repositories, and failures for the full-stack to-do application. In this part, we will:&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;&lt;p&gt;Make changes to the failure classes&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;Create new failures&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;&lt;p&gt;&lt;a target=&quot;_blank&quot; href=&quot;https://github.com/saileshbro/full_stack_todo_dart/blob/780b4662d4a03c17aaef281b100c8a686d8317bb/failures/lib/src/request_failure/request_failure.dart&quot;&gt;&lt;code&gt;RequestFailure&lt;/code&gt;&lt;/a&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;a target=&quot;_blank&quot; href=&quot;https://github.com/saileshbro/full_stack_todo_dart/blob/780b4662d4a03c17aaef281b100c8a686d8317bb/failures/lib/src/validation_failure/validation_failure.dart&quot;&gt;&lt;code&gt;ValidationFailure&lt;/code&gt;&lt;/a&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;a target=&quot;_blank&quot; href=&quot;https://github.com/saileshbro/full_stack_todo_dart/blob/780b4662d4a03c17aaef281b100c8a686d8317bb/failures/lib/src/server_failure/server_failure.dart&quot;&gt;&lt;code&gt;ServerFailure&lt;/code&gt;&lt;/a&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;/ul&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;Create new Exceptions&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;&lt;p&gt;&lt;a target=&quot;_blank&quot; href=&quot;https://github.com/saileshbro/full_stack_todo_dart/blob/780b4662d4a03c17aaef281b100c8a686d8317bb/exceptions/lib/src/server_exception/server_exception.dart&quot;&gt;&lt;code&gt;ServerException&lt;/code&gt;&lt;/a&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;a target=&quot;_blank&quot; href=&quot;https://github.com/saileshbro/full_stack_todo_dart/blob/780b4662d4a03c17aaef281b100c8a686d8317bb/exceptions/lib/src/http_exception/http_exception.dart&quot;&gt;&lt;code&gt;HttpException&lt;/code&gt;&lt;/a&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;a target=&quot;_blank&quot; href=&quot;https://github.com/saileshbro/full_stack_todo_dart/blob/780b4662d4a03c17aaef281b100c8a686d8317bb/exceptions/lib/src/http_exception/not_found_exception.dart&quot;&gt;&lt;code&gt;NotFoundException&lt;/code&gt;&lt;/a&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;a target=&quot;_blank&quot; href=&quot;https://github.com/saileshbro/full_stack_todo_dart/blob/780b4662d4a03c17aaef281b100c8a686d8317bb/exceptions/lib/src/http_exception/bad_request_exception.dart&quot;&gt;&lt;code&gt;BadRequestException&lt;/code&gt;&lt;/a&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;/ul&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;Add validation to DTOs&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;a target=&quot;_blank&quot; href=&quot;https://github.com/saileshbro/full_stack_todo_dart/blob/780b4662d4a03c17aaef281b100c8a686d8317bb/models/lib/src/serializers/date_time_converter.dart&quot;&gt;Add JSON converters&lt;/a&gt;&lt;/p&gt;
&lt;/li&gt;
&lt;/ul&gt;
&lt;h1 id=&quot;heading-creating-and-updating-packages&quot;&gt;Creating and updating packages 📦&lt;/h1&gt;
&lt;p&gt;In this section, we will create new packages using &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/very_good_cli&quot;&gt;very_good_cli&lt;/a&gt; and update existing ones to efficiently manage the packages in our full-stack to-do application.&lt;/p&gt;
&lt;h2 id=&quot;heading-working-with-failure-classes&quot;&gt;Working with Failure classes&lt;/h2&gt;
&lt;blockquote&gt;
&lt;p&gt;It&#39;s time to shake things up in the failure department! 💥 Let&#39;s get to work on updating our failure classes.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;h2 id=&quot;heading-create-buildyaml&quot;&gt;Create &lt;code&gt;build.yaml&lt;/code&gt;&lt;/h2&gt;
&lt;p&gt;We will now create a new file called &lt;a target=&quot;_blank&quot; href=&quot;https://github.com/saileshbro/full_stack_todo_dart/blob/780b4662d4a03c17aaef281b100c8a686d8317bb/failures/build.yaml&quot;&gt;&lt;code&gt;build.yaml&lt;/code&gt;&lt;/a&gt; in the &lt;code&gt;failures&lt;/code&gt; directory and add the following code. This will change the behaviour of the &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/json_serializable&quot;&gt;&lt;code&gt;json_serializable&lt;/code&gt;&lt;/a&gt; so that it generates JSON keys in &lt;code&gt;snake_case&lt;/code&gt;.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-yaml&quot;&gt;&lt;span class=&quot;hljs-attr&quot;&gt;targets:&lt;/span&gt;
  &lt;span class=&quot;hljs-string&quot;&gt;$default:&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;builders:&lt;/span&gt;
      &lt;span class=&quot;hljs-attr&quot;&gt;json_serializable:&lt;/span&gt;
        &lt;span class=&quot;hljs-attr&quot;&gt;options:&lt;/span&gt;
          &lt;span class=&quot;hljs-attr&quot;&gt;any_map:&lt;/span&gt; &lt;span class=&quot;hljs-literal&quot;&gt;false&lt;/span&gt;
          &lt;span class=&quot;hljs-attr&quot;&gt;checked:&lt;/span&gt; &lt;span class=&quot;hljs-literal&quot;&gt;false&lt;/span&gt;
          &lt;span class=&quot;hljs-attr&quot;&gt;create_factory:&lt;/span&gt; &lt;span class=&quot;hljs-literal&quot;&gt;true&lt;/span&gt;
          &lt;span class=&quot;hljs-attr&quot;&gt;disallow_unrecognized_keys:&lt;/span&gt; &lt;span class=&quot;hljs-literal&quot;&gt;false&lt;/span&gt;
          &lt;span class=&quot;hljs-attr&quot;&gt;explicit_to_json:&lt;/span&gt; &lt;span class=&quot;hljs-literal&quot;&gt;true&lt;/span&gt;
          &lt;span class=&quot;hljs-attr&quot;&gt;field_rename:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;snake&lt;/span&gt;
          &lt;span class=&quot;hljs-attr&quot;&gt;generic_argument_factories:&lt;/span&gt; &lt;span class=&quot;hljs-literal&quot;&gt;false&lt;/span&gt;
          &lt;span class=&quot;hljs-attr&quot;&gt;ignore_unannotated:&lt;/span&gt; &lt;span class=&quot;hljs-literal&quot;&gt;false&lt;/span&gt;
          &lt;span class=&quot;hljs-attr&quot;&gt;include_if_null:&lt;/span&gt; &lt;span class=&quot;hljs-literal&quot;&gt;true&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;h3 id=&quot;heading-update-failure&quot;&gt;Update &lt;code&gt;Failure&lt;/code&gt;&lt;/h3&gt;
&lt;p&gt;Let&#39;s add a new getter to the &lt;code&gt;Failure&lt;/code&gt; abstract class to get the status code of the failure. This will allow us to map the failure to the appropriate &lt;a target=&quot;_blank&quot; href=&quot;https://developer.mozilla.org/en-US/docs/Web/HTTP/Status&quot;&gt;HTTP status code&lt;/a&gt; in the controller.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-diff&quot;&gt;abstract class Failure {
  String get message;
&lt;span class=&quot;hljs-addition&quot;&gt;+ int get statusCode;&lt;/span&gt;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;h3 id=&quot;heading-update-networkfailure&quot;&gt;Update &lt;code&gt;NetworkFailure&lt;/code&gt;&lt;/h3&gt;
&lt;p&gt;We will update our failure package and add more failures to it. To do this, we will begin by renaming the &lt;code&gt;code&lt;/code&gt; field in our &lt;code&gt;NetworkFailure&lt;/code&gt; class to &lt;code&gt;statusCode&lt;/code&gt;. This will make the field more meaningful and easier for our readers to understand.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-diff&quot;&gt;class NetworkFailure extends Failure with _$NetworkFailure {
  /// {@macro network_failure}
  const factory NetworkFailure&lpar;{
    required String message,
&lt;span class=&quot;hljs-deletion&quot;&gt;-   required int code,&lt;/span&gt;
&lt;span class=&quot;hljs-addition&quot;&gt;+   required int statusCode,&lt;/span&gt;
    @Default&lpar;[]&rpar; List&amp;lt;String&amp;gt; errors,
  }&rpar; = _NetworkFailure;
&lt;/code&gt;&lt;/pre&gt;
&lt;h2 id=&quot;heading-create-new-failures&quot;&gt;Create new failures&lt;/h2&gt;
&lt;blockquote&gt;
&lt;p&gt;Time to add some more failure friends to our app! 🙌&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;We&#39;ll be creating &lt;a target=&quot;_blank&quot; href=&quot;https://github.com/saileshbro/full_stack_todo_dart/blob/780b4662d4a03c17aaef281b100c8a686d8317bb/failures/lib/src/request_failure/request_failure.dart&quot;&gt;&lt;code&gt;RequestFailure&lt;/code&gt;&lt;/a&gt;, &lt;a target=&quot;_blank&quot; href=&quot;https://github.com/saileshbro/full_stack_todo_dart/blob/780b4662d4a03c17aaef281b100c8a686d8317bb/failures/lib/src/server_failure/server_failure.dart&quot;&gt;&lt;code&gt;ServerFailure&lt;/code&gt;&lt;/a&gt;, and &lt;a target=&quot;_blank&quot; href=&quot;https://github.com/saileshbro/full_stack_todo_dart/blob/780b4662d4a03c17aaef281b100c8a686d8317bb/failures/lib/src/validation_failure/validation_failure.dart&quot;&gt;&lt;code&gt;ValidationFailure&lt;/code&gt;&lt;/a&gt; to help us map out any potential errors that may occur.&lt;/p&gt;
&lt;h3 id=&quot;heading-requestfailure&quot;&gt;&lt;code&gt;RequestFailure&lt;/code&gt;&lt;/h3&gt;
&lt;p&gt;To create a &lt;code&gt;RequestFailure&lt;/code&gt; class, we will create a new file in the &lt;code&gt;src&lt;/code&gt; directory called &lt;code&gt;request_failure/request_failure.dart&lt;/code&gt;.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;dart:io&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:failures/failures.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:freezed_annotation/freezed_annotation.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;part&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;request_failure.freezed.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-meta&quot;&gt;@freezed&lt;/span&gt;
&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;RequestFailure&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;extends&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;Failure&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;with&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;_&lt;/span&gt;$descriptionlt;span class=&quot;hljs-title&quot;&gt;RequestFailure&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;factory&lt;/span&gt; RequestFailure&lpar;{
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; message,
    &lt;span class=&quot;hljs-meta&quot;&gt;@Default&lt;/span&gt;&lpar;HttpStatus.badRequest&rpar; &lt;span class=&quot;hljs-built_in&quot;&gt;int&lt;/span&gt; statusCode,
  }&rpar; = _RequestFailure;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;We will create two new classes in the &lt;code&gt;src&lt;/code&gt; directory, &lt;code&gt;ServerFailure&lt;/code&gt; and &lt;code&gt;ValidationFailure&lt;/code&gt;. The &lt;code&gt;ServerFailure&lt;/code&gt; class will be used to represent errors that occur on the server side of our application, and the &lt;code&gt;ValidationFailure&lt;/code&gt; class will be used to represent validation errors in our application.&lt;/p&gt;
&lt;h3 id=&quot;heading-serverfailure&quot;&gt;&lt;code&gt;ServerFailure&lt;/code&gt;&lt;/h3&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;dart:io&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:failures/failures.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:freezed_annotation/freezed_annotation.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;part&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;server_failure.freezed.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-meta&quot;&gt;@freezed&lt;/span&gt;
&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;ServerFailure&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;extends&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;Failure&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;with&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;_&lt;/span&gt;$descriptionlt;span class=&quot;hljs-title&quot;&gt;ServerFailure&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;factory&lt;/span&gt; ServerFailure&lpar;{
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; message,
    &lt;span class=&quot;hljs-meta&quot;&gt;@Default&lt;/span&gt;&lpar;HttpStatus.internalServerError&rpar; &lt;span class=&quot;hljs-built_in&quot;&gt;int&lt;/span&gt; statusCode,
  }&rpar; = _ServerFailure;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;h3 id=&quot;heading-validationfailure&quot;&gt;&lt;code&gt;ValidationFailure&lt;/code&gt;&lt;/h3&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;dart:io&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:failures/failures.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:freezed_annotation/freezed_annotation.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;part&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;validation_failure.freezed.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-meta&quot;&gt;@freezed&lt;/span&gt;
&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;ValidationFailure&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;extends&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;Failure&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;with&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;_&lt;/span&gt;$descriptionlt;span class=&quot;hljs-title&quot;&gt;ValidationFailure&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;factory&lt;/span&gt; ValidationFailure&lpar;{
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; message,
    &lt;span class=&quot;hljs-meta&quot;&gt;@Default&lt;/span&gt;&lpar;HttpStatus.badRequest&rpar; &lt;span class=&quot;hljs-built_in&quot;&gt;int&lt;/span&gt; statusCode,
    &lt;span class=&quot;hljs-meta&quot;&gt;@Default&lt;/span&gt;&lpar;{}&rpar; &lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;&amp;gt;&amp;gt; errors,
  }&rpar; = _ValidationFailure;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;blockquote&gt;
&lt;p&gt;Don&#39;t forget to export and run &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/build_runner&quot;&gt;&lt;code&gt;build_runner&lt;/code&gt;&lt;/a&gt; 😎&lt;/p&gt;
&lt;/blockquote&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;library&lt;/span&gt; failures;

&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;src/failure.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;src/network_failure/network_failure.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;src/request_failure/request_failure.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;src/server_failure/server_failure.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;src/validation_failure/validation_failure.dart&#39;&lt;/span&gt;;
&lt;/code&gt;&lt;/pre&gt;
&lt;blockquote&gt;
&lt;p&gt;💡 Note: You can run the &lt;code&gt;build_runner&lt;/code&gt; command by running &lt;code&gt;flutter pub run build_runner build&lt;/code&gt; in the terminal.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;h2 id=&quot;heading-working-with-packages&quot;&gt;Working with packages&lt;/h2&gt;
&lt;blockquote&gt;
&lt;p&gt;Get ready for some package updating fun! 📦&lt;/p&gt;
&lt;/blockquote&gt;
&lt;h3 id=&quot;heading-update-typedefs-package&quot;&gt;Update &lt;code&gt;typedefs&lt;/code&gt; package&lt;/h3&gt;
&lt;p&gt;We will be creating a function called &lt;code&gt;mapTodoId&lt;/code&gt; in the &lt;code&gt;typedefs&lt;/code&gt; package. This function will be responsible for converting a string id to a &lt;code&gt;TodoId&lt;/code&gt; object. This is necessary because we need a way to convert user input into a format our application can understand and use. If the id is not valid, the &lt;code&gt;mapTodoId&lt;/code&gt; function will return a &lt;code&gt;RequestFailure&lt;/code&gt; object. This will allow us to handle any errors or invalid input gracefully, ensuring that our application is robust and can handle any potential issues&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;Either&amp;lt;Failure, TodoId&amp;gt; mapTodoId&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; id&rpar; {
  &lt;span class=&quot;hljs-keyword&quot;&gt;try&lt;/span&gt; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; todoId = &lt;span class=&quot;hljs-built_in&quot;&gt;int&lt;/span&gt;.tryParse&lpar;id&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;todoId == &lt;span class=&quot;hljs-keyword&quot;&gt;null&lt;/span&gt;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; BadRequestException&lpar;message: &lt;span class=&quot;hljs-string&quot;&gt;&#39;Invalid id&#39;&lt;/span&gt;&rpar;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Right&lpar;todoId&rpar;;
  } &lt;span class=&quot;hljs-keyword&quot;&gt;on&lt;/span&gt; BadRequestException &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Left&lpar;
      RequestFailure&lpar;
        message: e.message,
        statusCode: e.statusCode,
      &rpar;,
    &rpar;;
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;The &lt;code&gt;mapTodoId&lt;/code&gt; method will return either a &lt;code&gt;TodoId&lt;/code&gt; object or a &lt;code&gt;RequestFailure&lt;/code&gt; object. Make sure to add the dependencies &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/either_dart&quot;&gt;&lt;code&gt;either_dart&lt;/code&gt;&lt;/a&gt; and &lt;code&gt;failures&lt;/code&gt; to the &lt;code&gt;pubspec.yaml&lt;/code&gt; file of the &lt;code&gt;typedefs&lt;/code&gt; package.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-yaml&quot;&gt;&lt;span class=&quot;hljs-attr&quot;&gt;dependencies:&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;either_dart:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^0.3.0&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;exceptions:&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;path:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;../exceptions&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;failures:&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;path:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;../failures&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;h3 id=&quot;heading-create-a-new-exceptions-package&quot;&gt;Create a new &lt;code&gt;exceptions&lt;/code&gt; package&lt;/h3&gt;
&lt;p&gt;To handle internal exceptions and map them to the appropriate failures, we will create a new package called &lt;code&gt;exceptions&lt;/code&gt; and throw our custom exceptions. For example, if we encounter a &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/documentation/postgres/latest/postgres/PostgreSQLException-class.html&quot;&gt;&lt;code&gt;PostgreSQLException&lt;/code&gt;&lt;/a&gt; while inserting a new to-do, we will throw a &lt;code&gt;ServerException&lt;/code&gt; and map it to the &lt;code&gt;ServerFailure&lt;/code&gt; class. To create the &lt;code&gt;exceptions&lt;/code&gt; package, run the following command in the terminal:&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;very_good create -t dart_pkg exceptions
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;This package will include different types of exceptions such as &lt;code&gt;ServerException&lt;/code&gt;, &lt;code&gt;HttpException&lt;/code&gt;, and &lt;code&gt;NotFoundException&lt;/code&gt;. The &lt;code&gt;ServerException&lt;/code&gt; will be thrown in the case of an internal server error, while the &lt;code&gt;HttpException&lt;/code&gt; is an abstract class that will be extended by other exceptions like &lt;code&gt;NotFoundException&lt;/code&gt; and &lt;code&gt;BadRequestException&lt;/code&gt;. We can use these custom exceptions to handle internal errors and map them to the appropriate failure classes, such as &lt;code&gt;ServerFailure&lt;/code&gt; or &lt;code&gt;RequestFailure&lt;/code&gt;. We will start by creating a new file inside &lt;code&gt;src/server_exception/server_exception.dart&lt;/code&gt; and add the following code:&lt;/p&gt;
&lt;h4 id=&quot;heading-serverexception&quot;&gt;&lt;code&gt;ServerException&lt;/code&gt;&lt;/h4&gt;
&lt;p&gt;To create &lt;code&gt;ServerException&lt;/code&gt; we will create a new file &lt;code&gt;src/server_exception/server_exception.dart&lt;/code&gt; and add the following code:&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;ServerException&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;implements&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;Exception&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; ServerException&lpar;&lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;.message&rpar;;

  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; message;
  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; toString&lpar;&rpar; =&amp;gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;ServerException: &lt;span class=&quot;hljs-subst&quot;&gt;$message&lt;/span&gt;&#39;&lt;/span&gt;;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;h4 id=&quot;heading-httpexpection&quot;&gt;&lt;code&gt;HttpExpection&lt;/code&gt;&lt;/h4&gt;
&lt;p&gt;To create &lt;code&gt;HttpException&lt;/code&gt; we will create a new file &lt;code&gt;src/http_exception/http_exception.dart&lt;/code&gt; and add the following code:&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;abstract&lt;/span&gt; &lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;HttpException&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;implements&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;Exception&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; HttpException&lpar;&lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;.message, &lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;.statusCode&rpar;;
  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; message;
  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;int&lt;/span&gt; statusCode;

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; toString&lpar;&rpar; =&amp;gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;&lt;span class=&quot;hljs-subst&quot;&gt;$runtimeType&lt;/span&gt;: &lt;span class=&quot;hljs-subst&quot;&gt;$message&lt;/span&gt;&#39;&lt;/span&gt;;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;h4 id=&quot;heading-notfoundexception&quot;&gt;&lt;code&gt;NotFoundException&lt;/code&gt;&lt;/h4&gt;
&lt;p&gt;Next, we will create &lt;code&gt;NotFoundException&lt;/code&gt;, which will be thrown when a resource is not found. To do this, create a new file called &lt;code&gt;src/http_exception/not_found_exception.dart&lt;/code&gt; and add the following code:&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;NotFoundException&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;extends&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;HttpException&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; NotFoundException&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; message&rpar; : &lt;span class=&quot;hljs-keyword&quot;&gt;super&lt;/span&gt;&lpar;message, HttpStatus.notFound&rpar;;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;h4 id=&quot;heading-badrequestexception&quot;&gt;&lt;code&gt;BadRequestException&lt;/code&gt;&lt;/h4&gt;
&lt;p&gt;Similarly, we will create a new file inside &lt;code&gt;src/http_exception/bad_request_exception.dart&lt;/code&gt; and add the following code:&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;BadRequestException&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;extends&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;HttpException&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; BadRequestException&lpar;{
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; message,
    &lt;span class=&quot;hljs-keyword&quot;&gt;this&lt;/span&gt;.errors = &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; {},
  }&rpar; : &lt;span class=&quot;hljs-keyword&quot;&gt;super&lt;/span&gt;&lpar;message, HttpStatus.badRequest&rpar;;

  &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;&amp;gt;&amp;gt; errors;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Make sure to import the &lt;code&gt;HttpException&lt;/code&gt;. Once you are done with &lt;code&gt;HttpException&lt;/code&gt;, add an export statement in &lt;code&gt;http_exception.dart&lt;/code&gt; file.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;./bad_request_exception.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;./not_found_exception.dart&#39;&lt;/span&gt;;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;And finally, export the &lt;code&gt;HttpException&lt;/code&gt; from &lt;code&gt;exceptions/lib/exceptions.dart&lt;/code&gt; file.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;library&lt;/span&gt; exceptions;

&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;src/http_exception/http_exception.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;src/server_exception/server_exception.dart&#39;&lt;/span&gt;;
&lt;/code&gt;&lt;/pre&gt;
&lt;h3 id=&quot;heading-update-models-package&quot;&gt;Update &lt;code&gt;models&lt;/code&gt; package&lt;/h3&gt;
&lt;h4 id=&quot;heading-lets-handle-the-validation&quot;&gt;Let&#39;s handle the validation&lt;/h4&gt;
&lt;blockquote&gt;
&lt;p&gt;Ready to add some sass to your data validation? Let&#39;s get those DTOs in shape! 💪&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;To add validation to our &lt;code&gt;CreateTodoDto&lt;/code&gt; class, we will create a new static method called validated in &lt;code&gt;models/lib/src/create_todo_dto/create_todo_dto.dart&lt;/code&gt;. This method will return either a &lt;code&gt;ValidationFailure&lt;/code&gt; object or a &lt;code&gt;CreateTodoDto&lt;/code&gt; object. We will use this method to ensure that our to-do creation requests contain all necessary information before they are processed. The validation rules are:&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;&lt;p&gt;the &lt;code&gt;title&lt;/code&gt; should not be empty&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;the &lt;code&gt;description&lt;/code&gt; should not be empty&lt;/p&gt;
&lt;/li&gt;
&lt;/ul&gt;
&lt;p&gt;Before we can add the validated method to the &lt;code&gt;CreateTodoDto&lt;/code&gt; class, we need to make sure that the necessary packages are added to the &lt;code&gt;pubspec.yaml&lt;/code&gt; file.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-yaml&quot;&gt;&lt;span class=&quot;hljs-attr&quot;&gt;dependencies:&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;either_dart:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^0.3.0&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;exceptions:&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;path:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;../exceptions&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;failures:&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;path:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;../failures&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;freezed_annotation:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^2.2.0&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;json_annotation:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^4.7.0&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;typedefs:&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;path:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;../typedefs&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Now we will create a &lt;code&gt;validated&lt;/code&gt; method inside &lt;code&gt;CreateTodoDto&lt;/code&gt;&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  &lt;span class=&quot;hljs-keyword&quot;&gt;static&lt;/span&gt; Either&amp;lt;ValidationFailure, CreateTodoDto&amp;gt; validated&lpar;
    &lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;dynamic&lt;/span&gt;&amp;gt; json,
  &rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;try&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; errors = &amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;&amp;gt;&amp;gt;{};
      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;json[&lt;span class=&quot;hljs-string&quot;&gt;&#39;title&#39;&lt;/span&gt;] == &lt;span class=&quot;hljs-keyword&quot;&gt;null&lt;/span&gt;&rpar; {
        errors[&lt;span class=&quot;hljs-string&quot;&gt;&#39;title&#39;&lt;/span&gt;] = [&lt;span class=&quot;hljs-string&quot;&gt;&#39;Title is required&#39;&lt;/span&gt;];
      }
      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;json[&lt;span class=&quot;hljs-string&quot;&gt;&#39;description&#39;&lt;/span&gt;] == &lt;span class=&quot;hljs-keyword&quot;&gt;null&lt;/span&gt;&rpar; {
        errors[&lt;span class=&quot;hljs-string&quot;&gt;&#39;description&#39;&lt;/span&gt;] = [&lt;span class=&quot;hljs-string&quot;&gt;&#39;Description is required&#39;&lt;/span&gt;];
      }
      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;errors.isEmpty&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Right&lpar;CreateTodoDto.fromJson&lpar;json&rpar;&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; BadRequestException&lpar;
        message: &lt;span class=&quot;hljs-string&quot;&gt;&#39;Validation failed&#39;&lt;/span&gt;,
        errors: errors,
      &rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;on&lt;/span&gt; BadRequestException &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Left&lpar;
        ValidationFailure&lpar;
          message: e.message,
          errors: e.errors,
          statusCode: e.statusCode,
        &rpar;,
      &rpar;;
    }
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Similarly, we will create a new static method called &lt;code&gt;validated&lt;/code&gt; to validate the &lt;code&gt;UpdateTodoDto&lt;/code&gt;. We will ensure that at least one field is present.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;  &lt;span class=&quot;hljs-keyword&quot;&gt;static&lt;/span&gt; Either&amp;lt;ValidationFailure, UpdateTodoDto&amp;gt; validated&lpar;
    &lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;dynamic&lt;/span&gt;&amp;gt; json,
  &rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;try&lt;/span&gt; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;final&lt;/span&gt; errors = &amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;&amp;gt;&amp;gt;{};
      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;json[&lt;span class=&quot;hljs-string&quot;&gt;&#39;title&#39;&lt;/span&gt;] == &lt;span class=&quot;hljs-keyword&quot;&gt;null&lt;/span&gt; || json[&lt;span class=&quot;hljs-string&quot;&gt;&#39;title&#39;&lt;/span&gt;] == &lt;span class=&quot;hljs-string&quot;&gt;&#39;&#39;&lt;/span&gt;&rpar; {
        errors[&lt;span class=&quot;hljs-string&quot;&gt;&#39;title&#39;&lt;/span&gt;] = [&lt;span class=&quot;hljs-string&quot;&gt;&#39;At least one field must be provided&#39;&lt;/span&gt;];
      }
      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;json[&lt;span class=&quot;hljs-string&quot;&gt;&#39;description&#39;&lt;/span&gt;] == &lt;span class=&quot;hljs-keyword&quot;&gt;null&lt;/span&gt; || json[&lt;span class=&quot;hljs-string&quot;&gt;&#39;description&#39;&lt;/span&gt;] == &lt;span class=&quot;hljs-string&quot;&gt;&#39;&#39;&lt;/span&gt;&rpar; {
        errors[&lt;span class=&quot;hljs-string&quot;&gt;&#39;description&#39;&lt;/span&gt;] = [&lt;span class=&quot;hljs-string&quot;&gt;&#39;At least one field must be provided&#39;&lt;/span&gt;];
      }
      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;json[&lt;span class=&quot;hljs-string&quot;&gt;&#39;completed&#39;&lt;/span&gt;] == &lt;span class=&quot;hljs-keyword&quot;&gt;null&lt;/span&gt;&rpar; {
        errors[&lt;span class=&quot;hljs-string&quot;&gt;&#39;completed&#39;&lt;/span&gt;] = [&lt;span class=&quot;hljs-string&quot;&gt;&#39;At least one field must be provided&#39;&lt;/span&gt;];
      }
      &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;errors.length &amp;lt; &lt;span class=&quot;hljs-number&quot;&gt;3&lt;/span&gt;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Right&lpar;UpdateTodoDto.fromJson&lpar;json&rpar;&rpar;;
      &lt;span class=&quot;hljs-keyword&quot;&gt;throw&lt;/span&gt; BadRequestException&lpar;
        message: &lt;span class=&quot;hljs-string&quot;&gt;&#39;Validation failed&#39;&lt;/span&gt;,
        errors: errors,
      &rpar;;
    } &lt;span class=&quot;hljs-keyword&quot;&gt;on&lt;/span&gt; BadRequestException &lt;span class=&quot;hljs-keyword&quot;&gt;catch&lt;/span&gt; &lpar;e&rpar; {
      &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; Left&lpar;
        ValidationFailure&lpar;
          message: e.message,
          statusCode: e.statusCode,
          errors: e.errors,
        &rpar;,
      &rpar;;
    }
  }
&lt;/code&gt;&lt;/pre&gt;
&lt;h4 id=&quot;heading-custom-json-converters&quot;&gt;Custom JSON converters&lt;/h4&gt;
&lt;p&gt;To serialize and deserialize our &lt;code&gt;DateTime&lt;/code&gt; objects, we will create a new file called &lt;code&gt;models/lib/src/serializers/date_time_serializer.dart&lt;/code&gt;. In this file, we will add the necessary code to handle the serialization and deserialization of &lt;code&gt;DateTime&lt;/code&gt; objects.&lt;/p&gt;
&lt;p&gt;These classes will implement the &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/documentation/json_annotation/latest/json_annotation/JsonConverter-class.html&quot;&gt;&lt;code&gt;JsonConverter&lt;/code&gt;&lt;/a&gt; interface and provide the necessary logic to convert &lt;code&gt;DateTime&lt;/code&gt; objects to and from JSON. The &lt;code&gt;DateTimeConverterNullable&lt;/code&gt; class will handle cases where the &lt;code&gt;DateTime&lt;/code&gt; object may be &lt;code&gt;null&lt;/code&gt;, while the &lt;code&gt;DateTimeConverter&lt;/code&gt; class will handle non-null &lt;code&gt;DateTime&lt;/code&gt; objects. With these classes in place, we will be able to correctly handle the formatting of &lt;code&gt;DateTime&lt;/code&gt; objects when retrieving data from the database.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;DateTimeConverterNullable&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;extends&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;JsonConverter&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-title&quot;&gt;DateTime&lt;/span&gt;?, &lt;span class=&quot;hljs-title&quot;&gt;dynamic&lt;/span&gt;&amp;gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; DateTimeConverterNullable&lpar;&rpar;;

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  &lt;span class=&quot;hljs-built_in&quot;&gt;DateTime?&lt;/span&gt; fromJson&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;dynamic&lt;/span&gt; json&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;json == &lt;span class=&quot;hljs-keyword&quot;&gt;null&lt;/span&gt;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;null&lt;/span&gt;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; DateTimeConverter&lpar;&rpar;.fromJson&lpar;json&rpar;;
  }

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  &lt;span class=&quot;hljs-built_in&quot;&gt;String?&lt;/span&gt; toJson&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;DateTime?&lt;/span&gt; object&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;object == &lt;span class=&quot;hljs-keyword&quot;&gt;null&lt;/span&gt;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;null&lt;/span&gt;;
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; DateTimeConverter&lpar;&rpar;.toJson&lpar;object&rpar;;
  }
}
&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;DateTimeConverter&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;extends&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;JsonConverter&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-title&quot;&gt;DateTime&lt;/span&gt;, &lt;span class=&quot;hljs-title&quot;&gt;dynamic&lt;/span&gt;&amp;gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; DateTimeConverter&lpar;&rpar;;

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  &lt;span class=&quot;hljs-built_in&quot;&gt;DateTime&lt;/span&gt; fromJson&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;dynamic&lt;/span&gt; json&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;if&lt;/span&gt; &lpar;json &lt;span class=&quot;hljs-keyword&quot;&gt;is&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;DateTime&lt;/span&gt;&rpar; &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; json;
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;DateTime&lt;/span&gt;.parse&lpar;json &lt;span class=&quot;hljs-keyword&quot;&gt;as&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;&rpar;;
  }

  &lt;span class=&quot;hljs-meta&quot;&gt;@override&lt;/span&gt;
  &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; toJson&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;DateTime&lt;/span&gt; object&rpar; {
    &lt;span class=&quot;hljs-keyword&quot;&gt;return&lt;/span&gt; object.toIso8601String&lpar;&rpar;;
  }
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Now we can use this converter in our &lt;code&gt;Todo&lt;/code&gt; model.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-diff&quot;&gt;  factory Todo&lpar;{
    required TodoId id,
    required String title,
    @Default&lpar;&#39;&#39;&rpar; String description,
    @Default&lpar;false&rpar; bool? completed,
&lt;span class=&quot;hljs-deletion&quot;&gt;-   required DateTime createdAt,&lt;/span&gt;
&lt;span class=&quot;hljs-addition&quot;&gt;+   @DateTimeConverter&lpar;&rpar; required DateTime createdAt,&lt;/span&gt;
&lt;span class=&quot;hljs-deletion&quot;&gt;-   DateTime? updatedAt,&lt;/span&gt;
&lt;span class=&quot;hljs-addition&quot;&gt;+   @DateTimeConverterNullable&lpar;&rpar; DateTime? updatedAt,&lt;/span&gt;
  }&rpar; = _Todo;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Once you have finished updating the &lt;code&gt;Todo&lt;/code&gt; model to use the converters.&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;Don&#39;t forget to run &lt;code&gt;build_runner&lt;/code&gt; 😎&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;Woo hoo! We made it to the end of part 3 🎉&lt;/p&gt;
&lt;p&gt;In this part, we gave our failure classes a little update and created some new ones. We also added some shiny new exceptions and made sure our DTOs were properly validated. We&#39;re almost there, friends! Just a few more steps until we can fully implement the CRUD operations for our awesome to-do app.&lt;/p&gt;
&lt;p&gt;In the final part, we&#39;ll finally be able to connect to a Postgres database and complete all our backend routes. It&#39;s going to be a coding party 🎉 Are you ready to join the fun? I know I am! 🤩&lt;/p&gt;
&lt;p&gt;And if you ever need a reference, just head on over to the GitHub repo for this tutorial at &lt;a target=&quot;_blank&quot; href=&quot;https://github.com/saileshbro/full_stack_todo_dart&quot;&gt;https://github.com/saileshbro/full_stack_todo_dart&lt;/a&gt;.&lt;/p&gt;
&lt;p&gt;Let&#39;s get ready to code some magic in part 4! 😄&lt;/p&gt;
 

 - 🚀[🚀 Building a Fullstack App with dart_frog and Flutter in a Monorepo - Part 2](https://saileshdahal.com.np/building-a-fullstack-app-with-dartfrog-and-flutter-in-a-monorepo-part-2) 
 - &lt;p&gt;In the first part of this article, we set up &lt;a target=&quot;_blank&quot; href=&quot;https://docs.page/invertase/melos&quot;&gt;melos&lt;/a&gt; as a tool for managing monorepo projects and installed &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/dart_frog&quot;&gt;dart_frog&lt;/a&gt; as a web framework for building server-side apps with Dart. We also created a new Dart Frog project, which included adding the &lt;code&gt;dart_frog&lt;/code&gt; dependency on the project&#39;s &lt;code&gt;pubspec.yaml&lt;/code&gt; file and creating the necessary files and directories.&lt;/p&gt;
&lt;p&gt;We will create models, data sources, repositories, and failure classes as a separate Dart package in part 2.&lt;/p&gt;
&lt;p&gt;To do this, we will be using &lt;a target=&quot;_blank&quot; href=&quot;https://cli.vgv.dev/&quot;&gt;very_good_cli&lt;/a&gt;.&lt;/p&gt;
&lt;h1 id=&quot;heading-setting-up-models-repositories-and-data-services&quot;&gt;Setting up Models, Repositories, and Data Services 💻&lt;/h1&gt;
&lt;h2 id=&quot;heading-installing-verygoodclihttpsclivgvdev&quot;&gt;Installing &lt;a target=&quot;_blank&quot; href=&quot;https://cli.vgv.dev/&quot;&gt;very_good_cli&lt;/a&gt;&lt;/h2&gt;
&lt;blockquote&gt;
&lt;p&gt;&lt;strong&gt;very_good_cli&lt;/strong&gt;, a Command-Line Interface that provides helpful commands and templates for generating various types of projects, including Flutter apps, Flame games, Flutter packages, Dart packages, federated plugins, and Dart CLI projects.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;&lt;strong&gt;Very Good CLI&lt;/strong&gt; makes it easy to create and set up these types of projects with a single command, so let&#39;s get started!&lt;/p&gt;
&lt;p&gt;To install &lt;strong&gt;Very Good CLI&lt;/strong&gt;, open a terminal and enter the following command:&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;dart pub global activate very_good_cli
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;To confirm that Very Good CLI has been installed correctly, you can enter the following command in a terminal &lt;code&gt;very_good --version&lt;/code&gt; 🚀&lt;/p&gt;
&lt;h2 id=&quot;heading-creating-typedefs&quot;&gt;Creating &lt;code&gt;typedefs&lt;/code&gt;&lt;/h2&gt;
&lt;p&gt;We will have our &lt;strong&gt;typedefs&lt;/strong&gt;, which will be shared between the backend and frontend of our project. To create a new Dart package for these typedefs, we can use the following command:&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;very_good create -t dart_pkg typedefs
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;This will generate a new dart package &lt;code&gt;typedefs&lt;/code&gt;. Here &lt;code&gt;-t dart_pkg&lt;/code&gt; means we are creating a new dart package.&lt;/p&gt;
&lt;p&gt;Once the &lt;code&gt;typedefs&lt;/code&gt; package has been created and the necessary files and directories have been generated, you can navigate to &lt;code&gt;typedefs/lib/src/typedefs.dart&lt;/code&gt; to create a new typedef.&lt;/p&gt;
&lt;p&gt;In this file, you can create a new &lt;strong&gt;typedef&lt;/strong&gt; by adding the following code:&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-comment&quot;&gt;/// &lt;span class=&quot;markdown&quot;&gt;Primary key type for a Todo.&lt;/span&gt;&lt;/span&gt;
&lt;span class=&quot;hljs-keyword&quot;&gt;typedef&lt;/span&gt; TodoId = &lt;span class=&quot;hljs-built_in&quot;&gt;int&lt;/span&gt;;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;This will create a new typedef called &lt;code&gt;TodoId&lt;/code&gt;, an alias for the type &lt;code&gt;int&lt;/code&gt;. This typedef can then be used throughout the backend and frontend of your project to represent an identifier for a to-do item. Once you are done, make sure to export the file from &lt;code&gt;lib/typedefs.dart&lt;/code&gt;&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;library&lt;/span&gt; typedefs;
&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;src/typedefs.dart&#39;&lt;/span&gt;;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;We will add additional shared &lt;strong&gt;typedefs&lt;/strong&gt; to this file as needed. &lt;a target=&quot;_blank&quot; href=&quot;https://github.com/saileshbro/full_stack_todo_dart/tree/main/typedefs&quot;&gt;&lt;strong&gt;GitHub Link&lt;/strong&gt;&lt;/a&gt;&lt;/p&gt;
&lt;h2 id=&quot;heading-creating-models&quot;&gt;Creating &lt;code&gt;models&lt;/code&gt;&lt;/h2&gt;
&lt;p&gt;Similarly, we will have a separate package to house shared data models.&lt;/p&gt;
&lt;ol&gt;
&lt;li&gt;&lt;p&gt;&lt;code&gt;CreateTodoDto&lt;/code&gt; This will be used to send and receive payload for creating a new todo.&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;code&gt;UpdateTodoDto&lt;/code&gt; This will be used to send and receive payload for updating an existing todo.&lt;/p&gt;
&lt;/li&gt;
&lt;li&gt;&lt;p&gt;&lt;code&gt;Todo&lt;/code&gt; This is the representation of the &lt;code&gt;Todo&lt;/code&gt; entity.&lt;/p&gt;
&lt;/li&gt;
&lt;/ol&gt;
&lt;p&gt;To create a separate package for models you can use the &lt;code&gt;very_good&lt;/code&gt; CLI:&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;very_good create -t dart_pkg models
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Once the package has been created, we will install &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/freezed&quot;&gt;freezed&lt;/a&gt; for &lt;strong&gt;JSON serialization&lt;/strong&gt; and &lt;strong&gt;value equality&lt;/strong&gt;, as this library provides helpful tools for these tasks. We will use &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/json_serializable&quot;&gt;json_serializable&lt;/a&gt; for JSON serialization. To install &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/freezed&quot;&gt;freezed&lt;/a&gt; and &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/freezed_annotation&quot;&gt;freezed_annotation&lt;/a&gt;, open your terminal inside the &lt;code&gt;models&lt;/code&gt; package and use the command:&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;dart pub add freezed json_serializable build_runner -d
dart pub add freezed_annotation json_annotation
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Inside &lt;code&gt;models/lib&lt;/code&gt; we will create files in the given order. We have created a parent folder for each model to house the generated codes so that it will look cleaner.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;.
 models.dart
 src
     create_todo_dto
        create_todo_dto.dart
     todo
        todo.dart
     update_todo_dto
         update_todo_dto.dart
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Now, in &lt;code&gt;todo.dart&lt;/code&gt; we will use &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/freezed&quot;&gt;freezed&lt;/a&gt; package to create a data class.&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;&lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/freezed&quot;&gt;freezed&lt;/a&gt; package is a code generation tool that allows you to create immutable classes with concise, boilerplate-free syntax. It uses the &lt;code&gt;@freezed&lt;/code&gt; annotation to generate a number of useful methods and operators for your class, such as &lt;code&gt;==&lt;/code&gt;, &lt;code&gt;hashCode&lt;/code&gt;, and &lt;code&gt;copyWith&lt;/code&gt;.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:freezed_annotation/freezed_annotation.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:typedefs/typedefs.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;part&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;todo.freezed.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;part&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;todo.g.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-meta&quot;&gt;@freezed&lt;/span&gt;
&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;Todo&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;with&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;_&lt;/span&gt;$descriptionlt;span class=&quot;hljs-title&quot;&gt;Todo&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;factory&lt;/span&gt; Todo&lpar;{
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; TodoId id,
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; title,
    &lt;span class=&quot;hljs-meta&quot;&gt;@Default&lt;/span&gt;&lpar;&lt;span class=&quot;hljs-string&quot;&gt;&#39;&#39;&lt;/span&gt;&rpar; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; description,
    &lt;span class=&quot;hljs-meta&quot;&gt;@Default&lt;/span&gt;&lpar;&lt;span class=&quot;hljs-keyword&quot;&gt;false&lt;/span&gt;&rpar; &lt;span class=&quot;hljs-built_in&quot;&gt;bool?&lt;/span&gt; completed,
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;DateTime&lt;/span&gt; createdAt,
    &lt;span class=&quot;hljs-built_in&quot;&gt;DateTime?&lt;/span&gt; updatedAt,
  }&rpar; = _Todo;

  &lt;span class=&quot;hljs-keyword&quot;&gt;factory&lt;/span&gt; Todo.fromJson&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;dynamic&lt;/span&gt;&amp;gt; json&rpar; =&amp;gt; _$TodoFromJson&lpar;json&rpar;;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Since &lt;code&gt;TodoId&lt;/code&gt; is in a separate package, we will have to add it in the &lt;code&gt;models/pubspec.yaml&lt;/code&gt; file as a dependency. After adding the &lt;code&gt;pubspec.yaml&lt;/code&gt; should look like this.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-yaml&quot;&gt;&lt;span class=&quot;hljs-attr&quot;&gt;name:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;models&lt;/span&gt;
&lt;span class=&quot;hljs-attr&quot;&gt;description:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;A&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;Very&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;Good&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;Project&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;created&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;by&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;Very&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;Good&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;CLI.&lt;/span&gt;
&lt;span class=&quot;hljs-attr&quot;&gt;version:&lt;/span&gt; &lt;span class=&quot;hljs-number&quot;&gt;0.1&lt;/span&gt;&lt;span class=&quot;hljs-number&quot;&gt;.0&lt;/span&gt;&lt;span class=&quot;hljs-string&quot;&gt;+1&lt;/span&gt;
&lt;span class=&quot;hljs-attr&quot;&gt;publish_to:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;none&lt;/span&gt;

&lt;span class=&quot;hljs-attr&quot;&gt;environment:&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;sdk:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&quot;&amp;gt;=2.18.0 &amp;lt;3.0.0&quot;&lt;/span&gt;

&lt;span class=&quot;hljs-attr&quot;&gt;dependencies:&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;freezed_annotation:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^2.2.0&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;json_annotation:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^4.7.0&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;typedefs:&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;path:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;../typedefs&lt;/span&gt;

&lt;span class=&quot;hljs-attr&quot;&gt;dev_dependencies:&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;build_runner:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^2.3.3&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;freezed:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^2.3.2&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;json_serializable:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^6.5.4&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;lints:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^2.0.0&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;mocktail:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^0.3.0&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;test:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^1.19.2&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;very_good_analysis:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^3.1.0&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Similarly, we will create &lt;code&gt;create_todo_dto.dart&lt;/code&gt; for &lt;code&gt;CreateDotoDto&lt;/code&gt; class.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:freezed_annotation/freezed_annotation.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;part&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;create_todo_dto.freezed.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;part&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;create_todo_dto.g.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-meta&quot;&gt;@freezed&lt;/span&gt;
&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;CreateTodoDto&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;with&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;_&lt;/span&gt;$descriptionlt;span class=&quot;hljs-title&quot;&gt;CreateTodoDto&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;factory&lt;/span&gt; CreateTodoDto&lpar;{
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; title,
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; description,
  }&rpar; = _CreateTodoDto;

  &lt;span class=&quot;hljs-keyword&quot;&gt;factory&lt;/span&gt; CreateTodoDto.fromJson&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;dynamic&lt;/span&gt;&amp;gt; json&rpar; =&amp;gt;
      _$CreateTodoDtoFromJson&lpar;json&rpar;;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Similarly, we will create &lt;code&gt;update_todo_dto.dart&lt;/code&gt; for &lt;code&gt;UpdateTodoDto&lt;/code&gt; class.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:freezed_annotation/freezed_annotation.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;part&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;update_todo_dto.freezed.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;part&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;update_todo_dto.g.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-meta&quot;&gt;@freezed&lt;/span&gt;
&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;UpdateTodoDto&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;with&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;_&lt;/span&gt;$descriptionlt;span class=&quot;hljs-title&quot;&gt;UpdateTodoDto&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;factory&lt;/span&gt; UpdateTodoDto&lpar;{
    &lt;span class=&quot;hljs-built_in&quot;&gt;String?&lt;/span&gt; title,
    &lt;span class=&quot;hljs-built_in&quot;&gt;String?&lt;/span&gt; description,
    &lt;span class=&quot;hljs-built_in&quot;&gt;bool?&lt;/span&gt; completed,
  }&rpar; = _UpdateTodoDto;

  &lt;span class=&quot;hljs-keyword&quot;&gt;factory&lt;/span&gt; UpdateTodoDto.fromJson&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;dynamic&lt;/span&gt;&amp;gt; json&rpar; =&amp;gt;
      _$UpdateTodoDtoFromJson&lpar;json&rpar;;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Once this is done, we run &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/build_runner&quot;&gt;build_runner&lt;/a&gt; and generate the necessary code. To generate the missing code, you can run the following command:&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;dart pub run build_runner build --delete-conflicting-outputs
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;This will generate &lt;code&gt;*.g.dart&lt;/code&gt; and &lt;code&gt;*.freezed.dart&lt;/code&gt; files. Once this is done, you will have files inside &lt;code&gt;models/lib&lt;/code&gt; in the given order.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-plaintext&quot;&gt;.
 models.dart
 src
     create_todo_dto
        create_todo_dto.dart
        create_todo_dto.freezed.dart
        create_todo_dto.g.dart
     todo
        todo.dart
        todo.freezed.dart
        todo.g.dart
     update_todo_dto
         update_todo_dto.dart
         update_todo_dto.freezed.dart
         update_todo_dto.g.dart
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Once you are done creating the models, be sure to export them from &lt;code&gt;lib/models.dart&lt;/code&gt;&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;library&lt;/span&gt; models;

&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;src/create_todo_dto/create_todo_dto.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;src/todo/todo.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;src/update_todo_dto/update_todo_dto.dart&#39;&lt;/span&gt;;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;You can find the &lt;a target=&quot;_blank&quot; href=&quot;https://github.com/saileshbro/full_stack_todo_dart/tree/main/models&quot;&gt;GitHub link for models here&lt;/a&gt;.&lt;/p&gt;
&lt;h2 id=&quot;heading-creating-failures&quot;&gt;Creating &lt;code&gt;failures&lt;/code&gt;&lt;/h2&gt;
&lt;p&gt;In the next step, we will create a separate package to handle failures in our application. This package will contain all the failures that may occur, such as &lt;code&gt;NetworkFailure&lt;/code&gt; or &lt;code&gt;ServerFailure&lt;/code&gt;. Whenever we need to handle an error, we will encapsulate the value or error in a union type and return it from a repository. For example, when we make an API call to retrieve data, we may receive either the requested data or an error. By encapsulating this in an &lt;code&gt;Either&lt;/code&gt; type, we can effectively handle and manage failures in our app.&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;This is inspired by &lt;a target=&quot;_blank&quot; href=&quot;https://resocoder.com/flutter-clean-architecture-tdd/&quot;&gt;ReSo Coder&#39;s Clean Architecture&lt;/a&gt; tutorial.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;To create the failures package:&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;very_good create -t dart_pkg failures
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;This will create a new package in &lt;code&gt;failures&lt;/code&gt; directory. We will use &lt;code&gt;freezed&lt;/code&gt; and &lt;code&gt;json_serializable&lt;/code&gt; libraries for data serialization here as well.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;dart pub add freezed json_serializable build_runner -d
dart pub add freezed_annotation json_annotation
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;To begin, we will create a &lt;code&gt;Failure&lt;/code&gt; class inside the &lt;code&gt;lib/src/failure.dart&lt;/code&gt; directory. This class will be the base for all failure types and will handle and manage our app&#39;s failures.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;abstract&lt;/span&gt; &lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;Failure&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;get&lt;/span&gt; message;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;We can then create specific failure classes, such as &lt;code&gt;NetworkFailure&lt;/code&gt;, to return to the caller whenever there is a network exception. For instance, if we have a &lt;code&gt;TodosRemoteDataSource&lt;/code&gt; that makes a call to a backend and encounters a HTTP exception, the data source can throw a &lt;code&gt;NetworkException&lt;/code&gt; which will be caught by a repository &lt;code&gt;TodoRepository&lt;/code&gt;. The repository will then encapsulate the error in a union type and return either the requested data or the failure to the caller. This allows us to effectively handle and manage failures in our app.&lt;/p&gt;
&lt;p&gt;To create a &lt;code&gt;NetworkFailure&lt;/code&gt; class, we will create a new file in the &lt;code&gt;src&lt;/code&gt; directory called &lt;code&gt;network_failure/network_failure.dart&lt;/code&gt;.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:failures/failures.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:freezed_annotation/freezed_annotation.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;part&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;network_failure.freezed.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;part&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;network_failure.g.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-meta&quot;&gt;@freezed&lt;/span&gt;
&lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;NetworkFailure&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;extends&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;Failure&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;with&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;_&lt;/span&gt;$descriptionlt;span class=&quot;hljs-title&quot;&gt;NetworkFailure&lt;/span&gt; &lt;/span&gt;{
  &lt;span class=&quot;hljs-keyword&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;hljs-keyword&quot;&gt;factory&lt;/span&gt; NetworkFailure&lpar;{
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt; message,
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; &lt;span class=&quot;hljs-built_in&quot;&gt;int&lt;/span&gt; code,
    &lt;span class=&quot;hljs-meta&quot;&gt;@Default&lt;/span&gt;&lpar;[]&rpar; &lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;&amp;gt; errors,
  }&rpar; = _NetworkFailure;

  &lt;span class=&quot;hljs-keyword&quot;&gt;factory&lt;/span&gt; NetworkFailure.fromJson&lpar;&lt;span class=&quot;hljs-built_in&quot;&gt;Map&lt;/span&gt;&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;String&lt;/span&gt;, &lt;span class=&quot;hljs-built_in&quot;&gt;dynamic&lt;/span&gt;&amp;gt; json&rpar; =&amp;gt;
      _$NetworkFailureFromJson&lpar;json&rpar;;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Once you have finished creating the &lt;code&gt;NetworkFailure&lt;/code&gt; class, you can run the &lt;code&gt;build_runner&lt;/code&gt; command to generate the necessary files for your project.&lt;/p&gt;
&lt;p&gt;Make sure to export the failure class from &lt;code&gt;failures/lib/failures.dart&lt;/code&gt;&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;library&lt;/span&gt; failures;

&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;src/failure.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;src/network_failure/network_failure.dart&#39;&lt;/span&gt;;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;You can view &lt;a target=&quot;_blank&quot; href=&quot;https://github.com/saileshbro/full_stack_todo_dart/tree/main/failures&quot;&gt;the code from here.&lt;/a&gt;&lt;/p&gt;
&lt;h2 id=&quot;heading-creating-datasource&quot;&gt;Creating &lt;code&gt;data_source&lt;/code&gt;&lt;/h2&gt;
&lt;p&gt;We will create a new package with &lt;code&gt;very_good_cli&lt;/code&gt; for our data source.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;very_good create -t dart_pkg data_source
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Once the package is created, we can create an abstract data source contract.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:models/models.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:typedefs/typedefs.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;abstract&lt;/span&gt; &lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;TodoDataSource&lt;/span&gt; &lt;/span&gt;{
  Future&amp;lt;&lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&amp;lt;Todo&amp;gt;&amp;gt; getAllTodo&lpar;&rpar;;

  Future&amp;lt;Todo&amp;gt; getTodoById&lpar;TodoId id&rpar;;

  Future&amp;lt;Todo&amp;gt; createTodo&lpar;CreateTodoDto todo&rpar;;

  Future&amp;lt;Todo&amp;gt; updateTodo&lpar;{
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; TodoId id,
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; UpdateTodoDto todo,
  }&rpar;;

  Future&amp;lt;&lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt;&amp;gt; deleteTodoById&lpar;TodoId id&rpar;;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;You can import the missing packages in &lt;code&gt;pubspec.yaml&lt;/code&gt;. After importing, it should look like this.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-yaml&quot;&gt;&lt;span class=&quot;hljs-attr&quot;&gt;name:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;data_source&lt;/span&gt;
&lt;span class=&quot;hljs-attr&quot;&gt;description:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;A&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;Very&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;Good&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;Project&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;created&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;by&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;Very&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;Good&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;CLI.&lt;/span&gt;
&lt;span class=&quot;hljs-attr&quot;&gt;version:&lt;/span&gt; &lt;span class=&quot;hljs-number&quot;&gt;0.1&lt;/span&gt;&lt;span class=&quot;hljs-number&quot;&gt;.0&lt;/span&gt;&lt;span class=&quot;hljs-string&quot;&gt;+1&lt;/span&gt;
&lt;span class=&quot;hljs-attr&quot;&gt;publish_to:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;none&lt;/span&gt;

&lt;span class=&quot;hljs-attr&quot;&gt;environment:&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;sdk:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&quot;&amp;gt;=2.18.0 &amp;lt;3.0.0&quot;&lt;/span&gt;
&lt;span class=&quot;hljs-attr&quot;&gt;dependencies:&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;models:&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;path:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;../models&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;typedefs:&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;path:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;../typedefs&lt;/span&gt;

&lt;span class=&quot;hljs-attr&quot;&gt;dev_dependencies:&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;mocktail:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^0.3.0&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;test:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^1.19.2&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;very_good_analysis:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^3.1.0&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;The &lt;code&gt;TodoDataSource&lt;/code&gt; class will be used by both the frontend and backend of our app to access and manage data related to to-dos. This class will &lt;strong&gt;throw known exceptions&lt;/strong&gt; that can be handled in the &lt;code&gt;TodoRepository&lt;/code&gt;. To manage these exceptions, we will create a separate &lt;code&gt;exceptions&lt;/code&gt; package where we can &lt;strong&gt;register all the exceptions&lt;/strong&gt; used in our app. The &lt;code&gt;TodoRepository&lt;/code&gt; will then be &lt;strong&gt;responsible for handling these exceptions&lt;/strong&gt;, allowing us to effectively manage and handle errors in our application.&lt;/p&gt;
&lt;p&gt;Once you are done adding the data source, make sure to export it in &lt;code&gt;data_sources/data_sources.dart&lt;/code&gt;&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;library&lt;/span&gt; data_source;

&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;src/todo_data_source.dart&#39;&lt;/span&gt;;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;You can view the code &lt;a target=&quot;_blank&quot; href=&quot;https://github.com/saileshbro/full_stack_todo_dart/tree/main/data_source&quot;&gt;for the data_source from GitHub.&lt;/a&gt;&lt;/p&gt;
&lt;h2 id=&quot;heading-creating-repository&quot;&gt;Creating &lt;code&gt;repository&lt;/code&gt;&lt;/h2&gt;
&lt;p&gt;We will make use of the &lt;code&gt;TodoDataSource&lt;/code&gt; class to access and manage data related to to-dos. We will also catch any exceptions thrown by the &lt;code&gt;TodoDataSource&lt;/code&gt; and serialize them as failures. &lt;code&gt;TodoRepository&lt;/code&gt; will then return the failure or the requested data to the caller.&lt;/p&gt;
&lt;p&gt;To create the &lt;code&gt;TodoRepository&lt;/code&gt; class, we will first navigate to the root directory of our project and create a new package using the &lt;code&gt;very_good&lt;/code&gt; CLI:&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-bash&quot;&gt;very_good create -t dart_pkg repository
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;Once we are done, we will add all the dependencies in &lt;code&gt;pubspec.yaml&lt;/code&gt; and run &lt;code&gt;dart pub get&lt;/code&gt; to get all the packages.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-yaml&quot;&gt;&lt;span class=&quot;hljs-attr&quot;&gt;dependencies:&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;either_dart:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;^0.3.0&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;models:&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;path:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;../models&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;failures:&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;path:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;../failures&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;typedefs:&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;path:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;../typedefs&lt;/span&gt;
  &lt;span class=&quot;hljs-attr&quot;&gt;data_source:&lt;/span&gt;
    &lt;span class=&quot;hljs-attr&quot;&gt;path:&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;../data_source&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;To create an abstract &lt;code&gt;TodoRepository&lt;/code&gt; class, we will navigate to our project&#39;s &lt;code&gt;lib/src&lt;/code&gt; directory and create a new file called &lt;code&gt;todo_repository.dart&lt;/code&gt;. Inside this file, we will make the &lt;code&gt;TodoRepository&lt;/code&gt; class and add the necessary abstract methods that will be used to manage and access data related to to-dos.&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:either_dart/either.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:failures/failures.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:models/models.dart&#39;&lt;/span&gt;;
&lt;span class=&quot;hljs-keyword&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;package:typedefs/typedefs.dart&#39;&lt;/span&gt;;

&lt;span class=&quot;hljs-keyword&quot;&gt;abstract&lt;/span&gt; &lt;span class=&quot;hljs-class&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;class&lt;/span&gt; &lt;span class=&quot;hljs-title&quot;&gt;TodoRepository&lt;/span&gt; &lt;/span&gt;{
  Future&amp;lt;Either&amp;lt;Failure, &lt;span class=&quot;hljs-built_in&quot;&gt;List&lt;/span&gt;&amp;lt;Todo&amp;gt;&amp;gt;&amp;gt; getTodos&lpar;&rpar;;

  Future&amp;lt;Either&amp;lt;Failure, Todo&amp;gt;&amp;gt; getTodoById&lpar;TodoId id&rpar;;

  Future&amp;lt;Either&amp;lt;Failure, Todo&amp;gt;&amp;gt; createTodo&lpar;CreateTodoDto createTodoDto&rpar;;

  Future&amp;lt;Either&amp;lt;Failure, Todo&amp;gt;&amp;gt; updateTodo&lpar;{
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; TodoId id,
    &lt;span class=&quot;hljs-keyword&quot;&gt;required&lt;/span&gt; UpdateTodoDto updateTodoDto,
  }&rpar;;

  Future&amp;lt;Either&amp;lt;Failure, &lt;span class=&quot;hljs-keyword&quot;&gt;void&lt;/span&gt;&amp;gt;&amp;gt; deleteTodo&lpar;TodoId id&rpar;;
}
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;We are using &lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/either_dart&quot;&gt;either_dart&lt;/a&gt; to encapsulate the failure and data in the same place.&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;&lt;a target=&quot;_blank&quot; href=&quot;https://pub.dev/packages/either_dart&quot;&gt;either_dart&lt;/a&gt; is the error handling and railway-oriented programming library is a Dart library that supports async &quot;map&quot; and async &quot;then&quot; functions for working with asynchronous computations and handling errors with &lt;code&gt;Future&amp;lt;Either&amp;gt;&lt;/code&gt; values.&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;After you are done, make sure to export it in &lt;code&gt;src/repository.dart&lt;/code&gt;&lt;/p&gt;
&lt;pre&gt;&lt;code class=&quot;lang-dart&quot;&gt;&lt;span class=&quot;hljs-keyword&quot;&gt;library&lt;/span&gt; repository;

&lt;span class=&quot;hljs-keyword&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;hljs-string&quot;&gt;&#39;src/todo_repository.dart&#39;&lt;/span&gt;;
&lt;/code&gt;&lt;/pre&gt;
&lt;p&gt;You can find the &lt;a target=&quot;_blank&quot; href=&quot;https://github.com/saileshbro/full_stack_todo_dart/tree/main/repository&quot;&gt;code for this on GitHub&lt;/a&gt;.&lt;/p&gt;
&lt;p&gt;Damn! that was a lot of code and a lot of writing 😮💨&lt;/p&gt;
&lt;p&gt;🎉 In Part 3, we&#39;re going to get started on the implementation of our repository! 💻 We&#39;ll begin by setting up the backend and establishing database connections. 🔌 It&#39;s going to be a lot of fun and a great opportunity to get hands-on with the code. So stay tuned! 😎&lt;/p&gt;
 
<!-- BLOG-POST-LIST:END -->

## Contact 📱

You can reach me on the following platforms:

<p style="display:flex; gap:20px; justify-content:center;">
  <a target= "_blank" href="https://saileshdahal.com.np" alt="Blog"><img height='45' src="./icons/hashnode.png"></a>
  <a target= "_blank" href="mailto:saileshbro@gmail.com" alt="Mail"><img height='45' src="./icons/email.png"></a>
  <a target= "_blank" href="https://github.com/saileshbro" alt="GitHub"><img height='45' src="./icons/github.png"></a>
  <a target= "_blank" href="https://www.facebook.com/saileshbro/" alt="Facebook"><img height='45' src="./icons/facebook.png"></a>
  <a target= "_blank" href="https://twitter.com/sail_sail30" alt="Twitter"><img height='45' src="./icons/twitter.png"></a>
  <a target= "_blank" href="https://www.linkedin.com/in/saileshbro/" alt="Linkedin"><img height='45' src="./icons/linkedin.png"></a>
  <a target= "_blank" href="https://www.instagram.com/sail_sail30" alt="Instagram"><img height='45' src="./icons/instagram.png"></a>
</p>

Fun fact: 2023 is worst.
