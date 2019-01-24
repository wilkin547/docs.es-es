---
title: Introducción
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
ms.openlocfilehash: 7ddecf910b5f76fdb5e75300118fa0a063269116
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556407"
---
# <a name="getting-started"></a>Introducción
Mediante el uso de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], puede usar el [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] tecnología para acceder a SQL las bases de datos como para acceder a una colección en memoria.  
  
 Por ejemplo, en el código siguiente, se crea el objeto `nw` para representar la base de datos `Northwind`, el destino es la tabla `Customers`, las filas se filtran para `Customers` de `London` y se selecciona para la recuperación una cadena de `CompanyName`.  
  
 Cuando se ejecuta el bucle, se recupera la colección de valores `CompanyName`.  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="next-steps"></a>Pasos siguientes  
 Para ver algunos ejemplos adicionales, incluida la inserción y actualización, [lo que puede hacer con LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/what-you-can-do-with-linq-to-sql.md).  
  
 Luego, intente realizar algunos tutoriales para obtener experiencia práctica en el uso de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Consulte [aprender con tutoriales](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).  
  
 Por último, obtenga información sobre cómo empezar a trabajar en su propio [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proyecto leyendo [pasos habituales para usar LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md).  
  
## <a name="see-also"></a>Vea también
- [LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/index.md)
- [Introducción a LINQ](https://msdn.microsoft.com/library/24dddf19-12a0-4707-a4bc-eba4fa7f219e)
- [Modelo de objetos de LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
