import flet as ft

def main(page: ft.Page):
    page.title = "JUDOCOIn"
    page.theme_mode = ft. ThemeMode. DARK

    page.bgcolor = "#179222"
    
    page.vertical_alignment = ft.MainAxisAlignment.CENTER

    



    page.horizontal_alignment = ft. CrossAxisAlignment.CENTER

    page.fonts = {"Kanit": "https://raw.githubusercontent.com/google/fonts/master/ofl/kanit/Kanit-Bold.ttf"}

    page.theme = ft.Theme (font_family = "Kanit")
    
    page.update()
    score = 0

    def on_click(e):
        nonlocal score
        score += 1
        score_text.value = f"{score}"
        score_text.update()
    
    score_text = ft.Text(value=score,size=43)
    
    
    image = ft.Image (

        src=f"йцуке.png",width=400, height=400,

        fit=ft.ImageFit.CONTAIN,

        animate_scale=ft.Animation (duration = 600, curve=ft.AnimationCurve.EASE)
        
    )
    image_container = ft.Container(content=image, alignment=ft.Alignment(0.0,0.0))
    image_container.on_click = on_click
    page.add (score_text,image_container)
ft.app(target=main,port=3000)
