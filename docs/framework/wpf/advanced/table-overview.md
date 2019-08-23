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
# <a name="table-overview"></a><span data-ttu-id="655d3-102">Información general sobre tablas</span><span class="sxs-lookup"><span data-stu-id="655d3-102">Table Overview</span></span>
<span data-ttu-id="655d3-103"><xref:System.Windows.Documents.Table>es un elemento de nivel de bloque que admite la presentación basada en cuadrícula del contenido del documento dinámico.</span><span class="sxs-lookup"><span data-stu-id="655d3-103"><xref:System.Windows.Documents.Table> is a block level element that supports grid-based presentation of Flow document content.</span></span> <span data-ttu-id="655d3-104">La flexibilidad de este elemento lo hace muy útil, pero también más complicado de entender y usar correctamente.</span><span class="sxs-lookup"><span data-stu-id="655d3-104">The flexibility of this element makes it very useful, but also makes it more complicated to understand and use correctly.</span></span>  
  
 <span data-ttu-id="655d3-105">Este tema contiene las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="655d3-105">This topic contains the following sections.</span></span>  
  
- [<span data-ttu-id="655d3-106">Fundamentos de tablas</span><span class="sxs-lookup"><span data-stu-id="655d3-106">Table Basics</span></span>](#table_basics)  
  
- [<span data-ttu-id="655d3-107">¿En qué se diferencian las tablas de las cuadrículas?</span><span class="sxs-lookup"><span data-stu-id="655d3-107">How is Table Different then Grid?</span></span>](#table_vs_Grid)  
  
- [<span data-ttu-id="655d3-108">Estructura básica de las tablas</span><span class="sxs-lookup"><span data-stu-id="655d3-108">Basic Table Structure</span></span>](#basic_table_structure)  
  
- [<span data-ttu-id="655d3-109">Contención de tablas</span><span class="sxs-lookup"><span data-stu-id="655d3-109">Table Containment</span></span>](#table_containment)  
  
- [<span data-ttu-id="655d3-110">Agrupaciones de filas</span><span class="sxs-lookup"><span data-stu-id="655d3-110">Row Groupings</span></span>](#row_groupings)  
  
- [<span data-ttu-id="655d3-111">Prioridad de representación del fondo</span><span class="sxs-lookup"><span data-stu-id="655d3-111">Background Rendering Precedence</span></span>](#rendering_precedence)  
  
- [<span data-ttu-id="655d3-112">Abarcar filas o columnas</span><span class="sxs-lookup"><span data-stu-id="655d3-112">Spanning Rows or Columns</span></span>](#spanning_rows_or_columns)  
  
- [<span data-ttu-id="655d3-113">Creación de una tabla mediante código</span><span class="sxs-lookup"><span data-stu-id="655d3-113">Building a Table With Code</span></span>](#building_a_table_with_code)  
  
- <span data-ttu-id="655d3-114">[Temas relacionados]</span><span class="sxs-lookup"><span data-stu-id="655d3-114">[Related Topics]</span></span> 
  
<a name="table_basics"></a>   
## <a name="table-basics"></a><span data-ttu-id="655d3-115">Fundamentos de tablas</span><span class="sxs-lookup"><span data-stu-id="655d3-115">Table Basics</span></span>  
  
<a name="table_vs_Grid"></a>   
### <a name="how-is-table-different-then-grid"></a><span data-ttu-id="655d3-116">¿En qué se diferencian las tablas de las cuadrículas?</span><span class="sxs-lookup"><span data-stu-id="655d3-116">How is Table Different then Grid?</span></span>  
 <span data-ttu-id="655d3-117"><xref:System.Windows.Documents.Table>y <xref:System.Windows.Controls.Grid> comparten algunas funciones comunes, pero cada una de ellas es más adecuada para distintos escenarios.</span><span class="sxs-lookup"><span data-stu-id="655d3-117"><xref:System.Windows.Documents.Table> and <xref:System.Windows.Controls.Grid> share some common functionality, but each is best suited for different scenarios.</span></span> <span data-ttu-id="655d3-118">Un <xref:System.Windows.Documents.Table> está diseñado para su uso en el contenido dinámico (consulte [información general sobre documentos dinámicos](flow-document-overview.md) para obtener más información sobre el contenido dinámico).</span><span class="sxs-lookup"><span data-stu-id="655d3-118">A <xref:System.Windows.Documents.Table> is designed for use within flow content (see [Flow Document Overview](flow-document-overview.md) for more information on flow content).</span></span> <span data-ttu-id="655d3-119">Las cuadrículas son más apropiadas para formularios (básicamente, en cualquier lugar excepto en el contenido dinámico).</span><span class="sxs-lookup"><span data-stu-id="655d3-119">Grids are best used inside of forms (basically anywhere outside of flow content).</span></span> <span data-ttu-id="655d3-120">Dentro de <xref:System.Windows.Documents.Table> <xref:System.Windows.Controls.Grid> , admite los comportamientos del contenido dinámico, como la paginación, el reflujo de columnas y la selección de contenido, mientras que no. <xref:System.Windows.Documents.FlowDocument></span><span class="sxs-lookup"><span data-stu-id="655d3-120">Within a <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Table> supports flow content behaviors like pagination, column reflow, and content selection while a <xref:System.Windows.Controls.Grid> does not.</span></span> <span data-ttu-id="655d3-121">Por otra parte, se usa mejor fuera de un <xref:System.Windows.Documents.FlowDocument> por muchas razones, como <xref:System.Windows.Controls.Grid> agregar elementos basados en un índice de fila y de <xref:System.Windows.Documents.Table> columna, no. <xref:System.Windows.Controls.Grid></span><span class="sxs-lookup"><span data-stu-id="655d3-121">A <xref:System.Windows.Controls.Grid> on the other hand is best used outside of a <xref:System.Windows.Documents.FlowDocument> for many reasons including <xref:System.Windows.Controls.Grid> adds elements based on a row and column index, <xref:System.Windows.Documents.Table> does not.</span></span> <span data-ttu-id="655d3-122">El <xref:System.Windows.Controls.Grid> elemento permite la disposición en capas del contenido secundario, lo que permite que haya más de un elemento dentro de una sola "celda".</span><span class="sxs-lookup"><span data-stu-id="655d3-122">The <xref:System.Windows.Controls.Grid> element allows layering of child content, allowing more than one element to exist within a single "cell."</span></span> <span data-ttu-id="655d3-123"><xref:System.Windows.Documents.Table>no admite la disposición en capas.</span><span class="sxs-lookup"><span data-stu-id="655d3-123"><xref:System.Windows.Documents.Table> does not support layering.</span></span> <span data-ttu-id="655d3-124">Los elementos secundarios de <xref:System.Windows.Controls.Grid> se pueden colocar de manera absoluta en relación con el área de los límites de la "celda".</span><span class="sxs-lookup"><span data-stu-id="655d3-124">Child elements of a <xref:System.Windows.Controls.Grid> can be absolutely positioned relative to the area of their "cell" boundaries.</span></span> <span data-ttu-id="655d3-125"><xref:System.Windows.Documents.Table>no es compatible con esta característica.</span><span class="sxs-lookup"><span data-stu-id="655d3-125"><xref:System.Windows.Documents.Table> does not support this feature.</span></span> <span data-ttu-id="655d3-126">Por último, <xref:System.Windows.Controls.Grid> requiere menos recursos <xref:System.Windows.Documents.Table> y, por lo tanto, <xref:System.Windows.Controls.Grid> puede usar para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="655d3-126">Finally, a <xref:System.Windows.Controls.Grid> requires less resources then a <xref:System.Windows.Documents.Table> so consider using a <xref:System.Windows.Controls.Grid> to improve performance.</span></span>  
  
<a name="basic_table_structure"></a>   
### <a name="basic-table-structure"></a><span data-ttu-id="655d3-127">Estructura básica de las tablas</span><span class="sxs-lookup"><span data-stu-id="655d3-127">Basic Table Structure</span></span>  
 <span data-ttu-id="655d3-128"><xref:System.Windows.Documents.Table>proporciona una presentación basada en cuadrícula formada por columnas (representadas <xref:System.Windows.Documents.TableColumn> por elementos) y filas (representadas por <xref:System.Windows.Documents.TableRow> elementos).</span><span class="sxs-lookup"><span data-stu-id="655d3-128"><xref:System.Windows.Documents.Table> provides a grid-based presentation consisting of columns (represented by <xref:System.Windows.Documents.TableColumn> elements) and rows (represented by <xref:System.Windows.Documents.TableRow> elements).</span></span> <span data-ttu-id="655d3-129"><xref:System.Windows.Documents.TableColumn>los elementos no hospedan contenido; simplemente definen las columnas y características de las columnas.</span><span class="sxs-lookup"><span data-stu-id="655d3-129"><xref:System.Windows.Documents.TableColumn> elements do not host content; they simply define columns and characteristics of columns.</span></span> <span data-ttu-id="655d3-130"><xref:System.Windows.Documents.TableRow>los elementos deben estar hospedados <xref:System.Windows.Documents.TableRowGroup> en un elemento, que define una agrupación de filas para la tabla.</span><span class="sxs-lookup"><span data-stu-id="655d3-130"><xref:System.Windows.Documents.TableRow> elements must be hosted in a <xref:System.Windows.Documents.TableRowGroup> element, which defines a grouping of rows for the table.</span></span> <span data-ttu-id="655d3-131"><xref:System.Windows.Documents.TableCell>los elementos, que contienen el contenido real que va a presentar la tabla, deben estar hospedados <xref:System.Windows.Documents.TableRow> en un elemento.</span><span class="sxs-lookup"><span data-stu-id="655d3-131"><xref:System.Windows.Documents.TableCell> elements, which contain the actual content to be presented by the table, must be hosted in a <xref:System.Windows.Documents.TableRow> element.</span></span> <span data-ttu-id="655d3-132"><xref:System.Windows.Documents.TableCell>solo puede contener elementos que derivan <xref:System.Windows.Documents.Block>de.</span><span class="sxs-lookup"><span data-stu-id="655d3-132"><xref:System.Windows.Documents.TableCell> may only contain elements that derive from <xref:System.Windows.Documents.Block>.</span></span>  <span data-ttu-id="655d3-133">Elementos secundarios válidos para <xref:System.Windows.Documents.TableCell> un include.</span><span class="sxs-lookup"><span data-stu-id="655d3-133">Valid child elements for a <xref:System.Windows.Documents.TableCell> include.</span></span>  
  
- <xref:System.Windows.Documents.BlockUIContainer>  
  
- <xref:System.Windows.Documents.List>  
  
- <xref:System.Windows.Documents.Paragraph>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
> <span data-ttu-id="655d3-134"><xref:System.Windows.Documents.TableCell>los elementos no pueden hospedar directamente el contenido de texto.</span><span class="sxs-lookup"><span data-stu-id="655d3-134"><xref:System.Windows.Documents.TableCell> elements may not directly host text content.</span></span> <span data-ttu-id="655d3-135">Para obtener más información sobre las reglas de contención para elementos de <xref:System.Windows.Documents.TableCell>contenido dinámico como, consulte [información general sobre documentos dinámicos](flow-document-overview.md).</span><span class="sxs-lookup"><span data-stu-id="655d3-135">For more information about the containment rules for flow content elements like <xref:System.Windows.Documents.TableCell>, see [Flow Document Overview](flow-document-overview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="655d3-136"><xref:System.Windows.Documents.Table>es similar al <xref:System.Windows.Controls.Grid> elemento, pero tiene más funciones y, por lo tanto, requiere mayor sobrecarga de recursos.</span><span class="sxs-lookup"><span data-stu-id="655d3-136"><xref:System.Windows.Documents.Table> is similar to the <xref:System.Windows.Controls.Grid> element but has more capabilities and, therefore, requires greater resource overhead.</span></span>  
  
 <span data-ttu-id="655d3-137">En el ejemplo siguiente se define una tabla simple de 2 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]x 3 con.</span><span class="sxs-lookup"><span data-stu-id="655d3-137">The following example defines a simple 2 x 3 table with [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)].</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_BasicLayout](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 <span data-ttu-id="655d3-138">En la ilustración siguiente, se muestra cómo se representa este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="655d3-138">The following figure shows how this example renders.</span></span>  
  
 ![Captura de pantalla que muestra cómo se representa una tabla básica.](./media/table-overview/basic-table-render-example.png)  
  
<a name="table_containment"></a>   
### <a name="table-containment"></a><span data-ttu-id="655d3-140">Contención de tablas</span><span class="sxs-lookup"><span data-stu-id="655d3-140">Table Containment</span></span>  
 <span data-ttu-id="655d3-141"><xref:System.Windows.Documents.Table>deriva del <xref:System.Windows.Documents.Block> elemento y cumple las reglas comunes de los elementos de <xref:System.Windows.Documents.Block> nivel.</span><span class="sxs-lookup"><span data-stu-id="655d3-141"><xref:System.Windows.Documents.Table> derives from the <xref:System.Windows.Documents.Block> element, and adheres to the common rules for <xref:System.Windows.Documents.Block> level elements.</span></span>  <span data-ttu-id="655d3-142">Un <xref:System.Windows.Documents.Table> elemento puede estar contenido en cualquiera de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="655d3-142">A <xref:System.Windows.Documents.Table> element may be contained by any of the following elements:</span></span>  
  
- <xref:System.Windows.Documents.FlowDocument>  
  
- <xref:System.Windows.Documents.TableCell>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Floater>  
  
- <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>   
### <a name="row-groupings"></a><span data-ttu-id="655d3-143">Agrupaciones de filas</span><span class="sxs-lookup"><span data-stu-id="655d3-143">Row Groupings</span></span>  
 <span data-ttu-id="655d3-144">El <xref:System.Windows.Documents.TableRowGroup> elemento proporciona una manera de agrupar filas arbitrariamente dentro de una tabla; cada fila de una tabla debe pertenecer a una agrupación de filas.</span><span class="sxs-lookup"><span data-stu-id="655d3-144">The <xref:System.Windows.Documents.TableRowGroup> element provides a way to arbitrarily group rows within a table; every row in a table must belong to a row grouping.</span></span>  <span data-ttu-id="655d3-145">Las filas dentro de un grupo de filas comparten a menudo una finalidad común y se les puede asignar un estilo como grupo.</span><span class="sxs-lookup"><span data-stu-id="655d3-145">Rows within a row group often share a common intent, and may be styled as a group.</span></span>  <span data-ttu-id="655d3-146">Un uso común para las agrupaciones de filas es separar las filas que tienen una finalidad especial, como filas de título, encabezado y pie de página, del contenido principal incluido en la tabla.</span><span class="sxs-lookup"><span data-stu-id="655d3-146">A common use for row groupings is to separate special-purpose rows, such as a title, header, and footer rows, from the primary content contained by the table.</span></span>  
  
 <span data-ttu-id="655d3-147">En el ejemplo siguiente [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] se usa para definir una tabla con filas de encabezado y pie de página con estilo.</span><span class="sxs-lookup"><span data-stu-id="655d3-147">The following example uses [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] to define a table with styled header and footer rows.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_RowGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 <span data-ttu-id="655d3-148">En la ilustración siguiente, se muestra cómo se representa este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="655d3-148">The following figure shows how this example renders.</span></span>  
  
 <span data-ttu-id="655d3-149">![Captura Grupos]de filas de tabla(./media/table-rowgroups.png "Table_RowGroups")</span><span class="sxs-lookup"><span data-stu-id="655d3-149">![Screenshot: Table row groups](./media/table-rowgroups.png "Table_RowGroups")</span></span>  
  
<a name="rendering_precedence"></a>   
### <a name="background-rendering-precedence"></a><span data-ttu-id="655d3-150">Prioridad de representación del fondo</span><span class="sxs-lookup"><span data-stu-id="655d3-150">Background Rendering Precedence</span></span>  
 <span data-ttu-id="655d3-151">Los elementos de tabla se representan en el orden siguiente (orden z ascendente).</span><span class="sxs-lookup"><span data-stu-id="655d3-151">Table elements render in the following order (z-order from lowest to highest).</span></span> <span data-ttu-id="655d3-152">Este orden no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="655d3-152">This order cannot be changed.</span></span> <span data-ttu-id="655d3-153">Por ejemplo, no existe una propiedad de "orden Z" para estos elementos que se pueda usar para invalidar el orden establecido.</span><span class="sxs-lookup"><span data-stu-id="655d3-153">For example, there is no "Z-order" property for these elements that you can use to override this established order.</span></span>  
  
1. <xref:System.Windows.Documents.Table>  
  
2. <xref:System.Windows.Documents.TableColumn>  
  
3. <xref:System.Windows.Documents.TableRowGroup>  
  
4. <xref:System.Windows.Documents.TableRow>  
  
5. <xref:System.Windows.Documents.TableCell>  
  
 <span data-ttu-id="655d3-154">Observe el ejemplo siguiente, en el que se definen los colores de fondo para cada uno de estos elementos dentro de una tabla.</span><span class="sxs-lookup"><span data-stu-id="655d3-154">Consider the following example, which defines background colors for each of these elements within a table.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_ZOrder](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_zorder)]  
  
 <span data-ttu-id="655d3-155">En la ilustración siguiente se muestra cómo se representa este ejemplo (mostrando únicamente los colores de fondo).</span><span class="sxs-lookup"><span data-stu-id="655d3-155">The following figure shows how this example renders (showing background colors only).</span></span>  
  
 <span data-ttu-id="655d3-156">![Captura &#45;Orden]z de la tabla(./media/table-zorder.png "Table_ZOrder")</span><span class="sxs-lookup"><span data-stu-id="655d3-156">![Screenshot: Table z&#45;order](./media/table-zorder.png "Table_ZOrder")</span></span>  
  
<a name="spanning_rows_or_columns"></a>   
### <a name="spanning-rows-or-columns"></a><span data-ttu-id="655d3-157">Abarcar filas o columnas</span><span class="sxs-lookup"><span data-stu-id="655d3-157">Spanning Rows or Columns</span></span>  
 <span data-ttu-id="655d3-158">Las celdas de la tabla se pueden configurar para que abarquen varias <xref:System.Windows.Documents.TableCell.RowSpan%2A> filas <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> o columnas mediante los atributos o, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="655d3-158">Table cells may be configured to span multiple rows or columns by using the <xref:System.Windows.Documents.TableCell.RowSpan%2A> or <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> attributes, respectively.</span></span>  
  
 <span data-ttu-id="655d3-159">Considere el ejemplo siguiente, en el que una celda abarca tres columnas.</span><span class="sxs-lookup"><span data-stu-id="655d3-159">Consider the following example, in which a cell spans three columns.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_ColumnSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 <span data-ttu-id="655d3-160">En la ilustración siguiente, se muestra cómo se representa este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="655d3-160">The following figure shows how this example renders.</span></span>  
  
 <span data-ttu-id="655d3-161">![Captura Celda que abarca las tres]columnas(./media/table-columnspan.png "Table_ColumnSpan")</span><span class="sxs-lookup"><span data-stu-id="655d3-161">![Screenshot: Cell spanning all three columns](./media/table-columnspan.png "Table_ColumnSpan")</span></span>  
  
<a name="building_a_table_with_code"></a>   
## <a name="building-a-table-with-code"></a><span data-ttu-id="655d3-162">Creación de una tabla mediante código</span><span class="sxs-lookup"><span data-stu-id="655d3-162">Building a Table With Code</span></span>  
 <span data-ttu-id="655d3-163">En los siguientes ejemplos se muestra cómo crear un <xref:System.Windows.Documents.Table> y rellenarlo con contenido mediante programación.</span><span class="sxs-lookup"><span data-stu-id="655d3-163">The following examples show how to programmatically create a <xref:System.Windows.Documents.Table> and populate it with content.</span></span> <span data-ttu-id="655d3-164">El contenido de la tabla se distribuye en cinco filas (representadas por <xref:System.Windows.Documents.TableRow> objetos contenidos en un <xref:System.Windows.Documents.Table.RowGroups%2A> objeto) y seis columnas ( <xref:System.Windows.Documents.TableColumn> representadas por objetos).</span><span class="sxs-lookup"><span data-stu-id="655d3-164">The contents of the table are apportioned into five rows (represented by <xref:System.Windows.Documents.TableRow> objects contained in a <xref:System.Windows.Documents.Table.RowGroups%2A> object) and six columns (represented by <xref:System.Windows.Documents.TableColumn> objects).</span></span> <span data-ttu-id="655d3-165">Las filas se usan para distintos fines de presentación, e incluyen una fila de título usada para dar título a toda la tabla, una fila de encabezado para describir las columnas de datos de la tabla, y una fila de pie de página con información de resumen.</span><span class="sxs-lookup"><span data-stu-id="655d3-165">The rows are used for different presentation purposes, including a title row intended to title the entire table, a header row to describe the columns of data in the table, and a footer row with summary information.</span></span>  <span data-ttu-id="655d3-166">Tenga en cuenta que los conceptos de filas de "título", "encabezado" y "pie de página" no son inherentes a la tabla; se trata simplemente de filas con características diferentes.</span><span class="sxs-lookup"><span data-stu-id="655d3-166">Note that the notion of "title", "header", and "footer" rows are not inherent to the table; these are simply rows with different characteristics.</span></span> <span data-ttu-id="655d3-167">Las celdas de la tabla contienen el contenido real, que puede estar formado por texto, imágenes o casi cualquier [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] otro elemento.</span><span class="sxs-lookup"><span data-stu-id="655d3-167">Table cells contain the actual content, which can be comprised of text, images, or nearly any other [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] element.</span></span>  
  
 <span data-ttu-id="655d3-168">En primer lugar <xref:System.Windows.Documents.FlowDocument> , se crea un para <xref:System.Windows.Documents.Table>hospedar el, <xref:System.Windows.Documents.Table> y se <xref:System.Windows.Documents.FlowDocument>crea un nuevo y se agrega al contenido de.</span><span class="sxs-lookup"><span data-stu-id="655d3-168">First, a <xref:System.Windows.Documents.FlowDocument> is created to host the <xref:System.Windows.Documents.Table>, and a new <xref:System.Windows.Documents.Table> is created and added to the contents of the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 <span data-ttu-id="655d3-169">A continuación, <xref:System.Windows.Documents.TableColumn> se crean seis objetos y se agregan a <xref:System.Windows.Documents.Table.Columns%2A> la colección de la tabla, con el formato aplicado.</span><span class="sxs-lookup"><span data-stu-id="655d3-169">Next, six <xref:System.Windows.Documents.TableColumn> objects are created and added to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection, with some formatting applied.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="655d3-170">Tenga en cuenta que la <xref:System.Windows.Documents.Table.Columns%2A> colección de la tabla utiliza una indización de base cero estándar.</span><span class="sxs-lookup"><span data-stu-id="655d3-170">Note that the table's <xref:System.Windows.Documents.Table.Columns%2A> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
 <span data-ttu-id="655d3-171">Luego, se crea una fila de título y se agrega a la tabla tras aplicarle formato.</span><span class="sxs-lookup"><span data-stu-id="655d3-171">Next, a title row is created and added to the table with some formatting applied.</span></span>  <span data-ttu-id="655d3-172">La fila de título contiene una sola celda que abarca las seis columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="655d3-172">The title row happens to contain a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
 <span data-ttu-id="655d3-173">Después, se crea una fila de encabezado y se agrega a la tabla, y se crean y rellenan con contenido las celdas de la fila de encabezado.</span><span class="sxs-lookup"><span data-stu-id="655d3-173">Next, a header row is created and added to the table, and the cells in the header row are created and populated with content.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
 <span data-ttu-id="655d3-174">Después, se crea una fila para datos y se agrega a la tabla, y se crean y rellenan con contenido las celdas de esta fila.</span><span class="sxs-lookup"><span data-stu-id="655d3-174">Next, a row for data is created and added to the table, and the cells in this row are created and populated with content.</span></span>  <span data-ttu-id="655d3-175">La creación de esta fila es similar a la creación de la fila de encabezado con un formato ligeramente diferente.</span><span class="sxs-lookup"><span data-stu-id="655d3-175">Building this row is similar to building the header row, with slightly different formatting applied.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
 <span data-ttu-id="655d3-176">Por último, se crea una fila de pie de página, se agrega y se le da formato.</span><span class="sxs-lookup"><span data-stu-id="655d3-176">Finally, a footer row is created, added, and formatted.</span></span>  <span data-ttu-id="655d3-177">Al igual que la fila de título, el pie de página contiene una sola celda que abarca las seis columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="655d3-177">Like the title row, the footer contains a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a><span data-ttu-id="655d3-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="655d3-178">See also</span></span>

- [<span data-ttu-id="655d3-179">Información general sobre documentos dinámicos</span><span class="sxs-lookup"><span data-stu-id="655d3-179">Flow Document Overview</span></span>](flow-document-overview.md)
- [<span data-ttu-id="655d3-180">Definir una tabla con XAML</span><span class="sxs-lookup"><span data-stu-id="655d3-180">Define a Table with XAML</span></span>](how-to-define-a-table-with-xaml.md)
- [<span data-ttu-id="655d3-181">Documentos en WPF</span><span class="sxs-lookup"><span data-stu-id="655d3-181">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="655d3-182">Usar elementos de contenido dinámico</span><span class="sxs-lookup"><span data-stu-id="655d3-182">Use Flow Content Elements</span></span>](how-to-use-flow-content-elements.md)
