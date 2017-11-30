---
title: "Devolver una consulta de un método"
description: "Cómo devolver una consulta."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: db220f79-c35b-41f2-886c-cd068672d42d
ms.openlocfilehash: c1b69e3f5f0cd2c50ae80d2454e6b7f13dc30344
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2017
---
# <a name="how-to-return-a-query-from-a-method-c-programming-guide"></a>Cómo: Devolver una consulta desde un método (Guía de programación de C#)
En este ejemplo se muestra cómo devolver una consulta desde un método como un valor devuelto y como un parámetro `out`.  
  
 Los objetos de consulta admiten composición, lo que significa que puede devolver una consulta desde un método. Los objetos que representan consultas no almacenan la colección resultante, sino los pasos para generar los resultados cuando sea necesario. La ventaja de devolver objetos de consulta desde métodos es que se pueden componer o modificar todavía más. Por lo tanto, cualquier valor devuelto o parámetro `out` de un método que devuelve una consulta también debe tener ese tipo. Si un método materializa una consulta en un tipo concreto <xref:System.Collections.Generic.List%601> o <xref:System.Array>, se considera que está devolviendo los resultados de la consulta en lugar de la propia consulta. Una variable de consulta que se devuelve desde un método sigue pudiendo componerse o modificarse.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, el primer método devuelve una consulta como un valor devuelto y el segundo método devuelve una consulta como un parámetro `out`. Tenga en cuenta que, en ambos casos, se trata de una consulta que se devuelve, no de los resultados de la consulta.  
  
 [!code-csharp[csProgGuideLINQ#80](../../../samples/snippets/csharp/concepts/linq/how-to-return-a-query-from-a-method_1.cs)]  

## <a name="see-also"></a>Vea también  
 [Expresiones de consulta LINQ](index.md)
