---
title: "C&#243;mo: Ordenar una matriz en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "Array.Sort"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "matrices [Visual Basic], ordenar"
  - "ejemplos [Visual Basic], matrices"
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# C&#243;mo: Ordenar una matriz en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

En el siguiente ejemplo se declara una matriz de objetos `String` denominada `zooAnimals`, se llena y se ordena alfabéticamente.  
  
## Ejemplo  
  
```  
Private Sub sortAnimals()  
    Dim zooAnimals(2) As String  
    zooAnimals(0) = "lion"  
    zooAnimals(1) = "turtle"  
    zooAnimals(2) = "ostrich"  
    Array.Sort(zooAnimals)  
End Sub  
```  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Obtener acceso a Mscorlib.dll y al espacio de nombres <xref:System>.  
  
## Programación eficaz  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   La matriz está vacía \(clase <xref:System.ArgumentNullException>\)  
  
-   La matriz es multidimensional \(clase <xref:System.RankException>\)  
  
-   Uno o más elementos de la matriz no implementan la interfaz <xref:System.IComparable> \(clase <xref:System.InvalidOperationException>\).  
  
## Vea también  
 <xref:System.Array.Sort%2A?displayProperty=fullName>   
 [Matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Solucionar problemas de matrices](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)   
 [Colecciones](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)   
 [For Each...Next \(Instrucción\)](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)