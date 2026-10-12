## Hi there 👋

<!--
**Arsen-Almasov/Arsen-Almasov** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->

errors = pd.DataFrame({
    "Исходный текст": df.loc[X_test.index, "text"],
    "Истинный класс": y_test,
    "Предсказанный класс": pred_tfidf
})

errors = errors[
    errors["Истинный класс"] != errors["Предсказанный класс"]
]

print("Количество ошибок:", len(errors))

if len(errors) > 0:
    display(errors.head(5).reset_index(drop=True))
else:
    print("На этой тестовой выборке ошибок не найдено.")

