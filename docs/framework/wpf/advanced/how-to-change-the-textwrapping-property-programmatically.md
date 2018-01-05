---
title: "Cómo: Cambiar la propiedad TextWrapping mediante programación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], changing TextWrapping property programmatically
- TextWrapping property [WPF], changing programmatically
ms.assetid: 30d25554-4c82-4df9-a8d6-35683a4a13bb
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ca87d651f66edba00280a57ca1468af33657a329
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-textwrapping-property-programmatically"></a><span data-ttu-id="87b1f-102">Cómo: Cambiar la propiedad TextWrapping mediante programación</span><span class="sxs-lookup"><span data-stu-id="87b1f-102">How to: Change the TextWrapping Property Programmatically</span></span>
## <a name="example"></a><span data-ttu-id="87b1f-103">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="87b1f-103">Example</span></span>  
 <span data-ttu-id="87b1f-104">En el ejemplo de código siguiente se muestra cómo cambiar el valor de la <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> propiedad mediante programación.</span><span class="sxs-lookup"><span data-stu-id="87b1f-104">The following code example shows how to change the value of the <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> property programmatically.</span></span>  
  
 <span data-ttu-id="87b1f-105">Tres <xref:System.Windows.Controls.Button> elementos se colocan dentro de un <xref:System.Windows.Controls.StackPanel> elemento [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87b1f-105">Three <xref:System.Windows.Controls.Button> elements are placed within a <xref:System.Windows.Controls.StackPanel> element in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="87b1f-106">Cada <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos para un <xref:System.Windows.Controls.Button> se corresponde con un controlador de eventos en el código.</span><span class="sxs-lookup"><span data-stu-id="87b1f-106">Each <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event for a <xref:System.Windows.Controls.Button> corresponds with an event handler in the code.</span></span> <span data-ttu-id="87b1f-107">Los controladores de eventos utilizan el mismo nombre que el <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> valor se aplicarán a `txt2` cuando se hace clic en el botón.</span><span class="sxs-lookup"><span data-stu-id="87b1f-107">The event handlers use the same name as the <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> value they will apply to `txt2` when the button is clicked.</span></span> <span data-ttu-id="87b1f-108">Además, el texto en `txt1` (un <xref:System.Windows.Controls.TextBlock> no se muestra en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]) se actualiza para reflejar el cambio en la propiedad.</span><span class="sxs-lookup"><span data-stu-id="87b1f-108">Also, the text in `txt1` (a <xref:System.Windows.Controls.TextBlock> not shown in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]) is updated to reflect the change in the property.</span></span>  
  
 [!code-xaml[TextWrapProperty#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml#1)]  
  
 [!code-csharp[TextWrapProperty#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextWrapProperty/CSharp/Window1.xaml.cs#2)]
 [!code-vb[TextWrapProperty#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="87b1f-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="87b1f-109">See Also</span></span>  
 <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>  
 <xref:System.Windows.TextWrapping>
