
# Ex.No:7 Develop an android application to display the country name with image using list view in android studio.


## AIM:

To create and develop the application to display the place name with image using list view in android studio

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as “listview″ and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Get contacts details and Display details give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
```
/*
Program to print the list of item.
Developed by:
Registeration Number :
*/
```
## activity_main.xml:
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">

    <ListView
        android:id="@+id/simpleListView"
        android:layout_width="match_parent"
        android:layout_height="661dp"
        android:background="#FBFBFB"
        android:divider="#8E8A8A"
        android:dividerHeight="3dp"
        android:listSelector="#E3B5F6" />
</LinearLayout>
```
## mainactivity.java
```
package com.example.customadapter;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.widget.ArrayAdapter;
import android.widget.ListView;

public class MainActivity extends AppCompatActivity {
    ListView simpleList;
    String countryList[] = {"India", "China", "australia", "Portugal", "America", "NewZealand","Canada","Israel","Korea","Dubai","Japan"};
    int flags[] = {R.drawable.india, R.drawable.china, R.drawable.australia, R.drawable.portugal, R.drawable.america, R.drawable.new_zealand, R.drawable.canada, R.drawable.israel, R.drawable.korea, R.drawable.dubai,R.drawable.japan};

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        simpleList = (ListView) findViewById(R.id.simpleListView);
        CustomAdapter customAdapter = new CustomAdapter(getApplicationContext(), countryList, flags);
        simpleList.setAdapter(customAdapter);
    }
}
```
## activity_listview.xml
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="horizontal">

    <ImageView
        android:id="@+id/icon"
        android:layout_width="50dp"
        android:layout_height="50dp" />

    <TextView
        android:id="@+id/textView"
        android:layout_width="353dp"
        android:layout_height="wrap_content"
        android:layout_gravity="center"
        android:textColor="@color/black"
        android:textSize="20sp" />
</LinearLayout>
```
## customadapter.java
```
package com.example.customadapter;

import android.content.Context;
import android.media.Image;
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import android.widget.BaseAdapter;
import android.widget.ImageView;
import android.widget.TextView;

import java.util.zip.Inflater;

public class CustomAdapter extends BaseAdapter {
    Context context;
    String countryList[];
    int flags[];
    LayoutInflater inflter;

    public CustomAdapter(Context applicationContext, String[] countryList, int[] flags) {
        this.context = context;
        this.countryList = countryList;
        this.flags = flags;
        inflter = (LayoutInflater.from(applicationContext));
    }

    @Override
    public int getCount() {
        return countryList.length;
    }

    @Override
    public Object getItem(int i) {
        return null;
    }

    @Override
    public long getItemId(int i) {
        return 0;
    }

    @Override
    public View getView(int i, View view, ViewGroup viewGroup) {
        view = inflter.inflate(R.layout.activity_listview, null);
        TextView country = (TextView) view.findViewById(R.id.textView);
        ImageView icon = (ImageView) view.findViewById(R.id.icon);
        country.setText(countryList[i]);
        icon.setImageResource(flags[i]);
        return view;
    }
}
```
## OUTPUT
![Screenshot (65)](https://github.com/selva258963/listview/assets/121961701/cada1ac6-a619-49a7-b935-99bc36f7cfa9)
## RESULT
Thus a Simple Android Application to create and develop the application to display the country name with image using list view in android studio is developed and executed successfully.
