---
title: Consultas de agregado
ms.date: 03/30/2017
ms.assetid: 13ec5580-05ce-4a1f-9d3d-8660be7891a2
ms.openlocfilehash: e4d5e0a9dc1ffb0bf1857fee788d46947f3901d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358848"
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
 [Devolución del valor medio de una secuencia numérica](../../../../../../docs/framework/data/adonet/sql/linq/return-the-average-value-from-a-numeric-sequence.md)  
 Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Average%2A>.  
  
 [Conteo del número de elementos de una secuencia](../../../../../../docs/framework/data/adonet/sql/linq/count-the-number-of-elements-in-a-sequence.md)  
 Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Count%2A>.  
  
 [Búsqueda del valor máximo de una secuencia numérica](../../../../../../docs/framework/data/adonet/sql/linq/find-the-maximum-value-in-a-numeric-sequence.md)  
 Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Max%2A>.  
  
 [Búsqueda del valor mínimo de una secuencia numérica](../../../../../../docs/framework/data/adonet/sql/linq/find-the-minimum-value-in-a-numeric-sequence.md)  
 Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Min%2A>.  
  
 [Cálculo de la suma de valores de una secuencia numérica](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)  
 Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Sum%2A>.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Ejemplos de consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 Proporciona vínculos a consultas [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] en Visual Basic y C#.  
  
 [Conceptos sobre consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 Proporciona vínculos a temas donde se explican los conceptos del diseño de consultas [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Introducción a las consultas LINQ (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 Explica cómo funcionan las consultas en [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].
