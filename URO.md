'''python

from tkinter import Tk, Frame, Label, Entry, Button

top= Tk() # Vytvorenie hlavného okna aplikácie pomocou triedy Tk v Tkinteri, následne to len pridelíme premenneh
top.title("Hranie sa")
top.geometry("300x150")  # Nastavenie veľkosti okna by default


"""
// button s pouzitim place a pridania suradnic, dynamicky sa nemeni
button1 = Button(root, text="Click Me")
button1.place(x=40, y=80)
"""

""" umiestenie cez place s pouzitim relx a rely dynamicky sa meni na zaklade velkosti okna 
btn1 = Button(root, text="Button 1")
btn1.place(relx=0.5, rely=0.5, anchor="center")
"""

"""
# call triedy button, prvy argument kde sa zobrazi, aky text sa tam zobrazi
btn1 = Button(root, text="Button 1")
btn1.place(relx=0.5,rely=0.5,anchor='center')
btn2 = Button(root, text="Button 2")
btn3 = Button(root, text="Button 3")
btn4 = Button(root, text="Button 4")
"""

# grid je metóda v tkinteri = umiestnuje prvky do mriezkoveho systemu grid layout
# každý prvok dostava suradnice row and the columes ( matica )


# Čo je to sticky ?
"""
určuje ku ktorým okrajom bunky sa ma widget, prilepiť 
bez sticky sa widgety umiestnuju do stredu bunky 

Kedy zvoliť sticky ? 

Ak chceme nech nie je v strede
roztiahnuť na celu širku bunky 
tvorba neresponzivneho kde sa maju prvky dynamicky prisposobiť 

"""

"""
"n"	Prilepí widget k severu (hore)
"s"	Prilepí widget k juhu (dole)
"e"	Prilepí widget k východu (pravá strana)
"w"	Prilepí widget k západu (ľavá strana)
"ns"	Natiahne widget vertikálne (hore-dole)
"ew"	Natiahne widget horizontálne (do strán)
"nsew"	Natiahne widget do celej bunky (plné rozšírenie)
"""

""" kod
root.rowconfigure(0, weight=2) # prvy riadok sa bude zväčšovať 2x rychlejšie
root.rowconfigure(1, weight=5) # druhy riadok sa bude zvačovať 5 krat

root.columnconfigure(0, weight=1) # prvy stlpec
root.columnconfigure(1, weight=1) # druhy stlpec
"""

"""
overall umozuje aby sa gui spravne prisposobila pre velkosť okna 


rowconfigure(row, weight=N)
riadi ako sa hodnota bude zväčšovať pri zmene velkosti okna 
väčšia weight hodnota --> tym viac priestoru zaberie 
weight = 0 nemeni svoju velkost 

totožne pre : 
columnconfigure(column, weight=N)
"""

"""
Metoda .place()

Hodnoty sú v pixeloch od ľaveho horneho rohu okna 
widget bude presne tam kde ho umiestnime

Relatívnych súradníc (relx, rely)
Hodnoty sú v rozsahu 0.0 - 1.0, kde 0.0 = 0% okna a 1.0 = 100% veľkosti.
Používa sa na responzívne UI, pretože widgety sa prispôsobujú veľkosti okna.



"""






"""
btn1.grid(column=0, row=0, sticky="nsew") # zavolame metodu grid na premennu btn1 na pozicii
btn2.grid(column=1, row=0,sticky="nsew")
btn3.grid(column=0, row=1,sticky="nsew")
btn4.grid(column=1, row=1,sticky="nsew")
"""

"""
? ako funguje pack ? 

automaticky umiestnuje widgety do dostupneho priestoru v smere ktory určime horizontalne / vertikalne + centruje 

upravujeme pomocou 

1 - side 
top - odhora nadol 
bottom - odspodu nahor 
left - zlava doprava 
right - sprava dolava 

"""


# Framy
# vytvorenie ramaca pre organizaciu prvko
form_frame = Frame(top, bd=2) # okraje budu mať hrubku 2
form_frame.pack(side="top", fill="x", padx=10, pady=10)

# Pridanie Label a Entry do rámca
lbl1 = Label(form_frame, text="Name:")
input1 = Entry(form_frame, width=10)

# Umiestnenie Label a Entry pomocou grid()
lbl1.grid(row=0, column=0, sticky="e", padx=5, pady=5)  # Zarovnanie doprava
input1.grid(row=0, column=1, sticky="w", padx=5, pady=5)  # Zarovnanie doľava

# Vytvorenie tlačidiel mimo rámca
btn1 = Button(top, text="OK", bg="#7fffff", width=6)
btn2 = Button(top, text="Cancel", bg="#ff7f7f", width=6)

# Umiestnenie tlačidiel vedľa seba
btn1.pack(side="left", padx=10, pady=10)
btn2.pack(side="right", padx=10, pady=10)
'''
# Spustenie hlavnej slučky aplikácie
top.mainloop()
