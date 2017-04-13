---
title: "C&#243;mo: Representar columnas como generadas por la base de datos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# C&#243;mo: Representar columnas como generadas por la base de datos
Utilice la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] en el atributo <xref:System.Data.Linq.Mapping.ColumnAttribute> para designar que un campo o propiedad representa una columna generada por base de datos.  
  
 Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.  
  
### Para designar que un campo o propiedad representa una columna generada por base de datos  
  
1.  Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2.  Establezca el valor de propiedad en `true`.  
  
## Vea también  
 [Modelo de objetos de LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)   
 [Cómo: Personalizar clases de entidad mediante el editor de código](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)