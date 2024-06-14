Mainactivity.java

package com.example.urlshortener;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    private EditText editTextUrl;
    private Button buttonShorten;
    private TextView textViewShortenedUrl;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        editTextUrl = findViewById(R.id.editTextUrl);
        buttonShorten = findViewById(R.id.buttonShorten);
        textViewShortenedUrl = findViewById(R.id.textViewShortenedUrl);

        buttonShorten.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                shortenUrl();
            }
        });
    }

    private void shortenUrl() {
        String originalUrl = editTextUrl.getText().toString().trim();
        // Here, you would implement the actual URL shortening logic.
        // For this example, we simply append "short.ly/" to simulate a shortened URL.
        String shortenedUrl = "https://short.ly/" + originalUrl;
        textViewShortenedUrl.setText("Shortened URL: " + shortenedUrl);
    }
Mainactivity.xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <EditText
        android:id="@+id/editTextUrl"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter URL"
        android:layout_margin="16dp"
        android:inputType="textUri" />

    <Button
        android:id="@+id/buttonShorten"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Shorten URL"
        android:layout_below="@id/editTextUrl"
        android:layout_margin="16dp"
        android:layout_centerHorizontal="true" />

    <TextView
        android:id="@+id/textViewShortenedUrl"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Shortened URL will appear here"
        android:layout_below="@id/buttonShorten"
        android:layout_margin="16dp" />

</RelativeLayout>Main activity.xml

Menifest.xml
<manifest xmlns:android="http://schemas.android.com/apk/res/android">

    <!-- Permissions -->
    <uses-permission android:name="android.permission.INTERNET" />

    <!-- Main Activity Declaration -->
    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/AppTheme">
        <activity
            android:name=".MainActivity"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>
