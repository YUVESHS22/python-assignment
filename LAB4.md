import tkinter as tk
from tkinter import messagebox
def sort_words():
    input_text = entry.get()
    if not input_text:
        messagebox.showerror("Error", "Please enter a hyphen-separated sequence of words.")
        return
    words = input_text.split("-")
    words.sort()
    sorted_text = "-".join(words)
    result_label.config(
        text=f"Sorted Sequence:\n\n{sorted_text}",
        bg="#d1f7d1",  # Light green background for the result label
        fg="#005500",  # Dark green text
        font=("Courier", 14, "bold"),  # Monospace bold font for better readability
    )

root = tk.Tk()
root.title("Hyphen-Separated Word Sorter")
root.geometry("450x350")
root.configure(bg="#f2f2f2")
entry_label = tk.Label(root, text="Enter hyphen-separated words:", font=("Arial", 12), bg="#f2f2f2")
entry_label.pack(pady=10)
entry = tk.Entry(root, font=("Arial", 14), width=35)
entry.pack(pady=5)
sort_button = tk.Button(
    root, text="Sort Words", font=("Arial", 12), bg="#4CAF50", fg="white", command=sort_words
)
sort_button.pack(pady=15)
result_label = tk.Label(
    root, text="", font=("Arial", 12), bg="#e6f7ff", fg="#333333", wraplength=400, justify="center", relief="groove"
)
result_label.pack(pady=10, padx=10, fill="both", expand=True)
footer_label = tk.Label(
    root, text="Developed with using Tkinter", font=("Arial", 10, "italic"), bg="#f2f2f2", fg="#666666"
)
footer_label.pack(pady=5)
root.mainloop()
