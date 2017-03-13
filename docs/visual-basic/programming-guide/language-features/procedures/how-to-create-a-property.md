---
title: "C&#243;mo: Crear una propiedad (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "procedimientos, definir"
  - "propiedades [Visual Basic]"
  - "código de Visual Basic, procedimientos"
  - "código de Visual Basic, propiedades"
ms.assetid: 4d229712-6be8-4c5c-bac5-06995ce9185a
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# C&#243;mo: Crear una propiedad (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Una definición de propiedad se agrega entre una instrucción `Property` y una instrucción `End Property` Dentro de esta definición, se define un procedimiento `Get`, un procedimiento `Set` o ambos.  Todo el código de la propiedad está incluido dentro de estos procedimientos.  
  
 El procedimiento `Get` recupera el valor de la propiedad y el procedimiento `Set` almacena un valor.  Si desea que la propiedad tenga acceso de lectura y escritura, debe definir ambos procedimientos.  Para una propiedad de sólo lectura, se define únicamente `Get` y para una propiedad de sólo escritura, `Set`.  
  
### Para crear una propiedad  
  
1.  Fuera de cualquier propiedad o procedimiento, utilice [Property \(Instrucción\)](../../../../visual-basic/language-reference/statements/property-statement.md), seguido de una instrucción `End Property`.  
  
2.  Si la propiedad acepta parámetros, agregue detrás de la palabra clave `Property` el nombre del procedimiento y, a continuación, la lista de parámetros entre paréntesis.  
  
3.  Agregue detrás de los paréntesis una cláusula `As` para especificar el tipo de datos del valor de la propiedad.  Debe especificar el tipo de datos incluso para una propiedad de sólo escritura.  
  
4.  Agregue los procedimientos `Get` y `Set`, tal como sea preciso.  Vea las direcciones siguientes.  
  
### Para crear un procedimiento Get que recupera un valor de propiedad  
  
1.  Entre las instrucciones `Property` y `End Property`, escriba [Get \(Instrucción\)](../../../../visual-basic/language-reference/statements/get-statement.md), seguido de una instrucción `End Get`.  No necesita definir ningún parámetro para el procedimiento `Get`.  
  
2.  Coloque las instrucciones de código para recuperar el valor de la propiedad entre las instrucciones `Get` y `End Get` Este código puede incluir otros cálculos y manipulaciones de datos, además de generar y devolver el valor de la propiedad.  
  
3.  Utilice una instrucción `Return` para devolver el valor de la propiedad al código de llamada.  
  
 Debe escribir un procedimiento `Get` para una propiedad de lectura y escritura, así como para una propiedad de sólo lectura.  No debe definir un procedimiento `Get` para una propiedad de sólo escritura.  
  
### Para crear un procedimiento Set que escribe el valor de una propiedad  
  
1.  Entre las instrucciones `Property` y `End Property`, escriba [Set \(Instrucción\)](../../../../visual-basic/language-reference/statements/set-statement.md), seguido de una instrucción `End Set`.  
  
2.  En la instrucción `Set`, agregue detrás de la palabra clave `Set` una lista de parámetros entre paréntesis.  Esta lista de parámetros debe incluir por lo menos un parámetro de valor para el valor pasado por el código de llamada.  El nombre predeterminado para este parámetro de valor es `Value`, pero puede utilizar un nombre diferente, si es preciso.  El parámetro de valor debe tener el mismo tipo de datos que la propiedad misma.  
  
3.  Coloque las instrucciones de código para almacenar la propiedad entre las instrucciones `Set` y `End Set` Este código puede incluir otros cálculos y manipulaciones de datos, además de validar y almacenar el valor de la propiedad.  
  
4.  Utilice el parámetro de valor para aceptar el valor proporcionado por el código de llamada.  Puede almacenar este valor directamente en una instrucción de asignación o utilizarlo en una expresión para calcular el valor interno que se va a almacenar.  
  
 Debe escribir un procedimiento `Set` para una propiedad de lectura y escritura, así como para una propiedad de sólo escritura.  No debe definir un procedimiento `Set` para una propiedad de sólo lectura.  
  
## Ejemplo  
 El ejemplo siguiente crea una propiedad de lectura y escritura que almacena un nombre completo como dos nombres constitutivos, el nombre y el apellido.  Cuando el código de llamada lee `fullName`, el procedimiento `Get` combina los dos nombres constitutivos y devuelve el nombre completo.  Cuando el código de llamada asigna un nuevo nombre completo, el procedimiento `Set` intenta dividirlo en dos nombres constitutivos.  Si no encuentra espacio, lo almacena como nombre.  
  
 [!code-vb[VbVbcnProcedures#8](./codesnippet/VisualBasic/how-to-create-a-property_1.vb)]  
  
 El ejemplo siguiente muestra las llamadas típicas a los procedimientos de propiedad de `fullName`.  La primera llamada establece el valor de propiedad y la segunda la recupera.  
  
 [!code-vb[VbVbcnProcedures#9](./codesnippet/VisualBasic/how-to-create-a-property_2.vb)]  
  
## Vea también  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedimientos de propiedad](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Diferencias entre propiedades y variables en Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [Cómo: Declarar una propiedad con niveles de acceso mixtos](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)   
 [Cómo: Llamar a un procedimiento de propiedad](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-property-procedure.md)   
 [Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)   
 [Cómo: Establecer un valor en una propiedad](../../../../visual-basic/programming-guide/language-features/procedures/how-to-put-a-value-in-a-property.md)   
 [Cómo: Obtener un valor de una propiedad](../../../../visual-basic/programming-guide/language-features/procedures/how-to-get-a-value-from-a-property.md)