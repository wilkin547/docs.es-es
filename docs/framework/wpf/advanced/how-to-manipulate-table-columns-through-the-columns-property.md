---
title: Procedimiento Manipular las columnas de una tabla mediante la propiedad Columns
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], manipulating table columns
- properties [WPF], Columns [WPF], manipulating table columns
- tables [WPF], manipulating columns
- Columns property [WPF]
ms.assetid: 3f8884f4-7e1f-456b-be06-fbd3cf469bf3
ms.openlocfilehash: 18a26c76688ebf668293cb1254404d6d2cf15208
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913589"
---
# <a name="how-to-manipulate-a-tables-columns-through-the-columns-property"></a><span data-ttu-id="5a118-102">Procedimiento Manipular las columnas de una tabla mediante la propiedad Columns</span><span class="sxs-lookup"><span data-stu-id="5a118-102">How to: Manipulate a Table's Columns through the Columns Property</span></span>
<span data-ttu-id="5a118-103">En este ejemplo se muestran algunas de las operaciones más comunes que se pueden realizar en las columnas de una <xref:System.Windows.Documents.Table.Columns%2A> tabla a través de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="5a118-103">This example demonstrates some of the more common operations that can be performed on a table's columns through the <xref:System.Windows.Documents.Table.Columns%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a118-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5a118-104">Example</span></span>  
 <span data-ttu-id="5a118-105">En el ejemplo siguiente se crea una nueva tabla y, <xref:System.Windows.Documents.TableColumnCollection.Add%2A> a continuación, se usa el método para <xref:System.Windows.Documents.Table.Columns%2A> Agregar columnas a la colección de la tabla.</span><span class="sxs-lookup"><span data-stu-id="5a118-105">The following example creates a new table and then uses the <xref:System.Windows.Documents.TableColumnCollection.Add%2A> method to add columns to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Add](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_add)]
 [!code-vb[TableSnippets2#_Table_Columns_Add](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_add)]  
  
## <a name="example"></a><span data-ttu-id="5a118-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5a118-106">Example</span></span>  
 <span data-ttu-id="5a118-107">En el ejemplo siguiente se inserta un <xref:System.Windows.Documents.TableColumn>nuevo.</span><span class="sxs-lookup"><span data-stu-id="5a118-107">The following example inserts a new <xref:System.Windows.Documents.TableColumn>.</span></span>  <span data-ttu-id="5a118-108">La nueva columna se inserta en la posición 0 del índice, convirtiéndola en la nueva columna de la tabla.</span><span class="sxs-lookup"><span data-stu-id="5a118-108">The new column is inserted at index position 0, making it the new first column in the table.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5a118-109">La <xref:System.Windows.Documents.TableColumnCollection> colección utiliza la indexación estándar basada en cero.</span><span class="sxs-lookup"><span data-stu-id="5a118-109">The <xref:System.Windows.Documents.TableColumnCollection> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Insert](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_insert)]
 [!code-vb[TableSnippets2#_Table_Columns_Insert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_insert)]  
  
## <a name="example"></a><span data-ttu-id="5a118-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5a118-110">Example</span></span>  
 <span data-ttu-id="5a118-111">En el ejemplo siguiente se obtiene acceso a algunas propiedades arbitrarias <xref:System.Windows.Documents.TableColumnCollection> de las columnas de la colección, que hacen referencia a columnas determinadas por índice.</span><span class="sxs-lookup"><span data-stu-id="5a118-111">The following example accesses some arbitrary properties on columns in the <xref:System.Windows.Documents.TableColumnCollection> collection, referring to particular columns by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Manip](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_manip)]
 [!code-vb[TableSnippets2#_Table_Columns_Manip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_manip)]  
  
## <a name="example"></a><span data-ttu-id="5a118-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5a118-112">Example</span></span>  
 <span data-ttu-id="5a118-113">En el ejemplo siguiente se obtiene el número de columnas hospedadas actualmente por la tabla.</span><span class="sxs-lookup"><span data-stu-id="5a118-113">The following example gets the number of columns currently hosted by the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Count](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_count)]
 [!code-vb[TableSnippets2#_Table_Columns_Count](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_count)]  
  
## <a name="example"></a><span data-ttu-id="5a118-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5a118-114">Example</span></span>  
 <span data-ttu-id="5a118-115">En el ejemplo siguiente se quita una columna determinada por referencia.</span><span class="sxs-lookup"><span data-stu-id="5a118-115">The following example removes a particular column by reference.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelRef](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delref)]
 [!code-vb[TableSnippets2#_Table_Columns_DelRef](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delref)]  
  
## <a name="example"></a><span data-ttu-id="5a118-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5a118-116">Example</span></span>  
 <span data-ttu-id="5a118-117">En el ejemplo siguiente se quita una columna determinada por índice.</span><span class="sxs-lookup"><span data-stu-id="5a118-117">The following example removes a particular column by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delindex)]
 [!code-vb[TableSnippets2#_Table_Columns_DelIndex](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delindex)]  
  
## <a name="example"></a><span data-ttu-id="5a118-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5a118-118">Example</span></span>  
 <span data-ttu-id="5a118-119">En el siguiente ejemplo se quitan todas las columnas de la colección de columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="5a118-119">The following example removes all columns from the table's columns collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Clear](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_clear)]
 [!code-vb[TableSnippets2#_Table_Columns_Clear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_clear)]  
  
## <a name="see-also"></a><span data-ttu-id="5a118-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a118-120">See also</span></span>

- [<span data-ttu-id="5a118-121">Información general sobre tablas</span><span class="sxs-lookup"><span data-stu-id="5a118-121">Table Overview</span></span>](table-overview.md)
- [<span data-ttu-id="5a118-122">Definir una tabla con XAML</span><span class="sxs-lookup"><span data-stu-id="5a118-122">Define a Table with XAML</span></span>](how-to-define-a-table-with-xaml.md)
- [<span data-ttu-id="5a118-123">Compilar una tabla mediante programación</span><span class="sxs-lookup"><span data-stu-id="5a118-123">Build a Table Programmatically</span></span>](how-to-build-a-table-programmatically.md)
- [<span data-ttu-id="5a118-124">Manipular grupos de filas de una tabla mediante la propiedad RowGroups</span><span class="sxs-lookup"><span data-stu-id="5a118-124">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="5a118-125">Manipular un objeto FlowDocument mediante la propiedad Blocks</span><span class="sxs-lookup"><span data-stu-id="5a118-125">Manipulate a FlowDocument through the Blocks Property</span></span>](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [<span data-ttu-id="5a118-126">Manipular grupos de filas de una tabla mediante la propiedad RowGroups</span><span class="sxs-lookup"><span data-stu-id="5a118-126">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
