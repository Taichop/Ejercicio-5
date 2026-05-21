# Ejercicio-5

'Codigo por Juan Jurado - Ejercicio 5'


def escoger_datos():
    opcion = input(
        "Escriba 1 para usar una personal predefinida o 2 para usar una aleatoria: ")
    if opcion == "1":
        personal = [
            ["Ana", 1, 2, 3, 4, 5],
            ["Berto", 5, 4, 3, 2, 1],
            ["Carla", 0, 12, 10, 14, 12],
            ["Damaris", 24, 24, 24, 24, 24]
        ]

        print("Matriz predefinida seleccionada.")
        print(f"|{'Nombre':<10}|{'Lunes':<10}|{'Martes':<10}|{'Miércoles':<10}|{'Jueves':<10}|{'Viernes':<10}|")

        for fila in personal:
            print(
                f"|{fila[0]:<10}|{fila[1]:<10}|{fila[2]:<10}|{fila[3]:<10}|{fila[4]:<10}|{fila[5]:<10}|")

    elif opcion == "2":

        import random

        nombres_random = ["Valentina", "Camila", "Isabella", "Mariana", "Lucia",
                          "Valeria", "Sofia", "Daniela", "Natalia", "Victoria", "Alejandro", "Mateo", "Camilo", "Diego", "Santiago",
                          "Leonardo", "Andres", "Felipe", "Gabriel", "Sebastian"]
        personal = []

        for _ in range(4):
            nombre = random.choice(nombres_random)
            fila = [nombre] + [random.randint(6, 10) for _ in range(5)]
            personal.append(fila)

        print("Matriz aleatoria seleccionada.")
        print(f"|{'Nombre':<10}|{'Lunes':<10}|{'Martes':<10}|{'Miércoles':<10}|{'Jueves':<10}|{'Viernes':<10}|")

        for fila in personal:
            print(
                f"|{fila[0]:<10}|{fila[1]:<10}|{fila[2]:<10}|{fila[3]:<10}|{fila[4]:<10}|{fila[5]:<10}|")
    else:
        print("Opcion no valida.")
        return []

    return personal


def comprobar_jornada(personal):

    print("\nResultados de la jornada laboral:")
    print("-" * 44)
    print(f"|{'Nombre':^10}|{'Total Horas':^13}|{'Clasificacion':^17}|")
    print("-" * 44)
    for fila in personal:
        nombre = fila[0]
        horas = sum(fila[1:])
        if horas > 40:
            clasificar = "Sobretiempo"
        else:
            clasificar = "Horario  Estandar"
        print(
            f"|{nombre:^10}|{horas:^13}|{clasificar:^17}|")
    print("-" * 44)


if __name__ == "__main__":
    personal = escoger_datos()
    comprobar_jornada(personal)
