---
title: "C&#243;mo: Insertar filas en la base de datos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 44d99680-69c7-4879-a732-f6771b334211
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# C&#243;mo: Insertar filas en la base de datos
Para insertar filas en una base de datos, se agregan objetos a la colección [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] de <xref:System.Data.Linq.Table%601> asociada y después se envían los cambios a la base de datos. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] convierte los cambios en los comandos `INSERT` adecuados de SQL.  
  
> [!NOTE]
>  Puede invalidar los métodos predeterminados de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para las operaciones de base de datos `Insert`, `Update` y `Delete`.  Para obtener más información, consulte [Personalizar operaciones de actualización, inserción y eliminación](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
>   
>  Los desarrolladores de [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] pueden usar el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para desarrollar procedimientos almacenados con el mismo propósito.  
  
 En los pasos siguientes se asume que un objeto <xref:System.Data.Linq.DataContext> válido le conecta a la base de datos Northwind.  Para obtener más información, consulte [Cómo: Conectarse a una base de datos](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).  
  
### Para insertar una fila en la base de datos  
  
1.  Cree un nuevo objeto que incluya los datos de la columna que se van a enviar.  
  
2.  Agregue el nuevo objeto a la colección [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] de `Table` que está asociada a la tabla de destino en la base de datos.  
  
3.  Envíe el cambio a la base de datos.  
  
## Ejemplo  
 En el ejemplo de código siguiente se crea un nuevo objeto de tipo `Order` y se llena con los valores adecuados.  Después, se agrega el nuevo objeto a la colección `Order`.  Finalmente, se envía el cambio a la base de datos, como una nueva fila de la tabla `Orders`.  
  
 [!code-csharp[System.Data.Linq.Table#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.Table#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#1)]  
  
## Vea también  
 [Cómo: Administrar los conflictos de cambios](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)   
 [Métodos DataContext \(Object Relational Designer\)](../Topic/DataContext%20Methods%20\(O-R%20Designer\).md)   
 [Cómo: Asignar procedimientos almacenados para realizar actualizaciones, inserciones y eliminaciones \(Object Relational Designer\)](../Topic/How%20to:%20Assign%20stored%20procedures%20to%20perform%20updates,%20inserts,%20and%20deletes%20\(O-R%20Designer\).md)   
 [Crear y enviar cambios en los datos](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)