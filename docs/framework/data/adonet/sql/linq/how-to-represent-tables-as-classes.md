---
title: "Cómo: Representar tablas como clases"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 84dda12b-88a2-4cd2-92b3-8db87b28d14c
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 27e3d21e42dbf841768e2a68ccbfff62368500bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-represent-tables-as-classes"></a>Cómo: Representar tablas como clases
Use la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> atributo para designar una clase como una clase de entidad asociada a una tabla de base de datos.  
  
### <a name="to-map-a-class-to-a-database-table"></a>Para asignar una clase a una tabla de base de datos  
  
-   Agregue el atributo <xref:System.Data.Linq.Mapping.TableAttribute> a la declaración de la clase.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente establece la clase `Customer` como una clase de entidad que está asociada a la tabla de base de datos `Customers`.  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 No tiene que especificar la propiedad <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> si se puede deducir el nombre. Si no especifica ningún nombre, se supone que es el mismo que el de la propiedad o campo.  
  
## <a name="see-also"></a>Vea también  
 [Modelo de objetos de LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [Personalización de clases de entidades con el editor de código](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
