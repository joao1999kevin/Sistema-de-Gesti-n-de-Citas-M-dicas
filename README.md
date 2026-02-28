# Sistema-de-Gesti-n-de-Citas-M-dicas
/docs
   /diagramas
/src
README.md
sistema_citas.py
# Sistema de Gestión de Citas Médicas

citas = []

def registrar_cita():
    nombre = input("Ingrese nombre del paciente: ")
    fecha = input("Ingrese fecha de la cita: ")
    hora = input("Ingrese hora de la cita: ")
    
    # Validación: evitar horarios duplicados
    for cita in citas:
        if cita["fecha"] == fecha and cita["hora"] == hora:
            print("Ese horario ya está ocupado.")
            return
    
    citas.append({"nombre": nombre, "fecha": fecha, "hora": hora})
    print("Cita registrada correctamente.")

def mostrar_citas():
    if len(citas) == 0:
        print("No hay citas registradas.")
    else:
        print("\nLista de citas:")
        for cita in citas:
            print("Paciente:", cita["nombre"],
                  "| Fecha:", cita["fecha"],
                  "| Hora:", cita["hora"])

def menu():
    while True:
        print("\n--- SISTEMA DE CITAS MÉDICAS ---")
        print("1. Registrar cita")
        print("2. Mostrar citas")
        print("3. Salir")
        
        opcion = input("Seleccione una opción: ")
        
        if opcion == "1":
            registrar_cita()
        elif opcion == "2":
            mostrar_citas()
        elif opcion == "3":
            print("Saliendo del sistema...")
            break
        else:
            print("Opción inválida")

menu()
