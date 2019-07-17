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
ms.openlocfilehash: 13812fa5429bbe33341e51e4b3be14fbbcb361cb
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/16/2019
ms.locfileid: "68238448"
---
# <a name="optimizing-performance-taking-advantage-of-hardware"></a>Optimizar el rendimiento: Aprovechar el hardware
La arquitectura interna de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tiene dos canalizaciones de representación, hardware y software. En este tema se proporciona información sobre estas canalizaciones de representación que le ayudarán a tomar decisiones acerca de las optimizaciones del rendimiento de las aplicaciones.  
  
## <a name="hardware-rendering-pipeline"></a>Canalización de representación de hardware  
 Uno de los factores más importantes para determinar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] rendimiento es que está limitado por la representación: cuantos más píxeles tiene que representar, mayor será el costo de rendimiento. Sin embargo, se pueden descargar más representación el [!INCLUDE[TLA#tla_gpu](../../../../includes/tlasharptla-gpu-md.md)], mientras más beneficios de rendimiento, puede obtener. El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] canalización de representación de hardware de aplicación aprovecha plenamente [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] las características de hardware compatible con un mínimo de [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] versión 7.0. Se pueden conseguir más optimizaciones por hardware que admite [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] versión 7.0 y las características de PixelShader 2.0 +.  
  
## <a name="software-rendering-pipeline"></a>Canalización de representación de software  
 El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] canalización de representación de software es totalmente dependiente de CPU. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se aprovecha de las instrucciones de SSE y SSE2 se establece en la CPU para implementar un rasterizador de software optimizado con características completas. Reserva de software es transparente en cualquier momento a la funcionalidad de la aplicación no se puede representar mediante la canalización de representación de hardware.  
  
 El problema de rendimiento mayor que surgen al procesamiento en modo de software está relacionado con la velocidad de relleno, que se define como el número de píxeles que se está representando. Si le preocupa el rendimiento en modo de representación de software, intente minimizar el número de veces que se vuelve a dibujar un píxel. Por ejemplo, si tiene una aplicación con un fondo azul, que luego se representa una imagen ligeramente transparente encima de él, se representarán todos los píxeles en la aplicación dos veces. Como resultado, se tardará dos veces mientras para representar la aplicación con la imagen que si tuviera únicamente el fondo azul.  
  
### <a name="graphics-rendering-tiers"></a>Niveles de representación de gráficos  
 Puede ser muy difícil de predecir la configuración de hardware que se ejecutará la aplicación. Sin embargo, puede considerar un diseño que permite que la aplicación cambiar a la perfección características cuando se ejecuta en un hardware diferente, por lo que puede aprovechar al máximo cada configuración de hardware diferente.  
  
 Para lograrlo, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona funcionalidad para determinar la capacidad gráfica de un sistema en tiempo de ejecución. Capacidad para gráficos viene determinada por la clasificación de la tarjeta de vídeo como uno de los tres niveles de funcionalidad de representación. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] expone una API que permite que una aplicación consultar el nivel de funcionalidad de representación. La aplicación, a continuación, puede tomar diferentes rutas de código en tiempo de ejecución según el nivel de representación compatible con el hardware.  
  
 Las características del hardware gráfico que más afectan a los niveles de representación son:  
  
- **RAM de vídeo** La cantidad de memoria de vídeo en el hardware gráfico determina el tamaño y el número de búferes que puede utilizarse para la composición de gráficos.  
  
- **Sombreador de píxeles** Un sombreador de píxeles es una función de procesamiento de gráficos que calcula los efectos píxel por píxel. Según la resolución de los gráficos mostrados, puede haber varios millones de píxeles que deban procesarse en cada fotograma mostrado.  
  
- **Sombreador de vértices** Un sombreador de vértices es una función de procesamiento de gráficos que realiza operaciones matemáticas en los datos de vértice del objeto.  
  
- **Compatibilidad con texturas múltiples** La compatibilidad con texturas múltiples hace referencia a la capacidad de aplicar dos o más texturas distintas durante una operación de combinación en un objeto gráfico 3D. El grado de compatibilidad con texturas múltiples queda determinado por el número de unidades de múltiples texturas en el hardware gráfico.  
  
 El sombreador de píxeles, del sombreador de vértices y texturas múltiples características que se usan para definir específico [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] niveles de versión, que, a su vez, se usan para definir los niveles de representación diferente en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Las características del hardware gráfico determinan la capacidad de representación de una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. El sistema [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] define tres niveles de representación:  
  
- **Nivel de representación 0** Sin aceleración de hardware gráfico. El [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] el nivel de versión es menor que la versión 7.0.  
  
- **Nivel de representación 1** aceleración de hardware gráfico parcial. El [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] nivel de versión es mayor o igual a la versión 7.0, y **menor** que la versión 9.0.  
  
- **Nivel de representación 2** La mayoría de las características de gráficos utiliza la aceleración de hardware gráfico. El nivel de versión de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] es mayor o igual que la versión 9.0.  
  
 Para obtener más información sobre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] niveles de representación, vea [niveles de representación de gráficos](graphics-rendering-tiers.md).  
  
## <a name="see-also"></a>Vea también

- [Optimizar WPF: Rendimiento de aplicaciones](optimizing-wpf-application-performance.md)
- [Planear para mejorar el rendimiento de aplicaciones](planning-for-application-performance.md)
- [Presentación y diseño](optimizing-performance-layout-and-design.md)
- [Imágenes y gráficos 2D](optimizing-performance-2d-graphics-and-imaging.md)
- [Comportamiento de objetos](optimizing-performance-object-behavior.md)
- [Recursos de la aplicación](optimizing-performance-application-resources.md)
- [Texto](optimizing-performance-text.md)
- [Enlace de datos](optimizing-performance-data-binding.md)
- [Otras recomendaciones de rendimiento](optimizing-performance-other-recommendations.md)
