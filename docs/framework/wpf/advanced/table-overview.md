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
ms.openlocfilehash: 01a5233a5436688caee3783cb26d344284df52e9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964299"
---
# <a name="table-overview"></a>Información general sobre tablas
<xref:System.Windows.Documents.Table>es un elemento de nivel de bloque que admite la presentación basada en cuadrícula del contenido del documento dinámico. La flexibilidad de este elemento lo hace muy útil, pero también más complicado de entender y usar correctamente.  
  
 Este tema contiene las siguientes secciones:  
  
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
 <xref:System.Windows.Documents.Table>y <xref:System.Windows.Controls.Grid> comparten algunas funciones comunes, pero cada una de ellas es más adecuada para distintos escenarios. Un <xref:System.Windows.Documents.Table> está diseñado para su uso en el contenido dinámico (consulte [información general sobre documentos dinámicos](flow-document-overview.md) para obtener más información sobre el contenido dinámico). Las cuadrículas son más apropiadas para formularios (básicamente, en cualquier lugar excepto en el contenido dinámico). Dentro de <xref:System.Windows.Documents.Table> <xref:System.Windows.Controls.Grid> , admite los comportamientos del contenido dinámico, como la paginación, el reflujo de columnas y la selección de contenido, mientras que no. <xref:System.Windows.Documents.FlowDocument> Por otra parte, se usa mejor fuera de un <xref:System.Windows.Documents.FlowDocument> por muchas razones, como <xref:System.Windows.Controls.Grid> agregar elementos basados en un índice de fila y de <xref:System.Windows.Documents.Table> columna, no. <xref:System.Windows.Controls.Grid> El <xref:System.Windows.Controls.Grid> elemento permite la disposición en capas del contenido secundario, lo que permite que haya más de un elemento dentro de una sola "celda". <xref:System.Windows.Documents.Table>no admite la disposición en capas. Los elementos secundarios de <xref:System.Windows.Controls.Grid> se pueden colocar de manera absoluta en relación con el área de los límites de la "celda". <xref:System.Windows.Documents.Table>no es compatible con esta característica. Por último, <xref:System.Windows.Controls.Grid> requiere menos recursos <xref:System.Windows.Documents.Table> y, por lo tanto, <xref:System.Windows.Controls.Grid> puede usar para mejorar el rendimiento.  
  
<a name="basic_table_structure"></a>   
### <a name="basic-table-structure"></a>Estructura básica de las tablas  
 <xref:System.Windows.Documents.Table>proporciona una presentación basada en cuadrícula formada por columnas (representadas <xref:System.Windows.Documents.TableColumn> por elementos) y filas (representadas por <xref:System.Windows.Documents.TableRow> elementos). <xref:System.Windows.Documents.TableColumn>los elementos no hospedan contenido; simplemente definen las columnas y características de las columnas. <xref:System.Windows.Documents.TableRow>los elementos deben estar hospedados <xref:System.Windows.Documents.TableRowGroup> en un elemento, que define una agrupación de filas para la tabla. <xref:System.Windows.Documents.TableCell>los elementos, que contienen el contenido real que va a presentar la tabla, deben estar hospedados <xref:System.Windows.Documents.TableRow> en un elemento. <xref:System.Windows.Documents.TableCell>solo puede contener elementos que derivan <xref:System.Windows.Documents.Block>de.  Elementos secundarios válidos para <xref:System.Windows.Documents.TableCell> un include.  
  
- <xref:System.Windows.Documents.BlockUIContainer>  
  
- <xref:System.Windows.Documents.List>  
  
- <xref:System.Windows.Documents.Paragraph>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
> <xref:System.Windows.Documents.TableCell>los elementos no pueden hospedar directamente el contenido de texto. Para obtener más información sobre las reglas de contención para elementos de <xref:System.Windows.Documents.TableCell>contenido dinámico como, consulte [información general sobre documentos dinámicos](flow-document-overview.md).  
  
> [!NOTE]
> <xref:System.Windows.Documents.Table>es similar al <xref:System.Windows.Controls.Grid> elemento, pero tiene más funciones y, por lo tanto, requiere mayor sobrecarga de recursos.  
  
 En el ejemplo siguiente se define una tabla simple de 2 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]x 3 con.  
  
 [!code-xaml[TableSnippets2#_Table_BasicLayout](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 En la ilustración siguiente, se muestra cómo se representa este ejemplo.  
  
 ![Captura de pantalla que muestra cómo se representa una tabla básica.](./media/table-overview/basic-table-render-example.png)  
  
<a name="table_containment"></a>   
### <a name="table-containment"></a>Contención de tablas  
 <xref:System.Windows.Documents.Table>deriva del <xref:System.Windows.Documents.Block> elemento y cumple las reglas comunes de los elementos de <xref:System.Windows.Documents.Block> nivel.  Un <xref:System.Windows.Documents.Table> elemento puede estar contenido en cualquiera de los siguientes elementos:  
  
- <xref:System.Windows.Documents.FlowDocument>  
  
- <xref:System.Windows.Documents.TableCell>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Floater>  
  
- <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>   
### <a name="row-groupings"></a>Agrupaciones de filas  
 El <xref:System.Windows.Documents.TableRowGroup> elemento proporciona una manera de agrupar filas arbitrariamente dentro de una tabla; cada fila de una tabla debe pertenecer a una agrupación de filas.  Las filas dentro de un grupo de filas comparten a menudo una finalidad común y se les puede asignar un estilo como grupo.  Un uso común para las agrupaciones de filas es separar las filas que tienen una finalidad especial, como filas de título, encabezado y pie de página, del contenido principal incluido en la tabla.  
  
 En el ejemplo siguiente [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] se usa para definir una tabla con filas de encabezado y pie de página con estilo.  
  
 [!code-xaml[TableSnippets2#_Table_RowGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 En la ilustración siguiente, se muestra cómo se representa este ejemplo.  
  
 ![Captura Grupos]de filas de tabla(./media/table-rowgroups.png "Table_RowGroups")  
  
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
  
 ![Captura &#45;Orden]z de la tabla(./media/table-zorder.png "Table_ZOrder")  
  
<a name="spanning_rows_or_columns"></a>   
### <a name="spanning-rows-or-columns"></a>Abarcar filas o columnas  
 Las celdas de la tabla se pueden configurar para que abarquen varias <xref:System.Windows.Documents.TableCell.RowSpan%2A> filas <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> o columnas mediante los atributos o, respectivamente.  
  
 Considere el ejemplo siguiente, en el que una celda abarca tres columnas.  
  
 [!code-xaml[TableSnippets2#_Table_ColumnSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 En la ilustración siguiente, se muestra cómo se representa este ejemplo.  
  
 ![Captura Celda que abarca las tres]columnas(./media/table-columnspan.png "Table_ColumnSpan")  
  
<a name="building_a_table_with_code"></a>   
## <a name="building-a-table-with-code"></a>Creación de una tabla mediante código  
 En los siguientes ejemplos se muestra cómo crear un <xref:System.Windows.Documents.Table> y rellenarlo con contenido mediante programación. El contenido de la tabla se distribuye en cinco filas (representadas por <xref:System.Windows.Documents.TableRow> objetos contenidos en un <xref:System.Windows.Documents.Table.RowGroups%2A> objeto) y seis columnas ( <xref:System.Windows.Documents.TableColumn> representadas por objetos). Las filas se usan para distintos fines de presentación, e incluyen una fila de título usada para dar título a toda la tabla, una fila de encabezado para describir las columnas de datos de la tabla, y una fila de pie de página con información de resumen.  Tenga en cuenta que los conceptos de filas de "título", "encabezado" y "pie de página" no son inherentes a la tabla; se trata simplemente de filas con características diferentes. Las celdas de la tabla contienen el contenido real, que puede estar formado por texto, imágenes o casi cualquier [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] otro elemento.  
  
 En primer lugar <xref:System.Windows.Documents.FlowDocument> , se crea un para <xref:System.Windows.Documents.Table>hospedar el, <xref:System.Windows.Documents.Table> y se <xref:System.Windows.Documents.FlowDocument>crea un nuevo y se agrega al contenido de.  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 A continuación, <xref:System.Windows.Documents.TableColumn> se crean seis objetos y se agregan a <xref:System.Windows.Documents.Table.Columns%2A> la colección de la tabla, con el formato aplicado.  
  
> [!NOTE]
> Tenga en cuenta que la <xref:System.Windows.Documents.Table.Columns%2A> colección de la tabla utiliza una indización de base cero estándar.  
  
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
  
## <a name="see-also"></a>Vea también

- [Información general sobre documentos dinámicos](flow-document-overview.md)
- [Definir una tabla con XAML](how-to-define-a-table-with-xaml.md)
- [Documentos en WPF](documents-in-wpf.md)
- [Usar elementos de contenido dinámico](how-to-use-flow-content-elements.md)
