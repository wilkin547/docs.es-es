---
title: "Pasar matrices como argumentos (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "matrices [C#], pasar como argumentos"
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# Pasar matrices como argumentos (Gu&#237;a de programaci&#243;n de C#)
Las matrices se pueden pasar como argumentos a los parámetros de método.  Dado que las matrices son tipos de referencia, el método puede cambiar el valor de los elementos.  
  
## Pasar matrices unidimensionales como argumentos  
 Una matriz unidimensional inicializada se puede pasar a un método.  Por ejemplo, la siguiente instrucción envía una matriz a un método de impresión.  
  
 [!code-cs[csProgGuideArrays#34](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_1.cs)]  
  
 El código siguiente muestra una implementación parcial del método de impresión.  
  
 [!code-cs[csProgGuideArrays#33](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_2.cs)]  
  
 Puede inicializar y pasar una nueva matriz en un solo paso, como se muestra en el siguiente ejemplo.  
  
 [!code-cs[CsProgGuideArrays#35](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_3.cs)]  
  
## Ejemplo  
  
### Descripción  
 En el ejemplo siguiente, se inicializa una matriz de cadenas y se pasa como argumento a un método `PrintArray` para las cadenas.  El método muestra los elementos de la matriz.  A continuación, se invocan los métodos `ChangeArray` y `ChangeArrayElement` para mostrar que el envío de un argumento de matriz por valor no evita que se realicen cambios en los elementos de la matriz.  
  
### Código  
 [!code-cs[csProgGuideArrays#30](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_4.cs)]  
  
## Pasar matrices multidimensionales como argumentos  
 Una matriz multidimensional inicializada se pasa a un método del mismo modo que una matriz unidimensional.  
  
 [!code-cs[csProgGuideArrays#41](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_5.cs)]  
  
 En el código siguiente se muestra una declaración parcial de un método de impresión que acepta una matriz bidimensional como argumento.  
  
 [!code-cs[csProgGuideArrays#36](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_6.cs)]  
  
 Puede inicializar y pasar una nueva matriz en un solo paso, como se muestra en el siguiente ejemplo.  
  
 [!code-cs[csProgGuideArrays#32](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_7.cs)]  
  
## Ejemplo  
  
### Descripción  
 En el ejemplo siguiente, se inicializa una matriz de enteros bidimensional y se pasa al método `Print2DArray`.  El método muestra los elementos de la matriz.  
  
### Código  
 [!code-cs[csProgGuideArrays#31](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_8.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Matrices](../../../csharp/programming-guide/arrays/index.md)   
 [Matrices unidimensionales](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [Matrices multidimensionales](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [Matrices escalonadas](../../../csharp/programming-guide/arrays/jagged-arrays.md)