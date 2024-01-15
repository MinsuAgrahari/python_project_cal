# python_project_cal
#boomE_boomE_calculater

import tkinter as tk


root = tk.Tk()
root.title("BOOME_BOOME_Calculator")
root.geometry("267x267")


entry = tk.Entry(root, width=9, bd=8, font=("Arial", 35))
entry.grid(row=0, column=0, columnspan=6)

def add(x):
    current = entry.get()
    entry.delete(0, tk.END)
    entry.insert(0, str(current) + str(x))

def evalvate():
    try:
        result = eval(entry.get())
        entry.delete(0, tk.END)
        entry.insert(0, result)
    except Exception as e:
        entry.delete(0, tk.END)
        entry.insert(0, str(e))

def clear_field():
    entry.delete(0, tk.END)

def backspace():
    current = entry.get()
    entry.delete(0, tk.END)
    entry.insert(0, current[:-1])


# Backspace button
ass_backspace = tk.Button(root, text="⌫",bg="red",fg="black", command=backspace, width=5, font=("Arial", 14))
ass_backspace.grid(row=2, column=3)


# Other buttons
ass_1  = tk.Button(root, text="1",bg="grey", command=lambda: add(1), width=5, font=("Arial" ,14))
ass_1.grid(row=4, column=0)
ass_2  = tk.Button(root, text="2",bg="grey", command=lambda: add(2), width=5, font=("Arial" ,14))
ass_2.grid(row=4, column=1)
ass_3  = tk.Button(root, text="3",bg="grey", command=lambda: add(3), width=5, font=("Arial" ,14))
ass_3.grid(row=4, column=2)
ass_4  = tk.Button(root, text="4",bg="grey" ,command=lambda: add(4), width=5, font=("Arial" ,14))
ass_4.grid(row=3, column=0)
ass_5  = tk.Button(root, text="5",bg="grey", command=lambda: add(5), width=5, font=("Arial" ,14))
ass_5.grid(row=3, column=1)
ass_6  = tk.Button(root, text="6", bg="grey",command=lambda: add(6), width=5, font=("Arial" ,14))
ass_6.grid(row=3, column=2)
ass_7  = tk.Button(root, text="7",bg="grey", command=lambda: add(7), width=5, font=("Arial" ,14))
ass_7.grid(row=2, column=0)
ass_8  = tk.Button(root, text="8", bg="grey",command=lambda: add(8), width=5, font=("Arial" ,14))
ass_8.grid(row=2, column=1)
ass_9  = tk.Button(root, text="9", bg="grey",command=lambda: add(9), width=5, font=("Arial" ,14))
ass_9.grid(row=2, column=2)
ass_0 = tk.Button(root, text="0", bg="grey",command=lambda: add(0), width=5, font=("Arial" ,14))
ass_0.grid(row=5, column=1)


ass_plus = tk.Button(root, text="+", bg="orange",command=lambda: add("+"), width=5, font=("Arial" ,14))
ass_plus.grid(row=3, column=3)
ass_minus= tk.Button(root, text="-",bg="orange", command=lambda: add("-"), width=5, font=("Arial" ,14))
ass_minus.grid(row=4, column=3)
ass_multiply = tk.Button(root, text="*",bg="orange", command=lambda: add("*"), width=5, font=("Arial" ,14))
ass_multiply.grid(row=5, column=3)
ass_divide= tk.Button(root, text="/",bg="orange", command=lambda: add("/"), width=5, font=("Arial" ,14))
ass_divide.grid(row=6, column=3)
ass_equal= tk.Button(root, text="=",bg="orange", command=evalvate,width=5, font=("Arial" ,14))
ass_equal.grid(row=6, column=0)


ass_clear = tk.Button(root, text="C",bg="red", command=clear_field, width=5, font=("Arial" ,14))
ass_clear.grid(row=6,column =2)


ass_open = tk.Button(root, text="(", bg="grey",command=lambda: add("("), width=5, font=("Arial" ,14))
ass_open.grid(row=5, column=0)
ass_close = tk.Button(root, text=")",bg="grey" ,command=lambda: add(")"), width=5, font=("Arial" ,14))
ass_close.grid(row=5, column=2)

ass_decimal= tk.Button(root, text=".", bg="orange",command=lambda: add("."), width=5, font=("Arial" ,14))
ass_decimal.grid(row=6, column=1)

root.mainloop()
