---
title: "C&#243;mo: Compilar una tabla mediante programaci&#243;n | Microsoft Docs"
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
  - "crear, tablas mediante programación"
  - "documentos, crear tablas mediante programación"
  - "tablas, crear mediante programación"
ms.assetid: e3ca88f3-6e94-4b61-82fc-42104c10b761
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Compilar una tabla mediante programaci&#243;n
En los ejemplos siguientes se muestra cómo crear una <xref:System.Windows.Documents.Table> y rellenarla con contenido mediante programación.  El contenido de la tabla se distribuye en cinco filas \(representadas por objetos <xref:System.Windows.Documents.TableRow> contenidos en un objeto <xref:System.Windows.Documents.Table.RowGroups%2A>\) y seis columnas \(representadas por objetos <xref:System.Windows.Documents.TableColumn> \).  Las filas se utilizan para distintos fines de presentación, e incluyen una fila de título utilizada para dar título a toda la tabla, una fila de encabezado para describir las columnas de datos de la tabla, y una fila de pie de página con información de resumen.  Observe que los conceptos de filas de "título", "encabezado" y "pie de página" no son inherentes a la tabla; se trata simplemente de filas con características diferentes.  Las celdas de la tabla incluyen el contenido real, que puede estar compuesto de texto, imágenes o casi cualquier otro elemento de la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
## Ejemplo  
 En primer lugar, se crea un <xref:System.Windows.Documents.FlowDocument> para hospedar <xref:System.Windows.Documents.Table>. También se crea una nueva <xref:System.Windows.Documents.Table> y se agrega al contenido de <xref:System.Windows.Documents.FlowDocument>.  
  
 [!code-csharp[TableSnippets#_TableCreate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
## Ejemplo  
 A continuación, se crean seis objetos <xref:System.Windows.Documents.TableColumn> y se agregan a la colección <xref:System.Windows.Documents.Table.Columns%2A> de la tabla, tras aplicarles formato.  
  
> [!NOTE]
>  Observe que la colección <xref:System.Windows.Documents.Table.Columns%2A> de la tabla utiliza la indización estándar basada en cero.  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
## Ejemplo  
 Luego, se crea una fila de título y se agrega a la tabla tras aplicarle formato.  La fila de título contiene una sola celda que abarca las seis columnas de la tabla.  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
## Ejemplo  
 Después, se crea una fila de encabezado y se agrega a la tabla, y se crean y rellenan con contenido las celdas de la fila de encabezado.  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
## Ejemplo  
 En este momento, se crea una fila de datos y se agrega a la tabla, y se crean y rellenan con contenido las celdas de esta fila.  Compilar esta fila es similar a compilar la fila de encabezado, con un formato ligeramente diferente.  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
## Ejemplo  
 Por último, se crea una fila de pie de página, se agregó y se le da formato.  Al igual que la fila de título, el pie de página contiene una sola celda que abarca las seis columnas de la tabla.  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## Vea también  
 [Información general sobre tablas](../../../../docs/framework/wpf/advanced/table-overview.md)