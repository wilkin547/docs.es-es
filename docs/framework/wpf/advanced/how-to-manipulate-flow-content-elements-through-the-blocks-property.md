---
title: 'Cómo: Manipular elementos de contenido dinámico mediante la propiedad Blocks'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], manipulating flow content elements through Blocks property
- flow content elements [WPF], manipulating through Blocks property
- properties [WPF], Blocks [WPF], manipulating flow content elements
- Blocks property [WPF], manipulating flow content elements
ms.assetid: aeda4ece-b979-4818-a093-ef938e908751
ms.openlocfilehash: 74710c4a6dd58cf2836cd7671a3e39401a5ea774
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544555"
---
# <a name="how-to-manipulate-flow-content-elements-through-the-blocks-property"></a><span data-ttu-id="eb311-102">Cómo: Manipular elementos de contenido dinámico mediante la propiedad Blocks</span><span class="sxs-lookup"><span data-stu-id="eb311-102">How to: Manipulate Flow Content Elements through the Blocks Property</span></span>
<span data-ttu-id="eb311-103">Estos ejemplos muestran algunas de las operaciones más comunes que se pueden realizar en elementos de contenido dinámico a través de la **bloques** propiedad.</span><span class="sxs-lookup"><span data-stu-id="eb311-103">These examples demonstrate some of the more common operations that can be performed on flow content elements through the **Blocks** property.</span></span> <span data-ttu-id="eb311-104">Esta propiedad se utiliza para agregar y quitar elementos de <xref:System.Windows.Documents.BlockCollection>.</span><span class="sxs-lookup"><span data-stu-id="eb311-104">This property is used to add and remove items from <xref:System.Windows.Documents.BlockCollection>.</span></span> <span data-ttu-id="eb311-105">Flujo de contenido de elementos de esa característica un **bloques** propiedad incluyen:</span><span class="sxs-lookup"><span data-stu-id="eb311-105">Flow content elements that feature a **Blocks** property include:</span></span>  
  
-   <xref:System.Windows.Documents.Figure>  
  
-   <xref:System.Windows.Documents.Floater>  
  
-   <xref:System.Windows.Documents.ListItem>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.TableCell>  
  
 <span data-ttu-id="eb311-106">Estos ejemplos se realizará al usar <xref:System.Windows.Documents.Section> como el flujo de elemento de contenido, pero estas técnicas son aplicables a todos los elementos que hospedan una colección de elementos de contenido de flujo.</span><span class="sxs-lookup"><span data-stu-id="eb311-106">These examples happen to use <xref:System.Windows.Documents.Section> as the flow content element, but these techniques are applicable to all elements that host a flow content element collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb311-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eb311-107">Example</span></span>  
 <span data-ttu-id="eb311-108">En el ejemplo siguiente se crea un nuevo <xref:System.Windows.Documents.Section> y, a continuación, usa el **agregar** método para agregar un párrafo nuevo a la **sección** contenido.</span><span class="sxs-lookup"><span data-stu-id="eb311-108">The following example creates a new <xref:System.Windows.Documents.Section> and then uses the **Add** method to add a new Paragraph to the **Section** contents.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
## <a name="example"></a><span data-ttu-id="eb311-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eb311-109">Example</span></span>  
 <span data-ttu-id="eb311-110">En el ejemplo siguiente se crea un nuevo <xref:System.Windows.Documents.Paragraph> elemento y se inserta al principio de la <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="eb311-110">The following example creates a new <xref:System.Windows.Documents.Paragraph> element and inserts it at the beginning of the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksinsert)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksinsert)]  
  
## <a name="example"></a><span data-ttu-id="eb311-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eb311-111">Example</span></span>  
 <span data-ttu-id="eb311-112">En el ejemplo siguiente se obtiene el número de nivel superior <xref:System.Windows.Documents.Block> elementos incluidos en el <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="eb311-112">The following example gets the number of top-level <xref:System.Windows.Documents.Block> elements contained in the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksCount](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblockscount)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksCount](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblockscount)]  
  
## <a name="example"></a><span data-ttu-id="eb311-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eb311-113">Example</span></span>  
 <span data-ttu-id="eb311-114">En el ejemplo siguiente se elimina el último <xref:System.Windows.Documents.Block> elemento en el <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="eb311-114">The following example deletes the last <xref:System.Windows.Documents.Block> element in the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksremovelast)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksremovelast)]  
  
## <a name="example"></a><span data-ttu-id="eb311-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eb311-115">Example</span></span>  
 <span data-ttu-id="eb311-116">En el ejemplo siguiente se borra todo el contenido (<xref:System.Windows.Documents.Block> elementos) de la <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="eb311-116">The following example clears all of the contents (<xref:System.Windows.Documents.Block> elements) from the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksclear)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksclear)]  
  
## <a name="see-also"></a><span data-ttu-id="eb311-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb311-117">See Also</span></span>  
 <xref:System.Windows.Documents.BlockCollection>  
 <xref:System.Windows.Documents.InlineCollection>  
 <xref:System.Windows.Documents.ListItemCollection>  
 [<span data-ttu-id="eb311-118">Información general sobre documentos dinámicos</span><span class="sxs-lookup"><span data-stu-id="eb311-118">Flow Document Overview</span></span>](../../../../docs/framework/wpf/advanced/flow-document-overview.md)  
 [<span data-ttu-id="eb311-119">Manipular grupos de filas de una tabla mediante la propiedad RowGroups</span><span class="sxs-lookup"><span data-stu-id="eb311-119">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)  
 [<span data-ttu-id="eb311-120">Manipular las columnas de una tabla mediante la propiedad Columns</span><span class="sxs-lookup"><span data-stu-id="eb311-120">Manipulate a Table's Columns through the Columns Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)  
 [<span data-ttu-id="eb311-121">Manipular grupos de filas de una tabla mediante la propiedad RowGroups</span><span class="sxs-lookup"><span data-stu-id="eb311-121">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
