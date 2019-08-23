---
title: Procedimiento Manipular grupos de filas de una tabla mediante la propiedad RowGroups
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- row groups [WPF], manipulating through RowGroups property
- RowGroups property [WPF], manipulating row groups
- documents [WPF], manipulating row groups through RowGroups property
- properties [WPF], RowGroups [WPF], manipulating row groups
ms.assetid: ea61440f-08ae-44ed-b314-5716aaaae3ed
ms.openlocfilehash: 195920af64888bd3671b45befc0fe4cde463ae7b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913554"
---
# <a name="how-to-manipulate-a-tables-row-groups-through-the-rowgroups-property"></a><span data-ttu-id="2e003-102">Procedimiento Manipular grupos de filas de una tabla mediante la propiedad RowGroups</span><span class="sxs-lookup"><span data-stu-id="2e003-102">How to: Manipulate a Table's Row Groups through the RowGroups Property</span></span>
<span data-ttu-id="2e003-103">En este ejemplo se muestran algunas de las operaciones más comunes que se pueden realizar en los grupos de filas de <xref:System.Windows.Documents.Table.RowGroups%2A> una tabla a través de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="2e003-103">This example demonstrates some of the more common operations that can be performed on a table's row groups through the <xref:System.Windows.Documents.Table.RowGroups%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e003-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2e003-104">Example</span></span>  
 <span data-ttu-id="2e003-105">En el ejemplo siguiente se crea una nueva tabla y, <xref:System.Windows.Documents.TableRowGroupCollection.Add%2A> a continuación, se usa el método para <xref:System.Windows.Documents.Table.RowGroups%2A> Agregar columnas a la colección de la tabla.</span><span class="sxs-lookup"><span data-stu-id="2e003-105">The following example creates a new table and then uses the <xref:System.Windows.Documents.TableRowGroupCollection.Add%2A> method to add columns to the table's <xref:System.Windows.Documents.Table.RowGroups%2A> collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Add](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_add)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Add](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_add)]  
  
## <a name="example"></a><span data-ttu-id="2e003-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2e003-106">Example</span></span>  
 <span data-ttu-id="2e003-107">En el ejemplo siguiente se inserta un <xref:System.Windows.Documents.TableRowGroup>nuevo.</span><span class="sxs-lookup"><span data-stu-id="2e003-107">The following example inserts a new <xref:System.Windows.Documents.TableRowGroup>.</span></span>  <span data-ttu-id="2e003-108">La nueva columna se inserta en la posición 0 del índice, lo que lo convierte en el nuevo grupo de filas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="2e003-108">The new column is inserted at index position 0, making it the new first row group in the table.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2e003-109">La <xref:System.Windows.Documents.TableRowGroupCollection> colección utiliza la indexación estándar basada en cero.</span><span class="sxs-lookup"><span data-stu-id="2e003-109">The <xref:System.Windows.Documents.TableRowGroupCollection> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Insert](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_insert)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Insert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_insert)]  
  
## <a name="example"></a><span data-ttu-id="2e003-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2e003-110">Example</span></span>  
 <span data-ttu-id="2e003-111">En el siguiente ejemplo se agregan varias filas <xref:System.Windows.Documents.TableRowGroup> a un determinado (especificado por index) en la tabla.</span><span class="sxs-lookup"><span data-stu-id="2e003-111">The following example adds several rows to a particular <xref:System.Windows.Documents.TableRowGroup> (specified by index) in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddRows](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addrows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddRows](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addrows)]  
  
## <a name="example"></a><span data-ttu-id="2e003-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2e003-112">Example</span></span>  
 <span data-ttu-id="2e003-113">En el ejemplo siguiente se tiene acceso a algunas propiedades arbitrarias en filas del primer grupo de filas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="2e003-113">The following example accesses some arbitrary properties on rows in the first row group in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipRows](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_maniprows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipRows](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_maniprows)]  
  
## <a name="example"></a><span data-ttu-id="2e003-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2e003-114">Example</span></span>  
 <span data-ttu-id="2e003-115">En el siguiente ejemplo se agregan varias celdas <xref:System.Windows.Documents.TableRow> a un determinado (especificado por index) en la tabla.</span><span class="sxs-lookup"><span data-stu-id="2e003-115">The following example adds several cells to a particular <xref:System.Windows.Documents.TableRow> (specified by index) in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddCells](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddCells](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addcells)]  
  
## <a name="example"></a><span data-ttu-id="2e003-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2e003-116">Example</span></span>  
 <span data-ttu-id="2e003-117">En el ejemplo siguiente se tiene acceso a algunos métodos y propiedades arbitrarios en las celdas de la primera fila del primer grupo de filas.</span><span class="sxs-lookup"><span data-stu-id="2e003-117">The following example access some arbitrary methods and properties on cells in the first row in the first row group.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipCells](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_manipcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipCells](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_manipcells)]  
  
## <a name="example"></a><span data-ttu-id="2e003-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2e003-118">Example</span></span>  
 <span data-ttu-id="2e003-119">En el ejemplo siguiente se devuelve el <xref:System.Windows.Documents.TableRowGroup> número de elementos hospedados por la tabla.</span><span class="sxs-lookup"><span data-stu-id="2e003-119">The following example returns the number of <xref:System.Windows.Documents.TableRowGroup> elements hosted by the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Count](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_count)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Count](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_count)]  
  
## <a name="example"></a><span data-ttu-id="2e003-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2e003-120">Example</span></span>  
 <span data-ttu-id="2e003-121">En el ejemplo siguiente se quita un grupo de filas determinado por referencia.</span><span class="sxs-lookup"><span data-stu-id="2e003-121">The following example removes a particular row group by reference.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelRef](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delref)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelRef](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delref)]  
  
## <a name="example"></a><span data-ttu-id="2e003-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2e003-122">Example</span></span>  
 <span data-ttu-id="2e003-123">En el ejemplo siguiente se quita un grupo de filas determinado por índice.</span><span class="sxs-lookup"><span data-stu-id="2e003-123">The following example removes a particular row group by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delindex)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelIndex](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delindex)]  
  
## <a name="example"></a><span data-ttu-id="2e003-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2e003-124">Example</span></span>  
 <span data-ttu-id="2e003-125">En el ejemplo siguiente se quitan todos los grupos de filas de la colección de grupos de filas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="2e003-125">The following example removes all row groups from the table's row groups collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Clear](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_clear)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Clear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_clear)]  
  
## <a name="see-also"></a><span data-ttu-id="2e003-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e003-126">See also</span></span>

- [<span data-ttu-id="2e003-127">Colaboración Manipular elementos de contenido dinámico mediante la propiedad Inlines</span><span class="sxs-lookup"><span data-stu-id="2e003-127">How-to: Manipulate Flow Content Elements through the Inlines Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="2e003-128">Manipular un objeto FlowDocument mediante la propiedad Blocks</span><span class="sxs-lookup"><span data-stu-id="2e003-128">Manipulate a FlowDocument through the Blocks Property</span></span>](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [<span data-ttu-id="2e003-129">Manipular las columnas de una tabla mediante la propiedad Columns</span><span class="sxs-lookup"><span data-stu-id="2e003-129">Manipulate a Table's Columns through the Columns Property</span></span>](how-to-manipulate-table-columns-through-the-columns-property.md)
