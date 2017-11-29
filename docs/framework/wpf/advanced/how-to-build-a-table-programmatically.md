---
title: "Cómo: Compilar una tabla mediante programación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: tables [WPF], creating programmatically
ms.assetid: e3ca88f3-6e94-4b61-82fc-42104c10b761
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8ef961bb219f201cf5fe32a5b2bbdf70ef45e73b
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-build-a-table-programmatically"></a>Cómo: Compilar una tabla mediante programación
Los ejemplos siguientes muestran cómo crear mediante programación un <xref:System.Windows.Documents.Table> y rellenarla con contenido. El contenido de la tabla se distribuye en cinco filas (representados por <xref:System.Windows.Documents.TableRow> objetos incluidos en un <xref:System.Windows.Documents.Table.RowGroups%2A> objeto) y seis columnas (representado por <xref:System.Windows.Documents.TableColumn> objetos). Las filas se usan para distintos fines de presentación, e incluyen una fila de título usada para dar título a toda la tabla, una fila de encabezado para describir las columnas de datos de la tabla, y una fila de pie de página con información de resumen.  Tenga en cuenta que los conceptos de filas de "título", "encabezado" y "pie de página" no son inherentes a la tabla; se trata simplemente de filas con características diferentes. Celdas de la tabla incluyen el contenido real, que puede estar formado por texto, imágenes o casi cualquier otro [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] elemento.  
  
## <a name="example"></a>Ejemplo  
 En primer lugar, un <xref:System.Windows.Documents.FlowDocument> se crea al host la <xref:System.Windows.Documents.Table>y una nueva <xref:System.Windows.Documents.Table> se crea y se agrega al contenido de la <xref:System.Windows.Documents.FlowDocument>.  
  
 [!code-csharp[TableSnippets#_TableCreate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
## <a name="example"></a>Ejemplo  
 Después, seis <xref:System.Windows.Documents.TableColumn> objetos se crean y se agregan a la tabla <xref:System.Windows.Documents.Table.Columns%2A> colección tras aplicarle formato.  
  
> [!NOTE]
>  Tenga en cuenta que la tabla <xref:System.Windows.Documents.Table.Columns%2A> colección utiliza la indización de base cero estándar.  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
## <a name="example"></a>Ejemplo  
 Luego, se crea una fila de título y se agrega a la tabla tras aplicarle formato.  La fila de título contiene una sola celda que abarca las seis columnas de la tabla.  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
## <a name="example"></a>Ejemplo  
 Después, se crea una fila de encabezado y se agrega a la tabla, y se crean y rellenan con contenido las celdas de la fila de encabezado.  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
## <a name="example"></a>Ejemplo  
 Después, se crea una fila para datos y se agrega a la tabla, y se crean y rellenan con contenido las celdas de esta fila.  La creación de esta fila es similar a la creación de la fila de encabezado con un formato ligeramente diferente.  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
## <a name="example"></a>Ejemplo  
 Por último, se crea una fila de pie de página, se agrega y se le da formato.  Al igual que la fila de título, el pie de página contiene una sola celda que abarca las seis columnas de la tabla.  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre tablas](../../../../docs/framework/wpf/advanced/table-overview.md)
