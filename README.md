## ДЗ "Палиндром"
```kotlin
package com.example.lesson_5_homework_lite


import org.junit.Test
import org.junit.jupiter.api.Assertions
import java.util.Locale


// Функция для проверки текста на палиндромность. Вернет true, если переданная строка - палиндром
fun isPalindrome(string: String): Boolean{
    // модифицируем входную строку: удалим лишние пробелы в начале и конце текста,
    // а также переведем весь текст в нижний регистр
    val modifyString = string.trim().lowercase(Locale.getDefault())

    // сравниваем с помощью оператора `==` равны ли оригинальная и перевернутая строки
    return modifyString == modifyString.reversed()
}

class PalindromeTest {
    @Test
    fun `returns true if palindrome`(){
        val text = "MOm MoM"
        Assertions.assertTrue(isPalindrome(text))
    }

    @Test
    fun `returns true if not a palindrome`(){
        val text = "Aa bB"
        Assertions.assertFalse(isPalindrome(text))
    }
}
```
