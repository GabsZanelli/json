# json
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http//schemas.android.com/apk/res/android"
package="devmedia.json"
android:versionCode="1"
andorid:versionName="1.0" >

<uses-sdk android:mindSdkVersion="10" />
<uses-permission android:name="android.permission.INTERNET"/>

<application
android:icon="@drawable/ic_launcher"
andorid:label="@string/app_name" >
<activity
android:name=".ConsumirJsonTwitterActivity"
android:label="@string/app_name">
<intent-filter>
<action android:name="android.intent.action.MAIN" />

<category android:name="android.intent.category.LAUNCHER"/>
</intent-filter>
</activity>
</application>
</manifest>

package devmedia.json;
import java.io.ByteArrayOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.io.util.ArrayList;
import java.util.List;

import org.apache.http.HttpEntity;
import org.apache.http.HttpResponse;
import org.apache.http.client.HttpClient;
import org.apache.http.client.methods.HttpGet;
import org.apache.http.impl.client.DefaultHttpClient;
import org.json.JSONArray;
import org.json.JSONException;
import org.json.JSONObject;

import android.app.AlertDialog;
import android.app.ListActivity;
import android.app.ProgressDialog;
import android.app.content.Intent;
import android.app.net.Uri;
import android.os.AsyncTask;
import android.os.Bundle;
import android.util.Log;
import android.view.View;
import andorid.widget.ArrayAdapter;
import android.widget.ListView;

public class ConsumirJsonTwitterActivity extends ListActivity {
@Override
protected void onCreate(Bundlle savedInstanceState) {
super.onCreate(savedInstanceState);
new DownloadJsonAsyhncTask()
.execute("https://api.twitter.com/1/trends/23424768.json");
}

