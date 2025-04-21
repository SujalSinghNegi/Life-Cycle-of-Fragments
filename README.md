# Use Fragments

## Step1
### Inside the Build gradle
    ```
    implementation(libs.androidx.preference)
    val nav_version = "2.8.9"
    implementation("androidx.navigation:navigation-fragment:$nav_version")
    implementation("androidx.navigation:navigation-ui:$nav_version")
    ```


  ## Step2

  ### in the activiy_main.xml
  ```
 <FrameLayout
        android:id="@+id/frame"
        android:layout_width="match_parent"
        android:layout_height="0dp"
        app:layout_constraintBottom_toTopOf="@+id/button"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent">

    </FrameLayout>

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Button"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent" />
  ```

## Step3

### in the ActivityMain.kt
```
 button.setOnClickListener {
            var manager = supportFragmentManager
            var transaction = manager.beginTransaction()
            transaction.replace(R.id.frame, BlankFragment())
            transaction.commit()
        }
```
  
