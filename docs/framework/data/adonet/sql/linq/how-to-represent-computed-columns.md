---
title: "C&#243;mo: Representar columnas calculadas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4025f1fd-9dfa-46c0-b04f-34e8bc7957a2
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# C&#243;mo: Representar columnas calculadas
Utilice la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] en un atributo <xref:System.Data.Linq.Mapping.ColumnAttribute> para representar una columna cuyo contenido es el resultado de un cálculo.  
  
 Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no admite las columnas calculadas como claves principales.  
  
### Para representar una columna calculada  
  
1.  Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2.  Asigne una representación de cadena de la fórmula a la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.  
  
## Vea también  
 [Modelo de objetos de LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)   
 [Cómo: Personalizar clases de entidad mediante el editor de código](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)