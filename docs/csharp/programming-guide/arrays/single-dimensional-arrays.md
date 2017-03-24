---
title: "Matrices unidimensionales (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "matrices [C#], unidimensionales"
  - "matrices unidimensionales [C#]"
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# Matrices unidimensionales (Gu&#237;a de programaci&#243;n de C#)
Puede declarar una matriz unidimensional de cinco enteros como se muestra en el ejemplo siguiente:  
  
 [!code-cs[csProgGuideArrays#4](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_1.cs)]  
  
 Esta matriz contiene elementos desde `array[0]` hasta `array[4]`.  El operador [new](../../../csharp/language-reference/keywords/new.md) se utiliza para crear la matriz e inicializar sus elementos con valores predeterminados.  En este ejemplo, todos los elementos de la matriz se inicializan con cero.  
  
 Una matriz que almacena elementos de cadena se puede declarar del mismo modo.  Por ejemplo:  
  
 [!code-cs[csProgGuideArrays#5](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_2.cs)]  
  
## Inicialización de matrices  
 Es posible inicializar una matriz en el momento de su declaración, en cuyo caso, no es necesario el especificador de rango ya que éste viene dado por el número de elementos de la lista de inicialización.  Por ejemplo:  
  
 [!code-cs[csProgGuideArrays#6](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_3.cs)]  
  
 Una matriz de cadena se puede inicializar del mismo modo.  A continuación, se muestra una declaración de una matriz de cadena en la que cada elemento de la matriz se inicializa con el nombre de un día de la semana:  
  
 [!code-cs[csProgGuideArrays#7](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_4.cs)]  
  
 Cuando inicializa una matriz en el momento de su declaración, puede utilizar los siguientes métodos abreviados:  
  
 [!code-cs[csProgGuideArrays#8](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_5.cs)]  
  
 Es posible declarar una variable de matriz sin inicializarla, pero se debe utilizar el operador `new` al asignar una matriz a esta variable.  Por ejemplo:  
  
 [!code-cs[csProgGuideArrays#9](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_6.cs)]  
  
 C\# 3.0 presenta matrices con tipo implícito.  Para obtener más información, vea [Matrices con tipo implícito](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).  
  
## Matrices de tipo de valor y tipo de referencia  
 Considere la siguiente declaración de matriz:  
  
 [!code-cs[csProgGuideArrays#10](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_7.cs)]  
  
 El resultado de esta instrucción depende de si `SomeType` es un tipo de valor o un tipo de referencia.  Si es un tipo de valor, la instrucción crea una matriz de 10 elementos, cada una de las cuales tiene el tipo `SomeType`.  Si `SomeType` es un tipo de referencia, la instrucción crea una matriz de 10 elementos, cada uno de los cuales se inicializa con una referencia nula.  
  
 Para obtener más información sobre tipos de referencia y de valor, vea [Tipos](../../../csharp/language-reference/keywords/types.md).  
  
## Vea también  
 <xref:System.Array>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Matrices](../../../csharp/programming-guide/arrays/index.md)   
 [Matrices multidimensionales](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [Matrices escalonadas](../../../csharp/programming-guide/arrays/jagged-arrays.md)