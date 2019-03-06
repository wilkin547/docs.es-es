---
title: Procedimiento Usar elementos de contenido dinámico
ms.date: 03/30/2017
helpviewer_keywords:
- flow content elements [WPF]
- documents [WPF], flow content elements
ms.assetid: 70fa11cd-5fa7-4872-a1cc-04d80f1132be
ms.openlocfilehash: df591304736adf1725b2b4235149bd426fe15216
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368117"
---
# <a name="how-to-use-flow-content-elements"></a><span data-ttu-id="41c4f-102">Procedimiento Usar elementos de contenido dinámico</span><span class="sxs-lookup"><span data-stu-id="41c4f-102">How to: Use Flow Content Elements</span></span>
<span data-ttu-id="41c4f-103">En el ejemplo siguiente se muestra el uso declarativo de varios elementos de contenido dinámico y los atributos asociados.</span><span class="sxs-lookup"><span data-stu-id="41c4f-103">The following example demonstrates declarative usage for various flow content elements and associated attributes.</span></span>  <span data-ttu-id="41c4f-104">Los elementos y atributos que se muestran incluyen:</span><span class="sxs-lookup"><span data-stu-id="41c4f-104">Elements and attributes demonstrated include:</span></span>  
  
-   <span data-ttu-id="41c4f-105"><xref:System.Windows.Documents.Bold> (elemento)</span><span class="sxs-lookup"><span data-stu-id="41c4f-105"><xref:System.Windows.Documents.Bold> element</span></span>  
  
-   <span data-ttu-id="41c4f-106">Atributo <xref:System.Windows.Documents.Block.BreakPageBefore%2A></span><span class="sxs-lookup"><span data-stu-id="41c4f-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A> attribute</span></span>  
  
-   <span data-ttu-id="41c4f-107">Atributo <xref:System.Windows.Documents.TextElement.FontSize%2A></span><span class="sxs-lookup"><span data-stu-id="41c4f-107"><xref:System.Windows.Documents.TextElement.FontSize%2A> attribute</span></span>  
  
-   <span data-ttu-id="41c4f-108"><xref:System.Windows.Documents.Italic> (elemento)</span><span class="sxs-lookup"><span data-stu-id="41c4f-108"><xref:System.Windows.Documents.Italic> element</span></span>  
  
-   <span data-ttu-id="41c4f-109"><xref:System.Windows.Documents.LineBreak> (elemento)</span><span class="sxs-lookup"><span data-stu-id="41c4f-109"><xref:System.Windows.Documents.LineBreak> element</span></span>  
  
-   <span data-ttu-id="41c4f-110"><xref:System.Windows.Documents.List> (elemento)</span><span class="sxs-lookup"><span data-stu-id="41c4f-110"><xref:System.Windows.Documents.List> element</span></span>  
  
-   <span data-ttu-id="41c4f-111"><xref:System.Windows.Documents.ListItem> (elemento)</span><span class="sxs-lookup"><span data-stu-id="41c4f-111"><xref:System.Windows.Documents.ListItem> element</span></span>  
  
-   <span data-ttu-id="41c4f-112"><xref:System.Windows.Documents.Paragraph> (elemento)</span><span class="sxs-lookup"><span data-stu-id="41c4f-112"><xref:System.Windows.Documents.Paragraph> element</span></span>  
  
-   <span data-ttu-id="41c4f-113"><xref:System.Windows.Documents.Run> (elemento)</span><span class="sxs-lookup"><span data-stu-id="41c4f-113"><xref:System.Windows.Documents.Run> element</span></span>  
  
-   <span data-ttu-id="41c4f-114"><xref:System.Windows.Documents.Section> (elemento)</span><span class="sxs-lookup"><span data-stu-id="41c4f-114"><xref:System.Windows.Documents.Section> element</span></span>  
  
-   <span data-ttu-id="41c4f-115"><xref:System.Windows.Documents.Span> (elemento)</span><span class="sxs-lookup"><span data-stu-id="41c4f-115"><xref:System.Windows.Documents.Span> element</span></span>  
  
-   <span data-ttu-id="41c4f-116"><xref:System.Windows.Documents.Typography.Variants%2A> atributo (superíndice y subíndice)</span><span class="sxs-lookup"><span data-stu-id="41c4f-116"><xref:System.Windows.Documents.Typography.Variants%2A> attribute (superscript and subscript)</span></span>  
  
-   <span data-ttu-id="41c4f-117"><xref:System.Windows.Documents.Underline> (elemento)</span><span class="sxs-lookup"><span data-stu-id="41c4f-117"><xref:System.Windows.Documents.Underline> element</span></span>  
  
## <a name="example"></a><span data-ttu-id="41c4f-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="41c4f-118">Example</span></span>  
 [!code-xaml[FlowDocInlineSnippets#_InlineElementsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocInlineSnippets/CS/document.xaml#_inlineelementsxaml)]
