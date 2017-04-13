---
title: "C&#243;mo: Representar columnas como columnas de marca de tiempo o versi&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5afd5ce8-1d20-4bc3-a34f-49d95449f493
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# C&#243;mo: Representar columnas como columnas de marca de tiempo o versi&#243;n
Utilice la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] en el atributo <xref:System.Data.Linq.Mapping.ColumnAttribute> para designar que un campo o propiedad representa una columna de base de datos que contiene marcas de tiempo o números de versión de base de datos.  
  
 Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.  
  
### Para designar que un campo o propiedad representa una columna de marca de tiempo o versión  
  
1.  Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2.  Establezca el valor de propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> en `true`.  
  
## Vea también  
 [Modelo de objetos de LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)   
 [Cómo: Especificar los miembros que se comprueban en conflictos de simultaneidad](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)   
 [Cómo: Personalizar clases de entidad mediante el editor de código](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)