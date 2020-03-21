---
title: Información general sobre tablas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flow content elements [WPF], Table
- documents [WPF], tables
- tables [WPF]
ms.assetid: 5e1105f4-8fc4-473a-ba55-88c8e71386e6
ms.openlocfilehash: 4bd747cea43755116c56b16f1de9a6ffb59935ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187267"
---
# <a name="table-overview"></a>Información general sobre tablas
<xref:System.Windows.Documents.Table>es un elemento de nivel de bloque que admite la presentación basada en cuadrícula del contenido del documento Flow. La flexibilidad de este elemento lo hace muy útil, pero también más complicado de entender y usar correctamente.  
  
 Este tema contiene las siguientes secciones.  
  
- [Fundamentos de tablas](#table_basics)  
  
- [¿En qué se diferencian las tablas de las cuadrículas?](#table_vs_Grid)  
  
- [Estructura básica de las tablas](#basic_table_structure)  
  
- [Contención de tablas](#table_containment)  
  
- [Agrupaciones de filas](#row_groupings)  
  
- [Prioridad de representación del fondo](#rendering_precedence)  
  
- [Abarcar filas o columnas](#spanning_rows_or_columns)  
  
- [Creación de una tabla mediante código](#building_a_table_with_code)  
  
- [Temas relacionados]
  
<a name="table_basics"></a>
## <a name="table-basics"></a>Fundamentos de tablas  
  
<a name="table_vs_Grid"></a>
### <a name="how-is-table-different-then-grid"></a>¿En qué se diferencian las tablas de las cuadrículas?  
 <xref:System.Windows.Documents.Table>y <xref:System.Windows.Controls.Grid> compartir algunas funciones comunes, pero cada uno es el más adecuado para diferentes escenarios. A <xref:System.Windows.Documents.Table> está diseñado para su uso dentro del contenido de flujo (consulte [Información general](flow-document-overview.md) del documento de flujo para obtener más información sobre el contenido del flujo). Las cuadrículas son más apropiadas para formularios (básicamente, en cualquier lugar excepto en el contenido dinámico). Dentro <xref:System.Windows.Documents.FlowDocument>de <xref:System.Windows.Documents.Table> un , admite comportamientos de contenido de flujo <xref:System.Windows.Controls.Grid> como paginación, reflujo de columna y selección de contenido, mientras que a no. A <xref:System.Windows.Controls.Grid> por otro lado se utiliza <xref:System.Windows.Documents.FlowDocument> mejor fuera <xref:System.Windows.Controls.Grid> de un por muchas razones, incluyendo agrega elementos basados en un índice de fila y columna, <xref:System.Windows.Documents.Table> no lo hace. El <xref:System.Windows.Controls.Grid> elemento permite la creación de capas de contenido secundario, lo que permite que exista más de un elemento dentro de una sola "célula". <xref:System.Windows.Documents.Table>no admite capas. Los elementos <xref:System.Windows.Controls.Grid> secundarios de a se pueden colocar absolutamente en relación con el área de sus límites de "célula". <xref:System.Windows.Documents.Table>no admite esta función. Por último, a <xref:System.Windows.Controls.Grid> requiere <xref:System.Windows.Documents.Table> menos recursos <xref:System.Windows.Controls.Grid> y, a, por lo que considere la posibilidad de usar a para mejorar el rendimiento.  
  
<a name="basic_table_structure"></a>
### <a name="basic-table-structure"></a>Estructura básica de las tablas  
 <xref:System.Windows.Documents.Table>proporciona una presentación basada en cuadrícula que <xref:System.Windows.Documents.TableColumn> consta de columnas (representadas por elementos) y filas (representadas por <xref:System.Windows.Documents.TableRow> elementos). <xref:System.Windows.Documents.TableColumn>los elementos no alojan contenido; simplemente definen columnas y características de columnas. <xref:System.Windows.Documents.TableRow>los elementos deben <xref:System.Windows.Documents.TableRowGroup> hospedarse en un elemento, que define una agrupación de filas para la tabla. <xref:System.Windows.Documents.TableCell>los elementos, que contienen el contenido real que presentará <xref:System.Windows.Documents.TableRow> la tabla, deben hospedarse en un elemento. <xref:System.Windows.Documents.TableCell>sólo pueden contener elementos que se deriven de <xref:System.Windows.Documents.Block>.  Elementos secundarios <xref:System.Windows.Documents.TableCell> válidos para un include.  
  
- <xref:System.Windows.Documents.BlockUIContainer>  
  
- <xref:System.Windows.Documents.List>  
  
- <xref:System.Windows.Documents.Paragraph>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
> <xref:System.Windows.Documents.TableCell>elementos no pueden albergar directamente contenido de texto. Para obtener más información acerca de las <xref:System.Windows.Documents.TableCell>reglas de contención para elementos de contenido de flujo como , vea [Información general del documento](flow-document-overview.md)de flujo .  
  
> [!NOTE]
> <xref:System.Windows.Documents.Table>es similar <xref:System.Windows.Controls.Grid> al elemento, pero tiene más capacidades y, por lo tanto, requiere una mayor sobrecarga de recursos.  
  
 En el ejemplo siguiente se define una tabla simple de 2 x 3 con XAML.  
  
 [!code-xaml[TableSnippets2#_Table_BasicLayout](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 En la ilustración siguiente se muestra cómo se representa este ejemplo.  
  
 ![Captura de pantalla que muestra cómo se representa una tabla básica.](./media/table-overview/basic-table-render-example.png)  
  
<a name="table_containment"></a>
### <a name="table-containment"></a>Contención de tablas  
 <xref:System.Windows.Documents.Table>deriva del <xref:System.Windows.Documents.Block> elemento y se adhiere a <xref:System.Windows.Documents.Block> las reglas comunes para los elementos de nivel.  Un <xref:System.Windows.Documents.Table> elemento puede estar contenido por cualquiera de los siguientes elementos:  
  
- <xref:System.Windows.Documents.FlowDocument>  
  
- <xref:System.Windows.Documents.TableCell>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Floater>  
  
- <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>
### <a name="row-groupings"></a>Agrupaciones de filas  
 El <xref:System.Windows.Documents.TableRowGroup> elemento proporciona una manera de agrupar arbitrariamente filas dentro de una tabla; cada fila de una tabla debe pertenecer a una agrupación de filas.  Las filas dentro de un grupo de filas comparten a menudo una finalidad común y se les puede asignar un estilo como grupo.  Un uso común para las agrupaciones de filas es separar las filas que tienen una finalidad especial, como filas de título, encabezado y pie de página, del contenido principal incluido en la tabla.  
  
 En el ejemplo siguiente se usa XAML para definir una tabla con filas de encabezado y pie de página con estilo.  
  
 [!code-xaml[TableSnippets2#_Table_RowGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 En la ilustración siguiente se muestra cómo se representa este ejemplo.  
  
 ![Captura de pantalla: Grupos de filas de tablas](./media/table-rowgroups.png "Table_RowGroups")  
  
<a name="rendering_precedence"></a>
### <a name="background-rendering-precedence"></a>Prioridad de representación del fondo  
 Los elementos de tabla se representan en el orden siguiente (orden z ascendente). Este orden no se puede cambiar. Por ejemplo, no existe una propiedad de "orden Z" para estos elementos que se pueda usar para invalidar el orden establecido.  
  
1. <xref:System.Windows.Documents.Table>  
  
2. <xref:System.Windows.Documents.TableColumn>  
  
3. <xref:System.Windows.Documents.TableRowGroup>  
  
4. <xref:System.Windows.Documents.TableRow>  
  
5. <xref:System.Windows.Documents.TableCell>  
  
 Observe el ejemplo siguiente, en el que se definen los colores de fondo para cada uno de estos elementos dentro de una tabla.  
  
 [!code-xaml[TableSnippets2#_Table_ZOrder](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_zorder)]  
  
 En la ilustración siguiente se muestra cómo se representa este ejemplo (mostrando únicamente los colores de fondo).  
  
 ![Captura de pantalla: Tabla z&#45;orden](./media/table-zorder.png "Table_ZOrder")  
  
<a name="spanning_rows_or_columns"></a>
### <a name="spanning-rows-or-columns"></a>Abarcar filas o columnas  
 Las celdas de tabla se pueden configurar <xref:System.Windows.Documents.TableCell.RowSpan%2A> <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> para abarcar varias filas o columnas mediante los atributos o, respectivamente.  
  
 Considere el ejemplo siguiente, en el que una celda abarca tres columnas.  
  
 [!code-xaml[TableSnippets2#_Table_ColumnSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 En la ilustración siguiente se muestra cómo se representa este ejemplo.  
  
 ![Captura de pantalla: Celda que abarca las tres columnas](./media/table-columnspan.png "Table_ColumnSpan")  
  
<a name="building_a_table_with_code"></a>
## <a name="building-a-table-with-code"></a>Creación de una tabla mediante código  
 En los ejemplos siguientes se <xref:System.Windows.Documents.Table> muestra cómo crear mediante programación un y rellenarlo con contenido. El contenido de la tabla se prorratea <xref:System.Windows.Documents.TableRow> en cinco <xref:System.Windows.Documents.Table.RowGroups%2A> filas (representadas por objetos contenidos en un objeto) y seis columnas (representadas por <xref:System.Windows.Documents.TableColumn> objetos). Las filas se usan para distintos fines de presentación, e incluyen una fila de título usada para dar título a toda la tabla, una fila de encabezado para describir las columnas de datos de la tabla, y una fila de pie de página con información de resumen.  Tenga en cuenta que los conceptos de filas de "título", "encabezado" y "pie de página" no son inherentes a la tabla, se trata simplemente de filas con características diferentes. Las celdas de tabla contienen el contenido real, que [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] puede estar compuesto de texto, imágenes o casi cualquier otro elemento.  
  
 En primer <xref:System.Windows.Documents.FlowDocument> lugar, se <xref:System.Windows.Documents.Table>crea a <xref:System.Windows.Documents.Table> para hospedar el archivo <xref:System.Windows.Documents.FlowDocument>, y se crea un nuevo y se agrega al contenido del archivo .  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 A continuación, se crean seis <xref:System.Windows.Documents.TableColumn> objetos y se agregan a la colección de la <xref:System.Windows.Documents.Table.Columns%2A> tabla, con algún formato aplicado.  
  
> [!NOTE]
> Tenga en cuenta <xref:System.Windows.Documents.Table.Columns%2A> que la colección de la tabla utiliza la indexación estándar de base cero.  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
 Luego, se crea una fila de título y se agrega a la tabla tras aplicarle formato.  La fila de título contiene una sola celda que abarca las seis columnas de la tabla.  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
 Después, se crea una fila de encabezado y se agrega a la tabla, y se crean y rellenan con contenido las celdas de la fila de encabezado.  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
 Después, se crea una fila para datos y se agrega a la tabla, y se crean y rellenan con contenido las celdas de esta fila.  La creación de esta fila es similar a la creación de la fila de encabezado con un formato ligeramente diferente.  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
 Por último, se crea una fila de pie de página, se agrega y se le da formato.  Al igual que la fila de título, el pie de página contiene una sola celda que abarca las seis columnas de la tabla.  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre documentos dinámicos](flow-document-overview.md)
- [Definir una tabla con XAML](how-to-define-a-table-with-xaml.md)
- [Documentos en WPF](documents-in-wpf.md)
- [Usar elementos de contenido dinámico](how-to-use-flow-content-elements.md)
