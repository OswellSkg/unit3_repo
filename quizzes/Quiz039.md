# Task
Write a program that creates the GUI below:
<img width="970" alt="Screen Shot 2023-02-05 at 22 37 29" src="https://user-images.githubusercontent.com/112055140/216822365-86dc65c0-8b97-4d95-b25f-18297ece78c7.png">


# Program
```.py
#quiz.039.py

from kivymd.app import MDApp
class quiz039(MDApp):

    def __init__(self, **kwargs):
        super().__init__(**kwargs)
        self.count = 0

    def build(self):
        return

    def change(self, name: str):
        if 'up' in name and self.count < 15:
            self.count += 1
        else:
            None
        self.root.ids.counter_label.text = f"Count {self.count}"

test = quiz039()
test.run()
```

```.kv
#quiz039.kv

Screen:
    size:500,500

    MDBoxLayout:
        id:main_box
        pos_hint: {"center_x":.5,"center_y":.5}
        orientation:"horizontal"
        size_hint:.7,.3
        md_bg_color: "#a8dadc"
        pos_hint: {"center_x":.5,"center_y":.5}

        MDLabel:
            pos_hint: {"center_x":.5}
            id:counter_label
            font_style: "H3"
            halign:"center"

        MDRaisedButton:
            id:on_btn
            text: "Add +1"
            on_press: app.change("up")
            size_hint:1,1
            md_bg_color: "#e63946"
```

# Proof
<img width="912" alt="Screen Shot 2023-02-05 at 22 38 15" src="https://user-images.githubusercontent.com/112055140/216822527-60dd1fbc-ccb9-48a3-a3e6-f67f2a524920.png">
