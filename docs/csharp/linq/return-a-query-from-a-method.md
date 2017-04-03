---
title: "Devolver una consulta de un método"
description: "Cómo devolver una consulta."
keywords: .NET, .NET Core, C#
author: stevehoag
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: db220f79-c35b-41f2-886c-cd068672d42d
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 0a83e3cc0e131351ef581fc15c68a3d0fda2bcce
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-return-a-query-from-a-method-c-programming-guide"></a>Cómo: Devolver una consulta desde un método (Guía de programación de C#)
En este ejemplo se muestra cómo devolver una consulta desde un método como un valor devuelto y como un parámetro `out`.  
  
 Los objetos de consulta admiten composición, lo que significa que puede devolver una consulta desde un método. Los objetos que representan consultas no almacenan la colección resultante, sino los pasos para generar los resultados cuando sea necesario. La ventaja de devolver objetos de consulta desde métodos es que se pueden componer o modificar todavía más. Por lo tanto, cualquier valor devuelto o parámetro `out` de un método que devuelve una consulta también debe tener ese tipo. Si un método materializa una consulta en un tipo concreto <xref:System.Collections.Generic.List%601> o <xref:System.Array>, se considera que está devolviendo los resultados de la consulta en lugar de la propia consulta. Una variable de consulta que se devuelve desde un método sigue pudiendo componerse o modificarse.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, el primer método devuelve una consulta como un valor devuelto y el segundo método devuelve una consulta como un parámetro `out`. Tenga en cuenta que, en ambos casos, se trata de una consulta que se devuelve, no de los resultados de la consulta.  
  
 [!code-cs[csProgGuideLINQ#80](../../../samples/snippets/csharp/concepts/linq/how-to-return-a-query-from-a-method_1.cs)]  

## <a name="see-also"></a>Vea también  
 [Expresiones de consulta LINQ](index.md)
