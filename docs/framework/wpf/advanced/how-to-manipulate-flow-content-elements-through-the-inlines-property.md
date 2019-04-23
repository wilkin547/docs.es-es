---
title: Procedimiento Manipular elementos de contenido dinámico mediante la propiedad Inlines
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flow content elements [WPF], manipulating through Inlines property
- documents [WPF], manipulating flow Content elements through Inlines property
- Inlines property [WPF], manipulating flow Content elements
- properties [WPF], Inlines [WPF], manipulating flow Content elements
ms.assetid: 510780d2-3da1-4360-8763-7054bda22ea3
ms.openlocfilehash: cfff958bb4c87e6bfecf2d280224cda233c31806
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186074"
---
# <a name="how-to-manipulate-flow-content-elements-through-the-inlines-property"></a><span data-ttu-id="51274-102">Procedimiento Manipular elementos de contenido dinámico mediante la propiedad Inlines</span><span class="sxs-lookup"><span data-stu-id="51274-102">How to: Manipulate Flow Content Elements through the Inlines Property</span></span>
<span data-ttu-id="51274-103">Estos ejemplos muestran algunas de las operaciones más comunes que se pueden realizar en elementos de contenido dinámico insertado (y los contenedores de tales elementos, tales como <xref:System.Windows.Controls.TextBlock>) a través de la **Inlines** propiedad.</span><span class="sxs-lookup"><span data-stu-id="51274-103">These examples demonstrate some of the more common operations that can be performed on inline flow content elements (and containers of such elements, such as <xref:System.Windows.Controls.TextBlock>) through the **Inlines** property.</span></span> <span data-ttu-id="51274-104">Esta propiedad se utiliza para agregar y quitar elementos de <xref:System.Windows.Documents.InlineCollection>.</span><span class="sxs-lookup"><span data-stu-id="51274-104">This property is used to add and remove items from <xref:System.Windows.Documents.InlineCollection>.</span></span> <span data-ttu-id="51274-105">Flujo de contenido de elementos de esa característica un **Inlines** propiedad incluyen:</span><span class="sxs-lookup"><span data-stu-id="51274-105">Flow content elements that feature an **Inlines** property include:</span></span>  
  
-   <xref:System.Windows.Documents.Bold>  
  
-   <xref:System.Windows.Documents.Hyperlink>  
  
-   <xref:System.Windows.Documents.Italic>  
  
-   <xref:System.Windows.Documents.Paragraph>  
  
-   <xref:System.Windows.Documents.Span>  
  
-   <xref:System.Windows.Documents.Underline>  
  
 <span data-ttu-id="51274-106">Estos ejemplos se producen al usar <xref:System.Windows.Documents.Span> como el flujo de elemento de contenido, pero estas técnicas son aplicables a todos los elementos o controles que hospedan un <xref:System.Windows.Documents.InlineCollection> colección.</span><span class="sxs-lookup"><span data-stu-id="51274-106">These examples happen to use <xref:System.Windows.Documents.Span> as the flow content element, but these techniques are applicable to all elements or controls that host an <xref:System.Windows.Documents.InlineCollection> collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51274-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="51274-107">Example</span></span>  
 <span data-ttu-id="51274-108">En el ejemplo siguiente se crea un nuevo <xref:System.Windows.Documents.Span> objeto y, a continuación, utiliza el **agregar** método para agregar texto dos series como elementos secundarios de contenido de la <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="51274-108">The following example creates a new <xref:System.Windows.Documents.Span> object, and then uses the **Add** method to add two text runs as content children of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
## <a name="example"></a><span data-ttu-id="51274-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="51274-109">Example</span></span>  
 <span data-ttu-id="51274-110">En el ejemplo siguiente se crea un nuevo <xref:System.Windows.Documents.Run> elemento y lo inserta al principio de la <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="51274-110">The following example creates a new <xref:System.Windows.Documents.Run> element and inserts it at the beginning of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
## <a name="example"></a><span data-ttu-id="51274-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="51274-111">Example</span></span>  
 <span data-ttu-id="51274-112">En el ejemplo siguiente se obtiene el número de nivel superior <xref:System.Windows.Documents.Inline> elementos contenidos en el <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="51274-112">The following example gets the number of top-level <xref:System.Windows.Documents.Inline> elements contained in the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesCount](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinescount)]
 [!code-vb[SpanSnippets#_SpanInlinesCount](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinescount)]  
  
## <a name="example"></a><span data-ttu-id="51274-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="51274-113">Example</span></span>  
 <span data-ttu-id="51274-114">En el ejemplo siguiente se elimina la última <xref:System.Windows.Documents.Inline> elemento en el <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="51274-114">The following example deletes the last <xref:System.Windows.Documents.Inline> element in the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
## <a name="example"></a><span data-ttu-id="51274-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="51274-115">Example</span></span>  
 <span data-ttu-id="51274-116">El siguiente ejemplo borra todo el contenido (<xref:System.Windows.Documents.Inline> elementos) desde el <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="51274-116">The following example clears all of the contents (<xref:System.Windows.Documents.Inline> elements) from the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
## <a name="see-also"></a><span data-ttu-id="51274-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="51274-117">See also</span></span>

- <xref:System.Windows.Documents.BlockCollection>
- <xref:System.Windows.Documents.InlineCollection>
- <xref:System.Windows.Documents.ListItemCollection>
- [<span data-ttu-id="51274-118">Información general sobre documentos dinámicos</span><span class="sxs-lookup"><span data-stu-id="51274-118">Flow Document Overview</span></span>](flow-document-overview.md)
- [<span data-ttu-id="51274-119">Manipular un objeto FlowDocument mediante la propiedad Blocks</span><span class="sxs-lookup"><span data-stu-id="51274-119">Manipulate a FlowDocument through the Blocks Property</span></span>](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [<span data-ttu-id="51274-120">Manipular las columnas de una tabla mediante la propiedad Columns</span><span class="sxs-lookup"><span data-stu-id="51274-120">Manipulate a Table's Columns through the Columns Property</span></span>](how-to-manipulate-table-columns-through-the-columns-property.md)
- [<span data-ttu-id="51274-121">Manipular grupos de filas de una tabla mediante la propiedad RowGroups</span><span class="sxs-lookup"><span data-stu-id="51274-121">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
