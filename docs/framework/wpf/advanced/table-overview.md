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
ms.openlocfilehash: 6485aa9f2094b734f796ff38a33f4e0d3434e004
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59317667"
---
# <a name="table-overview"></a>Información general sobre tablas
<xref:System.Windows.Documents.Table> es un elemento de nivel de bloque que admite presentación basada en cuadrícula de contenido de documentos dinámicos. La flexibilidad de este elemento lo hace muy útil, pero también más complicado de entender y usar correctamente.  
  
 Este tema contiene las siguientes secciones:  
  
-   [Fundamentos de tablas](#table_basics)  
  
-   [¿En qué se diferencian las tablas de las cuadrículas?](#table_vs_Grid)  
  
-   [Estructura básica de las tablas](#basic_table_structure)  
  
-   [Contención de tablas](#table_containment)  
  
-   [Agrupaciones de filas](#row_groupings)  
  
-   [Prioridad de representación del fondo](#rendering_precedence)  
  
-   [Abarcar filas o columnas](#spanning_rows_or_columns)  
  
-   [Creación de una tabla mediante código](#building_a_table_with_code)  
  
-   [Temas relacionados] 
  
<a name="table_basics"></a>   
## <a name="table-basics"></a>Fundamentos de tablas  
  
<a name="table_vs_Grid"></a>   
### <a name="how-is-table-different-then-grid"></a>¿En qué se diferencian las tablas de las cuadrículas?  
 <xref:System.Windows.Documents.Table> y <xref:System.Windows.Controls.Grid> comparten funcionalidades comunes, pero cada una es adecuada para escenarios diferentes. Un <xref:System.Windows.Documents.Table> está diseñado para su uso en contenido dinámico (consulte [Flow Document Overview](flow-document-overview.md) para obtener más información sobre el contenido dinámico). Las cuadrículas son más apropiadas para formularios (básicamente, en cualquier lugar excepto en el contenido dinámico). Dentro de un <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Table> admite el flujo de los comportamientos del contenido, como paginación, ajuste dinámico de columnas y selección de contenido mientras una <xref:System.Windows.Controls.Grid> no lo hace. Un <xref:System.Windows.Controls.Grid> por otro lado se utiliza fuera de un <xref:System.Windows.Documents.FlowDocument> por diversos motivos incluidos <xref:System.Windows.Controls.Grid> agrega elementos basándose en un índice de fila y columna, <xref:System.Windows.Documents.Table> no lo hace. El <xref:System.Windows.Controls.Grid> elemento permite la disposición en capas del contenido secundario, lo que permite más de un elemento dentro de una sola "celda". <xref:System.Windows.Documents.Table> no admite la disposición en capas. Los elementos secundarios de un <xref:System.Windows.Controls.Grid> puede colocar de manera absoluta en relación con el área de los límites "celda". <xref:System.Windows.Documents.Table> no se admite esta característica. Por último, un <xref:System.Windows.Controls.Grid> requiere menos recursos, a continuación, un <xref:System.Windows.Documents.Table> por lo que puede usar un <xref:System.Windows.Controls.Grid> para mejorar el rendimiento.  
  
<a name="basic_table_structure"></a>   
### <a name="basic-table-structure"></a>Estructura básica de las tablas  
 <xref:System.Windows.Documents.Table> Proporciona una presentación basada en cuadrícula que consta de columnas (representado por <xref:System.Windows.Documents.TableColumn> elementos) y filas (representados por <xref:System.Windows.Documents.TableRow> elementos). <xref:System.Windows.Documents.TableColumn> los elementos no hospedan contenido; simplemente definen las columnas y las características de las columnas. <xref:System.Windows.Documents.TableRow> los elementos se deben hospedar en un <xref:System.Windows.Documents.TableRowGroup> elemento, que define una agrupación de filas de la tabla. <xref:System.Windows.Documents.TableCell> los elementos, que incluyen el contenido real que se presentará en la tabla, se deben hospedar en un <xref:System.Windows.Documents.TableRow> elemento. <xref:System.Windows.Documents.TableCell> solo puede contener elementos que se derivan de <xref:System.Windows.Documents.Block>.  Los elementos secundarios válidos para un <xref:System.Windows.Documents.TableCell> incluir.  
  
-   <xref:System.Windows.Documents.BlockUIContainer>  
  
-   <xref:System.Windows.Documents.List>  
  
-   <xref:System.Windows.Documents.Paragraph>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
>  <xref:System.Windows.Documents.TableCell> los elementos no pueden hospedar directamente contenido de texto. Para obtener más información acerca de las reglas de contención para el flujo de elementos de contenido como <xref:System.Windows.Documents.TableCell>, consulte [Flow Document Overview](flow-document-overview.md).  
  
> [!NOTE]
>  <xref:System.Windows.Documents.Table> es similar a la <xref:System.Windows.Controls.Grid> elemento, pero tiene más funciones y, por lo tanto, requiere mayor consumo de recursos.  
  
 En el ejemplo siguiente se define una tabla de 2 x 3 simple con [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)].  
  
 [!code-xaml[TableSnippets2#_Table_BasicLayout](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 En la ilustración siguiente, se muestra cómo se representa este ejemplo.  
  
 ![Captura de pantalla que muestra cómo se representa una tabla básica.](./media/table-overview/basic-table-render-example.png)  
  
<a name="table_containment"></a>   
### <a name="table-containment"></a>Contención de tablas  
 <xref:System.Windows.Documents.Table> deriva el <xref:System.Windows.Documents.Block> elemento y cumple las reglas comunes para <xref:System.Windows.Documents.Block> elementos de nivel.  Un <xref:System.Windows.Documents.Table> elemento puede contener cualquiera de los siguientes elementos:  
  
-   <xref:System.Windows.Documents.FlowDocument>  
  
-   <xref:System.Windows.Documents.TableCell>  
  
-   <xref:System.Windows.Controls.ListBoxItem>  
  
-   <xref:System.Windows.Controls.ListViewItem>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.Floater>  
  
-   <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>   
### <a name="row-groupings"></a>Agrupaciones de filas  
 El <xref:System.Windows.Documents.TableRowGroup> elemento proporciona una manera de agrupar filas arbitrariamente dentro de una tabla, todas las filas de una tabla deben pertenecer a una agrupación de filas.  Las filas dentro de un grupo de filas comparten a menudo una finalidad común y se les puede asignar un estilo como grupo.  Un uso común para las agrupaciones de filas es separar las filas que tienen una finalidad especial, como filas de título, encabezado y pie de página, del contenido principal incluido en la tabla.  
  
 En el ejemplo siguiente se usa [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] para definir una tabla con filas de encabezado y pie de página con estilo.  
  
 [!code-xaml[TableSnippets2#_Table_RowGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 En la ilustración siguiente, se muestra cómo se representa este ejemplo.  
  
 ![Captura de pantalla: Grupos de filas de tabla](./media/table-rowgroups.png "Table_RowGroups")  
  
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
 Las celdas de tabla pueden configurarse para abarcar varias filas o columnas mediante el uso de la <xref:System.Windows.Documents.TableCell.RowSpan%2A> o <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> atributos, respectivamente.  
  
 Considere el ejemplo siguiente, en el que una celda abarca tres columnas.  
  
 [!code-xaml[TableSnippets2#_Table_ColumnSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 En la ilustración siguiente, se muestra cómo se representa este ejemplo.  
  
 ![Captura de pantalla: Celda que abarca las tres columnas](./media/table-columnspan.png "Table_ColumnSpan")  
  
<a name="building_a_table_with_code"></a>   
## <a name="building-a-table-with-code"></a>Creación de una tabla mediante código  
 Los ejemplos siguientes muestran cómo crear mediante programación un <xref:System.Windows.Documents.Table> y rellenarla con contenido. El contenido de la tabla se distribuye en cinco filas (representados por <xref:System.Windows.Documents.TableRow> objetos incluidos en un <xref:System.Windows.Documents.Table.RowGroups%2A> objeto) y seis columnas (representado por <xref:System.Windows.Documents.TableColumn> objetos). Las filas se usan para distintos fines de presentación, e incluyen una fila de título usada para dar título a toda la tabla, una fila de encabezado para describir las columnas de datos de la tabla, y una fila de pie de página con información de resumen.  Tenga en cuenta que los conceptos de filas de "título", "encabezado" y "pie de página" no son inherentes a la tabla; se trata simplemente de filas con características diferentes. Las celdas de tabla incluyen el contenido real, que puede estar formado por texto, imágenes o casi cualquier otro [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] elemento.  
  
 En primer lugar, un <xref:System.Windows.Documents.FlowDocument> se crea al host la <xref:System.Windows.Documents.Table>y un nuevo <xref:System.Windows.Documents.Table> se crea y agrega al contenido de la <xref:System.Windows.Documents.FlowDocument>.  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 A continuación, seis <xref:System.Windows.Documents.TableColumn> objetos se crean y se agregan a la tabla <xref:System.Windows.Documents.Table.Columns%2A> colección aplicarles formato.  
  
> [!NOTE]
>  Tenga en cuenta que la tabla <xref:System.Windows.Documents.Table.Columns%2A> colección utiliza la indización de base cero estándar.  
  
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
