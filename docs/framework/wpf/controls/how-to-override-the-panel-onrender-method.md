---
title: 'Cómo: Invalidar el método OnRender de un objeto Panel'
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
ms.openlocfilehash: 8f3b65bdfe96efdc57c6b8d30991439d3bdb0bc5
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43404441"
---
# <a name="how-to-override-the-panel-onrender-method"></a><span data-ttu-id="1f932-102">Cómo: Invalidar el método OnRender de un objeto Panel</span><span class="sxs-lookup"><span data-stu-id="1f932-102">How to: Override the Panel OnRender Method</span></span>
<span data-ttu-id="1f932-103">En este ejemplo se muestra cómo invalidar el <xref:System.Windows.Controls.Panel.OnRender%2A> método <xref:System.Windows.Controls.Panel> con el fin de agregar efectos gráficos personalizados a un elemento de diseño.</span><span class="sxs-lookup"><span data-stu-id="1f932-103">This example shows how to override the <xref:System.Windows.Controls.Panel.OnRender%2A> method of <xref:System.Windows.Controls.Panel> in order to add custom graphical effects to a layout element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f932-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f932-104">Example</span></span>  
 <span data-ttu-id="1f932-105">Use el <xref:System.Windows.Controls.Panel.OnRender%2A> método para agregar efectos gráficos a un elemento panel representado.</span><span class="sxs-lookup"><span data-stu-id="1f932-105">Use the <xref:System.Windows.Controls.Panel.OnRender%2A> method in order to add graphical effects to a rendered panel element.</span></span> <span data-ttu-id="1f932-106">Por ejemplo, puede usar este método para agregar un borde personalizado o efectos en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="1f932-106">For example, you can use this method to add custom border or background effects.</span></span> <span data-ttu-id="1f932-107">Un <xref:System.Windows.Media.DrawingContext> objeto se pasa como argumento, que proporciona métodos para dibujar formas, texto, imágenes o vídeos.</span><span class="sxs-lookup"><span data-stu-id="1f932-107">A <xref:System.Windows.Media.DrawingContext> object is passed as an argument, which provides methods for drawing shapes, text, images, or videos.</span></span> <span data-ttu-id="1f932-108">Como resultado, este método es útil para la personalización de un objeto de panel.</span><span class="sxs-lookup"><span data-stu-id="1f932-108">As a result, this method is useful for customization of a panel object.</span></span>  
  
 [!code-csharp[LightWeightCustomPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1f932-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f932-109">See Also</span></span>  
 <xref:System.Windows.Controls.Panel>  
 [<span data-ttu-id="1f932-110">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="1f932-110">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="1f932-111">Ejemplo de Panel Radial personalizado</span><span class="sxs-lookup"><span data-stu-id="1f932-111">Custom Radial Panel Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159982)  
 [<span data-ttu-id="1f932-112">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="1f932-112">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/panel-how-to-topics.md)
