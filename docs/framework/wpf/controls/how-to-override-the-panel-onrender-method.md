---
title: Filtrar Invalidar el método OnRender de un objeto Panel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- overriding OnRender method
- Panel control, overriding OnRender method
- OnRender method
- controls, Panel, overriding OnRender method
helpviewer_keywords:
- overriding OnRender method of Panel control [WPF]
- OnRender method [WPF], overriding
- Panel control [WPF], overriding OnRender method
ms.assetid: 57397834-a085-4e36-90ab-416fad98f341
ms.openlocfilehash: 23c3353e130585ed83726816a467ca73f6aa9152
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666713"
---
# <a name="how-to-override-the-panel-onrender-method"></a><span data-ttu-id="59ae3-102">Filtrar Invalidar el método OnRender de un objeto Panel</span><span class="sxs-lookup"><span data-stu-id="59ae3-102">How to: Override the Panel OnRender Method</span></span>
<span data-ttu-id="59ae3-103">En este ejemplo se muestra cómo invalidar <xref:System.Windows.Controls.Panel.OnRender%2A> el <xref:System.Windows.Controls.Panel> método de para agregar efectos gráficos personalizados a un elemento de diseño.</span><span class="sxs-lookup"><span data-stu-id="59ae3-103">This example shows how to override the <xref:System.Windows.Controls.Panel.OnRender%2A> method of <xref:System.Windows.Controls.Panel> in order to add custom graphical effects to a layout element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59ae3-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="59ae3-104">Example</span></span>  
 <span data-ttu-id="59ae3-105">Use el <xref:System.Windows.Controls.Panel.OnRender%2A> método para agregar efectos gráficos a un elemento del panel representado.</span><span class="sxs-lookup"><span data-stu-id="59ae3-105">Use the <xref:System.Windows.Controls.Panel.OnRender%2A> method in order to add graphical effects to a rendered panel element.</span></span> <span data-ttu-id="59ae3-106">Por ejemplo, puede utilizar este método para agregar efectos de borde o de fondo personalizados.</span><span class="sxs-lookup"><span data-stu-id="59ae3-106">For example, you can use this method to add custom border or background effects.</span></span> <span data-ttu-id="59ae3-107">Un <xref:System.Windows.Media.DrawingContext> objeto se pasa como argumento, que proporciona métodos para dibujar formas, texto, imágenes o vídeos.</span><span class="sxs-lookup"><span data-stu-id="59ae3-107">A <xref:System.Windows.Media.DrawingContext> object is passed as an argument, which provides methods for drawing shapes, text, images, or videos.</span></span> <span data-ttu-id="59ae3-108">Como resultado, este método es útil para la personalización de un objeto de panel.</span><span class="sxs-lookup"><span data-stu-id="59ae3-108">As a result, this method is useful for customization of a panel object.</span></span>  
  
 [!code-csharp[LightWeightCustomPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="59ae3-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="59ae3-109">See also</span></span>

- <xref:System.Windows.Controls.Panel>
- [<span data-ttu-id="59ae3-110">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="59ae3-110">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="59ae3-111">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="59ae3-111">How-to Topics</span></span>](panel-how-to-topics.md)
