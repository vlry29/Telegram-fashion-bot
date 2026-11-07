# Telegram-fashion-bot
def virt_helper():
    print("Добро пожаловать в чат с нашим виртуальным ассистентом по подбору одежды!")
    print("Мы поможем вам:")
    print("- Определить стиль одежды.")
    print("- Подобрать подходящий магазин и одежду.")
    print("- Добавить аксессуары и уложиться в бюджет.")
    print("Давайте начнем!\n")
    season = input("Какой сейчас сезон? (зима, лето, весна, осень): ").strip().lower()
    if season == "зима":
        print("Зимой рекомендуем выбирать теплую одежду: пуховики, свитера, ботинки.")
    elif season == "лето":
        print("Летом подойдут легкие ткани: футболки, шорты, сарафаны.")
    elif season == "весна" or season == "осень":
        print("Весной и осенью рекомендуем куртки, джинсы и легкие свитера.")
    else:
        print("Неверный ввод сезона. Пожалуйста, попробуйте снова.")
        return
    print("\nДля начала определим ваш бюджет.")
    try:
        budget = float(input("Введите ваш бюджет на одежду в рублях: ").strip())
    except ValueError:
        print("Пожалуйста, введите корректное число.")
        return
    if budget >= 10000:
        print("Рекомендуем магазины премиального класса: Louis Vuitton, Gucci, Prada.")
        store = input("Выберите магазин из предложенных: ").strip()
        available_stores = ["louis vuitton", "gucci", "prada"]
    elif 3000 <= budget < 10000:
        print("Рекомендуем магазины среднего класса: Zara, Massimo Dutti, Mango.")
        store = input("Выберите магазин из предложенных: ").strip()
        available_stores = ["zara", "massimo dutti", "mango"]
    else:
        print("Рекомендуем магазины масс-маркета: H&M, Uniqlo, Sinsay.")
        store = input("Выберите магазин из предложенных: ").strip()
        available_stores = ["h&m", "uniqlo", "sinsay"]
    if store.lower() not in available_stores:
        print("К сожалению, выбранный магазин не найден в списке.")
        return
    print(f"Вы выбрали магазин: {store.title()}. Отличный выбор!")
    style = input("Какой стиль вы предпочитаете? (классический, спортивный, повседневный): ").strip().lower()
    if style not in ["классический", "спортивный", "повседневный"]:
        print("К сожалению, такого стиля нет в ассортименте. Попробуйте выбрать из предложенных.")
        return
    if style == "классический":
        clothing_options = ["костюм", "рубашка", "брюки", "пальто"]
        accessories = ["кожаный ремень", "галстук", "часы"]
        additions = ["платок", "кожаная сумка"]
    elif style == "спортивный":
        clothing_options = ["спортивный костюм", "футболка", "толстовка", "кроссовки"]
        accessories = ["спортивный рюкзак", "бутылка для воды"]
        additions = ["кепка", "сумка через плечо"]
    else:  
        clothing_options = ["джинсы", "свитшот", "футболка", "куртка"]
        accessories = ["шарф", "шляпа", "браслет"]
        additions = ["сумка", "кроссовки"]
    print(f"В стиле '{style}' доступны следующие виды одежды: {', '.join(clothing_options)}.")
    clothing_choice = input(f"Выберите один из вариантов одежды: ").strip().lower()
    if clothing_choice not in clothing_options:
        print(f"К сожалению, {clothing_choice} нет в наличии для стиля {style}.")
        return
    color = input("Какой цвет вам нравится?").strip().lower()
    available_colors = ["черный", "белый", "синий", "красный", "зеленый"]
    if color not in available_colors:
        print(f"К сожалению, у нас нет одежды цвета {color}. Доступные цвета: {', '.join(available_colors)}.")
        return
    size = input("Какой у вас размер?").strip().upper()
    available_sizes = ["XS", "S", "M", "L", "XL"]
    if size not in available_sizes:
        print(f"К сожалению, размера {size} нет в наличии. Доступные размеры: {', '.join(available_sizes)}.")
        return
    print(f"\nДля стиля '{style}' мы рекомендуем следующие аксессуары и дополнения:")
    print(f"Аксессуары: {', '.join(accessories)}")
    print(f"Дополнения к образу: {', '.join(additions)}")
    print(f"\nВаш итоговый выбор:\n- Магазин: {store.title()}\n- Стиль: {style.title()}\n- Одежда: {clothing_choice} ({color}, размер {size})")
    print("\nСпасибо за использование нашего онлайн-помощника по подбору образов! Надеемся, что вы остались довольны своим выбором. Удачного дня!")


if __name__ == "__main__":
    virt_helper()