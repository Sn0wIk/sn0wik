import tkinter as tk
from tkinter import simpledialog, messagebox
from random import sample

abcd = simpledialog.askinteger("Авторизуйтесь", "Введите  ваш номер счета:")
abc = "C:\Программа 1\[" + str(abcd) + "]"

with open( abc , 'r') as файл:
    asd = файл.read() 

adres = "16870"

balance = int(asd)

def choose_card():
    new_window = tk.Toplevel(root)
    new_window.title("Новое окно")

    button = tk.Button(new_window, text="Сбербанк", command=sber)
    button.pack(pady=20)

def sber():
    messagebox.showinfo("Реквезиты", "*номер карты сбера* - номер карты в СберБанке")


def chose_sum():
    global balance
    
    amount = simpledialog.askinteger("Перевод", "Введите сумму перевода:")

    adres = simpledialog.askinteger("Перевод", "Введите адрес счета куда хотите совершить перевод:")

    if int(amount) > int(balance) :
        messagebox.showwarning("Недостаточно средств", "На счету недостаточно денег")
    elif int(amount) <= int(balance) :
        if amount is not None and amount > 0:
            with open('C:\Программа 1\[' + str(adres) + ']', 'r') as файл:
                sum = int(файл.read())

            with open('C:\Программа 1\[' + str(adres) + ']', 'w') as файл:
                gh = sum + amount
                файл.write(str(gh))

            balance -= int(amount)
            balance_label.config(text=f"Баланс: {balance}")
            messagebox.showinfo("Успех", f"Перевод на сумму {amount} выполнен!")
        else:
            messagebox.showwarning("Ошибка", "Введите корректное значение суммы.")
    
    

            


def narkoshopubabki():
    global balance

    schet1 = simpledialog.askinteger("Оплата", "Введите номер счета для оплаты")
    amount = simpledialog.askinteger("Оплата", "Введите сумму для оплаты счета:")
    if amount > balance :
        messagebox.showwarning("Недостаточно средств", "На счету недостаточно денег")
    elif amount <= balance :
        if amount is not None and amount > 0:
            balance -= amount  
            balance_label.config(text=f"Баланс: {balance}")
            messagebox.showinfo("Успех", f"Оплата на сумму {amount} выполнена!")
        else:
            messagebox.showwarning("Ошибка", "Введите корректное значение счета.")


def add_balance():
    global balance
    
    amount = simpledialog.askinteger("Пополнение", "Введите сумму пополнения:")
    
    if amount is not None and amount > 0:
        balance += amount  
        balance_label.config(text=f"Баланс: {balance}")
        messagebox.showinfo("Успех", f"Баланс пополнен на {amount}!")
    else:
        messagebox.showwarning("Ошибка", "Введите корректное значение суммы.")

def schet():
    summascheta = simpledialog.askinteger("Создание счета", "Введите сумму счета:")
    money = str(summascheta)
    nums = list(range(150000))
    random_nums = str(sample(nums, 1))
    
    files = open(  random_nums , "w")
    files.write( str(money) )
    messagebox.showinfo("Успех", f"Счет на {money} создан!")

    
root = tk.Tk()
root.title("Баланс")


balance_label = tk.Label(root, text=f"Баланс: {balance}", font=('Helvetica', 16))
balance_label.pack(pady=20)


button = tk.Button(root, text="Пополнить", command=choose_card)
button.pack(pady=20)

button = tk.Button(root, text="Перевести", command=chose_sum)
button.pack(pady=20)

root.mainloop()
