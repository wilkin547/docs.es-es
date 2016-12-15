---
title: "Procedimientos gen&#233;ricos en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/08/2016"
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
  - "métodos genéricos"
  - "métodos genéricos, inferencia de tipos"
  - "procedimientos genéricos"
  - "procedimientos genéricos, inferencia de tipos"
  - "genéricos [Visual Basic], procedimientos"
  - "genéricos [Visual Basic], inferencia de tipos"
  - "procedimientos, genéricos"
  - "inferencia de tipos"
  - "inferencia de tipos, genéricos"
ms.assetid: 95577b28-137f-4d5c-a149-919c828600e5
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Procedimientos gen&#233;ricos en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Un *procedimiento genérico*, también denominado *método genérico*, es el que está definido con al menos un parámetro de tipo.  Esto permite que el código de llamada ajuste los tipos de datos a sus requisitos cada vez que llama al procedimiento.  
  
 El simple hecho de estar definido dentro de una clase o estructura genérica no convierte en genérico al procedimiento.  Para ser genérico, el procedimiento debe tomar por lo menos un parámetro de tipo, además de cualquier otro parámetro normal que pueda a tomar.  Una clase o estructura genérica puede contener procedimientos que no sean genéricos; y las clases, estructuras o módulos no genéricos pueden contener procedimientos genéricos.  
  
 Un procedimiento genérico puede utilizar los parámetros de tipo en su lista de parámetros normales, en su tipo de valor devuelto, si existe, y en su código de procedimiento.  
  
## Inferencia de tipo  
 Puede llamar a un procedimiento genérico sin proporcionar ningún argumento de tipo.  Al llamar de este modo, el compilador intenta determinar los tipos de datos adecuados para pasar los argumentos de tipo del procedimiento.  Esto se denomina *inferencia de tipo*.  El código siguiente muestra una llamada en la que el compilador deduce que debe pasar el tipo `String` al parámetro de tipo `t`.  
  
 [!code-vb[VbVbalrDataTypes#15](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_1.vb)]  
  
 Si el compilador no puede deducir los argumentos de tipo del contexto de su llamada, crea un informe de error.  Una posible causa de este tipo de error es la falta de coincidencia del rango de matriz.  Por ejemplo, suponga que define un parámetro normal como matriz de un parámetro de tipo.  Si se llama al procedimiento genérico proporcionando una matriz de distinto rango \(número de dimensiones\), la desigualdad provoca que se produzca un error en la inferencia de tipo.  En el código siguiente se muestra una llamada en la que se pasa una matriz bidimensional a un procedimiento que espera una matriz unidimensional.  
  
 `Public Sub demoSub(Of t)(ByVal arg() As t)`  
  
 `End Sub`  
  
 `Public Sub callDemoSub()`  
  
 `Dim twoDimensions(,) As Integer`  
  
 `demoSub(twoDimensions)`  
  
 `End Sub`  
  
 Sólo se puede invocar la inferencia de tipo omitiendo todos los argumentos de tipo.  Si proporciona alguno, debe proporcionarlos todos.  
  
 La inferencia de tipo sólo se admite para los procedimientos genéricos.  No puede invocar la inferencia de tipo en las clases, estructuras, interfaces o delegados genéricos.  
  
## Ejemplo  
  
### Descripción  
 En el ejemplo siguiente se define un procedimiento genérico `Function` para encontrar un elemento concreto en una matriz.  Se define un parámetro de tipo, que se utiliza para construir los dos parámetros de la lista de parámetros.  
  
### Código  
 [!code-vb[VbVbalrDataTypes#14](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_2.vb)]  
  
### Comentarios  
 Para el ejemplo anterior es necesario poder comparar `searchValue` con cada elemento de `searchArray`.  Para garantizar esta capacidad, se restringe el parámetro de tipo `T` para implementar la interfaz <xref:System.IComparable%601>.  El código utiliza el método <xref:System.IComparable%601.CompareTo%2A>, en lugar del operador `=`, puesto que no existen garantías de que el tipo de argumento proporcionado para `T` admita el operador `=`.  
  
 Puede probar el procedimiento `findElement` con el código siguiente.  
  
 [!code-vb[VbVbalrDataTypes#13](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_3.vb)]  
  
 Las llamadas anteriores a `MsgBox` muestran respectivamente "0", "1" y "\-1."  
  
## Vea también  
 [Tipos genéricos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Cómo: Definir una clase que pueda proporcionar la misma funcionalidad en tipos de datos diferentes](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)   
 [Cómo: Utilizar una clase genérica](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)   
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Lista de tipos](../../../../visual-basic/language-reference/statements/type-list.md)   
 [Lista de parámetros](../../../../visual-basic/language-reference/statements/parameter-list.md)