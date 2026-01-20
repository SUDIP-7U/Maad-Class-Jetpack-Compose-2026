# Jetpack Compose `Text` – Complete Guide with Properties & Previews

> **File:** `jetpack-compose-text-complete-guide.md`
>
> A production-ready Markdown reference for Android developers using Jetpack Compose.

---

## 1. Basic Text Usage

```kotlin
Text(text = "Hello Jetpack Compose")
```

---

## 2. Text Styling (Color, Size, Weight, Style)

```kotlin
Text(
    text = "Styled Text",
    color = Color.Red,
    fontSize = 20.sp,
    fontWeight = FontWeight.Bold,
    fontStyle = FontStyle.Italic
)
```

---

## 3. Text Alignment, Line Height & Letter Spacing

```kotlin
Text(
    text = "This is a paragraph for alignment demo",
    textAlign = TextAlign.Center,
    lineHeight = 24.sp,
    letterSpacing = 1.5.sp
)
```

---

## 4. MaxLines, Overflow & Soft Wrap

```kotlin
Text(
    text = "This is a very long text that may overflow",
    maxLines = 1,
    overflow = TextOverflow.Ellipsis,
    softWrap = false
)
```

---

## 5. Text Decoration

```kotlin
Text("Underlined", textDecoration = TextDecoration.Underline)
Text("Strikethrough", textDecoration = TextDecoration.LineThrough)
```

---

## 6. Font Family

```kotlin
Text(
    text = "Serif Font",
    fontFamily = FontFamily.Serif
)
```

### Custom Font

```kotlin
val myFontFamily = FontFamily(
    Font(R.font.poppins_regular),
    Font(R.font.poppins_bold, FontWeight.Bold)
)

Text("Poppins Font", fontFamily = myFontFamily)
```

---

## 7. TextStyle (Recommended)

```kotlin
Text(
    text = "Using TextStyle",
    style = TextStyle(
        fontSize = 18.sp,
        fontWeight = FontWeight.Medium,
        letterSpacing = 0.5.sp
    )
)
```

---

## 8. Material Theme Typography (Best Practice)

```kotlin
Text(
    text = "Headline",
    style = MaterialTheme.typography.headlineMedium
)
```

Common styles:
- displayLarge
- headlineMedium
- titleLarge
- bodyLarge
- labelSmall

---

## 9. AnnotatedString (Multi-style Text)

```kotlin
Text(
    buildAnnotatedString {
        append("Hello ")
        withStyle(SpanStyle(color = Color.Red)) {
            append("Compose")
        }
    }
)
```

---

## 10. Clickable Text

```kotlin
Text(
    text = "Click Me",
    modifier = Modifier.clickable { }
)
```

---

## 11. Shadow Text

```kotlin
Text(
    text = "Shadow",
    style = TextStyle(
        shadow = Shadow(
            color = Color.Gray,
            offset = Offset(2f, 2f),
            blurRadius = 4f
        )
    )
)
```

---

## 12. Modifier Usage

```kotlin
Text(
    text = "With Modifier",
    modifier = Modifier
        .padding(16.dp)
        .background(Color.LightGray)
        .fillMaxWidth()
)
```

---

## 13. Selectable Text

```kotlin
SelectionContainer {
    Text("Selectable text")
}
```

---

## 14. RTL & Text Direction

```kotlin
Text(
    text = "مرحبا",
    style = TextStyle(textDirection = TextDirection.Rtl)
)
```

---

## 15. Complete Text API Reference

```kotlin
Text(
    text: String | AnnotatedString,
    modifier: Modifier,
    color: Color,
    fontSize: TextUnit,
    fontStyle: FontStyle,
    fontWeight: FontWeight,
    fontFamily: FontFamily,
    letterSpacing: TextUnit,
    textDecoration: TextDecoration,
    textAlign: TextAlign,
    lineHeight: TextUnit,
    overflow: TextOverflow,
    softWrap: Boolean,
    maxLines: Int,
    onTextLayout: (TextLayoutResult) -> Unit,
    style: TextStyle
)
```

---

## 16. Preview Example

```kotlin
@Preview(showBackground = true)
@Composable
fun TextPreview() {
    Column(modifier = Modifier.padding(16.dp)) {
        Text("Default Text")
        Text("Headline", style = MaterialTheme.typography.headlineMedium)
        Text("Ellipsis example", maxLines = 1, overflow = TextOverflow.Ellipsis)
        Text("Clickable", modifier = Modifier.clickable { })
    }
}
```

---

## 17. Best Practices

- Use `MaterialTheme.typography`
- Prefer `TextStyle` over inline params
- Avoid hardcoded colors
- Use `AnnotatedString` for rich text

---

## 18. Usage Guide

| Use Case | Recommendation |
|--------|----------------|
| Title | headline / title typography |
| Body | bodyLarge / bodyMedium |
| Labels | labelSmall |
| Mixed styles | AnnotatedString |

---

**Author:** Mehedi Hasan  
**Stack:** Android · Kotlin · Jetpack Compose
