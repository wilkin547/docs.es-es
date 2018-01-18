---
title: "Cómo: Especificar tipos de datos de base de datos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2228fdad-7e6a-4b1b-b4d1-79d0198b7c28
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 17ac588a8cf6815b244cf0b515603263f41b53ad
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-specify-database-data-types"></a>Cómo: Especificar tipos de datos de base de datos
Use la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> propiedad en un <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para especificar el texto exacto que define la columna en una declaración de tabla de T-SQL.  
  
 Debe especificar la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> sólo si piensa utilizar <xref:System.Data.Linq.DataContext.CreateDatabase%2A> para crear una instancia de la base de datos.  
  
 Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.  
  
### <a name="to-specify-text-to-define-a-data-type-in-a-t-sql-table"></a>Para especificar texto para definir un tipo de datos en una tabla T-SQL  
  
1.  Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2.  Establezca el valor de la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> en el texto exacto que T-SQL utiliza.  
  
## <a name="see-also"></a>Vea también  
 [Modelo de objetos de LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [Personalización de clases de entidades con el editor de código](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
