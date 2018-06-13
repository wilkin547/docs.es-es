---
title: 'Cómo: manipular una tabla&#39;s grupos de filas a través de la propiedad de grupos de filas'
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
ms.openlocfilehash: 8cdf3b74fa5bf5a566c541ba035a1c7da7dd6949
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545170"
---
# <a name="how-to-manipulate-a-table39s-row-groups-through-the-rowgroups-property"></a><span data-ttu-id="c825f-102">Cómo: manipular una tabla&#39;s grupos de filas a través de la propiedad de grupos de filas</span><span class="sxs-lookup"><span data-stu-id="c825f-102">How to: Manipulate a Table&#39;s Row Groups through the RowGroups Property</span></span>
<span data-ttu-id="c825f-103">Este ejemplo muestra algunas de las operaciones más comunes que se pueden realizar en grupos de filas de una tabla a través de la <xref:System.Windows.Documents.Table.RowGroups%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="c825f-103">This example demonstrates some of the more common operations that can be performed on a table's row groups through the <xref:System.Windows.Documents.Table.RowGroups%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c825f-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c825f-104">Example</span></span>  
 <span data-ttu-id="c825f-105">En el ejemplo siguiente se crea una nueva tabla y, a continuación, usa el <xref:System.Windows.Documents.TableRowGroupCollection.Add%2A> método para agregar columnas a la tabla <xref:System.Windows.Documents.Table.RowGroups%2A> colección.</span><span class="sxs-lookup"><span data-stu-id="c825f-105">The following example creates a new table and then uses the <xref:System.Windows.Documents.TableRowGroupCollection.Add%2A> method to add columns to the table's <xref:System.Windows.Documents.Table.RowGroups%2A> collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Add](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_add)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Add](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_add)]  
  
## <a name="example"></a><span data-ttu-id="c825f-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c825f-106">Example</span></span>  
 <span data-ttu-id="c825f-107">En el ejemplo siguiente se inserta un nuevo <xref:System.Windows.Documents.TableRowGroup>.</span><span class="sxs-lookup"><span data-stu-id="c825f-107">The following example inserts a new <xref:System.Windows.Documents.TableRowGroup>.</span></span>  <span data-ttu-id="c825f-108">La nueva columna se inserta en la posición de índice 0, lo que la primera fila nuevo grupo en la tabla.</span><span class="sxs-lookup"><span data-stu-id="c825f-108">The new column is inserted at index position 0, making it the new first row group in the table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c825f-109">El <xref:System.Windows.Documents.TableRowGroupCollection> colección utiliza la indización de base cero estándar.</span><span class="sxs-lookup"><span data-stu-id="c825f-109">The <xref:System.Windows.Documents.TableRowGroupCollection> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Insert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_insert)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Insert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_insert)]  
  
## <a name="example"></a><span data-ttu-id="c825f-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c825f-110">Example</span></span>  
 <span data-ttu-id="c825f-111">En el ejemplo siguiente se agrega varias filas a una determinada <xref:System.Windows.Documents.TableRowGroup> (especificado por el índice) en la tabla.</span><span class="sxs-lookup"><span data-stu-id="c825f-111">The following example adds several rows to a particular <xref:System.Windows.Documents.TableRowGroup> (specified by index) in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddRows](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addrows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddRows](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addrows)]  
  
## <a name="example"></a><span data-ttu-id="c825f-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c825f-112">Example</span></span>  
 <span data-ttu-id="c825f-113">En el ejemplo siguiente se obtiene acceso a algunas propiedades arbitrarias en las filas en el primer grupo de filas en la tabla.</span><span class="sxs-lookup"><span data-stu-id="c825f-113">The following example accesses some arbitrary properties on rows in the first row group in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipRows](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_maniprows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipRows](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_maniprows)]  
  
## <a name="example"></a><span data-ttu-id="c825f-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c825f-114">Example</span></span>  
 <span data-ttu-id="c825f-115">En el ejemplo siguiente se agrega varias celdas a un determinado <xref:System.Windows.Documents.TableRow> (especificado por el índice) en la tabla.</span><span class="sxs-lookup"><span data-stu-id="c825f-115">The following example adds several cells to a particular <xref:System.Windows.Documents.TableRow> (specified by index) in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddCells](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddCells](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addcells)]  
  
## <a name="example"></a><span data-ttu-id="c825f-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c825f-116">Example</span></span>  
 <span data-ttu-id="c825f-117">En el siguiente ejemplo tener acceso a algunos métodos y propiedades arbitrarios en las celdas de la primera fila del primer grupo de filas.</span><span class="sxs-lookup"><span data-stu-id="c825f-117">The following example access some arbitrary methods and properties on cells in the first row in the first row group.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipCells](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_manipcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipCells](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_manipcells)]  
  
## <a name="example"></a><span data-ttu-id="c825f-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c825f-118">Example</span></span>  
 <span data-ttu-id="c825f-119">En el ejemplo siguiente se devuelve el número de <xref:System.Windows.Documents.TableRowGroup> elementos hospedados por la tabla.</span><span class="sxs-lookup"><span data-stu-id="c825f-119">The following example returns the number of <xref:System.Windows.Documents.TableRowGroup> elements hosted by the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Count](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_count)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Count](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_count)]  
  
## <a name="example"></a><span data-ttu-id="c825f-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c825f-120">Example</span></span>  
 <span data-ttu-id="c825f-121">En el ejemplo siguiente se quita un grupo de filas determinado por referencia.</span><span class="sxs-lookup"><span data-stu-id="c825f-121">The following example removes a particular row group by reference.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelRef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delref)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelRef](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delref)]  
  
## <a name="example"></a><span data-ttu-id="c825f-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c825f-122">Example</span></span>  
 <span data-ttu-id="c825f-123">En el ejemplo siguiente se quita un grupo de filas determinado por su índice.</span><span class="sxs-lookup"><span data-stu-id="c825f-123">The following example removes a particular row group by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delindex)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelIndex](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delindex)]  
  
## <a name="example"></a><span data-ttu-id="c825f-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c825f-124">Example</span></span>  
 <span data-ttu-id="c825f-125">En el ejemplo siguiente se quita todos los grupos de filas de la colección de grupos de filas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="c825f-125">The following example removes all row groups from the table's row groups collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Clear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_clear)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Clear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_clear)]  
  
## <a name="see-also"></a><span data-ttu-id="c825f-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="c825f-126">See Also</span></span>  
 [<span data-ttu-id="c825f-127">Cómo: Manipular elementos de contenido dinámico mediante la propiedad elementos incorporados</span><span class="sxs-lookup"><span data-stu-id="c825f-127">How-to: Manipulate Flow Content Elements through the Inlines Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)  
 [<span data-ttu-id="c825f-128">Manipular un objeto FlowDocument mediante la propiedad Blocks</span><span class="sxs-lookup"><span data-stu-id="c825f-128">Manipulate a FlowDocument through the Blocks Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)  
 [<span data-ttu-id="c825f-129">Manipular las columnas de una tabla mediante la propiedad Columns</span><span class="sxs-lookup"><span data-stu-id="c825f-129">Manipulate a Table's Columns through the Columns Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)
