---
title: "Cómo: Representar columnas como columnas generadas por la base de datos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a404451b1dca085707d05d1db54047cd0db0c986
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-represent-columns-as-database-generated"></a>Cómo: Representar columnas como columnas generadas por la base de datos
Use la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> propiedad en el <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para designar un campo o propiedad representa una columna generada por base de datos.  
  
 Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a>Para designar que un campo o propiedad representa una columna generada por base de datos  
  
1.  Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2.  Establezca el valor de propiedad en `true`.  
  
## <a name="see-also"></a>Vea también  
 [Modelo de objetos de LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [Personalización de clases de entidades con el editor de código](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
