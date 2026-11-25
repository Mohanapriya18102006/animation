# Ex.No:6 Develop a application to add animations to ImageView,Move,blink,fade,clockwise,zoom,slide operations are perform in android studio.


## AIM:

To develop a application to add animation to imageview,move,blink,fade,clockwise,zoom,slide operation using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Studio and then click on File → New → New Project.

Step 2: Then type the Application name as “Animation” and click Next.

Step 3: Then select the Minimum SDK as required and click Next.

Step 4: Then select the Empty Activity and click Next. Finally, click Finish.

Step 5: Design the layout in activity_main.xml with an ImageView and buttons for Move, Blink, Fade, Clockwise, Zoom, and Slide animations.

Step 6: Create separate animation XML files inside the res/anim/ folder for each animation and implement the logic in MainActivity.java to load and start each animation using AnimationUtils.

Step 7: Save and run the application to see different animations applied to the ImageView.

## PROGRAM:
```
Program to display animation operation”.
Developed by: MOHANA PRIYA R 
Register Number : 212224220065
```

## activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>

<ScrollView
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        android:gravity="center"
        android:padding="20dp">

        <!-- Image -->

        <ImageView
            android:id="@+id/imageview"
            android:layout_width="220dp"
            android:layout_height="220dp"
            android:src="@drawable/photo"
            android:scaleType="centerInside"
            android:contentDescription="Animated Image" />

        <!-- Blink -->

        <Button
            android:id="@+id/blink"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="BLINK" />

        <!-- Rotate -->

        <Button
            android:id="@+id/rotate"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="ROTATE" />

        <!-- Fade -->

        <Button
            android:id="@+id/fade"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="FADE" />

        <!-- Move -->

        <Button
            android:id="@+id/move"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="MOVE" />

        <!-- Slide -->

        <Button
            android:id="@+id/slide"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="SLIDE" />

        <!-- Zoom -->

        <Button
            android:id="@+id/zoom"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="ZOOM" />


        <!-- Stop -->

        <Button
            android:id="@+id/stop"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="STOP" />

    </LinearLayout>

</ScrollView>
```
## MainActivity.java
```
package com.example.animation;
import android.os.Bundle;
import android.view.View;
import android.view.animation.Animation;
import android.view.animation.AnimationUtils;
import android.widget.Button;
import android.widget.ImageView;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    ImageView imageView;

    Button blink, rotate, fade, move, slide, zoom, stop;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        imageView = findViewById(R.id.imageview);

        blink = findViewById(R.id.blink);
        rotate = findViewById(R.id.rotate);
        fade = findViewById(R.id.fade);
        move = findViewById(R.id.move);
        slide = findViewById(R.id.slide);
        zoom = findViewById(R.id.zoom);
        stop = findViewById(R.id.stop);

        createAnimation(blink, R.anim.blink);
        createAnimation(rotate, R.anim.rotate);
        createAnimation(fade, R.anim.fade);
        createAnimation(move, R.anim.move);
        createAnimation(slide, R.anim.slide);
        createAnimation(zoom, R.anim.zoom);

        stop.setOnClickListener(v -> imageView.clearAnimation());
    }

    private void createAnimation(View button, int animationResource) {
        button.setOnClickListener(v -> {
            Animation animation = AnimationUtils.loadAnimation(
                    MainActivity.this,
                    animationResource
            );

            imageView.startAnimation(animation);
        });
    }
}
```
## blink.xml
```
<?xml version="1.0" encoding="utf-8"?>

<alpha xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromAlpha="1.0"
    android:toAlpha="0.0"
    android:duration="300"
    android:repeatMode="reverse"
    android:repeatCount="5" />
```
## fade.xml
```
<?xml version="1.0" encoding="utf-8"?>
<alpha xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromAlpha="1.0"
    android:toAlpha="0.0"
    android:duration="1000"
    android:repeatMode="reverse"
    android:repeatCount="1" />

```
## move.xml
```
<?xml version="1.0" encoding="utf-8"?>
<translate xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromXDelta="0"
    android:toXDelta="300"
    android:duration="1000"
    android:repeatMode="reverse"
    android:repeatCount="2" />
``` 
## rotate.xml
```
<?xml version="1.0" encoding="utf-8"?>

<rotate xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromDegrees="0"
    android:toDegrees="360"
    android:pivotX="50%"
    android:pivotY="50%"
    android:duration="1000"
    android:repeatCount="2" />
```
## slide.xml
```
<?xml version="1.0" encoding="utf-8"?>
<translate xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromXDelta="-500"
    android:toXDelta="0"
    android:duration="1000" />

```
## zoom.xml
```
<?xml version="1.0" encoding="utf-8"?>
<scale xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromXScale="1.0"
    android:toXScale="1.5"
    android:fromYScale="1.0"
    android:toYScale="1.5"
    android:pivotX="50%"
    android:pivotY="50%"
    android:duration="1000"
    android:repeatMode="reverse"
    android:repeatCount="2" />
```


## OUTPUT


<img width="1920" height="1200" alt="Screenshot (184)" src="https://github.com/user-attachments/assets/b9fc8ee8-f1e1-46af-8edc-37c95959fca7" />

<img width="1920" height="1200" alt="Screenshot (183)" src="https://github.com/user-attachments/assets/c1ac00e0-2075-4765-b757-ef7b914534ee" />

<img width="1920" height="1200" alt="Screenshot (181)" src="https://github.com/user-attachments/assets/4387c687-9ffc-436e-95a4-eab0178f7bcd" />

<img width="1920" height="1200" alt="Screenshot (185)" src="https://github.com/user-attachments/assets/85d6b332-5655-42cf-b358-6dfa4da4a744" />

<img width="1920" height="1200" alt="Screenshot (186)" src="https://github.com/user-attachments/assets/6ce5be15-b0f2-4b0c-9dcc-8875964bf542" />

<img width="1920" height="1200" alt="Screenshot (189)" src="https://github.com/user-attachments/assets/7d12d2ea-85e4-4158-be54-97ee126ffb3c" />

<img width="1920" height="1200" alt="Screenshot (190)" src="https://github.com/user-attachments/assets/d10f1aff-3bad-4a97-999f-62f456ece7d0" />



## RESULT

Develop a application to add animations to ImageView,Move,blink,fade,clockwise,zoom,slide operations are perform in android studio successfully.
