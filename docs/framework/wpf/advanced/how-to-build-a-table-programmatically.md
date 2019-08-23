---
title: Procedimiento Compilar una tabla mediante programación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tables [WPF], creating programmatically
ms.assetid: e3ca88f3-6e94-4b61-82fc-42104c10b761
ms.openlocfilehash: 9c9061d3c4d6b3de5e1ab42a6b98c20813835ba8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964161"
---
# <a name="how-to-build-a-table-programmatically"></a>Procedimiento Compilar una tabla mediante programación
En los siguientes ejemplos se muestra cómo crear un <xref:System.Windows.Documents.Table> y rellenarlo con contenido mediante programación. El contenido de la tabla se distribuye en cinco filas (representadas por <xref:System.Windows.Documents.TableRow> objetos contenidos en un <xref:System.Windows.Documents.Table.RowGroups%2A> objeto) y seis columnas ( <xref:System.Windows.Documents.TableColumn> representadas por objetos). Las filas se usan para distintos fines de presentación, e incluyen una fila de título usada para dar título a toda la tabla, una fila de encabezado para describir las columnas de datos de la tabla, y una fila de pie de página con información de resumen.  Tenga en cuenta que los conceptos de filas de "título", "encabezado" y "pie de página" no son inherentes a la tabla; se trata simplemente de filas con características diferentes. Las celdas de la tabla contienen el contenido real, que puede estar formado por texto, imágenes o casi cualquier [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] otro elemento.  
  
## <a name="example"></a>Ejemplo  
 En primer lugar <xref:System.Windows.Documents.FlowDocument> , se crea un para <xref:System.Windows.Documents.Table>hospedar el, <xref:System.Windows.Documents.Table> y se <xref:System.Windows.Documents.FlowDocument>crea un nuevo y se agrega al contenido de.  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
## <a name="example"></a>Ejemplo  
 A continuación, <xref:System.Windows.Documents.TableColumn> se crean seis objetos y se agregan a <xref:System.Windows.Documents.Table.Columns%2A> la colección de la tabla, con el formato aplicado.  
  
> [!NOTE]
> Tenga en cuenta que la <xref:System.Windows.Documents.Table.Columns%2A> colección de la tabla utiliza una indización de base cero estándar.  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
## <a name="example"></a>Ejemplo  
 Luego, se crea una fila de título y se agrega a la tabla tras aplicarle formato.  La fila de título contiene una sola celda que abarca las seis columnas de la tabla.  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
## <a name="example"></a>Ejemplo  
 Después, se crea una fila de encabezado y se agrega a la tabla, y se crean y rellenan con contenido las celdas de la fila de encabezado.  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
## <a name="example"></a>Ejemplo  
 Después, se crea una fila para datos y se agrega a la tabla, y se crean y rellenan con contenido las celdas de esta fila.  La creación de esta fila es similar a la creación de la fila de encabezado con un formato ligeramente diferente.  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
## <a name="example"></a>Ejemplo  
 Por último, se crea una fila de pie de página, se agrega y se le da formato.  Al igual que la fila de título, el pie de página contiene una sola celda que abarca las seis columnas de la tabla.  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre tablas](table-overview.md)
