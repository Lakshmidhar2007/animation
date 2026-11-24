# Ex.No: 06 Develop a application to add animations to ImageView,Move,blink,fade,clockwise,zoom,slide operations are perform in android studio.


## AIM:

To develop a application to add animation to imageview,move,blink,fade,clockwise,zoom,slide operation using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Design the layout using activity_main.xml

Step 3: Add an ImageView to display the image and add buttons for each animation (Move, Blink, Fade, Clockwise, Zoom, Slide).

Step 4: Import the image into the drawable folder.

Step 5: Create animation XML files under res/anim/ for each animation type such as blink, fade, move, rotate, slide and zoom.

Step 6: Type the Java program in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
```
Program to display animation operation”.
Developed by: LAKSHMIDHAR N
Registration Number : 212224230138
```

## main_avtivity.java

```java
package com.example.exp6;

import android.app.Activity;
import android.os.Bundle;
import android.view.View;
import android.view.animation.Animation;
import android.view.animation.AnimationUtils;
import android.widget.Button;
import android.widget.ImageView;

public class MainActivity extends Activity {

    ImageView imageView;

    Button btnMove;
    Button btnBlink;
    Button btnFade;
    Button btnClockwise;
    Button btnZoom;
    Button btnSlide;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        imageView = findViewById(R.id.imageView);

        btnMove = findViewById(R.id.btnMove);
        btnBlink = findViewById(R.id.btnBlink);
        btnFade = findViewById(R.id.btnFade);
        btnClockwise = findViewById(R.id.btnClockwise);
        btnZoom = findViewById(R.id.btnZoom);
        btnSlide = findViewById(R.id.btnSlide);

        btnMove.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Animation animation =
                        AnimationUtils.loadAnimation(MainActivity.this, R.anim.move);
                imageView.startAnimation(animation);
            }
        });

        btnBlink.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Animation animation =
                        AnimationUtils.loadAnimation(MainActivity.this, R.anim.blink);
                imageView.startAnimation(animation);
            }
        });

        btnFade.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Animation animation =
                        AnimationUtils.loadAnimation(MainActivity.this, R.anim.fade);
                imageView.startAnimation(animation);
            }
        });

        btnClockwise.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Animation animation =
                        AnimationUtils.loadAnimation(MainActivity.this, R.anim.clockwise);
                imageView.startAnimation(animation);
            }
        });

        btnZoom.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Animation animation =
                        AnimationUtils.loadAnimation(MainActivity.this, R.anim.zoom);
                imageView.startAnimation(animation);
            }
        });

        btnSlide.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Animation animation =
                        AnimationUtils.loadAnimation(MainActivity.this, R.anim.slide);
                imageView.startAnimation(animation);
            }
        });
    }
}
```
## activity_main.xml

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:padding="16dp">

    <ImageView
        android:id="@+id/imageView"
        android:layout_width="200dp"
        android:layout_height="200dp"
        android:src="@drawable/photo"
        android:scaleType="centerInside"
        android:contentDescription="Animated Image"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"/>

    <!-- First row -->

    <Button
        android:id="@+id/btnMove"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:text="Move"
        android:layout_marginTop="20dp"
        android:layout_marginEnd="6dp"
        app:layout_constraintTop_toBottomOf="@id/imageView"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toStartOf="@id/btnBlink"
        app:layout_constraintHorizontal_weight="1"/>

    <Button
        android:id="@+id/btnBlink"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:text="Blink"
        android:layout_marginTop="20dp"
        android:layout_marginStart="6dp"
        app:layout_constraintTop_toBottomOf="@id/imageView"
        app:layout_constraintStart_toEndOf="@id/btnMove"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_weight="1"/>

    <!-- Second row -->

    <Button
        android:id="@+id/btnFade"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:text="Fade"
        android:layout_marginTop="8dp"
        android:layout_marginEnd="6dp"
        app:layout_constraintTop_toBottomOf="@id/btnMove"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toStartOf="@id/btnClockwise"/>

    <Button
        android:id="@+id/btnClockwise"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:text="Clockwise"
        android:layout_marginTop="8dp"
        android:layout_marginStart="6dp"
        app:layout_constraintTop_toBottomOf="@id/btnBlink"
        app:layout_constraintStart_toEndOf="@id/btnFade"
        app:layout_constraintEnd_toEndOf="parent"/>

    <!-- Third row -->

    <Button
        android:id="@+id/btnZoom"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:text="Zoom"
        android:layout_marginTop="8dp"
        android:layout_marginEnd="6dp"
        app:layout_constraintTop_toBottomOf="@id/btnFade"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toStartOf="@id/btnSlide"/>

    <Button
        android:id="@+id/btnSlide"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:text="Slide"
        android:layout_marginTop="8dp"
        android:layout_marginStart="6dp"
        app:layout_constraintTop_toBottomOf="@id/btnClockwise"
        app:layout_constraintStart_toEndOf="@id/btnZoom"
        app:layout_constraintEnd_toEndOf="parent"/>

</androidx.constraintlayout.widget.ConstraintLayout>
```
## MOVE.XML
```xml
<?xml version="1.0" encoding="utf-8"?>
<translate xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromXDelta="0"
    android:toXDelta="300"
    android:fromYDelta="0"
    android:toYDelta="0"
    android:duration="1000" />

```
## BLINK.XML
```xml
<?xml version="1.0" encoding="utf-8"?>
<alpha xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromAlpha="1.0"
    android:toAlpha="0.0"
    android:duration="500"
    android:repeatMode="reverse"
    android:repeatCount="5" />
```
## FADE.XML
```xml
<?xml version="1.0" encoding="utf-8"?>
<alpha xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromAlpha="1.0"
    android:toAlpha="0.0"
    android:duration="2000" />
```
## CLOCKWISE.XML
```xml
<?xml version="1.0" encoding="utf-8"?>
<rotate xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromDegrees="0"
    android:toDegrees="360"
    android:pivotX="50%"
    android:pivotY="50%"
    android:duration="1000" />
```
## ZOOM.XML
```xml
<?xml version="1.0" encoding="utf-8"?>
<scale xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromXScale="1.0"
    android:toXScale="2.0"
    android:fromYScale="1.0"
    android:toYScale="2.0"
    android:pivotX="50%"
    android:pivotY="50%"
    android:duration="1000" />
```
## SLIDE.XML
```xml
<?xml version="1.0" encoding="utf-8"?>
<translate xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromXDelta="-300"
    android:toXDelta="0"
    android:fromYDelta="0"
    android:toYDelta="0"
    android:duration="1000" />
```


## OUTPUT

<img width="1758" height="928" alt="image" src="https://github.com/user-attachments/assets/5b057bb0-5b8c-485d-93e8-8ea8f19fe566" />

<img width="1898" height="1016" alt="image" src="https://github.com/user-attachments/assets/3bcf5055-bdf2-4283-9962-d327f16ed8ed" />

<img width="1917" height="1020" alt="image" src="https://github.com/user-attachments/assets/b0045b67-08df-47df-b9cd-7d616af5cd8b" />

<img width="1917" height="1012" alt="image" src="https://github.com/user-attachments/assets/5df915f3-619c-44d8-b0a1-b24ba41a6a1a" />

<img width="1917" height="1020" alt="image" src="https://github.com/user-attachments/assets/7b3c5fca-f4c3-4c1f-a285-1610c4584eb6" />

<img width="1917" height="1020" alt="image" src="https://github.com/user-attachments/assets/528434a3-7bec-421a-8b4d-7f8d7a494eb7" />

<img width="1917" height="1020" alt="image" src="https://github.com/user-attachments/assets/ab510f63-e9ed-4308-983a-dfb7382c8714" />










## RESULT

Thus, the experiment Implementation of Animation application using android studio executed successfully.


