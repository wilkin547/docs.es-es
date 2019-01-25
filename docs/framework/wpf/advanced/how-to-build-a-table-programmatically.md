---
title: Procedimiento Compilar una tabla mediante programación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tables [WPF], creating programmatically
ms.assetid: e3ca88f3-6e94-4b61-82fc-42104c10b761
ms.openlocfilehash: 7eced80759f4c250cba5b4fb98ab33957b33de14
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715512"
---
# <a name="how-to-build-a-table-programmatically"></a><span data-ttu-id="1f913-102">Procedimiento Compilar una tabla mediante programación</span><span class="sxs-lookup"><span data-stu-id="1f913-102">How to: Build a Table Programmatically</span></span>
<span data-ttu-id="1f913-103">Los ejemplos siguientes muestran cómo crear mediante programación un <xref:System.Windows.Documents.Table> y rellenarla con contenido.</span><span class="sxs-lookup"><span data-stu-id="1f913-103">The following examples show how to programmatically create a <xref:System.Windows.Documents.Table> and populate it with content.</span></span> <span data-ttu-id="1f913-104">El contenido de la tabla se distribuye en cinco filas (representados por <xref:System.Windows.Documents.TableRow> objetos incluidos en un <xref:System.Windows.Documents.Table.RowGroups%2A> objeto) y seis columnas (representado por <xref:System.Windows.Documents.TableColumn> objetos).</span><span class="sxs-lookup"><span data-stu-id="1f913-104">The contents of the table are apportioned into five rows (represented by <xref:System.Windows.Documents.TableRow> objects contained in a <xref:System.Windows.Documents.Table.RowGroups%2A> object) and six columns (represented by <xref:System.Windows.Documents.TableColumn> objects).</span></span> <span data-ttu-id="1f913-105">Las filas se usan para distintos fines de presentación, e incluyen una fila de título usada para dar título a toda la tabla, una fila de encabezado para describir las columnas de datos de la tabla, y una fila de pie de página con información de resumen.</span><span class="sxs-lookup"><span data-stu-id="1f913-105">The rows are used for different presentation purposes, including a title row intended to title the entire table, a header row to describe the columns of data in the table, and a footer row with summary information.</span></span>  <span data-ttu-id="1f913-106">Tenga en cuenta que los conceptos de filas de "título", "encabezado" y "pie de página" no son inherentes a la tabla; se trata simplemente de filas con características diferentes.</span><span class="sxs-lookup"><span data-stu-id="1f913-106">Note that the notion of "title", "header", and "footer" rows are not inherent to the table; these are simply rows with different characteristics.</span></span> <span data-ttu-id="1f913-107">Las celdas de tabla incluyen el contenido real, que puede estar formado por texto, imágenes o casi cualquier otro [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] elemento.</span><span class="sxs-lookup"><span data-stu-id="1f913-107">Table cells contain the actual content, which can be comprised of text, images, or nearly any other [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f913-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f913-108">Example</span></span>  
 <span data-ttu-id="1f913-109">En primer lugar, un <xref:System.Windows.Documents.FlowDocument> se crea al host la <xref:System.Windows.Documents.Table>y un nuevo <xref:System.Windows.Documents.Table> se crea y agrega al contenido de la <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="1f913-109">First, a <xref:System.Windows.Documents.FlowDocument> is created to host the <xref:System.Windows.Documents.Table>, and a new <xref:System.Windows.Documents.Table> is created and added to the contents of the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
## <a name="example"></a><span data-ttu-id="1f913-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f913-110">Example</span></span>  
 <span data-ttu-id="1f913-111">A continuación, seis <xref:System.Windows.Documents.TableColumn> objetos se crean y se agregan a la tabla <xref:System.Windows.Documents.Table.Columns%2A> colección aplicarles formato.</span><span class="sxs-lookup"><span data-stu-id="1f913-111">Next, six <xref:System.Windows.Documents.TableColumn> objects are created and added to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection, with some formatting applied.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f913-112">Tenga en cuenta que la tabla <xref:System.Windows.Documents.Table.Columns%2A> colección utiliza la indización de base cero estándar.</span><span class="sxs-lookup"><span data-stu-id="1f913-112">Note that the table's <xref:System.Windows.Documents.Table.Columns%2A> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
## <a name="example"></a><span data-ttu-id="1f913-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f913-113">Example</span></span>  
 <span data-ttu-id="1f913-114">Luego, se crea una fila de título y se agrega a la tabla tras aplicarle formato.</span><span class="sxs-lookup"><span data-stu-id="1f913-114">Next, a title row is created and added to the table with some formatting applied.</span></span>  <span data-ttu-id="1f913-115">La fila de título contiene una sola celda que abarca las seis columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="1f913-115">The title row happens to contain a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
## <a name="example"></a><span data-ttu-id="1f913-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f913-116">Example</span></span>  
 <span data-ttu-id="1f913-117">Después, se crea una fila de encabezado y se agrega a la tabla, y se crean y rellenan con contenido las celdas de la fila de encabezado.</span><span class="sxs-lookup"><span data-stu-id="1f913-117">Next, a header row is created and added to the table, and the cells in the header row are created and populated with content.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
## <a name="example"></a><span data-ttu-id="1f913-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f913-118">Example</span></span>  
 <span data-ttu-id="1f913-119">Después, se crea una fila para datos y se agrega a la tabla, y se crean y rellenan con contenido las celdas de esta fila.</span><span class="sxs-lookup"><span data-stu-id="1f913-119">Next, a row for data is created and added to the table, and the cells in this row are created and populated with content.</span></span>  <span data-ttu-id="1f913-120">La creación de esta fila es similar a la creación de la fila de encabezado con un formato ligeramente diferente.</span><span class="sxs-lookup"><span data-stu-id="1f913-120">Building this row is similar to building the header row, with slightly different formatting applied.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
## <a name="example"></a><span data-ttu-id="1f913-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f913-121">Example</span></span>  
 <span data-ttu-id="1f913-122">Por último, se crea una fila de pie de página, se agrega y se le da formato.</span><span class="sxs-lookup"><span data-stu-id="1f913-122">Finally, a footer row is created, added, and formatted.</span></span>  <span data-ttu-id="1f913-123">Al igual que la fila de título, el pie de página contiene una sola celda que abarca las seis columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="1f913-123">Like the title row, the footer contains a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a><span data-ttu-id="1f913-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f913-124">See also</span></span>
- [<span data-ttu-id="1f913-125">Información general sobre tablas</span><span class="sxs-lookup"><span data-stu-id="1f913-125">Table Overview</span></span>](../../../../docs/framework/wpf/advanced/table-overview.md)
