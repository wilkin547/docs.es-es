---
title: "Cómo: Usar elementos de contenido dinámico"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- flow content elements [WPF]
- documents [WPF], flow content elements
ms.assetid: 70fa11cd-5fa7-4872-a1cc-04d80f1132be
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c1350a380e97631ac290e57de64fec696535fecc
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-flow-content-elements"></a><span data-ttu-id="fd4ff-102">Cómo: Usar elementos de contenido dinámico</span><span class="sxs-lookup"><span data-stu-id="fd4ff-102">How to: Use Flow Content Elements</span></span>
<span data-ttu-id="fd4ff-103">En el ejemplo siguiente se muestra el uso declarativo de varios elementos de contenido dinámico y los atributos asociados.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-103">The following example demonstrates declarative usage for various flow content elements and associated attributes.</span></span>  <span data-ttu-id="fd4ff-104">Los elementos y atributos que se muestran incluyen:</span><span class="sxs-lookup"><span data-stu-id="fd4ff-104">Elements and attributes demonstrated include:</span></span>  
  
-   <span data-ttu-id="fd4ff-105"><xref:System.Windows.Documents.Bold> (elemento)</span><span class="sxs-lookup"><span data-stu-id="fd4ff-105"><xref:System.Windows.Documents.Bold> element</span></span>  
  
-   <span data-ttu-id="fd4ff-106">Atributo <xref:System.Windows.Documents.Block.BreakPageBefore%2A></span><span class="sxs-lookup"><span data-stu-id="fd4ff-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A> attribute</span></span>  
  
-   <span data-ttu-id="fd4ff-107">Atributo <xref:System.Windows.Documents.TextElement.FontSize%2A></span><span class="sxs-lookup"><span data-stu-id="fd4ff-107"><xref:System.Windows.Documents.TextElement.FontSize%2A> attribute</span></span>  
  
-   <span data-ttu-id="fd4ff-108"><xref:System.Windows.Documents.Italic> (elemento)</span><span class="sxs-lookup"><span data-stu-id="fd4ff-108"><xref:System.Windows.Documents.Italic> element</span></span>  
  
-   <span data-ttu-id="fd4ff-109"><xref:System.Windows.Documents.LineBreak> (elemento)</span><span class="sxs-lookup"><span data-stu-id="fd4ff-109"><xref:System.Windows.Documents.LineBreak> element</span></span>  
  
-   <span data-ttu-id="fd4ff-110"><xref:System.Windows.Documents.List> (elemento)</span><span class="sxs-lookup"><span data-stu-id="fd4ff-110"><xref:System.Windows.Documents.List> element</span></span>  
  
-   <span data-ttu-id="fd4ff-111"><xref:System.Windows.Documents.ListItem> (elemento)</span><span class="sxs-lookup"><span data-stu-id="fd4ff-111"><xref:System.Windows.Documents.ListItem> element</span></span>  
  
-   <span data-ttu-id="fd4ff-112"><xref:System.Windows.Documents.Paragraph> (elemento)</span><span class="sxs-lookup"><span data-stu-id="fd4ff-112"><xref:System.Windows.Documents.Paragraph> element</span></span>  
  
-   <span data-ttu-id="fd4ff-113"><xref:System.Windows.Documents.Run> (elemento)</span><span class="sxs-lookup"><span data-stu-id="fd4ff-113"><xref:System.Windows.Documents.Run> element</span></span>  
  
-   <span data-ttu-id="fd4ff-114"><xref:System.Windows.Documents.Section> (elemento)</span><span class="sxs-lookup"><span data-stu-id="fd4ff-114"><xref:System.Windows.Documents.Section> element</span></span>  
  
-   <span data-ttu-id="fd4ff-115"><xref:System.Windows.Documents.Span> (elemento)</span><span class="sxs-lookup"><span data-stu-id="fd4ff-115"><xref:System.Windows.Documents.Span> element</span></span>  
  
-   <span data-ttu-id="fd4ff-116"><xref:System.Windows.Documents.Typography.Variants%2A>atributo (superíndice y subíndice)</span><span class="sxs-lookup"><span data-stu-id="fd4ff-116"><xref:System.Windows.Documents.Typography.Variants%2A> attribute (superscript and subscript)</span></span>  
  
-   <span data-ttu-id="fd4ff-117"><xref:System.Windows.Documents.Underline> (elemento)</span><span class="sxs-lookup"><span data-stu-id="fd4ff-117"><xref:System.Windows.Documents.Underline> element</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd4ff-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fd4ff-118">Example</span></span>  
 [!code-xaml[FlowDocInlineSnippets#_InlineElementsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocInlineSnippets/CS/document.xaml#_inlineelementsxaml)]
