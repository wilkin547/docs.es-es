---
title: Procedimiento Ajustar el espaciado entre párrafos
ms.date: 03/30/2017
helpviewer_keywords:
- spacing between paragraphs [WPF]
- paragraphs [WPF], spacing between
- documents [WPF], adjusting spacing between paragraphs
ms.assetid: 7cd2f2ac-0e19-4587-bfb6-7f5b18c9536e
ms.openlocfilehash: e2a6ba34e3ab15eb316671fef7c11bea03d53c73
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777018"
---
# <a name="how-to-adjust-spacing-between-paragraphs"></a><span data-ttu-id="92c69-102">Procedimiento Ajustar el espaciado entre párrafos</span><span class="sxs-lookup"><span data-stu-id="92c69-102">How to: Adjust Spacing Between Paragraphs</span></span>
<span data-ttu-id="92c69-103">En este ejemplo se muestra cómo ajustar o eliminar el espaciado entre párrafos en el contenido dinámico.</span><span class="sxs-lookup"><span data-stu-id="92c69-103">This example shows how to adjust or eliminate spacing between paragraphs in flow content.</span></span>  
  
 <span data-ttu-id="92c69-104">En el contenido dinámico, el espacio adicional que aparece entre párrafos es el resultado de los márgenes establecidos para estos párrafos; por lo tanto, se puede controlar el espaciado entre párrafos ajustando los márgenes en los párrafos.</span><span class="sxs-lookup"><span data-stu-id="92c69-104">In flow content, extra space that appears between paragraphs is the result of margins set on these paragraphs; thus, the spacing between paragraphs can be controlled by adjusting the margins on those paragraphs.</span></span>  <span data-ttu-id="92c69-105">Para eliminar por completo el espaciado adicional entre los dos párrafos, establezca los márgenes en los párrafos para **0**.</span><span class="sxs-lookup"><span data-stu-id="92c69-105">To eliminate extra spacing between two paragraphs altogether, set the margins for the paragraphs to **0**.</span></span>  <span data-ttu-id="92c69-106">Para lograr un espaciado uniforme entre párrafos a lo largo de toda una <xref:System.Windows.Documents.FlowDocument>, usar estilos para establecer un valor de margen uniforme para todos los párrafos en el <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="92c69-106">To achieve uniform spacing between paragraphs throughout an entire <xref:System.Windows.Documents.FlowDocument>, use styling to set a uniform margin value for all paragraphs in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 <span data-ttu-id="92c69-107">Es importante tener en cuenta que los márgenes de dos párrafos adyacentes se "contraerá" el mayor de los márgenes de dos, en lugar de duplicarlo.</span><span class="sxs-lookup"><span data-stu-id="92c69-107">It is important to note that the margins for two adjacent paragraphs will "collapse" to the larger of the two margins, rather than doubling up.</span></span> <span data-ttu-id="92c69-108">Por lo tanto, si dos párrafos adyacentes tienen los márgenes de 20 y 40 píxeles, respectivamente, el espacio entre los párrafos resultante es de 40 píxeles, el mayor de los dos valores de margen.</span><span class="sxs-lookup"><span data-stu-id="92c69-108">So, if two adjacent paragraphs have margins of 20 pixels and 40 pixels respectively, the resulting space between the paragraphs is 40 pixels, the larger of the two margin values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92c69-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="92c69-109">Example</span></span>  
 <span data-ttu-id="92c69-110">El ejemplo siguiente utiliza la aplicación de estilos para establecer el margen para todos <xref:System.Windows.Documents.Paragraph> elementos en un <xref:System.Windows.Documents.FlowDocument> a **0**, lo que elimina eficazmente espaciado adicional entre párrafos en el <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="92c69-110">The following example uses styling to set the margin for all <xref:System.Windows.Documents.Paragraph> elements in a <xref:System.Windows.Documents.FlowDocument> to **0**, which effectively eliminates extra spacing between paragraphs in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-xaml[BlockSnippets#_ParagraphSpacingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/BlockSnippets/CSharp/Window1.xaml#_paragraphspacingxaml)]
