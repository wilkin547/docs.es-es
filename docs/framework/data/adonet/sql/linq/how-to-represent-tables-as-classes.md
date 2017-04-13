---
title: "C&#243;mo: Representar tablas como clases | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 84dda12b-88a2-4cd2-92b3-8db87b28d14c
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# C&#243;mo: Representar tablas como clases
Utilice el atributo <xref:System.Data.Linq.Mapping.TableAttribute> de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para designar una clase como una clase de entidad asociada a una tabla de base de datos.  
  
### Para asignar una clase a una tabla de base de datos  
  
-   Agregue el atributo <xref:System.Data.Linq.Mapping.TableAttribute> a la declaración de la clase.  
  
## Ejemplo  
 El código siguiente establece la clase `Customer` como una clase de entidad que está asociada a la tabla de base de datos `Customers`.  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 No tiene que especificar la propiedad <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> si se puede deducir el nombre.  Si no especifica ningún nombre, se supone que es el mismo que el de la propiedad o campo.  
  
## Vea también  
 [Modelo de objetos de LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)   
 [Cómo: Personalizar clases de entidad mediante el editor de código](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)