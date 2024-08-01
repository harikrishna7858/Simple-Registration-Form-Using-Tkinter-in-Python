import tkinter as tk
from tkinter import messagebox

# Function to handle the submission of the form
def submit_form():
    name = name_entry.get()
    email = email_entry.get()
    age = age_entry.get()
    address = address_entry.get()
    
    # Validate fields (basic validation)
    if not name or not email or not age or not address:
        messagebox.showwarning("Input Error", "All fields are required!")
        return
    
    # Show a success message
    messagebox.showinfo("Form Submitted", f"Name: {name}\nEmail: {email}\nAge: {age}\nAddress: {address}")

    # Clear the form fields
    name_entry.delete(0, tk.END)
    email_entry.delete(0, tk.END)
    age_entry.delete(0, tk.END)
    address_entry.delete(0, tk.END)

# Create the main window
root = tk.Tk()
root.title("Registration Form")
root.geometry("300x250")

# Create and place labels and entry fields
tk.Label(root, text="Name").grid(row=0, column=0, padx=10, pady=5, sticky="e")
tk.Label(root, text="Email").grid(row=1, column=0, padx=10, pady=5, sticky="e")
tk.Label(root, text="Age").grid(row=2, column=0, padx=10, pady=5, sticky="e")
tk.Label(root, text="Address").grid(row=3, column=0, padx=10, pady=5, sticky="e")

name_entry = tk.Entry(root)
email_entry = tk.Entry(root)
age_entry = tk.Entry(root)
address_entry = tk.Entry(root)

name_entry.grid(row=0, column=1, padx=10, pady=5)
email_entry.grid(row=1, column=1, padx=10, pady=5)
age_entry.grid(row=2, column=1, padx=10, pady=5)
address_entry.grid(row=3, column=1, padx=10, pady=5)

# Create and place the submit button
submit_button = tk.Button(root, text="Submit", command=submit_form)
submit_button.grid(row=4, column=0, columnspan=2, pady=10)

# Run the application
root.mainloop()
