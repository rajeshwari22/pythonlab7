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
        bg="#d1f7d1",  
        fg="#005500", 
        font=("Courier", 14, "bold"),  
    )
root = tk.Tk()
root.title("Hyphen-Separated Word Sorter")
root.attributes('-fullscreen', True)
root.configure(bg="#f2f2f2")
header_label = tk.Label(root, text="Hyphen-Separated Word Sorter", font=("Helvetica", 28, "bold"), bg="#4CAF50", fg="white")
header_label.pack(fill=tk.X, pady=20)
entry_label = tk.Label(root, text="Enter hyphen-separated words:", font=("Arial", 16), bg="#f2f2f2")
entry_label.pack(pady=20)
entry = tk.Entry(root, font=("Arial", 18), width=50, justify="center")
entry.pack(pady=10)
sort_button = tk.Button(
    root, text="Sort Words", font=("Arial", 16, "bold"), bg="#4CAF50", fg="white", command=sort_words, padx=20, pady=10
)
sort_button.pack(pady=30)
result_label = tk.Label(
    root, text="", font=("Arial", 16), bg="#e6f7ff", fg="#333333", wraplength=800, justify="center", relief="groove", height=8
)
result_label.pack(pady=20, padx=50, fill="both", expand=True)
footer_label = tk.Label(
    root, text="Developed using Tkinter", font=("Arial", 12, "italic"), bg="#4CAF50", fg="white"
)
footer_label.pack(side=tk.BOTTOM, fill=tk.X, pady=10)
exit_button = tk.Button(
    root, text="Exit", font=("Arial", 14, "bold"), bg="red", fg="white", command=root.destroy, padx=20, pady=10
)
exit_button.pack(side=tk.BOTTOM, pady=20)
root.mainloop()
