---
title: Procedimiento Realizar pruebas de posicionamiento mediante un contenedor host Win32
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], using Win32 host containers
- visual objects [WPF], hit tests on
- Win32 host containers [WPF], hit tests using
ms.assetid: 9491f7f3-d8ba-4573-a888-2f064d1349dc
ms.openlocfilehash: ac5cae5bcd94dc8bf80ff95b8971914e1fa5ba2c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59081468"
---
# <a name="how-to-hit-test-using-a-win32-host-container"></a><span data-ttu-id="4ab52-102">Procedimiento Realizar pruebas de posicionamiento mediante un contenedor host Win32</span><span class="sxs-lookup"><span data-stu-id="4ab52-102">How to: Hit Test Using a Win32 Host Container</span></span>
<span data-ttu-id="4ab52-103">Puede crear objetos visuales dentro de un [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] ventana proporcionando un host de contenedor de ventana para los objetos visuales.</span><span class="sxs-lookup"><span data-stu-id="4ab52-103">You can create visual objects within a [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] window by providing a host window container for the visual objects.</span></span> <span data-ttu-id="4ab52-104">Para proporcionar control de eventos para los objetos visuales contenidos, proceso los mensajes que se pasan al bucle de filtro de mensajes del contenedor de la ventana del host.</span><span class="sxs-lookup"><span data-stu-id="4ab52-104">To provide event handling for the contained visual objects you process the messages passed to the host window container’s message filter loop.</span></span> <span data-ttu-id="4ab52-105">Consulte [Tutorial: Hospedar objetos visuales en una aplicación Win32](tutorial-hosting-visual-objects-in-a-win32-application.md) para obtener más información sobre cómo hospedar objetos visuales en un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana.</span><span class="sxs-lookup"><span data-stu-id="4ab52-105">Refer to [Tutorial: Hosting Visual Objects in a Win32 Application](tutorial-hosting-visual-objects-in-a-win32-application.md) for more information on how to host visual objects in a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ab52-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4ab52-106">Example</span></span>  
 <span data-ttu-id="4ab52-107">El código siguiente muestra cómo configurar controladores de eventos del mouse para un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana que se utiliza como un contenedor host para objetos visuales.</span><span class="sxs-lookup"><span data-stu-id="4ab52-107">The following code shows how to set up mouse event handlers for a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] window that is used as a host container for visual objects.</span></span>  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 <span data-ttu-id="4ab52-108">El ejemplo siguiente muestra cómo configurar una prueba de posicionamiento en respuesta a la captura de eventos de mouse concretos.</span><span class="sxs-lookup"><span data-stu-id="4ab52-108">The following example shows how to set up a hit test in response to trapping specific mouse events.</span></span>  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 <span data-ttu-id="4ab52-109">El <xref:System.Windows.Interop.HwndSource> objeto presenta [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] contenido dentro de un [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] ventana.</span><span class="sxs-lookup"><span data-stu-id="4ab52-109">The <xref:System.Windows.Interop.HwndSource> object presents [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content within a [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] window.</span></span> <span data-ttu-id="4ab52-110">El valor de la <xref:System.Windows.Interop.HwndSource.RootVisual%2A> propiedad de la <xref:System.Windows.Interop.HwndSource> objeto representa el nodo de nivel superior en la jerarquía del árbol visual.</span><span class="sxs-lookup"><span data-stu-id="4ab52-110">The value of the <xref:System.Windows.Interop.HwndSource.RootVisual%2A> property of the <xref:System.Windows.Interop.HwndSource> object represents the top-most node in the visual tree hierarchy.</span></span>  
  
 <span data-ttu-id="4ab52-111">Para obtener el ejemplo completo en la prueba de posicionamiento objetos mediante un contenedor host Win32, vea [prueba de posicionamiento con Win32 Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=159995).</span><span class="sxs-lookup"><span data-stu-id="4ab52-111">For the complete sample on hit testing objects using a Win32 host container, see [Hit Test with Win32 Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=159995).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ab52-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ab52-112">See also</span></span>

- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="4ab52-113">Realizar pruebas de posicionamiento en la capa visual</span><span class="sxs-lookup"><span data-stu-id="4ab52-113">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="4ab52-114">Tutorial: Hospedar objetos visuales en una aplicación Win32</span><span class="sxs-lookup"><span data-stu-id="4ab52-114">Tutorial: Hosting Visual Objects in a Win32 Application</span></span>](tutorial-hosting-visual-objects-in-a-win32-application.md)
