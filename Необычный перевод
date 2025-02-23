import tkinter as tk

# Раскладки клавиатуры
eng_layout = "qwertyuiop[]asdfghjkl;'zxcvbnm,./"
rus_layout = "йцукенгшщзхъфывапролджэячсмитьбю."


# Функция перевода текста
def convert_layout():
    text = entry.get()
    choice = var.get()

    if choice == 1:
        result = translate(text, eng_layout, rus_layout)
    else:
        result = translate(text, rus_layout, eng_layout)

    result_label.config(text="Результат: " + result)


# Функция перевода
def translate(text, from_layout, to_layout):
    converted = []
    for ch in text:
        index = from_layout.find(ch)
        converted.append(to_layout[index] if index != -1 else ch)
    return "".join(converted)


# Создаем окно
window = tk.Tk()
window.title("Переключатель раскладки")
window.geometry("400x300")

# Поле ввода текста
entry = tk.Entry(window, width=40)
entry.pack(pady=10)

# Выбор языка
var = tk.IntVar()
rb1 = tk.Radiobutton(window, text="С английского на русский", variable=var, value=1)
rb2 = tk.Radiobutton(window, text="С русского на английский", variable=var, value=2)
rb1.pack()
rb2.pack()
rb1.select()  # По умолчанию выбрана первая опция

# Кнопка перевода
btn = tk.Button(window, text="Перевести", command=convert_layout)
btn.pack(pady=10)

# Поле для результата
result_label = tk.Label(window, text="Результат: ", font=("Arial", 12))
result_label.pack()

# Запуск программы
window.mainloop()
