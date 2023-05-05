[![Downloads](https://static.pepy.tech/personalized-badge/managertk?period=total&units=none&left_color=black&right_color=brightgreen&left_text=Total%20Downloads)](https://pepy.tech/project/managertk) 
#
# Documentation ManagerTk
ManagerTk - is a library that aims to make writing code using Tkinter simple and fast.

###
## Download Package
```cmd
pip install ManagerTk
```
##
## Functions:
#
###### coord_view(window, mode_bool) - Creates an empty duplicate of the window in which it tracks the mouse coordinates in the window.
# 
# 
###### create_mpage(window, ui_page, size) - Creates a window with the specified parameters and interface.
#
#
###### redirect_pages(page_ui_1, page_ui_2, side=None) - Sends from one page of the program to another.
#
#
###### add_url_image(window, url, size) - Adds a picture from the url address as an object with a specified size (optional, you can omit it).
#
#
###### window_exit(title: str, message: str) - Displays the screen with the specified text and exits the program if the question is answered positively.
#
#
###### documentation() - Displays a link to the module documentation.
### 
## Example:
```python
import tkinter
import ManagerTk

window = tkinter.Tk()
window.title("Example")
count = 0


def counter_click():
    global count
    count += 1
    counter_label["text"] = f"Count clicks: {count}."


label_1_page = tkinter.Label(text="First Page Title")
label_2_page = tkinter.Label(text="Second Page Title")
label_1_in_1_page = tkinter.Label(text="Default text in page 1")
label_1_in_2_page = tkinter.Label(text="Default text in page 2")
button_1_in_2_page = tkinter.Button(text="Default button with function in page 2", command=counter_click)
counter_label = tkinter.Label(text=f"Count clicks: {count}.")
icon = ManagerTk.add_url_image(window, "https://i.ibb.co/p0yMNc0/DK404-icon.png", (80, 80))

button_1t2 = tkinter.Button(text="Redirect to second page.",
                            command=lambda: ManagerTk.redirect_pages(page_1, page_2))

button_2t1 = tkinter.Button(text="Redirect to first page",
                            command=lambda: ManagerTk.redirect_pages(page_2, page_1))

page_1 = [
    [label_1_page, [150, 20]],
    [label_1_in_1_page, [20, 60]],
    [icon, [320, 40]],
    [button_1t2, [20, 150]]
]

page_2 = [
    [label_2_page, [150, 20]],
    [label_1_in_2_page, [20, 60]],
    [button_1_in_2_page, [160, 80]],
    [counter_label, [20, 80]],
    [button_2t1, [20, 150]]
]

ManagerTk.create_mpage(window, page_1, "400x200")

window.mainloop()

```

###### This example creates a simple application with two functional pages that can be switched using buttons.

### Contacts
#
###### Telegram - [@DK50503](https://t.me/DK50503)
###### Discord - DK404#4089