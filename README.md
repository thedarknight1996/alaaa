from tkinter import*
from tkinter import ttk
import tkinter as tk
al = Tk()
al.geometry ("400x500+700+100")
al.attributes("-alpha",0.7)
al.title ("coding text")
pla=Frame(width="400",height="500",bg="gray")
pla.place(x=405,y=0)
adf1=Frame(width="400",height="500",bg="black")
adf1.place(x=0,y=0)


#al.resizable (False , False)

def tlt():
    ap1=rr2.get()
    ap2=ee2.get()
    ap3=ss2.get()
    ap4=cc2.get()

    if ap4 =="english" :

        alphabet = ["a", "b", "c", "d", "e", "f", "g", "h", "i", "j", "k", "l", "m", "n", "o", "p", "q", "r", "s", "t", "u",
"v", "w", "x", "y", "z", "a", "b", "c", "d", "e", "f", "g", "h", "i", "j", "k", "l", "m", "n", "o", "p",
"q", "r", "s", "t", "u", "v", "w", "x", "y", "z"]

        direction = ap2
        text =ap1.lower()
        shift = int(ap3)
        cipher = []
        data = list(ap1)
        if direction == "encode":
            for i in data:
                if i == " ":
                    cipher.append(" ")
                    continue
                location = alphabet.index(i)
                coding = location + shift
                cipher.append(alphabet[coding])
                cipher_text = "".join(cipher)
                gh1 = Entry(pla, font=("arial", 13))
                gh1.insert(0, f"{cipher_text}")
                gh1.config(state="readonly")
                gh1.place(x=101, y=300)

        elif direction == "decode":

            for i in data:
                if i == " ":
                    cipher.append(" ")
                    continue
                location = alphabet.index(i)
                coding = location - shift
                cipher.append(alphabet[coding])
                cipher_text = "".join(cipher)

                gh1 = Entry(pla, font=("arial", 13))
                gh1.insert(0, f"{cipher_text}")
                gh1.config(state="readonly")
                gh1.place(x=101, y=300)

    elif ap4 == "arabic" :

        alphabet=["ا","ب","ت","أ","ئ","ى","ث","ج","ح","خ","د","ذ","ر","ز","س","ش","ص","ض","ط","ظ","ع","غ","ف","ق",
"ك","ل","م","ن","و","ه","ي"]

        direction = ap2
        text =ap1
        shift = int(ap3)
        cipher = []
        data = list(ap1)
        if direction == "encode":
            for i in data:
                if i == " ":
                    cipher.append(" ")
                    continue
                location = alphabet.index(i)
                coding = location + shift
                cipher.append(alphabet[coding])
                cipher_text = "".join(cipher)

                gh1 = Entry(pla, font=("arial", 13))
                gh1.insert(0, f"{cipher_text}")
                gh1.config(state="readonly")
                gh1.place(x=101, y=300)

        elif direction == "decode":

            for i in data:
                if i == " ":
                    cipher.append(" ")
                    continue
                location = alphabet.index(i)
                coding = location - shift
                cipher.append(alphabet[coding])
                cipher_text = "".join(cipher)

                gh1 = Entry(pla, font=("arial", 13))
                gh1.insert(0, f"{cipher_text}")
                gh1.config(state="readonly")
                gh1.place(x=101, y=300)

ee=Label(adf1,text="welcome to my brogram do you wont to\n  encode    or    decode",font=("arial",13),bg="black",fg="white")
ee.place(x=50,y=10)

ee2=ttk.Combobox(adf1,value=("encode","decode"),state="readonly",font=("arial",13),justify="center")
ee2.place(x=100,y=70)


fd=Label(adf1,text="_____________________________________",font=("arial",15),bg="black",fg="white")
fd.place(x=10,y=90)


cc=Label(adf1,text="what the language do you want to code in\nenglish\tarabic",font=("arial",13),bg="black",fg="white")
cc.place(x=50,y=140)

cc2=ttk.Combobox(adf1,value=("english","arabic"),state="readonly",font=("arial",13),justify="center")
cc2.place(x=100,y=195)

fd=Label(adf1,text="_____________________________________",font=("arial",15),bg="black",fg="white")
fd.place(x=10,y=220)

ss=Label(adf1,text="Type the shift number",font=("arial",13),bg="black",fg="white")
ss.place(x=125,y=270)


ss2=Entry(adf1,font=("arial",13),justify="center",textvariable=IntVar())
ss2.place(x=110,y=310)

def next():
    al.geometry ("800x500+700+100")
fds=Button(adf1,text="next",command=next,font=("arial",15))
fds.place(x=180,y=380)

rr=Label(pla,text="Type your text",font=("arial",13),bg="gray",fg="white")
rr.place(x=150,y=10)

rr2=Entry(pla,font=("arial",13))
rr2.place(x=101,y=70)

fg=Button(pla,text="ENTER",command=tlt,font=("arial",14),fg="green")
fg.place(x=160,y=130)


al.mainloop()
