---
title: "Utilizar matrices como objetos (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "matrices [C#], como objetos"
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Utilizar matrices como objetos (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

En C\#, las matrices son de hecho objetos y no simplemente regiones direccionables de memoria contigua como ocurre en C y C\+\+.  <xref:System.Array> es el tipo base abstracto de todos los tipos de matrices.  Las propiedades y otros miembros de la clase <xref:System.Array> se pueden utilizar cuando sea necesario.  Un ejemplo de esto sería utilizar la propiedad <xref:System.Array.Length%2A>para obtener la longitud de una matriz.  El siguiente código asigna la longitud de la matriz `numbers`, que es `5`, a una variable denominada `lengthOfNumbers`:  
  
 [!code-cs[csProgGuideArrays#3](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_1.cs)]  
  
 La clase <xref:System.Array> proporciona muchos otros métodos y propiedades útiles para ordenar, buscar y copiar matrices.  
  
## Ejemplo  
 En este ejemplo se utiliza la propiedad <xref:System.Array.Rank%2A> para mostrar el número de dimensiones de una matriz.  
  
 [!code-cs[csProgGuideArrays#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_2.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Matrices](../../../csharp/programming-guide/arrays/index.md)   
 [Matrices unidimensionales](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [Matrices multidimensionales](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [Matrices escalonadas](../../../csharp/programming-guide/arrays/jagged-arrays.md)