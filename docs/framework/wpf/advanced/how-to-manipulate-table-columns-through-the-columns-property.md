---
title: 'Cómo: manipular una tabla&#39;s columnas mediante la propiedad Columns'
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
ms.openlocfilehash: 916764c621738ddc651580f1232e1f579a17e6f0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545303"
---
# <a name="how-to-manipulate-a-table39s-columns-through-the-columns-property"></a><span data-ttu-id="09c54-102">Cómo: manipular una tabla&#39;s columnas mediante la propiedad Columns</span><span class="sxs-lookup"><span data-stu-id="09c54-102">How to: Manipulate a Table&#39;s Columns through the Columns Property</span></span>
<span data-ttu-id="09c54-103">Este ejemplo muestra algunas de las operaciones más comunes que pueden realizarse en las columnas de una tabla a través de la <xref:System.Windows.Documents.Table.Columns%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="09c54-103">This example demonstrates some of the more common operations that can be performed on a table's columns through the <xref:System.Windows.Documents.Table.Columns%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09c54-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="09c54-104">Example</span></span>  
 <span data-ttu-id="09c54-105">En el ejemplo siguiente se crea una nueva tabla y, a continuación, usa el <xref:System.Windows.Documents.TableColumnCollection.Add%2A> método para agregar columnas a la tabla <xref:System.Windows.Documents.Table.Columns%2A> colección.</span><span class="sxs-lookup"><span data-stu-id="09c54-105">The following example creates a new table and then uses the <xref:System.Windows.Documents.TableColumnCollection.Add%2A> method to add columns to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Add](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_add)]
 [!code-vb[TableSnippets2#_Table_Columns_Add](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_add)]  
  
## <a name="example"></a><span data-ttu-id="09c54-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="09c54-106">Example</span></span>  
 <span data-ttu-id="09c54-107">En el ejemplo siguiente se inserta un nuevo <xref:System.Windows.Documents.TableColumn>.</span><span class="sxs-lookup"><span data-stu-id="09c54-107">The following example inserts a new <xref:System.Windows.Documents.TableColumn>.</span></span>  <span data-ttu-id="09c54-108">La nueva columna se inserta en la posición de índice 0, lo que la primera columna nueva en la tabla.</span><span class="sxs-lookup"><span data-stu-id="09c54-108">The new column is inserted at index position 0, making it the new first column in the table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09c54-109">El <xref:System.Windows.Documents.TableColumnCollection> colección utiliza la indización de base cero estándar.</span><span class="sxs-lookup"><span data-stu-id="09c54-109">The <xref:System.Windows.Documents.TableColumnCollection> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Insert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_insert)]
 [!code-vb[TableSnippets2#_Table_Columns_Insert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_insert)]  
  
## <a name="example"></a><span data-ttu-id="09c54-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="09c54-110">Example</span></span>  
 <span data-ttu-id="09c54-111">En el ejemplo siguiente se tiene acceso a algunas propiedades arbitrarias en columnas de la <xref:System.Windows.Documents.TableColumnCollection> colección, que hace referencia a las columnas concretas por su índice.</span><span class="sxs-lookup"><span data-stu-id="09c54-111">The following example accesses some arbitrary properties on columns in the <xref:System.Windows.Documents.TableColumnCollection> collection, referring to particular columns by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Manip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_manip)]
 [!code-vb[TableSnippets2#_Table_Columns_Manip](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_manip)]  
  
## <a name="example"></a><span data-ttu-id="09c54-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="09c54-112">Example</span></span>  
 <span data-ttu-id="09c54-113">En el ejemplo siguiente se obtiene el número de columnas hospedadas actualmente en la tabla.</span><span class="sxs-lookup"><span data-stu-id="09c54-113">The following example gets the number of columns currently hosted by the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Count](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_count)]
 [!code-vb[TableSnippets2#_Table_Columns_Count](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_count)]  
  
## <a name="example"></a><span data-ttu-id="09c54-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="09c54-114">Example</span></span>  
 <span data-ttu-id="09c54-115">En el ejemplo siguiente se quita una columna en particular por referencia.</span><span class="sxs-lookup"><span data-stu-id="09c54-115">The following example removes a particular column by reference.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelRef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delref)]
 [!code-vb[TableSnippets2#_Table_Columns_DelRef](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delref)]  
  
## <a name="example"></a><span data-ttu-id="09c54-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="09c54-116">Example</span></span>  
 <span data-ttu-id="09c54-117">En el ejemplo siguiente se quita una columna determinada por su índice.</span><span class="sxs-lookup"><span data-stu-id="09c54-117">The following example removes a particular column by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delindex)]
 [!code-vb[TableSnippets2#_Table_Columns_DelIndex](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delindex)]  
  
## <a name="example"></a><span data-ttu-id="09c54-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="09c54-118">Example</span></span>  
 <span data-ttu-id="09c54-119">En el ejemplo siguiente se quita todas las columnas de la colección de columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="09c54-119">The following example removes all columns from the table's columns collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Clear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_clear)]
 [!code-vb[TableSnippets2#_Table_Columns_Clear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_clear)]  
  
## <a name="see-also"></a><span data-ttu-id="09c54-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="09c54-120">See Also</span></span>  
 [<span data-ttu-id="09c54-121">Información general sobre tablas</span><span class="sxs-lookup"><span data-stu-id="09c54-121">Table Overview</span></span>](../../../../docs/framework/wpf/advanced/table-overview.md)  
 [<span data-ttu-id="09c54-122">Definir una tabla con XAML</span><span class="sxs-lookup"><span data-stu-id="09c54-122">Define a Table with XAML</span></span>](../../../../docs/framework/wpf/advanced/how-to-define-a-table-with-xaml.md)  
 [<span data-ttu-id="09c54-123">Compilar una tabla mediante programación</span><span class="sxs-lookup"><span data-stu-id="09c54-123">Build a Table Programmatically</span></span>](../../../../docs/framework/wpf/advanced/how-to-build-a-table-programmatically.md)  
 [<span data-ttu-id="09c54-124">Manipular grupos de filas de una tabla mediante la propiedad RowGroups</span><span class="sxs-lookup"><span data-stu-id="09c54-124">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)  
 [<span data-ttu-id="09c54-125">Manipular un objeto FlowDocument mediante la propiedad Blocks</span><span class="sxs-lookup"><span data-stu-id="09c54-125">Manipulate a FlowDocument through the Blocks Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)  
 [<span data-ttu-id="09c54-126">Manipular grupos de filas de una tabla mediante la propiedad RowGroups</span><span class="sxs-lookup"><span data-stu-id="09c54-126">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
