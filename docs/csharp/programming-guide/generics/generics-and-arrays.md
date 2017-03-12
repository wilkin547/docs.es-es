---
title: "Gen&#233;ricos y matrices (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "matrices [C#], genéricos"
  - "genéricos [C#], matrices"
ms.assetid: 7d956536-3851-41b5-94ad-3e7c0a5fe485
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# Gen&#233;ricos y matrices (Gu&#237;a de programaci&#243;n de C#)
En C\# 2.0 y versiones posteriores, las matrices unidimensionales que tienen un límite inferior de cero implementan automáticamente <xref:System.Collections.Generic.IList%601>.  Esto permite crear métodos genéricos que pueden utilizar el mismo código para recorrer en iteración matrices y otros tipos de colecciones.  Esta técnica resulta útil principalmente para leer datos de colecciones.  La interfaz <xref:System.Collections.Generic.IList%601> no puede utilizarse para agregar o quitar elementos en una matriz.  Se producirá una excepción si intenta llamar a un método <xref:System.Collections.Generic.IList%601>, como <xref:System.Collections.Generic.IList%601.RemoveAt%2A>, en una matriz en este contexto.  
  
 El siguiente ejemplo de código muestra la forma en que un solo método genérico que toma un parámetro de entrada <xref:System.Collections.Generic.IList%601> puede recorrer en iteración tanto una lista como una matriz; en este caso, una matriz de enteros.  
  
 [!code-cs[csProgGuideGenerics#35](../../../csharp/programming-guide/generics/codesnippet/csharp/generics-and-arrays_1.cs)]  
  
## Vea también  
 <xref:System.Collections.Generic>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Genéricos](../../../csharp/programming-guide/generics/index.md)   
 [Matrices](../../../csharp/programming-guide/arrays/index.md)   
 [Genéricos](../Topic/Generics%20in%20the%20.NET%20Framework.md)