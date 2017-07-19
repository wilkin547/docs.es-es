---
title: "C&#243;mo: Manipular grupos de filas de una tabla mediante la propiedad RowGroups | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "documentos, manipular grupos de filas mediante la propiedad RowGroups"
  - "propiedades, RowGroups, manipular grupos de filas"
  - "grupos de filas, manipular mediante la propiedad RowGroups"
  - "RowGroups (propiedad), manipular grupos de filas"
ms.assetid: ea61440f-08ae-44ed-b314-5716aaaae3ed
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Manipular grupos de filas de una tabla mediante la propiedad RowGroups
En este ejemplo se muestran algunas de las operaciones más comunes que se pueden realizar en los grupos de filas de una tabla mediante la propiedad <xref:System.Windows.Documents.Table.RowGroups%2A>.  
  
## Ejemplo  
 En el ejemplo siguiente se crea una nueva tabla y, a continuación, se utiliza el método <xref:System.Windows.Documents.TableRowGroupCollection.Add%2A> para agregar columnas a la colección <xref:System.Windows.Documents.Table.RowGroups%2A> de la tabla.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Add](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_add)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Add](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_add)]  
  
## Ejemplo  
 En el ejemplo siguiente se inserta un nuevo objeto <xref:System.Windows.Documents.TableRowGroup>.  La nueva columna se inserta en la posición de índice 0, lo que la convierte en el primer grupo de filas de la tabla.  
  
> [!NOTE]
>  La colección <xref:System.Windows.Documents.TableRowGroupCollection> utiliza la indización estándar basada en cero.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Insert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_insert)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Insert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_insert)]  
  
## Ejemplo  
 En el ejemplo siguiente se agregan varias filas a un objeto <xref:System.Windows.Documents.TableRowGroup> determinado \(especificado por su índice\) de la tabla.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddRows](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addrows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddRows](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addrows)]  
  
## Ejemplo  
 En el ejemplo siguiente se tiene acceso a algunas propiedades arbitrarias de las filas del primer grupo de filas de la tabla.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipRows](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_maniprows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipRows](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_maniprows)]  
  
## Ejemplo  
 En el ejemplo siguiente se agregan varias celdas a un objeto <xref:System.Windows.Documents.TableRow> determinado \(especificado por su índice\) de la tabla.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddCells](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddCells](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addcells)]  
  
## Ejemplo  
 En el ejemplo siguiente se tiene acceso a algunos métodos y propiedades arbitrarios de las celdas de la primera fila del primer grupo de filas.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipCells](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_manipcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipCells](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_manipcells)]  
  
## Ejemplo  
 En el ejemplo siguiente se devuelve el número de elementos <xref:System.Windows.Documents.TableRowGroup> hospedados por la tabla.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Count](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_count)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Count](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_count)]  
  
## Ejemplo  
 En el ejemplo siguiente se quita un grupo de filas en particular por su referencia.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelRef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delref)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelRef](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delref)]  
  
## Ejemplo  
 En el ejemplo siguiente se quita un grupo de filas en particular por su índice.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delindex)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelIndex](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delindex)]  
  
## Ejemplo  
 En el ejemplo siguiente se quitan todos los grupos de filas de la colección de grupos de filas de la tabla.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Clear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_clear)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Clear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_clear)]  
  
## Vea también  
 [How\-to: Manipulate Flow Content Elements through the Inlines Property](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)   
 [Manipular un objeto FlowDocument mediante la propiedad Blocks](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)   
 [Manipular las columnas de una tabla mediante la propiedad Columns](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)