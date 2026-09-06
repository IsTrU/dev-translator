# Dev Translator examples

These illustrative examples show what using the skill can look like. They are not recorded test transcripts. Both use text-only requests and do not assume a screenshot or access to project files.

Use `$dev-translator` in Codex or `/dev-translator` in Claude Code. The examples below use the Codex invocation.

## English: space inside a button

### User request

```text
$dev-translator The words inside the Save button on my profile page are touching the edges. I want more space around the words.
```

### Example response

**What you mean**

You want more space between the Save button's label and its edges on the profile page.

**Useful terms**

- **Padding:** Space inside the button, between its label and its edges. This is the spacing you want to increase.
- **Margin:** Space outside the button, between it and nearby elements.

**Prompt to copy**

```text
Increase the internal padding of the Save button on the profile page.
Its label currently touches the button edges. Give the label more
space inside the button, using the interface's existing spacing
conventions where available.

Check that there is visible space between the label and every button
edge and that the full label remains visible.
```

**Next time, you can say**

“Increase the padding inside the Save button on my profile page.”

## العربية: تذكّر اختيار الوضع الداكن

### طلب المستخدم

```text
$dev-translator لما أختار الوضع الليلي وأحدث الصفحة يرجع فاتح. أبيه يتذكر اختياري.
```

### مثال على الرد

**ما تقصده**

تبي التطبيق يتذكّر اختيارك للوضع الداكن، ويظل عليه بعد تحديث الصفحة.

**مصطلحات مفيدة**

- **تفضيل المظهر (Theme preference):** اختيارك بين الوضع الفاتح والداكن.
- **حفظ التفضيل (Persistence):** حفظ اختيارك بحيث يستمر بعد تحديث الصفحة، بدل ما يرجع للإعداد السابق.

**برومبت للنسخ**

```text
احفظ تفضيل المظهر (Theme preference) ليستمر بعد تحديث الصفحة.
حاليًا، عندما أختار الوضع الداكن ثم أحدث الصفحة، تعود الواجهة
إلى الوضع الفاتح. أريد أن تتذكّر الواجهة اختياري وتستعيده
عند تحميل الصفحة.

افحص طريقة إدارة المظهر وحفظ التفضيلات في المشروع، واستخدم
الآلية الموجودة إن توفرت.

للتحقق: اختر الوضع الداكن، ثم حدّث الصفحة وتأكد من بقاء
الواجهة في الوضع الداكن.
```

**في المرة القادمة، يمكنك القول**

«أبي تفضيل المظهر ينحفظ ويستمر بعد تحديث الصفحة.»
