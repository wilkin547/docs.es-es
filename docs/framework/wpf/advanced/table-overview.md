---
title: "Informaci&#243;n general sobre tablas | Microsoft Docs"
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
  - "documentos, tablas"
  - "elementos de contenido dinámico [WPF], Tabla"
  - "tablas"
ms.assetid: 5e1105f4-8fc4-473a-ba55-88c8e71386e6
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Informaci&#243;n general sobre tablas
<xref:System.Windows.Documents.Table> es un elemento de nivel de bloque que admite la presentación basada en cuadrícula de contenido de documentos dinámicos.  La flexibilidad de este elemento lo hace muy útil, pero también más complicado de entender y utilizar correctamente.  
  
 Este tema contiene las secciones siguientes.  
  
-   [Fundamentos de tablas](#table_basics)  
  
-   [¿En qué se diferencian las tablas de las cuadrículas?](#table_vs_Grid)  
  
-   [Estructura básica de las tablas](#basic_table_structure)  
  
-   [Contención de tablas](#table_containment)  
  
-   [Agrupaciones de filas](#row_groupings)  
  
-   [Prioridad de representación del fondo](#rednering_precedence)  
  
-   [Abarcar filas o columnas](#spanning_rows_or_columns)  
  
-   [Compilar una tabla mediante código](#building_a_table_with_code)  
  
-   [Temas relacionados](#see_also)  
  
<a name="table_basics"></a>   
## Fundamentos de tablas  
  
<a name="table_vs_Grid"></a>   
### ¿En qué se diferencian las tablas de las cuadrículas?  
 <xref:System.Windows.Documents.Table> y <xref:System.Windows.Controls.Grid> comparten funcionalidades comunes, pero cada elemento es más apropiado para determinados escenarios.  <xref:System.Windows.Documents.Table> se ha diseñado para su uso en contenido dinámico \(vea [Información general sobre documentos dinámicos](../../../../docs/framework/wpf/advanced/flow-document-overview.md) para obtener más información sobre el contenido dinámico\).  Las cuadrículas son más apropiadas para formularios \(básicamente, en cualquier lugar excepto en el contenido dinámico\).  Dentro de un <xref:System.Windows.Documents.FlowDocument>, una <xref:System.Windows.Documents.Table> admite los comportamientos del contenido dinámico, como la paginación, el ajuste dinámico de columnas y la selección de contenido, mientras que <xref:System.Windows.Controls.Grid> no.  Por su parte, <xref:System.Windows.Controls.Grid> es más apropiado fuera de un <xref:System.Windows.Documents.FlowDocument> por numerosas razones; una de ellas es que <xref:System.Windows.Controls.Grid> agrega elementos basándose en un índice de fila y columna, y <xref:System.Windows.Documents.Table> no.  El elemento <xref:System.Windows.Controls.Grid> permite la disposición en capas del contenido secundario, lo que permite que haya más de un elemento dentro de una sola "celda". <xref:System.Windows.Documents.Table> no admite la disposición en capas.  Los elementos secundarios de <xref:System.Windows.Controls.Grid> se pueden colocar de manera absoluta en relación con el área de los límites de la "celda".  <xref:System.Windows.Documents.Table> no admite esta característica.  Finalmente, <xref:System.Windows.Controls.Grid> requiere menos los recursos que <xref:System.Windows.Documents.Table>, por lo que puede ser conveniente utilizar <xref:System.Windows.Controls.Grid> para mejorar el rendimiento.  
  
<a name="basic_table_structure"></a>   
### Estructura básica de las tablas  
 <xref:System.Windows.Documents.Table> proporciona una presentación basada en cuadrícula que está compuesto de columnas \(representadas por elementos <xref:System.Windows.Documents.TableColumn> y filas \(representadas por elementos <xref:System.Windows.Documents.TableRow>\).  Los elementos <xref:System.Windows.Documents.TableColumn> no hospedan contenido; simplemente definen las columnas y sus características.  Los elementos <xref:System.Windows.Documents.TableRow> se deben hospedar en un elemento <xref:System.Windows.Documents.TableRowGroup>, que define una agrupación de filas para la tabla.  Los elementos <xref:System.Windows.Documents.TableCell> que incluyen el contenido real que la tabla va a presentar, se deben hospedar en un elemento <xref:System.Windows.Documents.TableRow>.  <xref:System.Windows.Documents.TableCell> sólo puede contener elementos que se derivan de <xref:System.Windows.Documents.Block>.  Entre los elementos secundarios válidos de <xref:System.Windows.Documents.TableCell> se incluyen:  
  
-   <xref:System.Windows.Documents.BlockUIContainer>  
  
-   <xref:System.Windows.Documents.List>  
  
-   <xref:System.Windows.Documents.Paragraph>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
>  Los elementos <xref:System.Windows.Documents.TableCell> no pueden hospedar directamente contenido de texto.  Para obtener más información sobre las reglas de contención de los elementos de contenido dinámico como <xref:System.Windows.Documents.TableCell>, consulte [Información general sobre documentos dinámicos](../../../../docs/framework/wpf/advanced/flow-document-overview.md).  
  
> [!NOTE]
>  <xref:System.Windows.Documents.Table> es similar al elemento <xref:System.Windows.Controls.Grid> pero tiene más funciones y, por consiguiente, requiere mayor consumo de recursos.  
  
 En el ejemplo siguiente se define una tabla simple de 2 x 3, con [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)].  
  
 [!code-xml[TableSnippets2#_Table_BasicLayout](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 En la ilustración siguiente se muestra cómo se representa este ejemplo.  
  
 ![Captura de pantalla: Representar una tabla básica](../../../../docs/framework/wpf/advanced/media/basictablerrender.png "BasicTablerRender")  
  
<a name="table_containment"></a>   
### Contención de tablas  
 <xref:System.Windows.Documents.Table> se deriva del elemento <xref:System.Windows.Documents.Block> y cumple las reglas comunes para los elementos de nivel de bloque, <xref:System.Windows.Documents.Block>.  Cualquiera de los elementos siguientes puede contener un elemento <xref:System.Windows.Documents.Table>:  
  
-   <xref:System.Windows.Documents.FlowDocument>  
  
-   <xref:System.Windows.Documents.TableCell>  
  
-   <xref:System.Windows.Controls.ListBoxItem>  
  
-   <xref:System.Windows.Controls.ListViewItem>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.Floater>  
  
-   <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>   
### Agrupaciones de filas  
 El elemento <xref:System.Windows.Documents.TableRowGroup> proporciona una manera de agrupar filas arbitrariamente dentro de una tabla; cada fila de una tabla debe pertenecer a una agrupación de filas.  Las filas dentro de un grupo de filas comparten a menudo una finalidad común y se les puede asignar un estilo como grupo.  Una costumbre habitual para las agrupaciones de filas es separar las filas que tienen una finalidad especial, como títulos, encabezados y filas del pie de página, del contenido principal incluido en la tabla.  
  
 En el ejemplo siguiente se utiliza [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] para definir una tabla con filas de encabezado y pie de página con estilo.  
  
 [!code-xml[TableSnippets2#_Table_RowGroups](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 En la ilustración siguiente se muestra cómo se representa este ejemplo.  
  
 ![Captura de pantalla: Grupos de filas de tablas](../../../../docs/framework/wpf/advanced/media/table-rowgroups.png "Table\_RowGroups")  
  
<a name="renderning_precedence"></a>   
### Prioridad de representación del fondo  
 Los elementos de tabla se representan en el orden siguiente \([orden z](GTMT) ascendente\).  Este orden no se puede modificar.  Por ejemplo, no existe una propiedad de orden z para estos elementos que se pueda utilizar para invalidar el orden establecido.  
  
1.  <xref:System.Windows.Documents.Table>  
  
2.  <xref:System.Windows.Documents.TableColumn>  
  
3.  <xref:System.Windows.Documents.TableRowGroup>  
  
4.  <xref:System.Windows.Documents.TableRow>  
  
5.  <xref:System.Windows.Documents.TableCell>  
  
 Estudie el ejemplo siguiente, en el que se definen los colores de fondo para cada uno de estos elementos dentro de una tabla.  
  
 [!code-xml[TableSnippets2#_Table_ZOrder](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_zorder)]  
  
 En la ilustración siguiente se muestra cómo se representa este ejemplo \(mostrando únicamente los colores de fondo\).  
  
 ![Captura de pantalla: Orden z de tabla](../../../../docs/framework/wpf/advanced/media/table-zorder.png "Table\_ZOrder")  
  
<a name="spanning_rows_or_columns"></a>   
### Abarcar filas o columnas  
 Las celdas de una tabla se pueden configurar para abarcar varias filas o columnas utilizando los atributos <xref:System.Windows.Documents.TableCell.RowSpan%2A> o <xref:System.Windows.Documents.TableCell.ColumnSpan%2A>, respectivamente.  
  
 Estudie el ejemplo siguiente, en el que una celda abarca tres columnas.  
  
 [!code-xml[TableSnippets2#_Table_ColumnSpan](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 En la ilustración siguiente se muestra cómo se representa este ejemplo.  
  
 ![Captura de pantalla: Celda que abarca las tres columnas](../../../../docs/framework/wpf/advanced/media/table-columnspan.png "Table\_ColumnSpan")  
  
<a name="building_a_table_with_code"></a>   
## Compilar una tabla mediante código  
 En los ejemplos siguientes se muestra cómo crear una <xref:System.Windows.Documents.Table> y rellenarla con contenido mediante programación.  El contenido de la tabla se distribuye en cinco filas \(representadas por objetos <xref:System.Windows.Documents.TableRow> contenidos en un objeto <xref:System.Windows.Documents.Table.RowGroups%2A>\) y seis columnas \(representadas por objetos <xref:System.Windows.Documents.TableColumn> \).  Las filas se utilizan para distintos fines de presentación, e incluyen una fila de título utilizada para dar título a toda la tabla, una fila de encabezado para describir las columnas de datos de la tabla, y una fila de pie de página con información de resumen.  Observe que los conceptos de filas de "título", "encabezado" y "pie de página" no son inherentes a la tabla; se trata simplemente de filas con características diferentes.  Las celdas de la tabla incluyen el contenido real, que puede estar compuesto de texto, imágenes o casi cualquier otro elemento de la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
 En primer lugar, se crea un <xref:System.Windows.Documents.FlowDocument> para hospedar <xref:System.Windows.Documents.Table>. También se crea una nueva <xref:System.Windows.Documents.Table> y se agrega al contenido de <xref:System.Windows.Documents.FlowDocument>.  
  
 [!code-csharp[TableSnippets#_TableCreate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 A continuación, se crean seis objetos <xref:System.Windows.Documents.TableColumn> y se agregan a la colección <xref:System.Windows.Documents.Table.Columns%2A> de la tabla, tras aplicarles formato.  
  
> [!NOTE]
>  Observe que la colección <xref:System.Windows.Documents.Table.Columns%2A> de la tabla utiliza la indización estándar basada en cero.  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
 Luego, se crea una fila de título y se agrega a la tabla tras aplicarle formato.  La fila de título contiene una sola celda que abarca las seis columnas de la tabla.  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
 Después, se crea una fila de encabezado y se agrega a la tabla, y se crean y rellenan con contenido las celdas de la fila de encabezado.  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
 En este momento, se crea una fila de datos y se agrega a la tabla, y se crean y rellenan con contenido las celdas de esta fila.  Compilar esta fila es similar a compilar la fila de encabezado, con un formato ligeramente diferente.  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
 Por último, se crea una fila de pie de página, se agregó y se le da formato.  Al igual que la fila de título, el pie de página contiene una sola celda que abarca las seis columnas de la tabla.  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## Vea también  
 [Información general sobre documentos dinámicos](../../../../docs/framework/wpf/advanced/flow-document-overview.md)   
 [Definir una tabla con XAML](../../../../docs/framework/wpf/advanced/how-to-define-a-table-with-xaml.md)   
 [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Usar elementos de contenido dinámico](../../../../docs/framework/wpf/advanced/how-to-use-flow-content-elements.md)