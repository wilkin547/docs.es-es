---
title: Información general sobre TextBlock
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], TextBlock
- TextBlock control [WPF]
ms.assetid: 24720bca-341a-4b03-8a6b-7a678023b10a
ms.openlocfilehash: c18ca64a25f436c3ed2ccd9e04316e25bab00a66
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556086"
---
# <a name="textblock-overview"></a><span data-ttu-id="cb719-102">Información general sobre TextBlock</span><span class="sxs-lookup"><span data-stu-id="cb719-102">TextBlock Overview</span></span>
<span data-ttu-id="cb719-103">El <xref:System.Windows.Controls.TextBlock> control proporciona compatibilidad con texto flexible [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="cb719-103">The <xref:System.Windows.Controls.TextBlock> control provides flexible text support for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span> <span data-ttu-id="cb719-104">El elemento se destina principalmente a los escenarios de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] básicos que no requieren más de un párrafo de texto.</span><span class="sxs-lookup"><span data-stu-id="cb719-104">The element is targeted primarily toward basic [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] scenarios that do not require more than one paragraph of text.</span></span> <span data-ttu-id="cb719-105">Admite un número de propiedades que permiten un control preciso de presentación, como <xref:System.Windows.Controls.TextBlock.FontFamily%2A>, <xref:System.Windows.Controls.TextBlock.FontSize%2A>, <xref:System.Windows.Controls.TextBlock.FontWeight%2A>, <xref:System.Windows.Controls.TextBlock.TextEffects%2A>, y <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>.</span><span class="sxs-lookup"><span data-stu-id="cb719-105">It supports a number of properties that enable precise control of presentation, such as <xref:System.Windows.Controls.TextBlock.FontFamily%2A>, <xref:System.Windows.Controls.TextBlock.FontSize%2A>, <xref:System.Windows.Controls.TextBlock.FontWeight%2A>, <xref:System.Windows.Controls.TextBlock.TextEffects%2A>, and <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>.</span></span> <span data-ttu-id="cb719-106">Contenido de texto se puede agregar utilizando el <xref:System.Windows.Controls.TextBlock.Text%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="cb719-106">Text content can be added using the <xref:System.Windows.Controls.TextBlock.Text%2A> property.</span></span> <span data-ttu-id="cb719-107">Cuando se utiliza en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], el contenido de las etiquetas de apertura y cierre se agrega implícitamente como texto del elemento.</span><span class="sxs-lookup"><span data-stu-id="cb719-107">When used in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], content between the open and closing tag is implicitly added as the text of the element.</span></span>  
  
 <span data-ttu-id="cb719-108">A <xref:System.Windows.Controls.TextBlock> elemento puede instanciarse muy simplemente mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb719-108">A <xref:System.Windows.Controls.TextBlock> element can be instantiated very simply using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[TextBlockSnip_XAML#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip_XAML/CS/default.xaml#2)]  
  
 <span data-ttu-id="cb719-109">De igual forma, el uso de la <xref:System.Windows.Controls.TextBlock> elemento de código es relativamente sencilla.</span><span class="sxs-lookup"><span data-stu-id="cb719-109">Similarly, usage of the <xref:System.Windows.Controls.TextBlock> element in code is relatively simple.</span></span>  
  
 [!code-csharp[TextBlockSnip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip/CSharp/TextBlockSnips.cs#1)]
 [!code-vb[TextBlockSnip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBlockSnip/VisualBasic/TextBlockSnips.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="cb719-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb719-110">See Also</span></span>  
 <xref:System.Windows.Controls.Label>
