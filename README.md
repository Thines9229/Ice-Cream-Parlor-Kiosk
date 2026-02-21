import tkinter as tk
from tkinter import*

#Price per scoop
def button_clicked():
    vanillaTotal = int(vanillasb.get()) * 2.25
    chocoTotal = int(chocosb.get()) * 2.25
    strawTotal = int(strawsb.get()) * 2.25
    manTotal = int(mansb.get()) * 2.25
    mbTotal = int(mbsb.get()) * 2.25
    cacTotal = int(cacsb.get()) * 2.25
    total_bills = vanillaTotal + chocoTotal + strawTotal + manTotal + mbTotal + cacTotal

    total_window = tk.Toplevel(root) 
    total_window.title("Order Total") 
    
    tk.Label(total_window, text=f"Your total is: ${total_bills:.2f}", 
             font=("Arial", 18)).pack(pady=20) 
    tk.Button(total_window, text="Close", command=total_window.destroy).pack(pady=10) 
#Total window
    def open_new_window():
        new_window = tk.Toplevel(root)
        new_window.title("Total")
        new_window.geometry("300x300") 
        tk.Label(new_window, text="Your total is: ").pack(pady=20)
        tk.Button(new_window, text="close", command=new_window.destroy).pack(pady=20)
        

root = Tk()
root.title("Creamery Dreamery")
root.maxsize(width=1600, height=900)
root.configure(bg="#98DDDA")

# Lables for the main window including title
icName = Label(text='Welcome to\nCreamery Dreamery', font=("Times New Roman", 20, "bold"), bg="#98DDDA")
icName.place(x=675, y=50)

quote = Label(text="The Flavors You Dream Of")
quote.place(x=725, y=125)

iclable = Label(text="Pick a flavor and how many scoops you want", font=("Times New Roman", 12, "normal"), bg="#98DDDA")
iclable.place(x=660 , y=200)

tk.Button(root, text="exit", command=root.destroy).pack(pady=20)

#Pick flavor and how many scoops with lables listing the flavor and the price displaying it with a picture
vanilla = PhotoImage(file="vanilla-ice-cream.png")
vanillalable = Label(root, image=vanilla, height=150, width=150)
vanillalable.place(x=50, y=130)
vanillainfo = Label(text="Vanilla\n$2.25", font=("Times New Romans", 10, "normal"), bg="#98DDDA")
vanillainfo.place(x=40, y=230)
vanillasb = Spinbox(from_=0, to=10, width=5)
vanillasb.place(x=80, y=270)


choco = PhotoImage(file="chocolate-ice-cream.png")
chocolable = Label(root, image=choco, height=150, width=150)
chocolable.place(x=200, y=130)
chocoinfo = Label(text="Chocolate\n$2.25", font=("Times New Romans", 10, "normal"), bg="#98DDDA")
chocoinfo.place(x=210, y=230)
chocosb = Spinbox(from_=0, to=10, width=5)
chocosb.place(x=225, y=270)

straw = PhotoImage(file="strawberry-ice-cream.png")
strawlable = Label(root, image=straw, height=150, width=150)
strawlable.place(x=350, y=130)
strawinfo = Label(text="Strawberry\n$2.25", font=("Times New Romans", 10, "normal"), bg="#98DDDA")
strawinfo.place(x=350, y=230)
strawsb = Spinbox(from_=0, to=10, width=5)
strawsb.place(x=380, y=270)

man = PhotoImage(file="mango-ice-cream.png")
manlable = Label(root, image=man, height=150, width=150)
manlable.place(x=50, y=380)
maninfo = Label(text="Mango\n$2.25", font=("Times New Romans", 10, "normal"), bg="#98DDDA")
maninfo.place(x=40, y=480)
mansb = Spinbox(from_=0, to=10, width=5)
mansb.place(x=80, y=520)

mb = PhotoImage(file="mixed-berry-ice-cream.png")
mblable = Label(root, image=mb, height=150, width=150)
mblable.place(x=200, y=380)
mbinfo = Label(text="Mixed Berry\n$2.25", font=("Times New Romans", 10, "normal"), bg="#98DDDA")
mbinfo.place(x=225, y=480)
mbsb = Spinbox(from_=0, to=10, width=5)
mbsb.place(x=230, y=520)

cac = PhotoImage(file="cookies-and-cream-ice-cream.png")
caclable = Label(root, image=cac, height=150, width=150)
caclable.place(x=1100, y=575)
cacinfo = Label(text="Cookies and Cream\n$2.25", font=("Times New Romans", 10, "normal"), bg="#98DDDA")
cacinfo.place(x=1115, y=775)
cacsb = Spinbox(from_=0, to=10, width=5)
cacsb.place(x=1155, y=750)

    
#The button to get the total of your order
finish = Button(text="Order", command=button_clicked)
finish.place(x= 400, y= 550)


root.mainloop()
