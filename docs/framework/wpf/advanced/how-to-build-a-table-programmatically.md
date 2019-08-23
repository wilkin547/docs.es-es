---
title: Procedimiento Compilar una tabla mediante programación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tables [WPF], creating programmatically
ms.assetid: e3ca88f3-6e94-4b61-82fc-42104c10b761
ms.openlocfilehash: 9c9061d3c4d6b3de5e1ab42a6b98c20813835ba8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964161"
---
# <a name="how-to-build-a-table-programmatically"></a><span data-ttu-id="67b8d-102">Procedimiento Compilar una tabla mediante programación</span><span class="sxs-lookup"><span data-stu-id="67b8d-102">How to: Build a Table Programmatically</span></span>
<span data-ttu-id="67b8d-103">En los siguientes ejemplos se muestra cómo crear un <xref:System.Windows.Documents.Table> y rellenarlo con contenido mediante programación.</span><span class="sxs-lookup"><span data-stu-id="67b8d-103">The following examples show how to programmatically create a <xref:System.Windows.Documents.Table> and populate it with content.</span></span> <span data-ttu-id="67b8d-104">El contenido de la tabla se distribuye en cinco filas (representadas por <xref:System.Windows.Documents.TableRow> objetos contenidos en un <xref:System.Windows.Documents.Table.RowGroups%2A> objeto) y seis columnas ( <xref:System.Windows.Documents.TableColumn> representadas por objetos).</span><span class="sxs-lookup"><span data-stu-id="67b8d-104">The contents of the table are apportioned into five rows (represented by <xref:System.Windows.Documents.TableRow> objects contained in a <xref:System.Windows.Documents.Table.RowGroups%2A> object) and six columns (represented by <xref:System.Windows.Documents.TableColumn> objects).</span></span> <span data-ttu-id="67b8d-105">Las filas se usan para distintos fines de presentación, e incluyen una fila de título usada para dar título a toda la tabla, una fila de encabezado para describir las columnas de datos de la tabla, y una fila de pie de página con información de resumen.</span><span class="sxs-lookup"><span data-stu-id="67b8d-105">The rows are used for different presentation purposes, including a title row intended to title the entire table, a header row to describe the columns of data in the table, and a footer row with summary information.</span></span>  <span data-ttu-id="67b8d-106">Tenga en cuenta que los conceptos de filas de "título", "encabezado" y "pie de página" no son inherentes a la tabla; se trata simplemente de filas con características diferentes.</span><span class="sxs-lookup"><span data-stu-id="67b8d-106">Note that the notion of "title", "header", and "footer" rows are not inherent to the table; these are simply rows with different characteristics.</span></span> <span data-ttu-id="67b8d-107">Las celdas de la tabla contienen el contenido real, que puede estar formado por texto, imágenes o casi cualquier [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] otro elemento.</span><span class="sxs-lookup"><span data-stu-id="67b8d-107">Table cells contain the actual content, which can be comprised of text, images, or nearly any other [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67b8d-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="67b8d-108">Example</span></span>  
 <span data-ttu-id="67b8d-109">En primer lugar <xref:System.Windows.Documents.FlowDocument> , se crea un para <xref:System.Windows.Documents.Table>hospedar el, <xref:System.Windows.Documents.Table> y se <xref:System.Windows.Documents.FlowDocument>crea un nuevo y se agrega al contenido de.</span><span class="sxs-lookup"><span data-stu-id="67b8d-109">First, a <xref:System.Windows.Documents.FlowDocument> is created to host the <xref:System.Windows.Documents.Table>, and a new <xref:System.Windows.Documents.Table> is created and added to the contents of the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
## <a name="example"></a><span data-ttu-id="67b8d-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="67b8d-110">Example</span></span>  
 <span data-ttu-id="67b8d-111">A continuación, <xref:System.Windows.Documents.TableColumn> se crean seis objetos y se agregan a <xref:System.Windows.Documents.Table.Columns%2A> la colección de la tabla, con el formato aplicado.</span><span class="sxs-lookup"><span data-stu-id="67b8d-111">Next, six <xref:System.Windows.Documents.TableColumn> objects are created and added to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection, with some formatting applied.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="67b8d-112">Tenga en cuenta que la <xref:System.Windows.Documents.Table.Columns%2A> colección de la tabla utiliza una indización de base cero estándar.</span><span class="sxs-lookup"><span data-stu-id="67b8d-112">Note that the table's <xref:System.Windows.Documents.Table.Columns%2A> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
## <a name="example"></a><span data-ttu-id="67b8d-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="67b8d-113">Example</span></span>  
 <span data-ttu-id="67b8d-114">Luego, se crea una fila de título y se agrega a la tabla tras aplicarle formato.</span><span class="sxs-lookup"><span data-stu-id="67b8d-114">Next, a title row is created and added to the table with some formatting applied.</span></span>  <span data-ttu-id="67b8d-115">La fila de título contiene una sola celda que abarca las seis columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="67b8d-115">The title row happens to contain a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
## <a name="example"></a><span data-ttu-id="67b8d-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="67b8d-116">Example</span></span>  
 <span data-ttu-id="67b8d-117">Después, se crea una fila de encabezado y se agrega a la tabla, y se crean y rellenan con contenido las celdas de la fila de encabezado.</span><span class="sxs-lookup"><span data-stu-id="67b8d-117">Next, a header row is created and added to the table, and the cells in the header row are created and populated with content.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
## <a name="example"></a><span data-ttu-id="67b8d-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="67b8d-118">Example</span></span>  
 <span data-ttu-id="67b8d-119">Después, se crea una fila para datos y se agrega a la tabla, y se crean y rellenan con contenido las celdas de esta fila.</span><span class="sxs-lookup"><span data-stu-id="67b8d-119">Next, a row for data is created and added to the table, and the cells in this row are created and populated with content.</span></span>  <span data-ttu-id="67b8d-120">La creación de esta fila es similar a la creación de la fila de encabezado con un formato ligeramente diferente.</span><span class="sxs-lookup"><span data-stu-id="67b8d-120">Building this row is similar to building the header row, with slightly different formatting applied.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
## <a name="example"></a><span data-ttu-id="67b8d-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="67b8d-121">Example</span></span>  
 <span data-ttu-id="67b8d-122">Por último, se crea una fila de pie de página, se agrega y se le da formato.</span><span class="sxs-lookup"><span data-stu-id="67b8d-122">Finally, a footer row is created, added, and formatted.</span></span>  <span data-ttu-id="67b8d-123">Al igual que la fila de título, el pie de página contiene una sola celda que abarca las seis columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="67b8d-123">Like the title row, the footer contains a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a><span data-ttu-id="67b8d-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="67b8d-124">See also</span></span>

- [<span data-ttu-id="67b8d-125">Información general sobre tablas</span><span class="sxs-lookup"><span data-stu-id="67b8d-125">Table Overview</span></span>](table-overview.md)
