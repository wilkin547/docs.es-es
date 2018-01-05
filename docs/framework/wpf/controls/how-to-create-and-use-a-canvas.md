---
title: "Cómo crear y utilizar un control Canvas"
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
- controls [WPF], Canvas
- Canvas control [WPF], creating
- Canvas control [WPF], using
ms.assetid: 420b9487-9a15-477c-9489-a22a4dec7779
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 562531f75d6a800ff93a02709a053b790de52ea2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-and-use-a-canvas"></a><span data-ttu-id="7c18f-102">Cómo crear y utilizar un control Canvas</span><span class="sxs-lookup"><span data-stu-id="7c18f-102">How to: Create and Use a Canvas</span></span>
<span data-ttu-id="7c18f-103">Este ejemplo muestra cómo crear y usar una instancia de <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="7c18f-103">This example shows how to create and use an instance of <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c18f-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7c18f-104">Example</span></span>  
 <span data-ttu-id="7c18f-105">En el ejemplo siguiente se coloca explícitamente dos <xref:System.Windows.Controls.TextBlock> elementos mediante el uso de la <xref:System.Windows.Controls.Canvas.SetTop%2A> y <xref:System.Windows.Controls.Canvas.SetLeft%2A> métodos de <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="7c18f-105">The following example explicitly positions two <xref:System.Windows.Controls.TextBlock> elements by using the <xref:System.Windows.Controls.Canvas.SetTop%2A> and <xref:System.Windows.Controls.Canvas.SetLeft%2A> methods of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="7c18f-106">El ejemplo también se asigna un <xref:System.Windows.Controls.Control.Background%2A> color de `LightSteelBlue` a la <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="7c18f-106">The example also assigns a <xref:System.Windows.Controls.Control.Background%2A> color of `LightSteelBlue` to the <xref:System.Windows.Controls.Canvas>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7c18f-107">Cuando usas [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] a posición <xref:System.Windows.Controls.TextBlock> elementos, use la <xref:System.Windows.Controls.Canvas.Top%2A> y <xref:System.Windows.Controls.Canvas.Left%2A> propiedades.</span><span class="sxs-lookup"><span data-stu-id="7c18f-107">When you use [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to position <xref:System.Windows.Controls.TextBlock> elements, use the <xref:System.Windows.Controls.Canvas.Top%2A> and <xref:System.Windows.Controls.Canvas.Left%2A> properties.</span></span>  
  
 [!code-csharp[CanvasCode#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasCode/CSharp/Canvas_Code.cs#1)]
 [!code-vb[CanvasCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasCode/VisualBasic/canvas_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7c18f-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c18f-108">See Also</span></span>  
 <xref:System.Windows.Controls.Canvas>  
 <xref:System.Windows.Controls.TextBlock>  
 <xref:System.Windows.Controls.Canvas.SetTop%2A>  
 <xref:System.Windows.Controls.Canvas.SetLeft%2A>  
 <xref:System.Windows.Controls.Canvas.Top%2A>  
 <xref:System.Windows.Controls.Canvas.Left%2A>  
 [<span data-ttu-id="7c18f-109">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="7c18f-109">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="7c18f-110">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="7c18f-110">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/canvas-how-to-topics.md)
