---
title: "Cómo: Representar columnas como miembros de clase"
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
ms.assetid: 7ab28021-4d15-4d9c-bf2e-6ccc0daa7d1a
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 31344d69df3db78303752e201a9aab84048d4ea1
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-represent-columns-as-class-members"></a>Cómo: Representar columnas como miembros de clase
Use la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para asociar una columna de base de datos en un campo o propiedad.  
  
### <a name="to-map-a-field-or-property-to-a-database-column"></a>Para asignar un campo o una propiedad a una columna de base de datos  
  
-   Agregue el atributo <xref:System.Data.Linq.Mapping.ColumnAttribute> a la propiedad o declaración de campo.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente asigna el campo `CustomerID` de la clase `Customer` a la columna `CustomerID` de la tabla de base de datos `Customers`.  
  
 [!code-csharp[DLinqCustomize#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#2)]
 [!code-vb[DLinqCustomize#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#2)]  
  
 No tiene que especificar la propiedad <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> si se puede deducir el nombre. Si no especifica ningún nombre, se supone que es el mismo que el de la propiedad o campo.  
  
## <a name="see-also"></a>Vea también  
 [Modelo de objetos de LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [Personalización de clases de entidades con el editor de código](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
