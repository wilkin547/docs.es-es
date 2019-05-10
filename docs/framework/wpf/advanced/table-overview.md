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
ms.openlocfilehash: 01ab11d8e3c1d2c84514770816ca9c9eab0835b6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649190"
---
# <a name="table-overview"></a><span data-ttu-id="e874f-102">Información general sobre tablas</span><span class="sxs-lookup"><span data-stu-id="e874f-102">Table Overview</span></span>
<span data-ttu-id="e874f-103"><xref:System.Windows.Documents.Table> es un elemento de nivel de bloque que admite presentación basada en cuadrícula de contenido de documentos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="e874f-103"><xref:System.Windows.Documents.Table> is a block level element that supports grid-based presentation of Flow document content.</span></span> <span data-ttu-id="e874f-104">La flexibilidad de este elemento lo hace muy útil, pero también más complicado de entender y usar correctamente.</span><span class="sxs-lookup"><span data-stu-id="e874f-104">The flexibility of this element makes it very useful, but also makes it more complicated to understand and use correctly.</span></span>  
  
 <span data-ttu-id="e874f-105">Este tema contiene las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="e874f-105">This topic contains the following sections.</span></span>  
  
- [<span data-ttu-id="e874f-106">Fundamentos de tablas</span><span class="sxs-lookup"><span data-stu-id="e874f-106">Table Basics</span></span>](#table_basics)  
  
- [<span data-ttu-id="e874f-107">¿En qué se diferencian las tablas de las cuadrículas?</span><span class="sxs-lookup"><span data-stu-id="e874f-107">How is Table Different then Grid?</span></span>](#table_vs_Grid)  
  
- [<span data-ttu-id="e874f-108">Estructura básica de las tablas</span><span class="sxs-lookup"><span data-stu-id="e874f-108">Basic Table Structure</span></span>](#basic_table_structure)  
  
- [<span data-ttu-id="e874f-109">Contención de tablas</span><span class="sxs-lookup"><span data-stu-id="e874f-109">Table Containment</span></span>](#table_containment)  
  
- [<span data-ttu-id="e874f-110">Agrupaciones de filas</span><span class="sxs-lookup"><span data-stu-id="e874f-110">Row Groupings</span></span>](#row_groupings)  
  
- [<span data-ttu-id="e874f-111">Prioridad de representación del fondo</span><span class="sxs-lookup"><span data-stu-id="e874f-111">Background Rendering Precedence</span></span>](#rendering_precedence)  
  
- [<span data-ttu-id="e874f-112">Abarcar filas o columnas</span><span class="sxs-lookup"><span data-stu-id="e874f-112">Spanning Rows or Columns</span></span>](#spanning_rows_or_columns)  
  
- [<span data-ttu-id="e874f-113">Creación de una tabla mediante código</span><span class="sxs-lookup"><span data-stu-id="e874f-113">Building a Table With Code</span></span>](#building_a_table_with_code)  
  
- <span data-ttu-id="e874f-114">[Temas relacionados]</span><span class="sxs-lookup"><span data-stu-id="e874f-114">[Related Topics]</span></span> 
  
<a name="table_basics"></a>   
## <a name="table-basics"></a><span data-ttu-id="e874f-115">Fundamentos de tablas</span><span class="sxs-lookup"><span data-stu-id="e874f-115">Table Basics</span></span>  
  
<a name="table_vs_Grid"></a>   
### <a name="how-is-table-different-then-grid"></a><span data-ttu-id="e874f-116">¿En qué se diferencian las tablas de las cuadrículas?</span><span class="sxs-lookup"><span data-stu-id="e874f-116">How is Table Different then Grid?</span></span>  
 <span data-ttu-id="e874f-117"><xref:System.Windows.Documents.Table> y <xref:System.Windows.Controls.Grid> comparten funcionalidades comunes, pero cada una es adecuada para escenarios diferentes.</span><span class="sxs-lookup"><span data-stu-id="e874f-117"><xref:System.Windows.Documents.Table> and <xref:System.Windows.Controls.Grid> share some common functionality, but each is best suited for different scenarios.</span></span> <span data-ttu-id="e874f-118">Un <xref:System.Windows.Documents.Table> está diseñado para su uso en contenido dinámico (consulte [Flow Document Overview](flow-document-overview.md) para obtener más información sobre el contenido dinámico).</span><span class="sxs-lookup"><span data-stu-id="e874f-118">A <xref:System.Windows.Documents.Table> is designed for use within flow content (see [Flow Document Overview](flow-document-overview.md) for more information on flow content).</span></span> <span data-ttu-id="e874f-119">Las cuadrículas son más apropiadas para formularios (básicamente, en cualquier lugar excepto en el contenido dinámico).</span><span class="sxs-lookup"><span data-stu-id="e874f-119">Grids are best used inside of forms (basically anywhere outside of flow content).</span></span> <span data-ttu-id="e874f-120">Dentro de un <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Table> admite el flujo de los comportamientos del contenido, como paginación, ajuste dinámico de columnas y selección de contenido mientras una <xref:System.Windows.Controls.Grid> no lo hace.</span><span class="sxs-lookup"><span data-stu-id="e874f-120">Within a <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Table> supports flow content behaviors like pagination, column reflow, and content selection while a <xref:System.Windows.Controls.Grid> does not.</span></span> <span data-ttu-id="e874f-121">Un <xref:System.Windows.Controls.Grid> por otro lado se utiliza fuera de un <xref:System.Windows.Documents.FlowDocument> por diversos motivos incluidos <xref:System.Windows.Controls.Grid> agrega elementos basándose en un índice de fila y columna, <xref:System.Windows.Documents.Table> no lo hace.</span><span class="sxs-lookup"><span data-stu-id="e874f-121">A <xref:System.Windows.Controls.Grid> on the other hand is best used outside of a <xref:System.Windows.Documents.FlowDocument> for many reasons including <xref:System.Windows.Controls.Grid> adds elements based on a row and column index, <xref:System.Windows.Documents.Table> does not.</span></span> <span data-ttu-id="e874f-122">El <xref:System.Windows.Controls.Grid> elemento permite la disposición en capas del contenido secundario, lo que permite más de un elemento dentro de una sola "celda".</span><span class="sxs-lookup"><span data-stu-id="e874f-122">The <xref:System.Windows.Controls.Grid> element allows layering of child content, allowing more than one element to exist within a single "cell."</span></span> <span data-ttu-id="e874f-123"><xref:System.Windows.Documents.Table> no admite la disposición en capas.</span><span class="sxs-lookup"><span data-stu-id="e874f-123"><xref:System.Windows.Documents.Table> does not support layering.</span></span> <span data-ttu-id="e874f-124">Los elementos secundarios de un <xref:System.Windows.Controls.Grid> puede colocar de manera absoluta en relación con el área de los límites "celda".</span><span class="sxs-lookup"><span data-stu-id="e874f-124">Child elements of a <xref:System.Windows.Controls.Grid> can be absolutely positioned relative to the area of their "cell" boundaries.</span></span> <span data-ttu-id="e874f-125"><xref:System.Windows.Documents.Table> no se admite esta característica.</span><span class="sxs-lookup"><span data-stu-id="e874f-125"><xref:System.Windows.Documents.Table> does not support this feature.</span></span> <span data-ttu-id="e874f-126">Por último, un <xref:System.Windows.Controls.Grid> requiere menos recursos, a continuación, un <xref:System.Windows.Documents.Table> por lo que puede usar un <xref:System.Windows.Controls.Grid> para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="e874f-126">Finally, a <xref:System.Windows.Controls.Grid> requires less resources then a <xref:System.Windows.Documents.Table> so consider using a <xref:System.Windows.Controls.Grid> to improve performance.</span></span>  
  
<a name="basic_table_structure"></a>   
### <a name="basic-table-structure"></a><span data-ttu-id="e874f-127">Estructura básica de las tablas</span><span class="sxs-lookup"><span data-stu-id="e874f-127">Basic Table Structure</span></span>  
 <span data-ttu-id="e874f-128"><xref:System.Windows.Documents.Table> Proporciona una presentación basada en cuadrícula que consta de columnas (representado por <xref:System.Windows.Documents.TableColumn> elementos) y filas (representados por <xref:System.Windows.Documents.TableRow> elementos).</span><span class="sxs-lookup"><span data-stu-id="e874f-128"><xref:System.Windows.Documents.Table> provides a grid-based presentation consisting of columns (represented by <xref:System.Windows.Documents.TableColumn> elements) and rows (represented by <xref:System.Windows.Documents.TableRow> elements).</span></span> <span data-ttu-id="e874f-129"><xref:System.Windows.Documents.TableColumn> los elementos no hospedan contenido; simplemente definen las columnas y las características de las columnas.</span><span class="sxs-lookup"><span data-stu-id="e874f-129"><xref:System.Windows.Documents.TableColumn> elements do not host content; they simply define columns and characteristics of columns.</span></span> <span data-ttu-id="e874f-130"><xref:System.Windows.Documents.TableRow> los elementos se deben hospedar en un <xref:System.Windows.Documents.TableRowGroup> elemento, que define una agrupación de filas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="e874f-130"><xref:System.Windows.Documents.TableRow> elements must be hosted in a <xref:System.Windows.Documents.TableRowGroup> element, which defines a grouping of rows for the table.</span></span> <span data-ttu-id="e874f-131"><xref:System.Windows.Documents.TableCell> los elementos, que incluyen el contenido real que se presentará en la tabla, se deben hospedar en un <xref:System.Windows.Documents.TableRow> elemento.</span><span class="sxs-lookup"><span data-stu-id="e874f-131"><xref:System.Windows.Documents.TableCell> elements, which contain the actual content to be presented by the table, must be hosted in a <xref:System.Windows.Documents.TableRow> element.</span></span> <span data-ttu-id="e874f-132"><xref:System.Windows.Documents.TableCell> solo puede contener elementos que se derivan de <xref:System.Windows.Documents.Block>.</span><span class="sxs-lookup"><span data-stu-id="e874f-132"><xref:System.Windows.Documents.TableCell> may only contain elements that derive from <xref:System.Windows.Documents.Block>.</span></span>  <span data-ttu-id="e874f-133">Los elementos secundarios válidos para un <xref:System.Windows.Documents.TableCell> incluir.</span><span class="sxs-lookup"><span data-stu-id="e874f-133">Valid child elements for a <xref:System.Windows.Documents.TableCell> include.</span></span>  
  
- <xref:System.Windows.Documents.BlockUIContainer>  
  
- <xref:System.Windows.Documents.List>  
  
- <xref:System.Windows.Documents.Paragraph>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
>  <span data-ttu-id="e874f-134"><xref:System.Windows.Documents.TableCell> los elementos no pueden hospedar directamente contenido de texto.</span><span class="sxs-lookup"><span data-stu-id="e874f-134"><xref:System.Windows.Documents.TableCell> elements may not directly host text content.</span></span> <span data-ttu-id="e874f-135">Para obtener más información acerca de las reglas de contención para el flujo de elementos de contenido como <xref:System.Windows.Documents.TableCell>, consulte [Flow Document Overview](flow-document-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e874f-135">For more information about the containment rules for flow content elements like <xref:System.Windows.Documents.TableCell>, see [Flow Document Overview](flow-document-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e874f-136"><xref:System.Windows.Documents.Table> es similar a la <xref:System.Windows.Controls.Grid> elemento, pero tiene más funciones y, por lo tanto, requiere mayor consumo de recursos.</span><span class="sxs-lookup"><span data-stu-id="e874f-136"><xref:System.Windows.Documents.Table> is similar to the <xref:System.Windows.Controls.Grid> element but has more capabilities and, therefore, requires greater resource overhead.</span></span>  
  
 <span data-ttu-id="e874f-137">En el ejemplo siguiente se define una tabla de 2 x 3 simple con [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e874f-137">The following example defines a simple 2 x 3 table with [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)].</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_BasicLayout](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 <span data-ttu-id="e874f-138">En la ilustración siguiente, se muestra cómo se representa este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e874f-138">The following figure shows how this example renders.</span></span>  
  
 ![Captura de pantalla que muestra cómo se representa una tabla básica.](./media/table-overview/basic-table-render-example.png)  
  
<a name="table_containment"></a>   
### <a name="table-containment"></a><span data-ttu-id="e874f-140">Contención de tablas</span><span class="sxs-lookup"><span data-stu-id="e874f-140">Table Containment</span></span>  
 <span data-ttu-id="e874f-141"><xref:System.Windows.Documents.Table> deriva el <xref:System.Windows.Documents.Block> elemento y cumple las reglas comunes para <xref:System.Windows.Documents.Block> elementos de nivel.</span><span class="sxs-lookup"><span data-stu-id="e874f-141"><xref:System.Windows.Documents.Table> derives from the <xref:System.Windows.Documents.Block> element, and adheres to the common rules for <xref:System.Windows.Documents.Block> level elements.</span></span>  <span data-ttu-id="e874f-142">Un <xref:System.Windows.Documents.Table> elemento puede contener cualquiera de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="e874f-142">A <xref:System.Windows.Documents.Table> element may be contained by any of the following elements:</span></span>  
  
- <xref:System.Windows.Documents.FlowDocument>  
  
- <xref:System.Windows.Documents.TableCell>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Floater>  
  
- <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>   
### <a name="row-groupings"></a><span data-ttu-id="e874f-143">Agrupaciones de filas</span><span class="sxs-lookup"><span data-stu-id="e874f-143">Row Groupings</span></span>  
 <span data-ttu-id="e874f-144">El <xref:System.Windows.Documents.TableRowGroup> elemento proporciona una manera de agrupar filas arbitrariamente dentro de una tabla, todas las filas de una tabla deben pertenecer a una agrupación de filas.</span><span class="sxs-lookup"><span data-stu-id="e874f-144">The <xref:System.Windows.Documents.TableRowGroup> element provides a way to arbitrarily group rows within a table; every row in a table must belong to a row grouping.</span></span>  <span data-ttu-id="e874f-145">Las filas dentro de un grupo de filas comparten a menudo una finalidad común y se les puede asignar un estilo como grupo.</span><span class="sxs-lookup"><span data-stu-id="e874f-145">Rows within a row group often share a common intent, and may be styled as a group.</span></span>  <span data-ttu-id="e874f-146">Un uso común para las agrupaciones de filas es separar las filas que tienen una finalidad especial, como filas de título, encabezado y pie de página, del contenido principal incluido en la tabla.</span><span class="sxs-lookup"><span data-stu-id="e874f-146">A common use for row groupings is to separate special-purpose rows, such as a title, header, and footer rows, from the primary content contained by the table.</span></span>  
  
 <span data-ttu-id="e874f-147">En el ejemplo siguiente se usa [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] para definir una tabla con filas de encabezado y pie de página con estilo.</span><span class="sxs-lookup"><span data-stu-id="e874f-147">The following example uses [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] to define a table with styled header and footer rows.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_RowGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 <span data-ttu-id="e874f-148">En la ilustración siguiente, se muestra cómo se representa este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e874f-148">The following figure shows how this example renders.</span></span>  
  
 <span data-ttu-id="e874f-149">![Captura de pantalla: Grupos de filas de tabla](./media/table-rowgroups.png "Table_RowGroups")</span><span class="sxs-lookup"><span data-stu-id="e874f-149">![Screenshot: Table row groups](./media/table-rowgroups.png "Table_RowGroups")</span></span>  
  
<a name="rendering_precedence"></a>   
### <a name="background-rendering-precedence"></a><span data-ttu-id="e874f-150">Prioridad de representación del fondo</span><span class="sxs-lookup"><span data-stu-id="e874f-150">Background Rendering Precedence</span></span>  
 <span data-ttu-id="e874f-151">Los elementos de tabla se representan en el orden siguiente (orden z ascendente).</span><span class="sxs-lookup"><span data-stu-id="e874f-151">Table elements render in the following order (z-order from lowest to highest).</span></span> <span data-ttu-id="e874f-152">Este orden no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="e874f-152">This order cannot be changed.</span></span> <span data-ttu-id="e874f-153">Por ejemplo, no existe una propiedad de "orden Z" para estos elementos que se pueda usar para invalidar el orden establecido.</span><span class="sxs-lookup"><span data-stu-id="e874f-153">For example, there is no "Z-order" property for these elements that you can use to override this established order.</span></span>  
  
1. <xref:System.Windows.Documents.Table>  
  
2. <xref:System.Windows.Documents.TableColumn>  
  
3. <xref:System.Windows.Documents.TableRowGroup>  
  
4. <xref:System.Windows.Documents.TableRow>  
  
5. <xref:System.Windows.Documents.TableCell>  
  
 <span data-ttu-id="e874f-154">Observe el ejemplo siguiente, en el que se definen los colores de fondo para cada uno de estos elementos dentro de una tabla.</span><span class="sxs-lookup"><span data-stu-id="e874f-154">Consider the following example, which defines background colors for each of these elements within a table.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_ZOrder](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_zorder)]  
  
 <span data-ttu-id="e874f-155">En la ilustración siguiente se muestra cómo se representa este ejemplo (mostrando únicamente los colores de fondo).</span><span class="sxs-lookup"><span data-stu-id="e874f-155">The following figure shows how this example renders (showing background colors only).</span></span>  
  
 <span data-ttu-id="e874f-156">![Captura de pantalla: Tabla z&#45;orden](./media/table-zorder.png "Table_ZOrder")</span><span class="sxs-lookup"><span data-stu-id="e874f-156">![Screenshot: Table z&#45;order](./media/table-zorder.png "Table_ZOrder")</span></span>  
  
<a name="spanning_rows_or_columns"></a>   
### <a name="spanning-rows-or-columns"></a><span data-ttu-id="e874f-157">Abarcar filas o columnas</span><span class="sxs-lookup"><span data-stu-id="e874f-157">Spanning Rows or Columns</span></span>  
 <span data-ttu-id="e874f-158">Las celdas de tabla pueden configurarse para abarcar varias filas o columnas mediante el uso de la <xref:System.Windows.Documents.TableCell.RowSpan%2A> o <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> atributos, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="e874f-158">Table cells may be configured to span multiple rows or columns by using the <xref:System.Windows.Documents.TableCell.RowSpan%2A> or <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> attributes, respectively.</span></span>  
  
 <span data-ttu-id="e874f-159">Considere el ejemplo siguiente, en el que una celda abarca tres columnas.</span><span class="sxs-lookup"><span data-stu-id="e874f-159">Consider the following example, in which a cell spans three columns.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_ColumnSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 <span data-ttu-id="e874f-160">En la ilustración siguiente, se muestra cómo se representa este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e874f-160">The following figure shows how this example renders.</span></span>  
  
 <span data-ttu-id="e874f-161">![Captura de pantalla: Celda que abarca las tres columnas](./media/table-columnspan.png "Table_ColumnSpan")</span><span class="sxs-lookup"><span data-stu-id="e874f-161">![Screenshot: Cell spanning all three columns](./media/table-columnspan.png "Table_ColumnSpan")</span></span>  
  
<a name="building_a_table_with_code"></a>   
## <a name="building-a-table-with-code"></a><span data-ttu-id="e874f-162">Creación de una tabla mediante código</span><span class="sxs-lookup"><span data-stu-id="e874f-162">Building a Table With Code</span></span>  
 <span data-ttu-id="e874f-163">Los ejemplos siguientes muestran cómo crear mediante programación un <xref:System.Windows.Documents.Table> y rellenarla con contenido.</span><span class="sxs-lookup"><span data-stu-id="e874f-163">The following examples show how to programmatically create a <xref:System.Windows.Documents.Table> and populate it with content.</span></span> <span data-ttu-id="e874f-164">El contenido de la tabla se distribuye en cinco filas (representados por <xref:System.Windows.Documents.TableRow> objetos incluidos en un <xref:System.Windows.Documents.Table.RowGroups%2A> objeto) y seis columnas (representado por <xref:System.Windows.Documents.TableColumn> objetos).</span><span class="sxs-lookup"><span data-stu-id="e874f-164">The contents of the table are apportioned into five rows (represented by <xref:System.Windows.Documents.TableRow> objects contained in a <xref:System.Windows.Documents.Table.RowGroups%2A> object) and six columns (represented by <xref:System.Windows.Documents.TableColumn> objects).</span></span> <span data-ttu-id="e874f-165">Las filas se usan para distintos fines de presentación, e incluyen una fila de título usada para dar título a toda la tabla, una fila de encabezado para describir las columnas de datos de la tabla, y una fila de pie de página con información de resumen.</span><span class="sxs-lookup"><span data-stu-id="e874f-165">The rows are used for different presentation purposes, including a title row intended to title the entire table, a header row to describe the columns of data in the table, and a footer row with summary information.</span></span>  <span data-ttu-id="e874f-166">Tenga en cuenta que los conceptos de filas de "título", "encabezado" y "pie de página" no son inherentes a la tabla; se trata simplemente de filas con características diferentes.</span><span class="sxs-lookup"><span data-stu-id="e874f-166">Note that the notion of "title", "header", and "footer" rows are not inherent to the table; these are simply rows with different characteristics.</span></span> <span data-ttu-id="e874f-167">Las celdas de tabla incluyen el contenido real, que puede estar formado por texto, imágenes o casi cualquier otro [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] elemento.</span><span class="sxs-lookup"><span data-stu-id="e874f-167">Table cells contain the actual content, which can be comprised of text, images, or nearly any other [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] element.</span></span>  
  
 <span data-ttu-id="e874f-168">En primer lugar, un <xref:System.Windows.Documents.FlowDocument> se crea al host la <xref:System.Windows.Documents.Table>y un nuevo <xref:System.Windows.Documents.Table> se crea y agrega al contenido de la <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="e874f-168">First, a <xref:System.Windows.Documents.FlowDocument> is created to host the <xref:System.Windows.Documents.Table>, and a new <xref:System.Windows.Documents.Table> is created and added to the contents of the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 <span data-ttu-id="e874f-169">A continuación, seis <xref:System.Windows.Documents.TableColumn> objetos se crean y se agregan a la tabla <xref:System.Windows.Documents.Table.Columns%2A> colección aplicarles formato.</span><span class="sxs-lookup"><span data-stu-id="e874f-169">Next, six <xref:System.Windows.Documents.TableColumn> objects are created and added to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection, with some formatting applied.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e874f-170">Tenga en cuenta que la tabla <xref:System.Windows.Documents.Table.Columns%2A> colección utiliza la indización de base cero estándar.</span><span class="sxs-lookup"><span data-stu-id="e874f-170">Note that the table's <xref:System.Windows.Documents.Table.Columns%2A> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
 <span data-ttu-id="e874f-171">Luego, se crea una fila de título y se agrega a la tabla tras aplicarle formato.</span><span class="sxs-lookup"><span data-stu-id="e874f-171">Next, a title row is created and added to the table with some formatting applied.</span></span>  <span data-ttu-id="e874f-172">La fila de título contiene una sola celda que abarca las seis columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="e874f-172">The title row happens to contain a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
 <span data-ttu-id="e874f-173">Después, se crea una fila de encabezado y se agrega a la tabla, y se crean y rellenan con contenido las celdas de la fila de encabezado.</span><span class="sxs-lookup"><span data-stu-id="e874f-173">Next, a header row is created and added to the table, and the cells in the header row are created and populated with content.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
 <span data-ttu-id="e874f-174">Después, se crea una fila para datos y se agrega a la tabla, y se crean y rellenan con contenido las celdas de esta fila.</span><span class="sxs-lookup"><span data-stu-id="e874f-174">Next, a row for data is created and added to the table, and the cells in this row are created and populated with content.</span></span>  <span data-ttu-id="e874f-175">La creación de esta fila es similar a la creación de la fila de encabezado con un formato ligeramente diferente.</span><span class="sxs-lookup"><span data-stu-id="e874f-175">Building this row is similar to building the header row, with slightly different formatting applied.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
 <span data-ttu-id="e874f-176">Por último, se crea una fila de pie de página, se agrega y se le da formato.</span><span class="sxs-lookup"><span data-stu-id="e874f-176">Finally, a footer row is created, added, and formatted.</span></span>  <span data-ttu-id="e874f-177">Al igual que la fila de título, el pie de página contiene una sola celda que abarca las seis columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="e874f-177">Like the title row, the footer contains a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a><span data-ttu-id="e874f-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="e874f-178">See also</span></span>

- [<span data-ttu-id="e874f-179">Información general sobre documentos dinámicos</span><span class="sxs-lookup"><span data-stu-id="e874f-179">Flow Document Overview</span></span>](flow-document-overview.md)
- [<span data-ttu-id="e874f-180">Definir una tabla con XAML</span><span class="sxs-lookup"><span data-stu-id="e874f-180">Define a Table with XAML</span></span>](how-to-define-a-table-with-xaml.md)
- [<span data-ttu-id="e874f-181">Documentos en WPF</span><span class="sxs-lookup"><span data-stu-id="e874f-181">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="e874f-182">Usar elementos de contenido dinámico</span><span class="sxs-lookup"><span data-stu-id="e874f-182">Use Flow Content Elements</span></span>](how-to-use-flow-content-elements.md)
