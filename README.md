# KoiilAI
import tkinter as tk

# Терезе жасау
window = tk.Tk()

window.title("Emotion AI ChatBot")
window.geometry("600x500")
window.config(bg="#202020")

# Эмоцияны анықтау функциясы
def analyze_emotion():

    text = entry.get().lower()

    positive_words = [
        "жақсы",
        "керемет",
        "бақыт",
        "қуаныш",
        "супер",
        "тамаша",
        "ұнады"
    ]

    negative_words = [
        "жаман",
        "қайғы",
        "ашу",
        "ренжідім",
        "ұнамады",
        "шаршадым",
        "жек көремін"
    ]

    result = "😐 Бейтарап эмоция"
    color = "white"

    for word in positive_words:
        if word in text:
            result = "😊 Позитивті эмоция"
            color = "#00ff99"

    for word in negative_words:
        if word in text:
            result = "😢 Негативті эмоция"
            color = "#ff5555"

    output_label.config(text=result, fg=color)

# Тақырып
title = tk.Label(
    window,
    text="Emotion AI ChatBot",
    font=("Arial", 24, "bold"),
    bg="#202020",
    fg="white"
)

title.pack(pady=20)

# Нұсқаулық
info = tk.Label(
    window,
    text="Мәтін жазыңыз:",
    font=("Arial", 14),
    bg="#202020",
    fg="white"
)

info.pack()

# Енгізу жолағы
entry = tk.Entry(
    window,
    font=("Arial", 16),
    width=35
)

entry.pack(pady=20)

# Батырма
button = tk.Button(
    window,
    text="Эмоцияны анықтау",
    font=("Arial", 14, "bold"),
    bg="#4CAF50",
    fg="white",
    padx=10,
    pady=5,
    command=analyze_emotion
)

button.pack(pady=10)

# Нәтиже
output_label = tk.Label(
    window,
    text="",
    font=("Arial", 22, "bold"),
    bg="#202020"
)

output_label.pack(pady=40)

# Терезені ашу
window.mainloop()
