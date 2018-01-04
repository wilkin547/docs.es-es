---
title: "Cómo: Ajustar el espaciado entre párrafos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- spacing between paragraphs [WPF]
- paragraphs [WPF], spacing between
- documents [WPF], adjusting spacing between paragraphs
ms.assetid: 7cd2f2ac-0e19-4587-bfb6-7f5b18c9536e
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8b2d02e1513a0d8a3c31e4a13c9599666a4122a3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-adjust-spacing-between-paragraphs"></a><span data-ttu-id="81c09-102">Cómo: Ajustar el espaciado entre párrafos</span><span class="sxs-lookup"><span data-stu-id="81c09-102">How to: Adjust Spacing Between Paragraphs</span></span>
<span data-ttu-id="81c09-103">En este ejemplo se muestra cómo ajustar o eliminar el espaciado entre párrafos en el contenido del flujo.</span><span class="sxs-lookup"><span data-stu-id="81c09-103">This example shows how to adjust or eliminate spacing between paragraphs in flow content.</span></span>  
  
 <span data-ttu-id="81c09-104">En el contenido del flujo, el espacio adicional que aparece entre los párrafos es el resultado de los márgenes establecidos para estos párrafos; por lo tanto, se puede controlar el espaciado entre párrafos ajustando los márgenes en los párrafos.</span><span class="sxs-lookup"><span data-stu-id="81c09-104">In flow content, extra space that appears between paragraphs is the result of margins set on these paragraphs; thus, the spacing between paragraphs can be controlled by adjusting the margins on those paragraphs.</span></span>  <span data-ttu-id="81c09-105">Para eliminar por completo un espaciado adicional entre dos párrafos, establezca los márgenes de los párrafos a **0**.</span><span class="sxs-lookup"><span data-stu-id="81c09-105">To eliminate extra spacing between two paragraphs altogether, set the margins for the paragraphs to **0**.</span></span>  <span data-ttu-id="81c09-106">Para conseguir un espaciado uniforme entre los párrafos a lo largo de toda una <xref:System.Windows.Documents.FlowDocument>, utilice un estilo para establecer un valor de margen uniforme para todos los párrafos del <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="81c09-106">To achieve uniform spacing between paragraphs throughout an entire <xref:System.Windows.Documents.FlowDocument>, use styling to set a uniform margin value for all paragraphs in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 <span data-ttu-id="81c09-107">Es importante tener en cuenta que los márgenes de dos párrafos adyacentes se "contraerán" para el mayor de los dos márgenes, en lugar de duplicarlo.</span><span class="sxs-lookup"><span data-stu-id="81c09-107">It is important to note that the margins for two adjacent paragraphs will "collapse" to the larger of the two margins, rather than doubling up.</span></span> <span data-ttu-id="81c09-108">Por lo tanto, si dos párrafos adyacentes tienen, márgenes de 20 y 40 píxeles respectivamente, el espacio entre los párrafos resultante es de 40 píxeles, el mayor de los valores de margen de dos.</span><span class="sxs-lookup"><span data-stu-id="81c09-108">So, if two adjacent paragraphs have margins of 20 pixels and 40 pixels respectively, the resulting space between the paragraphs is 40 pixels, the larger of the two margin values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81c09-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="81c09-109">Example</span></span>  
 <span data-ttu-id="81c09-110">En el ejemplo siguiente se utiliza un estilo para establecer el margen para todas las <xref:System.Windows.Documents.Paragraph> elementos en una <xref:System.Windows.Documents.FlowDocument> a **0**, lo que elimina eficazmente un espaciado adicional entre los párrafos en los <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="81c09-110">The following example uses styling to set the margin for all <xref:System.Windows.Documents.Paragraph> elements in a <xref:System.Windows.Documents.FlowDocument> to **0**, which effectively eliminates extra spacing between paragraphs in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-xaml[BlockSnippets#_ParagraphSpacingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BlockSnippets/CSharp/Window1.xaml#_paragraphspacingxaml)]
