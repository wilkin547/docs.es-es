---
title: Consultas de agregado
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 13ec5580-05ce-4a1f-9d3d-8660be7891a2
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: cb1f26ec1fb8e5344946938206bb2418eeb6cd2d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="aggregate-queries"></a>Consultas de agregado
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite los operadores de agregado `Average`, `Count`, `Max`, `Min` y `Sum`. Tener en cuenta las características siguientes de los operadores de agregado en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:  
  
-   Las consultas de funciones agregadas se ejecutan inmediatamente.  
  
     Para obtener más información, vea [Introduction to LINQ queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md) [Introducción a las consultas LINQ (C#)].  
  
-   Las consultas de funciones agregadas normalmente devuelven un número en lugar de una colección.  
  
     Para obtener más información, consulte [operaciones de agregación](http://msdn.microsoft.com/library/36d97c83-5de5-457d-971d-10a69365e7c4).  
  
-   No se puede llamar a funciones de agregado en tipos anónimos.  
  
 Los ejemplos de los temas siguientes se derivan de la base de datos de ejemplo Northwind. Para obtener más información, consulte [descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [Devolver el valor medio de una secuencia numérica](../../../../../../docs/framework/data/adonet/sql/linq/return-the-average-value-from-a-numeric-sequence.md)  
 Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Average%2A>.  
  
 [Contar el número de elementos de una secuencia](../../../../../../docs/framework/data/adonet/sql/linq/count-the-number-of-elements-in-a-sequence.md)  
 Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Count%2A>.  
  
 [Buscar el valor máximo de una secuencia numérica](../../../../../../docs/framework/data/adonet/sql/linq/find-the-maximum-value-in-a-numeric-sequence.md)  
 Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Max%2A>.  
  
 [Buscar el valor mínimo de una secuencia numérica](../../../../../../docs/framework/data/adonet/sql/linq/find-the-minimum-value-in-a-numeric-sequence.md)  
 Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Min%2A>.  
  
 [Calcular la suma de los valores de una secuencia numérica](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)  
 Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Sum%2A>.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Ejemplos de consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 Proporciona vínculos a consultas [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] en Visual Basic y C#.  
  
 [Conceptos sobre consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 Proporciona vínculos a temas donde se explican los conceptos del diseño de consultas [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Introducción a las consultas LINQ (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 Explica cómo funcionan las consultas en [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].
