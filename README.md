# Control-de-Gastos-y-Patrimonio-con-Ahorro-o-Inversion

opcion=int(input("Ingresa la opcion que mas te guste, ahorrar o invertir: 1(Ahorrar), 2(Invertir): ")) #Aqui ingresas la opcion que vayas a usar o mas te guste6
if opcion==1:
 print("Muy Bien Elegiste Ahorrar")
 Tipo_Salario=int(input("Pregunta ¿Tu salario es neto o bruto?, ingresalo aqui:  1(Neto), 2(Bruto):")) #En esta linea respondes si tu salario es neto o bruto, pd: SAT(Diputados) no te lo robes :( xd
 while True:
    try:
        Salario=float(input("Ingresa tu salario Mensual: (MXN)  "))


        if Salario <=0:
            print("Tu salario debe de ser mayor a 0, a y que tenga seguro social")
            continue
        break
    except ValueError:
      print("Debes ingresar el 1 o el 2, no letras ni simbolos")
     
 if Tipo_Salario==1:
   print("Muy bien, tu salario es neto, ¡ya no mas impuestos!")

 else:
  print("Tu Salario es bruto, se te descontara un % del IVA mas el ISR")
  IVA=float(input("Ingresa el % del IVA: "))
  ISR=float(input("Ingresa el % del ISR: "))
  Impuestos=IVA+ISR
  Ingreso_neto=Salario*(1-Impuestos/100) #< Este es el IVA y el ISR, lo agregue asi por que es mas directo que IVA=Salario*.16 como tenia en mi anterior version, subire la final o una beta a Github cuando este lista
 Patrimonio=[] #Esta es una lista y sirve para agregar los patrimonios con la funcion  Patrimonio.append(Metas)
 while True:   
  Metas="  Escribe que Metas y objetivos buscas lograr,una casa, una familia, un negocio ,un viaje, tu Reultado"
  if Metas =="":
      print("Debes de tener por lo menos una meta, vamos se ambicioso")
      continue
  break
 while Metas.lower() != "fin": #Aqui se repite este ciclo de "Ingresar metas" hasta que le pongas fin
  Metas=(input("Ingresa las Metas aqui: ")) 

 if Metas.lower() != "fin": #Esta es la variable que indica el "break" o fin para el ciclo
  Patrimonio.append(Metas.title())
 while True:
  try:
     Costo=float(input("Ingresa el costo Total de tu Patrimonio: ")) #Aqui ingresas el costo de tus metas y sueños, Todo se puede en esta vida primeramente Dios, ¡Creelo, Buscalo, Logralo! :)
     if Costo <=0:
        print("El Costo debe de ser mayor a 0, a menos que sea un souvenir jajaj")
        continue
     break
  except ValueError:
        print("Ingresa solo valores numericos al costo: ")
 if Tipo_Salario==1:
  Ingreso_neto=Salario
 Porcentaje_Ahorro=float(input("Ingresa el %/ De Ahorro para tus metas: "))
 Dinero_destinado= Ingreso_neto*Porcentaje_Ahorro/100

 if Dinero_destinado <=0:
   print("Necesitas Ahorrar una cantidad, si no quedaras en 0")
   exit()

 Meses= Costo/Dinero_destinado
 Años= Meses/12
 print("Salario", Salario)
 print("Patrimonio".join(Patrimonio))
 print("Ingreso neto", Ingreso_neto)
 print("Dinero para Ahorrar", Dinero_destinado)
 print("Precio Final", Costo)
 print("Te tomara", Meses , "Meses de Ganancias para tener capital, tiempo al tiempo")
 print("Te tomara", Años , "Años de Ganancias para tener capital, el interes compuesto es oro")
 exit()
if opcion==2:
    print("Invertir Entonces")
    Tipo_Salario=int(input("Pregunta ¿Tu salario es neto o bruto?, ingresalo aqui:  1(Neto), 2(Bruto):"))
    Salario=float(input("Ingresa tu salario Mensual: (MXN)  "))

    if Salario <=0:
        print("Tu salario debe de ser mayor a 0, a y que tenga seguro social")
        exit()

    if Tipo_Salario==2:
        print("Tu Salario es bruto, se te descontara un % del IVA mas el ISR")
        IVA=float(input("Ingresa el % del IVA: "))
        ISR=float(input("Ingresa el % del ISR: "))
        Impuestos=IVA+ISR
        Ingreso_neto=Salario*(1-Impuestos/100)

    else:
        print("Muy bien, tu salario es neto, ¡ya no mas impuestos!")
        Ingreso_neto=Salario
    Patrimonio=[] #Esta es una lista y sirve para agregar los patrimonios con la funcion  Patrimonio.append(Metas)
    while True:   
     Metas="  Escribe que Metas y objetivos buscas lograr,una casa, una familia, un negocio ,un viaje, tu Reultado"
     if Metas =="":
      print("Debes de tener por lo menos una meta, vamos se ambicioso")
      continue
     break
    while Metas.lower() != "fin": #Aqui se repite este ciclo de "Ingresar metas" hasta que le pongas fin
     Metas=(input("Ingresa las Metas aqui: ")) 
    if Metas.lower() != "fin": #Esta es la variable que indica el "break" o fin para el ciclo
         Patrimonio.append(Metas.title())       
Costo = float(input("Ingresa el costo Total de tu Patrimonio: "))
Inversion = float(input("Ingresa el % de Inversion para tus metas: "))
Ganancia = float(input("Ingresa el % de Ganancia Anual que esperas obtener: "))
Inflacion= float(input("Ingresa el % de inflacion anual de tu pais: "))
Ganancia_final = Ganancia - Inflacion
if Ganancia_final <= 0:
     print("Tu ganancia real es 0 o negativa. La inflación te gana we")
else:
    print(f"{Ganancia}% - {Inflacion}% = {Ganancia_final}%")
    
    Dinero_invertir = Ingreso_neto * Inversion / 100 #Aqui se calcula tu ganancia cada mes, esta se reinvierte y se agrega de nuevo a la inversion :)
 # Total que se suma cada mes: inversión + ganancia
    if Inversion >0:
        meses=0
        tasa_mes= Ganancia_final/100/12
        acumulado=0
        lista_meses=[]
        lista_acumulado=[]   
        while acumulado < Costo:       
         acumulado=acumulado * (1 +tasa_mes) + Dinero_invertir
         meses +=1
         lista_meses.append(meses)
         lista_acumulado.append(acumulado)
    else:
     print("El % de inversión debe ser mayor a 0")

    print(f" Resultado de la Inversion ")
    print(f" Dinero de la meta: ${Costo:,.2f}")
    print(f" Dinero acumulado: %{acumulado:,.2f}")
    print(f" Te sobraron: ${acumulado - Costo:,.2f}")
    print(f" Te tomo: {meses} meses = {meses/12:.1f} años")  
    print("Salario:", Salario)
    print("Patrimonio:".join(Patrimonio))
    print("Ingreso neto:", Ingreso_neto)
    print("Dinero para Invertir al mes:", round(Dinero_invertir, 2))
    print("Beneficio Mensual aprox:", round(tasa_mes * 100, 2), "%")
    print("Precio Final:", Costo)
if opcion >=3:
  print("Ingresa una opcion valida, ya sea Ahorrar(el 1) o Invertir (el 2)")
