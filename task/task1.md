# Task


# Program

```.py
from kivymd.app import MDApp

red = "\033[0;31m"

class task1(MDApp):
    def __init__(self, **kwargs):
        super().__init__(**kwargs)
        self.input = 0

    def build(self):
        return

    def val_input(self):
        if self.root.ids.input.text.isdigit():
            self.input = int(self.root.ids.input.text)
            self.root.ids.result.color = "#000000"
            self.root.ids.result.font_size = 70

        else:
            self.root.ids.result.color = "#FF0000"
            self.root.ids.result.font_size = 35
            self.root.ids.result.text ="Please enter a valid number"

    def convert_usd(self):
        self.converted = round(self.input * 1.07, 2)
        self.root.ids.result.text = f" {self.converted} USD"

    def convert_jpy(self):
        self.converted = round(self.input * 140.81, 2)
        self.root.ids.result.text = f" {self.converted} JPY"


app = task1()
app.run()
```

```.kv
Screen:
    size: 500,500

    MDBoxLayout:
        id: main_box
        orientation: 'vertical'
        size_hint:1,.6
        pos_hint: {'center_x':.5, 'center_y':.5}

        MDLabel:
            id: title
            text: "Currency Converter"
            font_style: "H4"
            pos_hint: {"center_x": .5}
            halign: "center"

        MDTextField:
            id: input
            hint_text: "Enter Amount in EUR"
            pos_hint: {'center_x':.5}
            size_hint: .7, .35
            on_text:
                app.val_input()

        MDBoxLayout:
            id: currency_box
            orientation: 'horizontal'
            size_hint:1,.6
            pos_hint: {'center_x':.5, 'center_y':.5}


            MDLabel:
                id : click_con
                text: "Choose target currency:"
                halign: 'center'
                size_hint: .275, .35
                pos_hint: {'center_x':.5,'center_y': .8}

            MDBoxLayout:
                id: button_result
                orientation:"vertical"
                size_hint: .3, 1


                MDBoxLayout:
                    id: Buttons
                    orientation: "horizontal"
                    size_hint: .55, 1
                    pos_hint: {'center_x':.7, 'center_y':.1}

                    MDRaisedButton:
                        id: USD_button
                        text: "USD"
                        pos_hint: {"center_x": .4, "center_y": .45}
                        on_release: app.convert_usd()
                        md_bg_color:"#000066"

                    MDRaisedButton:
                        id: JPY_button
                        text: "JPY"
                        pos_hint: {"center_x": .75, "center_y": .45}
                        on_release: app.convert_jpy()
                        md_bg_color:"#FF0000"

                MDLabel:
                    id: result
                    text: "0"
                    halign: 'left'
                    font_size:70
                    color:"#000000"
```

# Proof

EUR to USD
<img width="912" alt="Screen Shot 2023-02-08 at 12 14 28" src="https://user-images.githubusercontent.com/112055140/217419714-e4c20be4-97fa-488b-b7b8-79f86f89ce8f.png">

EUR to JPY
<img width="912" alt="Screen Shot 2023-02-08 at 12 14 34" src="https://user-images.githubusercontent.com/112055140/217419749-17a9ec7d-d683-40f1-955a-770821ba3c69.png">

Error text for non-ingeter input
<img width="912" alt="Screen Shot 2023-02-08 at 12 14 37" src="https://user-images.githubusercontent.com/112055140/217419778-48d57e5f-1c04-46bd-93ef-59eaba33c724.png">
