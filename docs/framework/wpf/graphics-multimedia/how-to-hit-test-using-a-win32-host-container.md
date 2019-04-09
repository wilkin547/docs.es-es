---
title: Filtrar Realizar pruebas de posicionamiento mediante un contenedor host Win32
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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081468"
---
# <a name="how-to-hit-test-using-a-win32-host-container"></a>Filtrar Realizar pruebas de posicionamiento mediante un contenedor host Win32
Puede crear objetos visuales dentro de un [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] ventana proporcionando un host de contenedor de ventana para los objetos visuales. Para proporcionar control de eventos para los objetos visuales contenidos, proceso los mensajes que se pasan al bucle de filtro de mensajes del contenedor de la ventana del host. Consulte [Tutorial: Hospedar objetos visuales en una aplicación Win32](tutorial-hosting-visual-objects-in-a-win32-application.md) para obtener más información sobre cómo hospedar objetos visuales en un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra cómo configurar controladores de eventos del mouse para un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana que se utiliza como un contenedor host para objetos visuales.  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 El ejemplo siguiente muestra cómo configurar una prueba de posicionamiento en respuesta a la captura de eventos de mouse concretos.  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 El <xref:System.Windows.Interop.HwndSource> objeto presenta [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] contenido dentro de un [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] ventana. El valor de la <xref:System.Windows.Interop.HwndSource.RootVisual%2A> propiedad de la <xref:System.Windows.Interop.HwndSource> objeto representa el nodo de nivel superior en la jerarquía del árbol visual.  
  
 Para obtener el ejemplo completo en la prueba de posicionamiento objetos mediante un contenedor host Win32, vea [prueba de posicionamiento con Win32 Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=159995).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Interop.HwndSource>
- [Realizar pruebas de posicionamiento en la capa visual](hit-testing-in-the-visual-layer.md)
- [Tutorial: Hospedar objetos visuales en una aplicación Win32](tutorial-hosting-visual-objects-in-a-win32-application.md)
