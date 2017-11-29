---
title: "Cómo: Invalidar el método OnRender de un objeto Panel"
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
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 774c612b09d5cb0ffdf36024a7e6a543f407cf67
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-override-the-panel-onrender-method"></a><span data-ttu-id="fe9c6-102">Cómo: Invalidar el método OnRender de un objeto Panel</span><span class="sxs-lookup"><span data-stu-id="fe9c6-102">How to: Override the Panel OnRender Method</span></span>
<span data-ttu-id="fe9c6-103">Este ejemplo muestra cómo invalidar el <xref:System.Windows.Controls.Panel.OnRender%2A> método <xref:System.Windows.Controls.Panel> para agregar efectos gráficos personalizados a un elemento de diseño.</span><span class="sxs-lookup"><span data-stu-id="fe9c6-103">This example shows how to override the <xref:System.Windows.Controls.Panel.OnRender%2A> method of <xref:System.Windows.Controls.Panel> in order to add custom graphical effects to a layout element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe9c6-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fe9c6-104">Example</span></span>  
 <span data-ttu-id="fe9c6-105">Use la <xref:System.Windows.Controls.Panel.OnRender%2A> método para agregar efectos gráficos a un elemento del panel representado.</span><span class="sxs-lookup"><span data-stu-id="fe9c6-105">Use the <xref:System.Windows.Controls.Panel.OnRender%2A> method in order to add graphical effects to a rendered panel element.</span></span> <span data-ttu-id="fe9c6-106">Por ejemplo, puede usar este método para agregar un borde personalizado o efectos de fondo.</span><span class="sxs-lookup"><span data-stu-id="fe9c6-106">For example, you can use this method to add custom border or background effects.</span></span> <span data-ttu-id="fe9c6-107">Un <xref:System.Windows.Media.DrawingContext> objeto se pasa como argumento, que proporciona métodos para dibujar formas, texto, imágenes o vídeos.</span><span class="sxs-lookup"><span data-stu-id="fe9c6-107">A <xref:System.Windows.Media.DrawingContext> object is passed as an argument, which provides methods for drawing shapes, text, images, or videos.</span></span> <span data-ttu-id="fe9c6-108">Como resultado, este método es útil para la personalización de un objeto de panel.</span><span class="sxs-lookup"><span data-stu-id="fe9c6-108">As a result, this method is useful for customization of a panel object.</span></span>  
  
 [!code-csharp[LightWeightCustomPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="fe9c6-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe9c6-109">See Also</span></span>  
 <xref:System.Windows.Controls.Panel>  
 [<span data-ttu-id="fe9c6-110">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="fe9c6-110">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="fe9c6-111">Ejemplo Custom Radial Panel</span><span class="sxs-lookup"><span data-stu-id="fe9c6-111">Custom Radial Panel Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159982)  
 [<span data-ttu-id="fe9c6-112">Temas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="fe9c6-112">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/panel-how-to-topics.md)
