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
ms.openlocfilehash: fa7106207c69f19b647ba80ab7e724e9aad174c1
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005080"
---
# <a name="table-overview"></a>Información general sobre tablas
<xref:System.Windows.Documents.Table> es un elemento de nivel de bloque que admite la presentación basada en cuadrícula del contenido del documento dinámico. La flexibilidad de este elemento lo hace muy útil, pero también más complicado de entender y usar correctamente.  
  
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
 <xref:System.Windows.Documents.Table> y <xref:System.Windows.Controls.Grid> comparten alguna funcionalidad común, pero cada una de ellas es más adecuada para distintos escenarios. Un <xref:System.Windows.Documents.Table> está diseñado para su uso en el contenido dinámico (consulte [información general sobre documentos dinámicos](flow-document-overview.md) para obtener más información sobre el contenido dinámico). Las cuadrículas son más apropiadas para formularios (básicamente, en cualquier lugar excepto en el contenido dinámico). Dentro de un <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Table> admite los comportamientos del contenido dinámico, como la paginación, el reflujo de columnas y la selección de contenido, mientras que @no__t 2 no. Por otro lado, un <xref:System.Windows.Controls.Grid> se utiliza mejor fuera de un <xref:System.Windows.Documents.FlowDocument> por muchas razones, como <xref:System.Windows.Controls.Grid> agrega elementos basados en un índice de fila y columna, <xref:System.Windows.Documents.Table> no. El elemento <xref:System.Windows.Controls.Grid> permite la disposición en capas del contenido secundario, lo que permite que haya más de un elemento dentro de una sola "celda". <xref:System.Windows.Documents.Table> no admite la disposición en capas. Los elementos secundarios de un <xref:System.Windows.Controls.Grid> se pueden colocar de manera absoluta en relación con el área de los límites de la "celda". <xref:System.Windows.Documents.Table> no admite esta característica. Por último, un <xref:System.Windows.Controls.Grid> requiere menos recursos que un <xref:System.Windows.Documents.Table>, por lo que puede usar un @no__t 2 para mejorar el rendimiento.  
  
<a name="basic_table_structure"></a>   
### <a name="basic-table-structure"></a>Estructura básica de las tablas  
 <xref:System.Windows.Documents.Table> proporciona una presentación basada en cuadrícula formada por columnas (representadas por elementos <xref:System.Windows.Documents.TableColumn>) y filas (representadas por elementos <xref:System.Windows.Documents.TableRow>). los elementos <xref:System.Windows.Documents.TableColumn> no hospedan contenido; simplemente definen las columnas y características de las columnas. los elementos <xref:System.Windows.Documents.TableRow> deben estar hospedados en un elemento <xref:System.Windows.Documents.TableRowGroup>, que define una agrupación de filas para la tabla. los elementos <xref:System.Windows.Documents.TableCell>, que contienen el contenido real que va a presentar la tabla, deben estar hospedados en un elemento <xref:System.Windows.Documents.TableRow>. <xref:System.Windows.Documents.TableCell> solo puede contener elementos que se deriven de <xref:System.Windows.Documents.Block>.  Los elementos secundarios válidos para un <xref:System.Windows.Documents.TableCell> incluyen.  
  
- <xref:System.Windows.Documents.BlockUIContainer>  
  
- <xref:System.Windows.Documents.List>  
  
- <xref:System.Windows.Documents.Paragraph>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
> los elementos <xref:System.Windows.Documents.TableCell> no pueden hospedar directamente el contenido de texto. Para obtener más información sobre las reglas de contención de los elementos de contenido dinámico como <xref:System.Windows.Documents.TableCell>, consulte [información general sobre documentos dinámicos](flow-document-overview.md).  
  
> [!NOTE]
> <xref:System.Windows.Documents.Table> es similar al elemento <xref:System.Windows.Controls.Grid> pero tiene más funciones y, por lo tanto, requiere mayor sobrecarga de recursos.  
  
 En el ejemplo siguiente se define una tabla simple de 2 x 3 con XAML.  
  
 [!code-xaml[TableSnippets2#_Table_BasicLayout](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 En la ilustración siguiente, se muestra cómo se representa este ejemplo.  
  
 ![Captura de pantalla que muestra cómo se representa una tabla básica.](./media/table-overview/basic-table-render-example.png)  
  
<a name="table_containment"></a>   
### <a name="table-containment"></a>Contención de tablas  
 <xref:System.Windows.Documents.Table> deriva del elemento <xref:System.Windows.Documents.Block> y cumple las reglas comunes de los elementos de nivel de @no__t 2.  Un elemento <xref:System.Windows.Documents.Table> puede estar contenido en cualquiera de los siguientes elementos:  
  
- <xref:System.Windows.Documents.FlowDocument>  
  
- <xref:System.Windows.Documents.TableCell>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Floater>  
  
- <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>   
### <a name="row-groupings"></a>Agrupaciones de filas  
 El elemento <xref:System.Windows.Documents.TableRowGroup> proporciona una manera de agrupar filas arbitrariamente dentro de una tabla. cada fila de una tabla debe pertenecer a una agrupación de filas.  Las filas dentro de un grupo de filas comparten a menudo una finalidad común y se les puede asignar un estilo como grupo.  Un uso común para las agrupaciones de filas es separar las filas que tienen una finalidad especial, como filas de título, encabezado y pie de página, del contenido principal incluido en la tabla.  
  
 En el ejemplo siguiente se usa XAML para definir una tabla con filas de encabezado y pie de página con estilo.  
  
 [!code-xaml[TableSnippets2#_Table_RowGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 En la ilustración siguiente, se muestra cómo se representa este ejemplo.  
  
 @no__t 0Screenshot: Grupos de filas de tabla @ no__t-0(./media/table-rowgroups.png "Table_RowGroups")  
  
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
  
 @no__t 0Screenshot: Orden z&#45;de la tabla @ no__t-1(./media/table-zorder.png "Table_ZOrder")  
  
<a name="spanning_rows_or_columns"></a>   
### <a name="spanning-rows-or-columns"></a>Abarcar filas o columnas  
 Las celdas de la tabla se pueden configurar para que abarquen varias filas o columnas usando los atributos <xref:System.Windows.Documents.TableCell.RowSpan%2A> o <xref:System.Windows.Documents.TableCell.ColumnSpan%2A>, respectivamente.  
  
 Considere el ejemplo siguiente, en el que una celda abarca tres columnas.  
  
 [!code-xaml[TableSnippets2#_Table_ColumnSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 En la ilustración siguiente, se muestra cómo se representa este ejemplo.  
  
 @no__t 0Screenshot: Celda que abarca las tres columnas @ no__t-0(./media/table-columnspan.png "Table_ColumnSpan")  
  
<a name="building_a_table_with_code"></a>   
## <a name="building-a-table-with-code"></a>Creación de una tabla mediante código  
 En los siguientes ejemplos se muestra cómo crear mediante programación un <xref:System.Windows.Documents.Table> y rellenarlo con contenido. El contenido de la tabla se distribuye en cinco filas (representadas por objetos <xref:System.Windows.Documents.TableRow> contenidos en un objeto <xref:System.Windows.Documents.Table.RowGroups%2A>) y seis columnas (representadas por objetos <xref:System.Windows.Documents.TableColumn>). Las filas se usan para distintos fines de presentación, e incluyen una fila de título usada para dar título a toda la tabla, una fila de encabezado para describir las columnas de datos de la tabla, y una fila de pie de página con información de resumen.  Tenga en cuenta que los conceptos de filas de "título", "encabezado" y "pie de página" no son inherentes a la tabla; se trata simplemente de filas con características diferentes. Las celdas de la tabla contienen el contenido real, que puede estar formado por texto, imágenes o casi cualquier otro elemento [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
 En primer lugar, se crea un <xref:System.Windows.Documents.FlowDocument> para hospedar el <xref:System.Windows.Documents.Table> y se crea un nuevo <xref:System.Windows.Documents.Table> y se agrega al contenido del <xref:System.Windows.Documents.FlowDocument>.  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 A continuación, se crean seis objetos <xref:System.Windows.Documents.TableColumn> y se agregan a la colección <xref:System.Windows.Documents.Table.Columns%2A> de la tabla, con algún formato aplicado.  
  
> [!NOTE]
> Tenga en cuenta que la colección <xref:System.Windows.Documents.Table.Columns%2A> de la tabla usa la indexación estándar basada en cero.  
  
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
