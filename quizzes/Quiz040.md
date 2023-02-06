# Task
Write a program that creates the GUI below:
<img width="994" alt="Screen Shot 2023-02-07 at 0 36 13" src="https://user-images.githubusercontent.com/112055140/217015015-913b575c-bef4-486b-9e52-b38e90adbbf9.png">


# Program
```.py
#Quiz040.py

from kivymd.app import MDApp
class quiz040(MDApp):

    def build(self):
        return


    def change(self):
        print(self.root.ids.main_box.md_bg_color)
        if self.root.ids.main_box.md_bg_color == [1.0, 1.0, 1.0, 1.0]:
            self.root.ids.main_box.md_bg_color = "#000000"
            self.root.ids.your_name.color = "#FFFFFF"
            self.root.ids.background_color_button.text = "Light Mode"
        else:
            self.root.ids.main_box.md_bg_color = "#FFFFFF"
            self.root.ids.your_name.color = "#000000"
            self.root.ids.background_color_button.text = "Dark Mode"

test = quiz040()
test.run()
```

```.kv
#quiz040.kv

MDScreen:
    size:500,500
    md_bg_color:"#FFFFFF"

    MDBoxLayout:
        id:main_box
        orientation:"vertical"
        size_hint:1,1
        md_bg_color:"FFFFFF"

        MDLabel:
            id:your_name
            text:"Oswell"
            pos_hint: {"center_x":.5}
            font_style: "H3"
            halign:"center"
            color:"#000000"

        MDRaisedButton:
            id:background_color_button
            text: "Dark Mode"
            on_press: app.change()
```
# Proof

https://user-images.githubusercontent.com/112055140/217015275-29e628a4-f337-4a0a-9c99-a323ce15549f.MOV


