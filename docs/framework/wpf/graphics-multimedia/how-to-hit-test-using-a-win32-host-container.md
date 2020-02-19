---
title: 'Cómo: Realizar pruebas de posicionamiento mediante un contenedor host Win32'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], using Win32 host containers
- visual objects [WPF], hit tests on
- Win32 host containers [WPF], hit tests using
ms.assetid: 9491f7f3-d8ba-4573-a888-2f064d1349dc
ms.openlocfilehash: a86c1c36f75fa232d52731959371268a8b2593d7
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452810"
---
# <a name="how-to-hit-test-using-a-win32-host-container"></a><span data-ttu-id="8399e-102">Cómo: Realizar pruebas de posicionamiento mediante un contenedor host Win32</span><span class="sxs-lookup"><span data-stu-id="8399e-102">How to: Hit Test Using a Win32 Host Container</span></span>
<span data-ttu-id="8399e-103">Puede crear objetos visuales en una ventana de Win32 proporcionando un contenedor de ventana host para los objetos visuales.</span><span class="sxs-lookup"><span data-stu-id="8399e-103">You can create visual objects within a Win32 window by providing a host window container for the visual objects.</span></span> <span data-ttu-id="8399e-104">Para proporcionar control de eventos para los objetos visuales contenidos, proceso los mensajes que se pasan al bucle de filtro de mensajes del contenedor de la ventana del host.</span><span class="sxs-lookup"><span data-stu-id="8399e-104">To provide event handling for the contained visual objects you process the messages passed to the host window container’s message filter loop.</span></span> <span data-ttu-id="8399e-105">Consulte [Tutorial: hospedar objetos visuales en una aplicación Win32](tutorial-hosting-visual-objects-in-a-win32-application.md) para obtener más información sobre cómo hospedar objetos visuales en una ventana de Win32.</span><span class="sxs-lookup"><span data-stu-id="8399e-105">Refer to [Tutorial: Hosting Visual Objects in a Win32 Application](tutorial-hosting-visual-objects-in-a-win32-application.md) for more information on how to host visual objects in a Win32 window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8399e-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8399e-106">Example</span></span>  
 <span data-ttu-id="8399e-107">En el código siguiente se muestra cómo configurar los controladores de eventos del mouse para una ventana de Win32 que se usa como contenedor host para objetos visuales.</span><span class="sxs-lookup"><span data-stu-id="8399e-107">The following code shows how to set up mouse event handlers for a Win32 window that is used as a host container for visual objects.</span></span>  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 <span data-ttu-id="8399e-108">En el ejemplo siguiente se muestra cómo configurar una prueba de posicionamiento en respuesta a la captura de eventos de mouse concretos.</span><span class="sxs-lookup"><span data-stu-id="8399e-108">The following example shows how to set up a hit test in response to trapping specific mouse events.</span></span>  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 <span data-ttu-id="8399e-109">El objeto <xref:System.Windows.Interop.HwndSource> presenta [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] contenido dentro de una ventana de Win32.</span><span class="sxs-lookup"><span data-stu-id="8399e-109">The <xref:System.Windows.Interop.HwndSource> object presents [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content within a Win32 window.</span></span> <span data-ttu-id="8399e-110">El valor de la propiedad <xref:System.Windows.Interop.HwndSource.RootVisual%2A> del objeto <xref:System.Windows.Interop.HwndSource> representa el nodo de nivel superior de la jerarquía de árbol visual.</span><span class="sxs-lookup"><span data-stu-id="8399e-110">The value of the <xref:System.Windows.Interop.HwndSource.RootVisual%2A> property of the <xref:System.Windows.Interop.HwndSource> object represents the top-most node in the visual tree hierarchy.</span></span>  
  
 <span data-ttu-id="8399e-111">Para obtener el ejemplo completo de los objetos de prueba de posicionamiento mediante un contenedor host de Win32, vea [prueba de posicionamiento con el ejemplo de interoperación de Win32](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting).</span><span class="sxs-lookup"><span data-stu-id="8399e-111">For the complete sample on hit testing objects using a Win32 host container, see [Hit Test with Win32 Interoperation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8399e-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8399e-112">See also</span></span>

- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="8399e-113">Realizar pruebas de posicionamiento en la capa visual</span><span class="sxs-lookup"><span data-stu-id="8399e-113">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="8399e-114">Tutorial: Hospedar objetos visuales en una aplicación Win32</span><span class="sxs-lookup"><span data-stu-id="8399e-114">Tutorial: Hosting Visual Objects in a Win32 Application</span></span>](tutorial-hosting-visual-objects-in-a-win32-application.md)
