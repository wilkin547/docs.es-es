---
title: "C&#243;mo: Manipular las columnas de una tabla mediante la propiedad Columns | Microsoft Docs"
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
  - "Columns (propiedad)"
  - "documentos, manipular columnas de tabla"
  - "propiedades, Columnas, manipular columnas de tabla"
  - "tablas, manipular columnas"
ms.assetid: 3f8884f4-7e1f-456b-be06-fbd3cf469bf3
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Manipular las columnas de una tabla mediante la propiedad Columns
En este ejemplo se muestran algunas de las operaciones más comunes que se pueden realizar en las columnas de una tabla mediante la propiedad <xref:System.Windows.Documents.Table.Columns%2A>.  
  
## Ejemplo  
 En el ejemplo siguiente se crea una nueva tabla y, a continuación, se utiliza el método <xref:System.Windows.Documents.TableColumnCollection.Add%2A> para agregar columnas a la colección <xref:System.Windows.Documents.Table.Columns%2A> de la tabla.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Add](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_add)]
 [!code-vb[TableSnippets2#_Table_Columns_Add](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_add)]  
  
## Ejemplo  
 En el ejemplo siguiente se inserta un nuevo objeto <xref:System.Windows.Documents.TableColumn>.  La nueva columna se inserta en la posición de índice 0, lo que la convierte en la nueva primera columna de la tabla.  
  
> [!NOTE]
>  La colección <xref:System.Windows.Documents.TableColumnCollection> utiliza la indización estándar basada en cero.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Insert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_insert)]
 [!code-vb[TableSnippets2#_Table_Columns_Insert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_insert)]  
  
## Ejemplo  
 En el ejemplo siguiente se tiene acceso a algunas propiedades arbitrarias de las columnas de la colección <xref:System.Windows.Documents.TableColumnCollection>, y se hace referencia a las columnas concretas por su índice.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Manip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_manip)]
 [!code-vb[TableSnippets2#_Table_Columns_Manip](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_manip)]  
  
## Ejemplo  
 En el ejemplo siguiente se obtiene el número de columnas hospedadas por la tabla en este momento.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Count](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_count)]
 [!code-vb[TableSnippets2#_Table_Columns_Count](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_count)]  
  
## Ejemplo  
 En el ejemplo siguiente se quita una columna en particular por su referencia.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelRef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delref)]
 [!code-vb[TableSnippets2#_Table_Columns_DelRef](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delref)]  
  
## Ejemplo  
 En el ejemplo siguiente se quita una columna en particular por su índice.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delindex)]
 [!code-vb[TableSnippets2#_Table_Columns_DelIndex](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delindex)]  
  
## Ejemplo  
 En el ejemplo siguiente se quitan todas las columnas de la colección de columnas de la tabla.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Clear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_clear)]
 [!code-vb[TableSnippets2#_Table_Columns_Clear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_clear)]  
  
## Vea también  
 [Información general sobre tablas](../../../../docs/framework/wpf/advanced/table-overview.md)   
 [Definir una tabla con XAML](../../../../docs/framework/wpf/advanced/how-to-define-a-table-with-xaml.md)   
 [Compilar una tabla mediante programación](../../../../docs/framework/wpf/advanced/how-to-build-a-table-programmatically.md)   
 [Manipular grupos de filas de una tabla mediante la propiedad RowGroups](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)   
 [Manipular un objeto FlowDocument mediante la propiedad Blocks](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)   
 [Manipular grupos de filas de una tabla mediante la propiedad RowGroups](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)