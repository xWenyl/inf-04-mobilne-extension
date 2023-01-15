# INF.04 Aplikacje mobilne

❗ | Więcej informacji na https://zawodowe.it 

## Lista snippetów

> Poniższe snippety są dla języka `Kotlin`, w przypadku używania `Javy` mogą nie działać poprawnie.

| Snippet              | Opis                             |
| ---------------------| -------------------------------- |
| `inf04-changebgcolor`| Zmiana koloru tła                |
| `inf04-setimage`     | Programowa zmiana obrazka        |
| `inf04-newactivity`  | Otworzenie nowej aktywności      |




## Ważne zagadnienia

<details>

<summary>Generowanie funkcji onClick</summary>


![Zdjęcie 1](/images/1.png)
![Zdjęcie 2](/images/2.png)
![Zdjęcie 3](/images/3.png)

W pliku MainActivity wygenerowania zostanie funkcja gotowa do użytku.

</details>

---

## Przykładowe zadania

<details>

<summary>Rejestracja konta</summary>

```kt
// Plik MainActivity.kt
package com.example.a01sl2022 // W miejsce a01sl2022 wstaw nazwę Twojego projektu

import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.view.View
import android.widget.EditText
import android.widget.TextView

class MainActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
    }

    fun zatwierdz(view: View) {
        // Definicja zmiennych i pobranie potrzebnych wartości
        val email = findViewById<EditText>(R.id.emailinput).text.toString()
        val haslo = findViewById<EditText>(R.id.hasloinput).text.toString()
        val powtorzhaslo = findViewById<EditText>(R.id.powtorzhasloinput).text.toString()
        var zadanieoutput = findViewById<TextView>(R.id.zadanieoutput)

        if (!email.contains("@")) // Sprawdzamy czy email nie zawiera "@"
        { 
            zadanieoutput.text = "Nieprawidlowy adres e-mail"
        } 
        else if (haslo != powtorzhaslo) // Sprawdzamy czy hasła nie są równe
        {
            zadanieoutput.text = "Hasła się różnią"
        } 
        else 
        {
            zadanieoutput.text = "Witaj ${email}" 
        }
    }
}
```
```xml
 <!-- Plik activity_main.xml -->
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    android:orientation="vertical">

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Rejestruj konto"
        android:textSize="32dp"
        android:background="#008080"
        android:textColor="@color/white"/>
    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Podaj e-mail:"
        android:textSize="20dp"
        />
    <EditText
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="email"
        android:id="@+id/emailinput"/>
    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Podaj hasło:"
        android:textSize="20dp"
        />
    <EditText
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:inputType="textPassword"
        android:id="@+id/hasloinput"/>
    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Powtórz hasło:"
        android:textSize="20dp"
        />
    <EditText
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:inputType="textPassword"
        android:id="@+id/powtorzhasloinput"/>
    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Zatwierdź"
        android:layout_gravity="center"
        android:onClick="zatwierdz"
        />
    <TextView
        android:id="@+id/zadanieoutput"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Autor: pesel"
        android:textSize="20dp"
        android:textAlignment="center"/>
</LinearLayout>
```

</details>

---