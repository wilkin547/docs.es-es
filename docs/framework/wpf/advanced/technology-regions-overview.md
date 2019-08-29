---
title: Información general sobre áreas de la tecnología
ms.date: 03/30/2017
helpviewer_keywords:
- window regions [WPF]
- Win32 code [WPF], WPF interoperation
- Win32 code [WPF], airspace
- airspace [WPF]
- interoperability [WPF], airspace
- Win32 code [WPF], window regions
ms.assetid: b7cc350f-b9e2-48b1-be14-60f3d853222e
ms.openlocfilehash: 4f1489065a70065700d2f8ceb974e66ecceeebd0
ms.sourcegitcommit: 77e33b682db39955e331b8e8eda4ef1925a24e78
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2019
ms.locfileid: "70133815"
---
# <a name="technology-regions-overview"></a>Información general sobre áreas de la tecnología
Si se usan varias tecnologías de representación en una aplicación, como WPF, Win32 o DirectX, deben compartir las áreas de representación en una ventana común de nivel superior. En este tema se describen los problemas que podrían afectar a la presentación y la entrada de una aplicación de interoperación WPF.  
  
## <a name="regions"></a>Regiones  
 Dentro de una ventana de nivel superior, puede interpretarse que cada HWND que incluye una de las tecnologías de una aplicación de interoperación tiene su propia región (conocida también como "espacio aéreo"). Cada píxel de la ventana pertenece exactamente a un HWND, que constituye la región de ese HWND. (En realidad, hay más de una región de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] si hay más de un HWND de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], pero para los propósitos de este tutorial, puede suponer que solo hay una). La región implica que todas las capas u otras ventanas que intentan representarse sobre ese píxel durante la duración de la aplicación deben formar parte de la misma tecnología de nivel de representación. El intento de representar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] píxeles sobre [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] los resultados no deseados y no se permite en la medida de lo posible a través de las API de interoperación.  
  
### <a name="region-examples"></a>Ejemplos de región  
 En la ilustración siguiente se muestra una aplicación [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]que combina, DirectX [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]y. Cada tecnología usa su propio conjunto de píxeles independientes no superpuestos y no hay ningún problema con la región.  
  
 ![Un ejemplo de una aplicación que combina Win32, DirectX y WPF.](./media/technology-regions-overview/win32-directx-windows-presentation-foundation-application.png)  
  
 Suponga que esta aplicación usa la posición del puntero del mouse para crear una animación que se intenta representar sobre cualquiera de estas tres regiones. Independientemente de cuál fuese la tecnología responsable de la animación propiamente dicha, esa tecnología invadiría la región de las otras dos. En la ilustración siguiente se muestra un intento de representar un círculo de WPF sobre una región de Win32.  
  
 ![Intento de representar un círculo de WPF en una región de Win32.](./media/technology-regions-overview/render-windows-presentation-foundation-circle-over-win32-region.png)  
  
 Otra infracción consiste en intentar usar la transparencia/combinación alfa entre distintas tecnologías.  En la ilustración siguiente, el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] cuadro infringe las [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] regiones de DirectX y. Dado que los píxeles [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de ese cuadro son semitransparentes, deben ser propiedad conjunta de DirectX y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], lo que no es posible.  Por tanto, es otra infracción y no se puede generar.  
  
 ![Diagrama que muestra un cuadro de WPF que infringe las regiones Win32 y DirectX.](./media/technology-regions-overview/windows-foundation-presentation-box-violate-win32-directx-region.png)  
  
 En los tres ejemplos anteriores se usaban regiones rectangulares, pero es posible usar formas diferentes.  Por ejemplo, una región puede tener un hueco. En la ilustración siguiente se [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] muestra una región con un orificio rectangular que es el tamaño [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de las regiones de y DirectX combinados.  
  
 ![Diagrama que muestra una región de Win32 con un orificio rectangular.](./media/technology-regions-overview/win32-region-rectangular-hole.png)  
  
 Las regiones también pueden adoptar cualquier forma no rectangular, o cualquier forma que pueda describirse mediante un HRGN de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] (región).  
  
 ![Diagrama que muestra una región no rectangular.](./media/technology-regions-overview/nonrectangular-win32-region.png)  
  
## <a name="transparency-and-top-level-windows"></a>Transparencia y ventanas de nivel superior  
 El administrador de ventanas de Windows realmente solo procesa los HWND de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Por lo tanto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , cada <xref:System.Windows.Window> es un HWND. <xref:System.Windows.Window> HWND debe cumplir las reglas generales de cualquier HWND. Dentro de ese HWND [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , el código puede hacer todo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] lo que admiten las API globales. Pero para las interacciones con otros HWND en el escritorio, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] debe cumplir las reglas de procesamiento y representación de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]admite ventanas no rectangulares mediante el [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] uso de API: hrgn para ventanas no rectangulares y ventanas superpuestas para un alfa por píxel.  
  
 No se admiten los valores de alfa ni las claves de color constantes.  Las capacidades de las ventanas superpuestas de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] varían según la plataforma.  
  
 Las ventanas superpuestas pueden hacer que toda la ventana sea translúcida (semitransparente) especificando un valor de alfa que se aplique a todos los píxeles de la ventana.  (De hecho, [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] admite el valor alfa por píxel, pero se trata de algo muy complicado de usar en programas prácticos, porque en este modo se debería dibujar manualmente cada HWND secundario, incluidos los cuadros de diálogo y los cuadros desplegables).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]admite hrgn; sin embargo, no hay ninguna API administrada para esta funcionalidad. Puede usar la invocación de <xref:System.Windows.Interop.HwndSource> plataforma y llamar a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] las API pertinentes. Para más información, vea [Llamar a funciones nativas desde código administrado](/cpp/dotnet/calling-native-functions-from-managed-code).  
  
 Las ventanas superpuestas de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tienen características diferentes según el sistema operativo. Esto se debe [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a que usa DirectX para representarse y las ventanas superpuestas se diseñaron principalmente para la representación de GDI, no para la representación de DirectX.  
  
- WPF admite ventanas superpuestas con aceleración de hardware.  
  
- [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no admite las claves de color de transparencia, porque [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no puede garantizar que se represente exactamente el color que se solicita, en particular cuando se aplica la aceleración de hardware a la representación.  
  
## <a name="see-also"></a>Vea también

- [Interoperabilidad de WPF y Win32](wpf-and-win32-interoperation.md)
- [Tutorial: Hospedar un reloj de WPF en Win32](walkthrough-hosting-a-wpf-clock-in-win32.md)
- [Hospedar contenido de Win32 en WPF](hosting-win32-content-in-wpf.md)
