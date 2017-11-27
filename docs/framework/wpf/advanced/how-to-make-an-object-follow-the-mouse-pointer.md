---
title: "Cómo: Crear un objeto que siga el puntero del mouse"
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
- following the mouse pointer (cursor)
- mouse pointer (cursor), making objects follow
- cursor (mouse pointer), making objects follow
ms.assetid: 50b20415-14bc-405c-baf3-2fb254fffde3
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1991d2a4b43c679fe7e30f633742e01e281e19b3
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-make-an-object-follow-the-mouse-pointer"></a><span data-ttu-id="7be47-102">Cómo: Crear un objeto que siga el puntero del mouse</span><span class="sxs-lookup"><span data-stu-id="7be47-102">How to: Make an Object Follow the Mouse Pointer</span></span>
<span data-ttu-id="7be47-103">Este ejemplo muestra cómo cambiar las dimensiones de un objeto cuando el puntero del mouse se mueve en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="7be47-103">This example shows how to change the dimensions of an object when the mouse pointer moves on the screen.</span></span>  
  
 <span data-ttu-id="7be47-104">El ejemplo incluye una [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivos que crea el [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] y un archivo de código subyacente que crea el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="7be47-104">The example includes an [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file that creates the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] and a code-behind file that creates the event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7be47-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7be47-105">Example</span></span>  
 <span data-ttu-id="7be47-106">El siguiente [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] crea el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], que consta de un <xref:System.Windows.Shapes.Ellipse> dentro de un <xref:System.Windows.Controls.StackPanel>y asocia el controlador de eventos para el <xref:System.Windows.UIElement.MouseMove> eventos.</span><span class="sxs-lookup"><span data-stu-id="7be47-106">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], which consists of an <xref:System.Windows.Shapes.Ellipse> inside of a <xref:System.Windows.Controls.StackPanel>, and attaches the event handler for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>  
  
 [!code-xaml[mouseMoveWithPointer#MouseMoveWithPointerXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 <span data-ttu-id="7be47-107">El siguiente código detrás de crea el <xref:System.Windows.UIElement.MouseMove> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="7be47-107">The following code behind creates the <xref:System.Windows.UIElement.MouseMove> event handler.</span></span>  <span data-ttu-id="7be47-108">Cuando se mueve el puntero del mouse, el alto y el ancho de la <xref:System.Windows.Shapes.Ellipse> se aumenta y disminuye.</span><span class="sxs-lookup"><span data-stu-id="7be47-108">When the mouse pointer moves, the height and the width of the <xref:System.Windows.Shapes.Ellipse> are increased and decreased.</span></span>  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## <a name="see-also"></a><span data-ttu-id="7be47-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="7be47-109">See Also</span></span>  
 [<span data-ttu-id="7be47-110">Información general sobre acciones del usuario</span><span class="sxs-lookup"><span data-stu-id="7be47-110">Input Overview</span></span>](../../../../docs/framework/wpf/advanced/input-overview.md)
