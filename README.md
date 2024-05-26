PYTHON CODE FOR SPELL CORRECTOR GUI USING TKINTER
import tkinter as tk
from textblob import TextBlob
from tkinter import ttk, Listbox
# Function to perform spell correction
def correct_spelling():
input_text = input_text_box.get("1.0", tk.END)
corrected_text = str(TextBlob(input_text).correct())
output_text_box.delete("1.0", tk.END)
output_text_box.insert("1.0", corrected_text)
# Create the main window
root = tk.Tk()
root.title("Spell Corrector")
root.configure(bg='purple')
# Change the background color
# Create a text widget for input with blue text on a yellow background
input_text_box = tk.Text(root, height=10, width=50, fg='blue',
bg='black', insertbackground='white')
input_text_box.pack(pady=20)
# Create a text widget for output with green text on a black background
output_text_box = tk.Text(root, height=10, width=50, fg='green',
bg='white', insertbackground='white')
output_text_box.pack(pady=20)
# Add a button to correct the entire text with a white and blue theme
button = ttk.Button(root, text="Correct Spelling",
command=correct_spelling, style='TButton')
button.pack()
# Create a style for the button
style = ttk.Style()
style.configure('TButton', foreground='white', background='blue')
# Run the application
root.mainloop()
