---
title: Filtrar Manipular un objeto FlowDocument mediante la propiedad Blocks
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'documents [WPF], manipulating FlowDocuments through Blocks property [WPF], , '
- ', '
ms.assetid: cbb7291e-3f1b-433e-9e16-f4d93ced14e8
ms.openlocfilehash: c8098df74bb8472648dae2ca04de7a18f062c9e3
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365937"
---
# <a name="how-to-manipulate-a-flowdocument-through-the-blocks-property"></a><span data-ttu-id="1bdc0-102">Filtrar Manipular un objeto FlowDocument mediante la propiedad Blocks</span><span class="sxs-lookup"><span data-stu-id="1bdc0-102">How to: Manipulate a FlowDocument through the Blocks Property</span></span>
<span data-ttu-id="1bdc0-103">Estos ejemplos muestran algunas de las operaciones más comunes que pueden realizarse en un <xref:System.Windows.Documents.FlowDocument> a través de la <xref:System.Windows.Documents.FlowDocument.Blocks%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="1bdc0-103">These examples demonstrate some of the more common operations that can be performed on a <xref:System.Windows.Documents.FlowDocument> through the <xref:System.Windows.Documents.FlowDocument.Blocks%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bdc0-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1bdc0-104">Example</span></span>  
 <span data-ttu-id="1bdc0-105">En el ejemplo siguiente se crea un nuevo <xref:System.Windows.Documents.FlowDocument> y, a continuación, se anexa un nuevo <xref:System.Windows.Documents.Paragraph> elemento a la <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="1bdc0-105">The following example creates a new <xref:System.Windows.Documents.FlowDocument> and then appends a new <xref:System.Windows.Documents.Paragraph> element to the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksadd)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksadd)]  
  
## <a name="example"></a><span data-ttu-id="1bdc0-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1bdc0-106">Example</span></span>  
 <span data-ttu-id="1bdc0-107">En el ejemplo siguiente se crea un nuevo <xref:System.Windows.Documents.Paragraph> elemento y lo inserta al principio de la <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="1bdc0-107">The following example creates a new <xref:System.Windows.Documents.Paragraph> element and inserts it at the beginning of the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksinsert)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksinsert)]  
  
## <a name="example"></a><span data-ttu-id="1bdc0-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1bdc0-108">Example</span></span>  
 <span data-ttu-id="1bdc0-109">En el ejemplo siguiente se obtiene el número de nivel superior <xref:System.Windows.Documents.Block> elementos contenidos en el <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="1bdc0-109">The following example gets the number of top-level <xref:System.Windows.Documents.Block> elements contained in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksCount](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblockscount)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksCount](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblockscount)]  
  
## <a name="example"></a><span data-ttu-id="1bdc0-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1bdc0-110">Example</span></span>  
 <span data-ttu-id="1bdc0-111">En el ejemplo siguiente se elimina la última <xref:System.Windows.Documents.Block> elemento en el <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="1bdc0-111">The following example deletes the last <xref:System.Windows.Documents.Block> element in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksremovelast)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksremovelast)]  
  
## <a name="example"></a><span data-ttu-id="1bdc0-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1bdc0-112">Example</span></span>  
 <span data-ttu-id="1bdc0-113">El siguiente ejemplo borra todo el contenido (<xref:System.Windows.Documents.Block> elementos) desde el <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="1bdc0-113">The following example clears all of the contents (<xref:System.Windows.Documents.Block> elements) from the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksClear](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksclear)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksclear)]  
  
## <a name="see-also"></a><span data-ttu-id="1bdc0-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="1bdc0-114">See also</span></span>
- [<span data-ttu-id="1bdc0-115">Manipular grupos de filas de una tabla mediante la propiedad RowGroups</span><span class="sxs-lookup"><span data-stu-id="1bdc0-115">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="1bdc0-116">Manipular las columnas de una tabla mediante la propiedad Columns</span><span class="sxs-lookup"><span data-stu-id="1bdc0-116">Manipulate a Table's Columns through the Columns Property</span></span>](how-to-manipulate-table-columns-through-the-columns-property.md)
- [<span data-ttu-id="1bdc0-117">Manipular grupos de filas de una tabla mediante la propiedad RowGroups</span><span class="sxs-lookup"><span data-stu-id="1bdc0-117">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
