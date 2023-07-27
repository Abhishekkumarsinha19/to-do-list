# to-do-list
#let's import the tkinter module to create GUIs
import tkinter as tk

#let's see whats inside  tk module
#print(dir(tk ))

#create the empty gui
root=tk.Tk()

#lets define function
def add():
    print('Adding task to the list')

    #let's get the text written inside the entry widget
    data=entry.get()

    #let's check first if data is empty or not
    if data:
        
        #shift that text to listbox
        #arguments:index number(0-->First element),data you want put
        #task_list.insert(0,data)
        task_list.insert(tk.END,data)

        #let's clean the entry widget
        entry.delete(0,tk.END)

def delete():
    print('Deleting task from the list')

    #let's delete the active element from the list
    task_list.delete(tk.ACTIVE)

#let's define its size
root.geometry('400x400')

#let's stoop the resizing
root.resizable(width=False,height=False)

#let's change the titlea
root.title('To do List')

#let's start adding components or widgets
#let's add entry widget
entry=tk.Entry(root)
entry.pack(padx=30,pady=10,fill='x')

#let's add a button -->add task
#in command parameter,we only put the function name
add_button=tk.Button(root,text='Add Task',width=20,command=add)
add_button.pack()

#let's add the task list
task_list=tk.Listbox(root)
task_list.pack(fill='x',padx=20,pady=10)

#let's add one more button-->delete task
delete_button=tk.Button(root,text='Delete Task',width=20,command=delete)
delete_button.pack()

#let's use the mainloop
#it display's the GUI continuously
#it listens for any event on gui
root.mainloop()
