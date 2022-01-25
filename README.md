# Calculadora


import tkinter

window = tkinter.Tk()
window.title("Calculadora")

#window.tkinter.call('wm', 'iconphoto', window._w, tkinter.PhotoImage(file='D:\Users\rafae\AppData\Local\Programs\Python\Python310\Imagens')

#CentrarNoMonitor
window.eval('tk::PlaceWindow . center')


#Tamanho window
window.geometry("334x284")
window.maxsize(334, 284)
window.minsize(334, 284)




expressao = ""


def add(valor):
     global expressao
     expressao += valor
     label_resultado.config(text=expressao)
    

#def add



def clear():
    
    global expressao
    expressao = ""
    label_resultado.config(text=expressao)

#def clear




def igual():
    
     global expressao
     resultado = ""
     
     if expressao != "":
        try:
            resultado = eval(expressao)
        except:
            resultado = "ERRO"
            expressao = ""
     label_resultado.config(text=resultado)

     
    
   
    
   

#def calcular




#Estrutura Calculadora

#TextoDaCalculadora
label_resultado = tkinter.Label(window, bg="lightgray", pady=2, font=(None,16), height=2, width=28, text ="")
label_resultado.grid (row = 0, column = 0, columnspan = 16)


#BotõesNúmeros
#0
button_0 = tkinter.Button(window, text = "0", width = 27, height=3, command = lambda: add("0"))
button_0.grid (row = 4, column = 0, columnspan=3)

#1
button_1 = tkinter.Button(window, text = "1", width = 8, height=3, command = lambda: add("1"))
button_1.grid (row = 1, column = 0)

#2
button_2 = tkinter.Button(window, text = "2", width = 8, height=3, command = lambda: add("2"))
button_2.grid (row = 1, column = 1)

#3
button_3 = tkinter.Button(window, text = "3", width = 8, height=3, command = lambda: add("3"))
button_3.grid (row = 1, column = 2)

#4
button_4 = tkinter.Button(window, text = "4", width = 8, height=3, command = lambda: add("4"))
button_4.grid (row = 2, column = 0)

#5
button_5 = tkinter.Button(window, text = "5", width = 8, height=3, command = lambda: add("5"))
button_5.grid (row = 2, column = 1)

#6
button_6 = tkinter.Button(window, text = "6", width = 8, height=3, command = lambda: add("6"))
button_6.grid (row = 2, column = 2)

#7
button_7 = tkinter.Button(window, text = "7", width = 8, height=3, command = lambda: add("7"))
button_7.grid (row = 3, column = 0)

#8
button_8 = tkinter.Button(window, text = "8", width = 8, height=3, command = lambda: add("8"))
button_8.grid (row = 3, column = 1)

#9
button_9 = tkinter.Button(window, text = "9", width = 8, height=3, command = lambda: add("9"))
button_9.grid (row = 3, column = 2)


#BotõesAções
#Somar
button_somar = tkinter.Button(window, text ="+", width = 8, height=3, command = lambda: add("+"))
button_somar.grid (row = 1, column = 3, )

#Subtrair
button_subtrair = tkinter.Button(window, text ="-", width = 8, height=3, command = lambda: add("-"))
button_subtrair.grid (row = 2, column = 3)

#Dividir
button_dividir = tkinter.Button(window, text ="/", width = 8, height=3, command = lambda: add("/"))
button_dividir.grid (row = 1, column = 4)

#Multiplicar
button_multiplicar = tkinter.Button(window, text ="*", width = 8, height=3, command = lambda: add("*"))
button_multiplicar.grid (row = 2, column = 4)

#Clear
button_clear = tkinter.Button(window, text ="C", bg="firebrick", height = 7, width = 8, command = lambda: clear())
button_clear.grid (row = 3, column = 3, rowspan = 2)

#Igual
button_igual = tkinter.Button(window, text ="=", bg="DarkseaGreen", height = 7, width = 8, command = lambda: igual())
button_igual.grid (row = 3, column = 4, rowspan = 2)

                   
window.mainloop()



