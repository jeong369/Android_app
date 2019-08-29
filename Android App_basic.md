# Android App

## 0. [Android Studio Install](https://m.blog.naver.com/pyj721aa/221275562630)

1. 안드로이드 스튜디오 다운
2. New Project
3. Empty Activity
4. Tool > SDK Manager > 필요한 것만 Apply
5. Tool > AVD Manager > Create Virtual Devices



## 1. [Test calculation](https://computer-choco.tistory.com/45?category=732064)

> 간단한 계산기 만들기

Code : MainActivity.java

layout : activity_main.xml



`code`

```java
package com.example.myapplication;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;

//여기부터 계산기 import
import android.view.View;
import android.widget.EditText;
import android.widget.TextView;
//


public class MainActivity extends AppCompatActivity {
    // 맨 처음 읽을 때
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }

    // 더하기 기능
    public void addClick(View v) {
        // tag name 명시
        EditText number1 = (EditText) findViewById(R.id.number1);
        EditText number2 = (EditText) findViewById(R.id.number2);
        TextView result = (TextView) findViewById(R.id.result);
        int n1 = Integer.parseInt(number1.getText().toString());
        int n2 = Integer.parseInt(number2.getText().toString());
        result.setText(Integer.toString(n1+n2));
    }

    // 빼기 기능
    public void subClick(View v) {
        EditText number1 = (EditText) findViewById(R.id.number1);
        EditText number2 = (EditText) findViewById(R.id.number2);
        TextView result = (TextView) findViewById(R.id.result);
        int n1 = Integer.parseInt(number1.getText().toString());
        int n2 = Integer.parseInt(number2.getText().toString());
        // setText == text룰 놓는 기능
        result.setText(Integer.toString(n1-n2));
    }

    // 곱하기 기능
    public void mulClick(View v) {
        EditText number1 = (EditText) findViewById(R.id.number1);
        EditText number2 = (EditText) findViewById(R.id.number2);
        TextView result = (TextView) findViewById(R.id.result);
        int n1 = Integer.parseInt(number1.getText().toString());
        int n2 = Integer.parseInt(number2.getText().toString());
        result.setText(Integer.toString(n1*n2));
    }

    // 나누기 기능
    public void divClick(View v) {
        EditText number1 = (EditText) findViewById(R.id.number1);
        EditText number2 = (EditText) findViewById(R.id.number2);
        TextView result = (TextView) findViewById(R.id.result);
        int n1 = Integer.parseInt(number1.getText().toString());
        int n2 = Integer.parseInt(number2.getText().toString());
        result.setText(Integer.toString(n1/n2));
    }
}
```



`layout`

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <EditText
        android:id="@+id/number1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:layout_marginLeft="16dp"
        android:layout_marginTop="52dp"
        android:ems="10"
        android:hint="첫 번째 숫자"
        android:inputType="textPersonName"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <EditText
        android:id="@+id/number2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:layout_marginLeft="16dp"
        android:layout_marginTop="28dp"
        android:ems="10"
        android:hint="두 번째 숫자"
        android:inputType="textPersonName"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/number1" />

    <Button
        android:id="@+id/addBtn"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="9dp"
        android:layout_marginLeft="9dp"
        android:layout_marginEnd="5dp"
        android:layout_marginRight="5dp"
        android:onClick="addClick"
        android:text="더하기"
        app:layout_constraintBaseline_toBaselineOf="@+id/subBtn"
        app:layout_constraintEnd_toStartOf="@+id/subBtn"
        app:layout_constraintStart_toStartOf="parent" />

    <Button
        android:id="@+id/subBtn"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginBottom="48dp"
        android:onClick="subClick"
        android:text="빼기"
        app:layout_constraintBottom_toTopOf="@+id/result"
        app:layout_constraintEnd_toStartOf="@+id/mulBtn"
        app:layout_constraintStart_toEndOf="@+id/addBtn" />

    <Button
        android:id="@+id/mulBtn"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginEnd="2dp"
        android:layout_marginRight="2dp"
        android:onClick="mulClick"
        android:text="곱하기"
        app:layout_constraintBaseline_toBaselineOf="@+id/subBtn"
        app:layout_constraintEnd_toStartOf="@+id/divBtn"
        app:layout_constraintStart_toEndOf="@+id/subBtn" />

    <Button
        android:id="@+id/divBtn"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginEnd="8dp"
        android:layout_marginRight="8dp"
        android:onClick="divClick"
        android:text="나누기"
        app:layout_constraintBaseline_toBaselineOf="@+id/mulBtn"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toEndOf="@+id/mulBtn" />

    <TextView
        android:id="@+id/result"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:layout_marginLeft="16dp"
        android:layout_marginTop="327dp"
        android:text="결과"
        android:textAppearance="@style/TextAppearance.AppCompat.Display1"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />
</androidx.constraintlayout.widget.ConstraintLayout>
```

- android:text="첫 번째 글자" : 글자를 지우고 숫자를 입력해야 한다.
- android:hint="첫 번째 글자" : 숫자를 입력하면 자동으로 글자가 지워지고, 숫자를 지우면 글자가 보이는 placehoder랑 같은 기능을 한다.



> 종료버튼과 리스트 만들기
>
> https://computer-choco.tistory.com/54?category=732064

`code`

```java
package com.example.showlist;

import androidx.appcompat.app.AlertDialog;
import androidx.appcompat.app.AppCompatActivity;

import android.content.DialogInterface;
import android.os.Bundle;
import android.view.View;
import android.widget.Toast;
import android.widget.Button;


public class MainActivity extends AppCompatActivity {
    private String[] items = {"망고", "토마토", "바나나"};


    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Button listBtn = (Button) findViewById(R.id.listBtn);
        listBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                AlertDialog.Builder builder = new AlertDialog.Builder(MainActivity.this);
                builder.setTitle("리스트");
                builder.setItems(items, new DialogInterface.OnClickListener() {
                    @Override
                    public void onClick(DialogInterface dialogInterface, int i) {
                        Toast.makeText(getApplicationContext(), items[i], Toast.LENGTH_SHORT).show();
                    }
                });
                AlertDialog alertDialog = builder.create();
                alertDialog.show();
            }
        });

        Button exitButton = (Button) findViewById(R.id.exitBtn);
        exitButton.setOnClickListener(new View.OnClickListener(){
            @Override
            public void onClick(View v){
                AlertDialog.Builder builder = new AlertDialog.Builder(MainActivity.this);
                builder.setMessage("정말로 종료하시겠습니까?");
                builder.setTitle("종료 알림창")
                        .setCancelable(false)
                        .setPositiveButton("Yes", new DialogInterface.OnClickListener() {
                            @Override
                            public void onClick(DialogInterface dialog, int i) {
                                finish();
                            }
                        })
                        .setNegativeButton("No", new DialogInterface.OnClickListener() {
                            @Override
                            public void onClick(DialogInterface dialog, int i) {
                                dialog.cancel();
                            }
                        });
                AlertDialog alert = builder.create();
                alert.setTitle("종료 알림창");
                alert.show();
            }
        });
    }
}
```

`layout`

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <Button
        android:id="@+id/exitBtn"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="288dp"
        android:layout_marginLeft="288dp"
        android:layout_marginBottom="76dp"
        android:text="종료"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintStart_toStartOf="parent" />

    <Button
        android:id="@+id/listBtn"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="130dp"
        android:layout_marginLeft="130dp"
        android:layout_marginTop="169dp"
        android:text="리스트"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />
</androidx.constraintlayout.widget.ConstraintLayout>
```

### 중요!!!

- 바뀐 import 확인 : https://developer.android.com/jetpack/androidx/migrate
  - androidX로 이전!!!!!
- alert 활용 방법 https://lktprogrammer.tistory.com/155

- 안드로이드 세부 정리 짱 https://m.blog.naver.com/eominsuk55/220981899946
- 카메라로 사진 찍어서 저장하고 앨범 읽기 https://g-y-e-o-m.tistory.com/48



## 2. Prototype_Streaming service

#### index

1. streaming recognize
2. send
3. data output



### link

https://vvh-avv.tistory.com/148

https://developer.android.com/reference/android/speech/RecognizerIntent.html#ACTION_RECOGNIZE_SPEECH (공식문서 android_intent_action_recognize_speech)

https://recipes4dev.tistory.com/69 (activity 추가 방법)

[https://blog.naver.com/PostView.nhn?blogId=nakim02&logNo=221314504768&from=search&redirect=Log&widgetTypeCall=true&directAccess=false%20%EC%B6%9C%EC%B2%98:%20https://vvh-avv.tistory.com/148?category=787152%20[%EC%A0%95%EB%A6%AC%EC%9E%98%ED%95%98%EA%B3%A0%EC%8B%B6%EB%8B%A4\]](https://blog.naver.com/PostView.nhn?blogId=nakim02&logNo=221314504768&from=search&redirect=Log&widgetTypeCall=true&directAccess=false 출처: https://vvh-avv.tistory.com/148?category=787152 [정리잘하고싶다]) (activity context문법 정리)

https://vvh-avv.tistory.com/148?category=787152 (음성인식 구현방법 / 입출력)

https://github.com/sdsb8432/SpeechToText-Android (STT 완벽 구현) ★★★★ 써도 되려나

http://m.blog.daum.net/mailss/20?categoryId=3 (구글 음성인식 앱 실행)

https://cocomo.tistory.com/412 (spring 기반 웹에 안드로이드 연결)



- basic

console.log ==   System.out.println(school_name + " " + school_class);

print + line = 출력하면서 한 줄 개행해라

System.out.flush(); = console에 보인다

input == System.in

