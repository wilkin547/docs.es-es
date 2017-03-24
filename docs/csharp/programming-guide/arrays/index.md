---
title: "Matrices (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "matrices [C#]"
  - "lenguaje C#, matrices"
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
caps.latest.revision: 33
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 33
---
# Matrices (Gu&#237;a de programaci&#243;n de C#)
Puede almacenar distintas variables del mismo tipo en una estructura de datos de matriz.  Para declarar una matriz especifique el tipo de sus elementos.  
  
 `type[] arrayName;`  
  
 Los ejemplos siguientes crean matrices unidimensionales, multidimensionales y escalonadas:  
  
 [!code-cs[csProgGuideArrays#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/index_1.cs)]  
  
## Información general sobre las matrices  
 Una matriz tiene las propiedades siguientes:  
  
-   Una matriz puede ser [unidimensional](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md), [multidimensional](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) o [escalonada](../../../csharp/programming-guide/arrays/jagged-arrays.md).  
  
-   El número de dimensiones y la longitud de cada dimensión se establecen cuando se crea la instancia de la matriz.  Estos valores no se pueden cambiar durante la duración de la instancia.  
  
-   Los valores predeterminado de los elementos numéricos de matriz se establece en cero y el de los elementos de referencia se establece en null.  
  
-   Una matriz escalonada es una matriz de matrices y por consiguiente sus elementos son tipos de referencia y se inicializan en `null`.  
  
-   Las matrices se indizan basadas en cero: una matriz con `n` elementos se indiza desde `0` hasta `n-1`.  
  
-   Los elementos de una matriz pueden ser de cualquier tipo, incluido el tipo matriz.  
  
-   Los tipos de matriz son [tipos de referencia](../../../csharp/language-reference/keywords/reference-types.md) derivados del tipo base abstracto <xref:System.Array>.  Puesto que este tipo implementa <xref:System.Collections.IEnumerable> e <xref:System.Collections.Generic.IEnumerable%601>, puede utilizar la iteración [foreach](../../../csharp/language-reference/keywords/foreach-in.md) en todas las matrices de C\#.  
  
## Secciones relacionadas  
  
-   [Utilizar matrices como objetos](../../../csharp/programming-guide/arrays/arrays-as-objects.md)  
  
-   [Utilizar foreach con matrices](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
-   [Pasar matrices como argumentos](../../../csharp/programming-guide/arrays/passing-arrays-as-arguments.md)  
  
-   [Pasar matrices mediante Ref y Out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)  
  
-   [Más información sobre variables](http://go.microsoft.com/fwlink/?LinkId=221230) en [Comenzar a usar Visual C\# 2010](http://go.microsoft.com/fwlink/?LinkId=221214)  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Colecciones](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)   
 [Array Collection Type](http://msdn.microsoft.com/es-es/8a9964de-8941-47b1-a3cf-a01bc88db9e8)