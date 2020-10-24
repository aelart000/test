import tkinter as tk
from tkinter import StringVar
from tkinter import messagebox as m_box,Listbox,LEFT
from tkinter.ttk import Combobox

root = tk.Tk()
def namefood():
    if combo.get() != 'กรุณาเลือกรายการ' :
        m_box.showinfo('ตกลง','ยืนยันการทำรายการ')
        print(combo.get())
    else: m_box.showerror('มีข้อผิดพลาด','กรุณาเลือกรายการอารหาร')
    print('มีข้อผิดพลาด')
def clear():
    combo.set("กรุณาเลือกรายการ")



root.title("Mini Pro")
root.geometry("1000x900")

frame = tk.Frame(root, bg='#EAEFF9', )
frame.place(relx=0.1, rely=0, relwidth=0.5, relheight=1, anchor='n')


button_Ok = tk.Button(frame, text='ตกลง', font=40,command=namefood)

button_Ok.place(x=70,y=800, relx=0.2, relwidth=0.2, relheight=0.1)


button_reset = tk.Button(frame, text='ล้าง', font=40,command=clear)

button_reset.place(x=220,y=800, relx=0.2, relwidth=0.2, relheight=0.1)


lower_frame = tk.Frame(root, bg= '#80c1ff', bd=5)
lower_frame.place(x=250,y=-180,relx=0.4, rely=0.2, relwidth=0.7, relheight=1, anchor='n')

label1 = tk.Label(lower_frame, font=('Courier', 18), anchor='nw', justify='left') # ไว้แสดงข้อความบน lower_frame
label1.place(relwidth=1, relheight= 1)





##เริ่มcombo
fontExample = ("Courier", 15, "bold")

combo = Combobox(frame,width=18,font=fontExample,state="readonly")
combo['values']=('ข้าวผัดกระเพราเนื้อ',
                 'ข้าวผัดกระเพราหมู',
                 'ข้าวผัดกระเพราไก่'
)

combo.set("กรุณาเลือกรายการ")
combo.pack()

##จบcombo



root.mainloop()


