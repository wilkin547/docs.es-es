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
ms.openlocfilehash: 7acf5a3f48ac4987037873c63111d988ec3a4979
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629652"
---
# <a name="optimizing-performance-taking-advantage-of-hardware"></a>Optimizar el rendimiento: Aprovechar el hardware
La arquitectura interna de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tiene dos canalizaciones de representación, hardware y software. En este tema se proporciona información acerca de estas canalizaciones de representación para ayudarle a tomar decisiones sobre las optimizaciones de rendimiento de las aplicaciones.  
  
## <a name="hardware-rendering-pipeline"></a>Canalización de representación de hardware  
 Uno de los factores más importantes a la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hora de determinar el rendimiento es que es un límite de representación; cuanto más píxeles tiene que representar, mayor será el costo de rendimiento. Sin embargo, cuanto más representación se puede descargar en el [!INCLUDE[TLA#tla_gpu](../../../../includes/tlasharptla-gpu-md.md)], más beneficios de rendimiento puede obtener. La [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] canalización de representación de hardware de aplicaciones aprovecha al máximo las características de Microsoft DirectX en hardware que admite como mínimo la versión 7,0 de Microsoft DirectX. Puede obtener más optimizaciones mediante hardware que admita las características de Microsoft DirectX versión 7,0 y u 2.0 +.  
  
## <a name="software-rendering-pipeline"></a>Canalización de representación de software  
 La [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] canalización de representación de software está totalmente enlazada a la CPU. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]aprovecha los conjuntos de instrucciones SSE y SSE2 de la CPU para implementar un rasterizador de software optimizado y con todas las características. La reserva para el software es fluida siempre que no se pueda representar la funcionalidad de la aplicación mediante la canalización de representación de hardware.  
  
 El mayor problema de rendimiento que encontrará al representarse en modo de software está relacionado con la velocidad de relleno, que se define como el número de píxeles que está representando. Si le preocupa el rendimiento en el modo de representación de software, intente minimizar el número de veces que se vuelve a dibujar un píxel. Por ejemplo, si tiene una aplicación con un fondo azul, que, a continuación, representa una imagen ligeramente transparente sobre ella, se representarán dos veces todos los píxeles de la aplicación. Como resultado, se tardará dos veces más en presentar la aplicación con la imagen que si solo tenía el fondo azul.  
  
### <a name="graphics-rendering-tiers"></a>Niveles de representación de gráficos  
 Puede ser muy difícil predecir la configuración de hardware en la que se ejecutará la aplicación. Sin embargo, es posible que desee considerar un diseño que permita a la aplicación cambiar sin problemas las características cuando se ejecuta en hardware diferente, de modo que pueda aprovechar al máximo cada configuración de hardware diferente.  
  
 Para ello, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona funcionalidad para determinar la funcionalidad de gráficos de un sistema en tiempo de ejecución. La capacidad de gráficos se determina mediante la categorización de la tarjeta de vídeo como uno de tres niveles de capacidad de representación. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]expone una API que permite que una aplicación consulte el nivel de capacidad de representación. A continuación, la aplicación puede tomar diferentes rutas de código en tiempo de ejecución según el nivel de representación admitido por el hardware.  
  
 Las características del hardware gráfico que más afectan a los niveles de representación son:  
  
- **RAM de vídeo** La cantidad de memoria de vídeo en el hardware gráfico determina el tamaño y el número de búferes que puede utilizarse para la composición de gráficos.  
  
- **Sombreador de píxeles** Un sombreador de píxeles es una función de procesamiento de gráficos que calcula los efectos píxel por píxel. Según la resolución de los gráficos mostrados, puede haber varios millones de píxeles que deban procesarse en cada fotograma mostrado.  
  
- **Sombreador de vértices** Un sombreador de vértices es una función de procesamiento de gráficos que realiza operaciones matemáticas en los datos de vértice del objeto.  
  
- **Compatibilidad con texturas múltiples** La compatibilidad con texturas múltiples hace referencia a la capacidad de aplicar dos o más texturas distintas durante una operación de combinación en un objeto gráfico 3D. El grado de compatibilidad con texturas múltiples queda determinado por el número de unidades de múltiples texturas en el hardware gráfico.  
  
 El sombreador de píxeles, el sombreador de vértices y las características de varias texturas se utilizan para definir niveles de versión específicos de DirectX, que, a su vez, se usan [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]para definir los distintos niveles de representación en.  
  
 Las características del hardware gráfico determinan la capacidad de representación de una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. El sistema [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] define tres niveles de representación:  
  
- **Nivel de representación 0** Sin aceleración de hardware gráfico. El nivel de versión de DirectX es anterior a la versión 7,0.  
  
- **Nivel de representación 1** Aceleración de hardware de gráficos parcial. El nivel de versión de DirectX es mayor o igual que la versión 7,0 y **menor** que la versión 9,0.  
  
- **Nivel de representación 2** La mayoría de las características de gráficos utiliza la aceleración de hardware gráfico. El nivel de versión de DirectX es mayor o igual que la versión 9,0.  
  
 Para obtener más información [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sobre la representación de niveles, vea [niveles de representación de gráficos](graphics-rendering-tiers.md).  
  
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
