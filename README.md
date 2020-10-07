# calculation-of-fuel
""" Программа для расчета топлива и затрат на еду.
Для тех кто путешествует на машине..."""


rashod_na_100_km = 0
all_km = 0
price_litr = 0
all_rashod = 0
all_price = 0
price_eda = ""
day_travel = 0
valuta = ""
valuta = input("Введите валюту для расчетов: ")

if (valuta == ""):
    valuta = "руб."


while (rashod_na_100_km <= 0):
    rashod_na_100_km = float(input("Введите расход топлива на 100 км.: "))
    if (rashod_na_100_km <= 0):
        print("Ошибка данных! Значение не может быть 0 или меньше. Повторите ввод!")


while (all_km <= 0):
    all_km = float(input("Введите сколько километров собираетесь проехать: "))
    if (all_km <= 0):
        print("Ошибка данных! Значение не может быть 0 или меньше. Повторите ввод!")


while (price_litr <= 0):
    price_litr = float(input("Сколлько стоит литр бензина? "))
    if (price_litr <= 0):
        print("Ошибка данных! Значение не может быть 0 или меньше. Повторите ввод!")

all_rashod = all_km / 100 * rashod_na_100_km
all_price = all_rashod * price_litr

calculation_food = input("Произвести расчёт затрат на еду? (yes/no)")
if calculation_food == 'yes':
    price_eda = int(input("Введите сумму суточного расхода на еду: "))
    while day_travel <= 0:
        day_travel = int(input("Введите кол-во дней путешествия: "))
        if day_travel <= 0:
            print("Введено не верное кол-во дней! Повторите ввод!")

    print("***********************")
    print()
    print("***********************")
    print("Всего затрачено на еду: ", price_eda * day_travel, valuta)

if calculation_food == 'no':
    print("Продолжайте далее")

print("Всего потратите топлива:", int(all_rashod * 100) / 100, "л.")
print("Общая цена на топливо:", int(all_price * 100) / 100, valuta)
print("Общие затраты на топливо и еду: ", int(all_price + price_eda * day_travel), valuta)
