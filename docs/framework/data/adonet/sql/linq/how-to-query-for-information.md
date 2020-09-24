---
title: Procedimiento para consultar información
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: d45fdfa8b8976e3cdc86b905443bf7bcea578714
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166409"
---
# <a name="how-to-query-for-information"></a>Procedimiento para consultar información

Las consultas de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] usan la misma sintaxis que las consultas de Linq. La única diferencia es que los objetos a los que se hace referencia en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] las consultas se asignan a los elementos de una base de datos. Para obtener más información, vea [Introducción a las consultas LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] convierte las consultas que se escriben en consultas SQL equivalentes y las envía al servidor para su procesamiento.  
  
 Algunas características de las consultas LINQ pueden necesitar especial atención en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] las aplicaciones. Para obtener más información, vea [conceptos de consultas](query-concepts.md).  
  
## <a name="example"></a>Ejemplo  

 La consulta siguiente solicita una lista de clientes de Londres. En este ejemplo, `Customers` es una tabla de la base de datos de ejemplo Northwind.  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>Consulte también

- [Crear el modelo de objetos](creating-the-object-model.md)
- [Descargar bases de datos de ejemplo](downloading-sample-databases.md)
- [Consultar la base de datos](querying-the-database.md)
