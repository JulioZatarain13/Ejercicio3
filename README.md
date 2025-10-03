# Ejercicio3
Ejercicio 3  Reestructuración de JSON


# Descripción
Este Sistema hace una reestructuracion de los datos recibidos mediante JSON para crear un nuevo JSON de salida con los mismos datos recibidos pero con una diferente estructura

-Proceso
  -Validar si el JSON recibido es nulo
  -Inicializar variables
  -Mapear Dato unico de la orden (orden.id -> orderId)
  -Combinar datos del nombre del cliente (cliente.nombre + cliente.apellido -> customerName)
  -Mapear total de la orden (order.monto -> total)
  -Retornar el Resultado

## Analisis de Complejidad
- Temporal
    - Procesamiento de datos
    - Acceso a propiedas y el concateamiento de algunos datos
-Espacial
  -Objeto nuevo con 3 propiedades
  -No depede el tamaño de entrada
-Si el JSON es muy grande:
  -Procesamiento pro lotes
  -Stream Processing para evitar una carga mayor en la memoria
  -Uso de bibliotecas eficientes

##Casis de Prueba
** Caso 1
  {
    "cliente" : {"nombre": "Julio", "apellido": "Zatarain"},
    "orden": {"id": 1 ,"monto": 777 }
  }

  Salida esperada: 
  {
    "orderId": 1,
    "customerName": "Julio Zatarain",
    "total": 777
  }

** Caso 2
  {
    "cliente" : {"nombre": "Julio"},
    "orden": {"id": 1 ,"monto": 777 }
  }

  Salida esperada: 
  {
    "orderId": 1,
    "customerName": "Julio",
    "total": 777
  }
