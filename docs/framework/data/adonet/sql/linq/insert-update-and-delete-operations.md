---
title: "Operaciones de actualizaci&#243;n, inserci&#243;n y eliminaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 26a43a4f-83c9-4732-806d-bb23aad0ff6b
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Operaciones de actualizaci&#243;n, inserci&#243;n y eliminaci&#243;n
En `Insert`, las operaciones `Update`, `Delete` y [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] se realizan agregando, cambiando y quitando objetos en el modelo de objetos.  De forma predeterminada, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] convierte estas acciones a SQL y envía los cambios a la base de datos.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proporciona la máxima flexibilidad para manipular y conservar los cambios realizados en los objetos.  En cuanto están disponibles los objetos entidad \(ya sea recuperándolos a través de una consulta o construyéndolos nuevamente\), puede cambiarlos como los objetos normales de la aplicación.  Es decir, puede cambiar sus valores, agregarlos a las colecciones y quitarlos de las mismas.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] realiza un seguimiento de los cambios y está listo para volver a transmitirlos a la base de datos cuando llame al método <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no admite ni reconoce las operaciones de eliminación en cascada.  Si desea eliminar una fila de una tabla que tiene restricciones, deberá establecer la regla `ON DELETE CASCADE` en la restricción FOREIGN KEY de la base de datos o bien utilizar su propio código para eliminar primero los objetos secundarios que impiden que se elimine el objeto primario. De lo contrario, se inicia una excepción.  Para obtener más información, consulte [Cómo: Eliminar filas de la base de datos](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).  
  
 En los siguientes extractos se utilizan las clases `Customer` y `Order` de la base de datos de ejemplo Northwind.  Para no extendernos demasiado, no incluimos las definiciones de clase.  
  
 [!code-csharp[DLinqCRUDOps#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCRUDOps/cs/Program.cs#1)]
 [!code-vb[DLinqCRUDOps#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCRUDOps/vb/Module1.vb#1)]  
  
 Al llamar a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] genera y ejecuta automáticamente los comandos SQL necesarios para volver a transmitir los cambios a la base de datos.  
  
> [!NOTE]
>  Puede invalidar este comportamiento utilizando su propia lógica personalizada, normalmente mediante un procedimiento almacenado.  Para obtener más información, consulte [Responsabilidades del desarrollador en la invalidación del comportamiento predeterminado](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)  
>   
>  Los desarrolladores de [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] pueden usar el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para desarrollar procedimientos almacenados con este propósito.  
  
## Vea también  
 [Descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)   
 [Personalizar operaciones de actualización, inserción y eliminación](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)