import  tkinter as tk


def show_output():
    number = int(number_input.get())

    if number == 0 :
        output_label.configure(text='กรุณาใส่เลขที่มากกว่า0',fg= 'red')
        return

    output = f'ตารางสุูตรคูณเเม่ {number}\n' + '-'*10 + '\n'
    for i in range(1,13):
        output += str(number) + 'x' + str(i)
        output += ' = ' + str(number * i) + '\n'

    output_label.configure(text=output,fg='black',justify= 'left')

window  = tk.Tk()
window.title('Python Multiplication Tool')
window.minsize(400 ,500)

title_label = tk.Label(master=window, text='โปรเเกรมสูตรคูณ', font='Tahoma')
title_label.pack()
title_label.pack(pady=20)

number_input = tk.Entry(master=window, font=('Tahoma',14), justify= 'center')
number_input.pack(pady=10)

go_button = tk.Button(
    master=window , text = 'เเสดงผลสูตรคูณ',
    command=show_output , width=15 , height=2 ,font=( 'Tahoma',12 ) ,fg= 'green' ,
pady=5, padx=20,bg='white',cursor= 'hand2'
)
go_button.pack(pady=10)

go_button.pack(pady=20)

output_label = tk.Label(master = window, text='' , font=('Courier New',12))
output_label.pack()

window.mainloop()
