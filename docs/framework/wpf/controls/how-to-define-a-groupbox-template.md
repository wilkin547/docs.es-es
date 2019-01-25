---
title: Procedimiento Definir una plantilla de un control GroupBox
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], GroupBox
- GroupBox control [WPF], creating templates
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
ms.openlocfilehash: 0e1b0487629bba3550a8b6b4a31c163a7ade6a87
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743730"
---
# <a name="how-to-define-a-groupbox-template"></a><span data-ttu-id="ad2b4-102">Procedimiento Definir una plantilla de un control GroupBox</span><span class="sxs-lookup"><span data-stu-id="ad2b4-102">How to: Define a GroupBox Template</span></span>
<span data-ttu-id="ad2b4-103">En este ejemplo se muestra cómo crear una plantilla para un <xref:System.Windows.Controls.GroupBox> control.</span><span class="sxs-lookup"><span data-stu-id="ad2b4-103">This example shows how to create a template for a <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad2b4-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad2b4-104">Example</span></span>  
 <span data-ttu-id="ad2b4-105">En el ejemplo siguiente se define un <xref:System.Windows.Controls.GroupBox> plantilla de control mediante el uso de un <xref:System.Windows.Controls.Grid> control para el diseño.</span><span class="sxs-lookup"><span data-stu-id="ad2b4-105">The following example defines a <xref:System.Windows.Controls.GroupBox> control template by using a <xref:System.Windows.Controls.Grid> control for layout.</span></span> <span data-ttu-id="ad2b4-106">La plantilla utiliza un <xref:System.Windows.Controls.BorderGapMaskConverter> para definir el borde de la <xref:System.Windows.Controls.GroupBox> para que el borde no oculte el <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> contenido.</span><span class="sxs-lookup"><span data-stu-id="ad2b4-106">The template uses a <xref:System.Windows.Controls.BorderGapMaskConverter> to define the border of the <xref:System.Windows.Controls.GroupBox> so that the border does not obscure the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> content.</span></span>  
  
 [!code-xaml[GroupBoxSnippet#GroupBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## <a name="see-also"></a><span data-ttu-id="ad2b4-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad2b4-107">See also</span></span>
- <xref:System.Windows.Controls.GroupBox>
- [<span data-ttu-id="ad2b4-108">Temas de procedimientos de GroupBox</span><span class="sxs-lookup"><span data-stu-id="ad2b4-108">GroupBox How-to Topics</span></span>](https://msdn.microsoft.com/library/7692e155-a4c6-428c-b7e0-64b3740daca7)
