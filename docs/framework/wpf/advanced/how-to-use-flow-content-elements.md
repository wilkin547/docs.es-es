---
title: Procedimiento Usar elementos de contenido dinámico
ms.date: 03/30/2017
helpviewer_keywords:
- flow content elements [WPF]
- documents [WPF], flow content elements
ms.assetid: 70fa11cd-5fa7-4872-a1cc-04d80f1132be
ms.openlocfilehash: df591304736adf1725b2b4235149bd426fe15216
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052357"
---
# <a name="how-to-use-flow-content-elements"></a><span data-ttu-id="60f10-102">Procedimiento Usar elementos de contenido dinámico</span><span class="sxs-lookup"><span data-stu-id="60f10-102">How to: Use Flow Content Elements</span></span>
<span data-ttu-id="60f10-103">En el ejemplo siguiente se muestra el uso declarativo de varios elementos de contenido dinámico y los atributos asociados.</span><span class="sxs-lookup"><span data-stu-id="60f10-103">The following example demonstrates declarative usage for various flow content elements and associated attributes.</span></span>  <span data-ttu-id="60f10-104">Los elementos y atributos que se muestran incluyen:</span><span class="sxs-lookup"><span data-stu-id="60f10-104">Elements and attributes demonstrated include:</span></span>  
  
- <span data-ttu-id="60f10-105">Elemento <xref:System.Windows.Documents.Bold></span><span class="sxs-lookup"><span data-stu-id="60f10-105"><xref:System.Windows.Documents.Bold> element</span></span>  
  
- <span data-ttu-id="60f10-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A> Atributo</span><span class="sxs-lookup"><span data-stu-id="60f10-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A> attribute</span></span>  
  
- <span data-ttu-id="60f10-107"><xref:System.Windows.Documents.TextElement.FontSize%2A> Atributo</span><span class="sxs-lookup"><span data-stu-id="60f10-107"><xref:System.Windows.Documents.TextElement.FontSize%2A> attribute</span></span>  
  
- <span data-ttu-id="60f10-108">Elemento <xref:System.Windows.Documents.Italic></span><span class="sxs-lookup"><span data-stu-id="60f10-108"><xref:System.Windows.Documents.Italic> element</span></span>  
  
- <span data-ttu-id="60f10-109">Elemento <xref:System.Windows.Documents.LineBreak></span><span class="sxs-lookup"><span data-stu-id="60f10-109"><xref:System.Windows.Documents.LineBreak> element</span></span>  
  
- <span data-ttu-id="60f10-110">Elemento <xref:System.Windows.Documents.List></span><span class="sxs-lookup"><span data-stu-id="60f10-110"><xref:System.Windows.Documents.List> element</span></span>  
  
- <span data-ttu-id="60f10-111">Elemento <xref:System.Windows.Documents.ListItem></span><span class="sxs-lookup"><span data-stu-id="60f10-111"><xref:System.Windows.Documents.ListItem> element</span></span>  
  
- <span data-ttu-id="60f10-112">Elemento <xref:System.Windows.Documents.Paragraph></span><span class="sxs-lookup"><span data-stu-id="60f10-112"><xref:System.Windows.Documents.Paragraph> element</span></span>  
  
- <span data-ttu-id="60f10-113">Elemento <xref:System.Windows.Documents.Run></span><span class="sxs-lookup"><span data-stu-id="60f10-113"><xref:System.Windows.Documents.Run> element</span></span>  
  
- <span data-ttu-id="60f10-114">Elemento <xref:System.Windows.Documents.Section></span><span class="sxs-lookup"><span data-stu-id="60f10-114"><xref:System.Windows.Documents.Section> element</span></span>  
  
- <span data-ttu-id="60f10-115">Elemento <xref:System.Windows.Documents.Span></span><span class="sxs-lookup"><span data-stu-id="60f10-115"><xref:System.Windows.Documents.Span> element</span></span>  
  
- <span data-ttu-id="60f10-116"><xref:System.Windows.Documents.Typography.Variants%2A> atributo (superíndice y subíndice)</span><span class="sxs-lookup"><span data-stu-id="60f10-116"><xref:System.Windows.Documents.Typography.Variants%2A> attribute (superscript and subscript)</span></span>  
  
- <span data-ttu-id="60f10-117">Elemento <xref:System.Windows.Documents.Underline></span><span class="sxs-lookup"><span data-stu-id="60f10-117"><xref:System.Windows.Documents.Underline> element</span></span>  
  
## <a name="example"></a><span data-ttu-id="60f10-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="60f10-118">Example</span></span>  
 [!code-xaml[FlowDocInlineSnippets#_InlineElementsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocInlineSnippets/CS/document.xaml#_inlineelementsxaml)]
