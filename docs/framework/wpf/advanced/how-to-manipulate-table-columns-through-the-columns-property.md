---
title: Procedimiento Manipular una tabla&#39;s columnas mediante la propiedad Columns
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
ms.openlocfilehash: f560e85888b5617f545082d47d124163d492ec00
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655824"
---
# <a name="how-to-manipulate-a-table39s-columns-through-the-columns-property"></a><span data-ttu-id="61f35-102">Procedimiento Manipular una tabla&#39;s columnas mediante la propiedad Columns</span><span class="sxs-lookup"><span data-stu-id="61f35-102">How to: Manipulate a Table&#39;s Columns through the Columns Property</span></span>
<span data-ttu-id="61f35-103">En este ejemplo muestra algunas de las operaciones más comunes que pueden realizarse en las columnas de una tabla mediante el <xref:System.Windows.Documents.Table.Columns%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="61f35-103">This example demonstrates some of the more common operations that can be performed on a table's columns through the <xref:System.Windows.Documents.Table.Columns%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61f35-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="61f35-104">Example</span></span>  
 <span data-ttu-id="61f35-105">El ejemplo siguiente se crea una nueva tabla y, a continuación, usa el <xref:System.Windows.Documents.TableColumnCollection.Add%2A> método para agregar columnas a la tabla <xref:System.Windows.Documents.Table.Columns%2A> colección.</span><span class="sxs-lookup"><span data-stu-id="61f35-105">The following example creates a new table and then uses the <xref:System.Windows.Documents.TableColumnCollection.Add%2A> method to add columns to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Add](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_add)]
 [!code-vb[TableSnippets2#_Table_Columns_Add](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_add)]  
  
## <a name="example"></a><span data-ttu-id="61f35-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="61f35-106">Example</span></span>  
 <span data-ttu-id="61f35-107">El ejemplo siguiente inserta un nuevo <xref:System.Windows.Documents.TableColumn>.</span><span class="sxs-lookup"><span data-stu-id="61f35-107">The following example inserts a new <xref:System.Windows.Documents.TableColumn>.</span></span>  <span data-ttu-id="61f35-108">La nueva columna se inserta en la posición de índice 0, lo que la primera columna nueva en la tabla.</span><span class="sxs-lookup"><span data-stu-id="61f35-108">The new column is inserted at index position 0, making it the new first column in the table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61f35-109">El <xref:System.Windows.Documents.TableColumnCollection> colección utiliza la indización de base cero estándar.</span><span class="sxs-lookup"><span data-stu-id="61f35-109">The <xref:System.Windows.Documents.TableColumnCollection> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Insert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_insert)]
 [!code-vb[TableSnippets2#_Table_Columns_Insert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_insert)]  
  
## <a name="example"></a><span data-ttu-id="61f35-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="61f35-110">Example</span></span>  
 <span data-ttu-id="61f35-111">El ejemplo siguiente se obtiene acceso a algunas propiedades arbitrarias en las columnas de la <xref:System.Windows.Documents.TableColumnCollection> colección, que hace referencia a columnas concretas por su índice.</span><span class="sxs-lookup"><span data-stu-id="61f35-111">The following example accesses some arbitrary properties on columns in the <xref:System.Windows.Documents.TableColumnCollection> collection, referring to particular columns by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Manip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_manip)]
 [!code-vb[TableSnippets2#_Table_Columns_Manip](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_manip)]  
  
## <a name="example"></a><span data-ttu-id="61f35-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="61f35-112">Example</span></span>  
 <span data-ttu-id="61f35-113">El ejemplo siguiente obtiene el número de columnas que están actualmente alojadas por la tabla.</span><span class="sxs-lookup"><span data-stu-id="61f35-113">The following example gets the number of columns currently hosted by the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Count](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_count)]
 [!code-vb[TableSnippets2#_Table_Columns_Count](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_count)]  
  
## <a name="example"></a><span data-ttu-id="61f35-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="61f35-114">Example</span></span>  
 <span data-ttu-id="61f35-115">El ejemplo siguiente quita una columna en particular por referencia.</span><span class="sxs-lookup"><span data-stu-id="61f35-115">The following example removes a particular column by reference.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelRef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delref)]
 [!code-vb[TableSnippets2#_Table_Columns_DelRef](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delref)]  
  
## <a name="example"></a><span data-ttu-id="61f35-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="61f35-116">Example</span></span>  
 <span data-ttu-id="61f35-117">El ejemplo siguiente quita una determinada columna al índice.</span><span class="sxs-lookup"><span data-stu-id="61f35-117">The following example removes a particular column by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delindex)]
 [!code-vb[TableSnippets2#_Table_Columns_DelIndex](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delindex)]  
  
## <a name="example"></a><span data-ttu-id="61f35-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="61f35-118">Example</span></span>  
 <span data-ttu-id="61f35-119">El ejemplo siguiente quita todas las columnas de la colección de columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="61f35-119">The following example removes all columns from the table's columns collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Clear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_clear)]
 [!code-vb[TableSnippets2#_Table_Columns_Clear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_clear)]  
  
## <a name="see-also"></a><span data-ttu-id="61f35-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="61f35-120">See also</span></span>
- [<span data-ttu-id="61f35-121">Información general sobre tablas</span><span class="sxs-lookup"><span data-stu-id="61f35-121">Table Overview</span></span>](../../../../docs/framework/wpf/advanced/table-overview.md)
- [<span data-ttu-id="61f35-122">Definir una tabla con XAML</span><span class="sxs-lookup"><span data-stu-id="61f35-122">Define a Table with XAML</span></span>](../../../../docs/framework/wpf/advanced/how-to-define-a-table-with-xaml.md)
- [<span data-ttu-id="61f35-123">Compilar una tabla mediante programación</span><span class="sxs-lookup"><span data-stu-id="61f35-123">Build a Table Programmatically</span></span>](../../../../docs/framework/wpf/advanced/how-to-build-a-table-programmatically.md)
- [<span data-ttu-id="61f35-124">Manipular grupos de filas de una tabla mediante la propiedad RowGroups</span><span class="sxs-lookup"><span data-stu-id="61f35-124">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="61f35-125">Manipular un objeto FlowDocument mediante la propiedad Blocks</span><span class="sxs-lookup"><span data-stu-id="61f35-125">Manipulate a FlowDocument through the Blocks Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [<span data-ttu-id="61f35-126">Manipular grupos de filas de una tabla mediante la propiedad RowGroups</span><span class="sxs-lookup"><span data-stu-id="61f35-126">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
