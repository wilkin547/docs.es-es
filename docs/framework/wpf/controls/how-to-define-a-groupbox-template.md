---
title: 'Cómo: Definir una plantilla de un control GroupBox'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], GroupBox
- GroupBox control [WPF], creating templates
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
ms.openlocfilehash: ed66d51e87a25f74e646d0d535ac9e4ee9c8a056
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551141"
---
# <a name="how-to-define-a-groupbox-template"></a><span data-ttu-id="771ba-102">Cómo: Definir una plantilla de un control GroupBox</span><span class="sxs-lookup"><span data-stu-id="771ba-102">How to: Define a GroupBox Template</span></span>
<span data-ttu-id="771ba-103">Este ejemplo muestra cómo crear una plantilla para un <xref:System.Windows.Controls.GroupBox> control.</span><span class="sxs-lookup"><span data-stu-id="771ba-103">This example shows how to create a template for a <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="771ba-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="771ba-104">Example</span></span>  
 <span data-ttu-id="771ba-105">En el ejemplo siguiente se define un <xref:System.Windows.Controls.GroupBox> plantilla de control mediante una <xref:System.Windows.Controls.Grid> control de diseño.</span><span class="sxs-lookup"><span data-stu-id="771ba-105">The following example defines a <xref:System.Windows.Controls.GroupBox> control template by using a <xref:System.Windows.Controls.Grid> control for layout.</span></span> <span data-ttu-id="771ba-106">La plantilla utiliza un <xref:System.Windows.Controls.BorderGapMaskConverter> para definir el borde de la <xref:System.Windows.Controls.GroupBox> para que el borde no oculte el <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> contenido.</span><span class="sxs-lookup"><span data-stu-id="771ba-106">The template uses a <xref:System.Windows.Controls.BorderGapMaskConverter> to define the border of the <xref:System.Windows.Controls.GroupBox> so that the border does not obscure the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> content.</span></span>  
  
 [!code-xaml[GroupBoxSnippet#GroupBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## <a name="see-also"></a><span data-ttu-id="771ba-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="771ba-107">See Also</span></span>  
 <xref:System.Windows.Controls.GroupBox>  
 [<span data-ttu-id="771ba-108">Temas de procedimientos de control GroupBox</span><span class="sxs-lookup"><span data-stu-id="771ba-108">GroupBox How-to Topics</span></span>](http://msdn.microsoft.com/library/7692e155-a4c6-428c-b7e0-64b3740daca7)
