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
ms.openlocfilehash: b71783f2d061c9139de4449d8e0106eb00345894
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740173"
---
# <a name="how-to-hit-test-using-a-win32-host-container"></a>Cómo: Realizar pruebas de posicionamiento mediante un contenedor host Win32
Puede crear objetos visuales en una ventana de Win32 proporcionando un contenedor de ventana host para los objetos visuales. Para proporcionar control de eventos para los objetos visuales contenidos, proceso los mensajes que se pasan al bucle de filtro de mensajes del contenedor de la ventana del host. Consulte [Tutorial: hospedar objetos visuales en una aplicación Win32](tutorial-hosting-visual-objects-in-a-win32-application.md) para obtener más información sobre cómo hospedar objetos visuales en una ventana de Win32.  
  
## <a name="example"></a>Ejemplo  
 En el código siguiente se muestra cómo configurar los controladores de eventos del mouse para una ventana de Win32 que se usa como contenedor host para objetos visuales.  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 En el ejemplo siguiente se muestra cómo configurar una prueba de posicionamiento en respuesta a la captura de eventos de mouse concretos.  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 El objeto <xref:System.Windows.Interop.HwndSource> presenta [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] contenido dentro de una ventana de Win32. El valor de la propiedad <xref:System.Windows.Interop.HwndSource.RootVisual%2A> del objeto <xref:System.Windows.Interop.HwndSource> representa el nodo de nivel superior de la jerarquía de árbol visual.  
  
 Para obtener el ejemplo completo de los objetos de prueba de posicionamiento mediante un contenedor host de Win32, vea [prueba de posicionamiento con el ejemplo de interoperación de Win32](https://go.microsoft.com/fwlink/?LinkID=159995).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Interop.HwndSource>
- [Realizar pruebas de posicionamiento en la capa visual](hit-testing-in-the-visual-layer.md)
- [Tutorial: Hospedar objetos visuales en una aplicación Win32](tutorial-hosting-visual-objects-in-a-win32-application.md)
