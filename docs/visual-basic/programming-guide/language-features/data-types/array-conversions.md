---
title: "Conversi&#243;n de matrices (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "matrices [Visual Basic], convertir un tipo"
  - "matrices [Visual Basic], tipos de datos"
  - "conversiones, tipos de matriz"
  - "conversiones, tipo de datos"
  - "conversiones, tipo"
  - "conversión de tipos de datos, conversiones de matrices"
  - "matrices de objetos"
  - "matrices de objetos, convertir un tipo"
  - "conversión de tipos, matrices"
ms.assetid: fceff7d2-a1b7-44c7-b9aa-8bd831d8a444
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Conversi&#243;n de matrices (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Puede convertir un tipo de matriz en otro tipo de matriz diferente, siempre que se cumplan las condiciones siguientes:  
  
-   **Rango igual.** Los rangos de las dos matrices deben ser los mismos; es decir, deben tener las mismas dimensiones.  Sin embargo, las longitudes de las dimensiones respectivas no tienen que ser necesariamente iguales.  
  
-   **Tipo de datos de elementos.** Los tipos de datos de los elementos de ambas matrices deben ser tipos de referencia.  No se puede convertir una matriz `Integer` en una matriz `Long`, ni siquiera en una matriz `Object`, ya que hay al menos un tipo de valor implicado.  Para obtener más información, vea [Tipos de valor y tipos de referencia](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
-   **Convertibilidad.** Una conversión, ya sea de ampliación o de restricción, debe poder realizarse entre los tipos de elementos de las dos matrices.  Un ejemplo en el que se incumple este requisito es una conversión intentada entre una matriz `String` y una matriz de una clase derivada de <xref:System.Attribute?displayProperty=fullName>.  Estos dos tipos no tienen nada en común y no existe ningún tipo de conversión entre ellos.  
  
 Una conversión de un tipo de matriz en otro será de ampliación o de restricción en función de si la conversión de los respectivos elementos es de ampliación o de restricción.  Para obtener más información, vea [Conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
## Conversión en una matriz de objeto  
 Al declarar una matriz `Object` sin inicializarla, su tipo de elemento es `Object` mientras permanezca sin inicializar.  Cuando se establece una matriz de una clase específica, adopta el tipo de la clase.  Sin embargo, su tipo subyacente continúa siendo `Object` y es posible establecerlo más tarde en otra matriz de una clase no relacionada.  Dado que todas las clases derivan de `Object`, es posible cambiar el tipo de elemento de la matriz de una clase cualquiera a otra.  
  
 En el ejemplo siguiente, no existe ninguna conversión entre los tipos `student` y `String`, pero ambos derivan de `Object`, así que todas las asignaciones son válidas.  
  
```  
' Assume student has already been defined as a class.  
Dim testArray() As Object  
' testArray is still an Object array at this point.  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
testArray = New student(3) {}  
' testArray is now of type student().  
testArray = names  
' testArray is now a String array.  
```  
  
### Tipo subyacente de una matriz  
 Si declara originalmente una matriz con una clase específica, su tipo de elemento subyacente será esa clase.  Si más tarde la establece en una matriz de otra clase, deberá haber una conversión entre las dos clases.  
  
 En el ejemplo siguiente, `students` es una matriz `student`.  Puesto que no existe ninguna conversión entre `String` y `student`, en la última instrucción se producirá un error.  
  
```  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## Vea también  
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Conversiones implícitas y explícitas](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Conversiones entre cadenas y otros tipos](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)   
 [Cómo: Convertir un objeto en otro tipo en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)   
 [Tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Funciones de conversión de tipos](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md)