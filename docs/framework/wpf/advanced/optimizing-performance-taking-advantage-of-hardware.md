---
title: 'Optimizar el rendimiento: Aprovechar el hardware'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], performance
- hardware rendering pipeline [WPF]
- rendering tiers [WPF]
- graphics rendering tiers [WPF]
- graphics [WPF], rendering tiers
- software rendering pipeline [WPF]
ms.assetid: bfb89bae-7aab-4cac-a26c-a956eda8fce2
ms.openlocfilehash: eb790da63b4636e3dd6c25ea118075304702acc0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547259"
---
# <a name="optimizing-performance-taking-advantage-of-hardware"></a>Optimizar el rendimiento: Aprovechar el hardware
La arquitectura interna de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tiene dos canalizaciones de representación, hardware y software. Este tema proporciona información acerca de estas canalizaciones de representación para ayudarle a tomar decisiones sobre la optimización del rendimiento de las aplicaciones.  
  
## <a name="hardware-rendering-pipeline"></a>Canalización de representación de hardware  
 Uno de los factores más importantes en la determinación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] rendimiento es que está limitado por la representación: cuantos más píxeles se deben representar, mayor será el costo de rendimiento. Sin embargo, cuantos más de representación que se pueden descargar en el [!INCLUDE[TLA#tla_gpu](../../../../includes/tlasharptla-gpu-md.md)], las ventajas de rendimiento más puede obtener. El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] canalización de representación de hardware de aplicación aprovecha al máximo de [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] características de hardware que es compatible con un mínimo de [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] versión 7.0. Mayor nivel de optimización puede obtenerse con el hardware que admita [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] versión 7.0 y las características de compatible del sombreador de píxeles 2.0 +.  
  
## <a name="software-rendering-pipeline"></a>Canalización de representación de software  
 El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] canalización de representación de software es totalmente dependiente de CPU. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se aprovecha de las instrucciones de SSE y SSE2 se establece en la CPU para implementar un rasterizador de software optimizado con características completas. Reserva de software es perfecto siempre que no se puede representar la funcionalidad de la aplicación mediante la canalización de representación de hardware.  
  
 El principal problema de rendimiento se produce cuando la representación en modo de software está relacionada con la velocidad de relleno, que se define como el número de píxeles que está representando. Si le preocupa el rendimiento en modo de representación de software, pruebe a minimizar el número de veces que se vuelve a dibujar un píxel. Por ejemplo, si tiene una aplicación con un fondo azul, que luego se representa una imagen ligeramente transparente sobre él, se representarán todos los píxeles de la aplicación dos veces. Como resultado, se tardará dos veces siempre para representar la aplicación con la imagen que si tuviera únicamente el fondo azul.  
  
### <a name="graphics-rendering-tiers"></a>Niveles de representación de gráficos  
 Puede ser muy difícil de predecir la configuración de hardware que se ejecutará la aplicación. Sin embargo, debe tener en cuenta un diseño que permite a la aplicación cambiar sin fisuras las características cuando se ejecuta en un hardware diferente, por lo que pueden aprovechar al máximo de cada configuración de hardware diferente.  
  
 Para lograr esto, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona funcionalidad para determinar la capacidad gráfica de un sistema en tiempo de ejecución. Capacidad para gráficos se determina categorizando la tarjeta de vídeo como uno de los tres niveles de capacidad de representación. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] expone un [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] que permite que una aplicación consultar el nivel de capacidad de representación. La aplicación, a continuación, puede tomar diferentes rutas de código en tiempo de ejecución según el nivel de representación compatible con el hardware.  
  
 Las características del hardware gráfico que más afectan a los niveles de representación son:  
  
-   **RAM de vídeo** La cantidad de memoria de vídeo en el hardware gráfico determina el tamaño y el número de búferes que puede utilizarse para la composición de gráficos.  
  
-   **Sombreador de píxeles** Un sombreador de píxeles es una función de procesamiento de gráficos que calcula los efectos píxel por píxel. Según la resolución de los gráficos mostrados, puede haber varios millones de píxeles que deban procesarse en cada fotograma mostrado.  
  
-   **Sombreador de vértices** Un sombreador de vértices es una función de procesamiento de gráficos que realiza operaciones matemáticas en los datos de vértice del objeto.  
  
-   **Compatibilidad con texturas múltiples** La compatibilidad con texturas múltiples hace referencia a la capacidad de aplicar dos o más texturas distintas durante una operación de combinación en un objeto gráfico 3D. El grado de compatibilidad con texturas múltiples queda determinado por el número de unidades de múltiples texturas en el hardware gráfico.  
  
 El sombreador de píxeles, el sombreador de vértices y características de texturas múltiples se utilizan para definir específico [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] niveles de versión, que a su vez, se utilizan para definir los niveles de representación diferente en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Las características del hardware gráfico determinan la capacidad de representación de una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. El sistema [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] define tres niveles de representación:  
  
-   **Nivel de representación 0** Sin aceleración de hardware gráfico. El [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] el nivel de versión es menor que la versión 7.0.  
  
-   **Representación de nivel 1** aceleración de hardware gráfico parcial. El [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] nivel de versión es mayor o igual a la versión 7.0, y **menor** a la versión 9.0.  
  
-   **Nivel de representación 2** La mayoría de las características de gráficos utiliza la aceleración de hardware gráfico. El nivel de versión de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] es mayor o igual que la versión 9.0.  
  
 Para obtener más información sobre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] niveles de representación, vea [niveles de representación de gráficos](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md).  
  
## <a name="see-also"></a>Vea también  
 [Optimizar WPF: Rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [Planear para mejorar el rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [Presentación y diseño](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [Imágenes y gráficos 2D](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Comportamiento de objetos](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [Recursos de la aplicación](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [Texto](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [Enlace de datos](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [Otras recomendaciones de rendimiento](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
