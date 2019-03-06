---
title: Filtrar Cambiar la propiedad TextWrapping mediante programación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], changing TextWrapping property programmatically
- TextWrapping property [WPF], changing programmatically
ms.assetid: 30d25554-4c82-4df9-a8d6-35683a4a13bb
ms.openlocfilehash: 70dc73fe16ebb98e466c4363e5ac26562329dcd4
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362271"
---
# <a name="how-to-change-the-textwrapping-property-programmatically"></a><span data-ttu-id="24e00-102">Filtrar Cambiar la propiedad TextWrapping mediante programación</span><span class="sxs-lookup"><span data-stu-id="24e00-102">How to: Change the TextWrapping Property Programmatically</span></span>
## <a name="example"></a><span data-ttu-id="24e00-103">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="24e00-103">Example</span></span>  
 <span data-ttu-id="24e00-104">El ejemplo de código siguiente muestra cómo cambiar el valor de la <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> propiedad mediante programación.</span><span class="sxs-lookup"><span data-stu-id="24e00-104">The following code example shows how to change the value of the <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> property programmatically.</span></span>  
  
 <span data-ttu-id="24e00-105">Tres <xref:System.Windows.Controls.Button> elementos se colocan dentro de un <xref:System.Windows.Controls.StackPanel> elemento [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24e00-105">Three <xref:System.Windows.Controls.Button> elements are placed within a <xref:System.Windows.Controls.StackPanel> element in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="24e00-106">Cada <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos para un <xref:System.Windows.Controls.Button> se corresponde con un controlador de eventos en el código.</span><span class="sxs-lookup"><span data-stu-id="24e00-106">Each <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event for a <xref:System.Windows.Controls.Button> corresponds with an event handler in the code.</span></span> <span data-ttu-id="24e00-107">Los controladores de eventos usan el mismo nombre que el <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> valor también se aplicarán en `txt2` cuando se hace clic en el botón.</span><span class="sxs-lookup"><span data-stu-id="24e00-107">The event handlers use the same name as the <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> value they will apply to `txt2` when the button is clicked.</span></span> <span data-ttu-id="24e00-108">Además, el texto en `txt1` (un <xref:System.Windows.Controls.TextBlock> no se muestra en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]) se actualiza para reflejar el cambio en la propiedad.</span><span class="sxs-lookup"><span data-stu-id="24e00-108">Also, the text in `txt1` (a <xref:System.Windows.Controls.TextBlock> not shown in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]) is updated to reflect the change in the property.</span></span>  
  
 [!code-xaml[TextWrapProperty#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml#1)]  
  
 [!code-csharp[TextWrapProperty#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextWrapProperty/CSharp/Window1.xaml.cs#2)]
 [!code-vb[TextWrapProperty#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="24e00-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="24e00-109">See also</span></span>
- <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>
- <xref:System.Windows.TextWrapping>
