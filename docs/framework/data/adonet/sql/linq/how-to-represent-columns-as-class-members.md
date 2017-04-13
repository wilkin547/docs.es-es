---
title: "C&#243;mo: Representar columnas como miembros de clase | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7ab28021-4d15-4d9c-bf2e-6ccc0daa7d1a
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# C&#243;mo: Representar columnas como miembros de clase
Utilice el atributo <xref:System.Data.Linq.Mapping.ColumnAttribute> de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para asociar un campo o una propiedad a una columna de base de datos.  
  
### Para asignar un campo o una propiedad a una columna de base de datos  
  
-   Agregue el atributo <xref:System.Data.Linq.Mapping.ColumnAttribute> a la propiedad o declaración de campo.  
  
## Ejemplo  
 El código siguiente asigna el campo `CustomerID` de la clase `Customer` a la columna `CustomerID` de la tabla de base de datos `Customers`.  
  
 [!code-csharp[DLinqCustomize#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#2)]
 [!code-vb[DLinqCustomize#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#2)]  
  
 No tiene que especificar la propiedad <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> si se puede deducir el nombre.  Si no especifica ningún nombre, se supone que es el mismo que el de la propiedad o campo.  
  
## Vea también  
 [Modelo de objetos de LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)   
 [Cómo: Personalizar clases de entidad mediante el editor de código](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)