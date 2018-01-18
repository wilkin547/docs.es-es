---
title: "Cómo: Representar columnas como columnas que permiten valores null"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ebb71a37-1f4c-4fa7-b2d2-d903f13c4af1
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 509c0554c6ce2bd02f1294fe19b1138241864ca9
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-represent-columns-as-allowing-null-values"></a>Cómo: Representar columnas como columnas que permiten valores null
Use la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> propiedad en el <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para especificar que la columna de base de datos asociada puede contener valores null.  
  
 Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.  
  
### <a name="to-designate-a-column-as-allowing-null-values"></a>Para designar que una columna permite valores nulos  
  
1.  Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2.  Establezca el valor de propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> en `true`.  
  
## <a name="see-also"></a>Vea también  
 [Modelo de objetos de LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [Personalización de clases de entidades con el editor de código](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
