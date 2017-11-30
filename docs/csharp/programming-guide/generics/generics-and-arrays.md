---
title: "Genéricos y matrices (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], arrays
- arrays [C#], generics
ms.assetid: 7d956536-3851-41b5-94ad-3e7c0a5fe485
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 94b144075fac44ff749474a5bfa8e81aaadc0a0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="generics-and-arrays-c-programming-guide"></a>Genéricos y matrices (Guía de programación de C#)
En C# 2.0 y versiones posteriores, las matrices unidimensionales que tienen un límite inferior de cero implementan <xref:System.Collections.Generic.IList%601> automáticamente. Esto le permite crear métodos genéricos que pueden usar el mismo código para recorrer en iteración matrices y otros tipos de colección. Esta técnica es útil principalmente para leer datos en colecciones. La interfaz <xref:System.Collections.Generic.IList%601> no puede usarse para agregar o quitar elementos de una matriz. Se generará una excepción si intenta llamar a un método <xref:System.Collections.Generic.IList%601> como <xref:System.Collections.Generic.IList%601.RemoveAt%2A> en una matriz en este contexto.  
  
 En el siguiente ejemplo de código se muestra cómo un método genérico único que toma un parámetro de entrada <xref:System.Collections.Generic.IList%601> puede recorrer en iteración una lista y una matriz, en este caso una matriz de enteros.  
  
 [!code-csharp[csProgGuideGenerics#35](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-arrays_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Collections.Generic>  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Genéricos](../../../csharp/programming-guide/generics/index.md)  
 [Matrices](../../../csharp/programming-guide/arrays/index.md)  
 [Genéricos](~/docs/standard/generics/index.md)
