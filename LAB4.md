import tkinter as tk
from tkinter import messagebox

def show_table():
    try:
        num = int(entry.get())
        table_text = ""
        for i in range(1, 11):
            table_text += f"{num} x {i} = {num * i}\n"
     
result_label.config(text=table_text, bg="#e6f7ff")
    
except ValueError:
        messagebox.showerror("Invalid Input", "Please enter a valid number.")

root = tk.Tk()
root.title("Multiplication Table")
root.geometry("400x200")
root.configure(bg="#f2f2f2")

entry_label = tk.Label(root, text="Enter a number:", font=("Arial", 14), bg="#FFFF00")
entry_label.pack(pady=10)

entry = tk.Entry(root, font=("Arial", 14), justify="center", bd=2, relief="solid")
entry.pack(pady=5, ipadx=10, ipady=5)

generate_button = tk.Button(
    root, text="Generate Table", font=("Arial", 14), bg="#4CAF50", fg="white", command=show_table
)
generate_button.pack(pady=15)

result_frame = tk.Frame(root, bg="#FFFF00", bd=4, relief="solid")

result_frame.pack(pady=10, padx=10, fill="both", expand=True)

result_label = tk.Label(
    result_frame, 
    text="", 
    font=("Courier", 24), 
    justify="center", 
    anchor="center",  
    bg="#FFC0CB", 
    fg="#333333", 
)
result_label.pack(pady=10, padx=10, fill="both", expand=True)

root.mainloop()
