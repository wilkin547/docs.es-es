---
title: Procedimiento Manipular las columnas de una tabla mediante la propiedad Columns
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], manipulating table columns
- properties [WPF], Columns [WPF], manipulating table columns
- tables [WPF], manipulating columns
- Columns property [WPF]
ms.assetid: 3f8884f4-7e1f-456b-be06-fbd3cf469bf3
ms.openlocfilehash: 18a26c76688ebf668293cb1254404d6d2cf15208
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913589"
---
# <a name="how-to-manipulate-a-tables-columns-through-the-columns-property"></a>Procedimiento Manipular las columnas de una tabla mediante la propiedad Columns
En este ejemplo se muestran algunas de las operaciones más comunes que se pueden realizar en las columnas de una <xref:System.Windows.Documents.Table.Columns%2A> tabla a través de la propiedad.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea una nueva tabla y, <xref:System.Windows.Documents.TableColumnCollection.Add%2A> a continuación, se usa el método para <xref:System.Windows.Documents.Table.Columns%2A> Agregar columnas a la colección de la tabla.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Add](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_add)]
 [!code-vb[TableSnippets2#_Table_Columns_Add](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_add)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se inserta un <xref:System.Windows.Documents.TableColumn>nuevo.  La nueva columna se inserta en la posición 0 del índice, convirtiéndola en la nueva columna de la tabla.  
  
> [!NOTE]
> La <xref:System.Windows.Documents.TableColumnCollection> colección utiliza la indexación estándar basada en cero.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Insert](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_insert)]
 [!code-vb[TableSnippets2#_Table_Columns_Insert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_insert)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se obtiene acceso a algunas propiedades arbitrarias <xref:System.Windows.Documents.TableColumnCollection> de las columnas de la colección, que hacen referencia a columnas determinadas por índice.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Manip](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_manip)]
 [!code-vb[TableSnippets2#_Table_Columns_Manip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_manip)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se obtiene el número de columnas hospedadas actualmente por la tabla.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Count](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_count)]
 [!code-vb[TableSnippets2#_Table_Columns_Count](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_count)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se quita una columna determinada por referencia.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelRef](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delref)]
 [!code-vb[TableSnippets2#_Table_Columns_DelRef](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delref)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se quita una columna determinada por índice.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delindex)]
 [!code-vb[TableSnippets2#_Table_Columns_DelIndex](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delindex)]  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se quitan todas las columnas de la colección de columnas de la tabla.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Clear](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_clear)]
 [!code-vb[TableSnippets2#_Table_Columns_Clear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_clear)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre tablas](table-overview.md)
- [Definir una tabla con XAML](how-to-define-a-table-with-xaml.md)
- [Compilar una tabla mediante programación](how-to-build-a-table-programmatically.md)
- [Manipular grupos de filas de una tabla mediante la propiedad RowGroups](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [Manipular un objeto FlowDocument mediante la propiedad Blocks](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Manipular grupos de filas de una tabla mediante la propiedad RowGroups](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
