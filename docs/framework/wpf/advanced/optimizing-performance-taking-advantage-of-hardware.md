---
title: "Optimizar el rendimiento: Aprovechar el hardware | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "niveles de representación de gráficos"
  - "gráficos, rendimiento"
  - "gráficos, niveles de representación"
  - "canalización de representación de hardware"
  - "niveles de representación"
  - "canalización de representación de software"
ms.assetid: bfb89bae-7aab-4cac-a26c-a956eda8fce2
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Optimizar el rendimiento: Aprovechar el hardware
La arquitectura interna de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tiene dos canalizaciones de representación, la de hardware y la de software.  En este tema se proporciona información sobre estas canalizaciones de representación a fin de ayudarle a tomar las decisiones relativas a la optimización del rendimiento de las aplicaciones.  
  
## Canalización de representación de hardware  
 Uno de los factores más importantes para determinar el rendimiento de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es que está limitado por la representación: cuantos más píxeles se deben representar, mayor es el costo de rendimiento.  Sin embargo, cuanta más representación se pueda descargar a la [!INCLUDE[TLA#tla_gpu](../../../../includes/tlasharptla-gpu-md.md)], mayores ventajas de rendimiento se pueden conseguir.  La canalización de representación de hardware de las aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aprovecha plenamente las características de [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] en el hardware que admite como mínimo la versión 7.0 de [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)].  Se puede obtener mayor nivel de optimización con hardware que admita las características de [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] versión 7.0 y de PixelShader 2.0\+.  
  
## Canalización de representación de software  
 En la canalización de representación de software de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], la CPU impone la totalidad de la limitación.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aprovecha los conjuntos de instrucciones de SSE y SSE2 de la CPU para implementar un rasterizador de software optimizado con características completas.  El recurso al software se realiza sin fisuras en cualquier momento en que no es posible representar las funcionalidades de la aplicación mediante la canalización de representación de hardware.  
  
 El principal problema de rendimiento que encontrará al representar en modo de software tiene que ver con la velocidad de relleno, que es el número de píxeles que se representan.  Si le preocupa el rendimiento en el modo de representación de software, intente minimizar la cantidad de veces que se vuelve a dibujar un píxel.  Por ejemplo, si tiene una aplicación con fondo azul que, a continuación, representa una imagen ligeramente transparente sobre él, se representarán dos veces todos los píxeles de la aplicación.  Como resultado, se tardará el doble en representar la aplicación con la imagen que si tuviera únicamente el fondo azul.  
  
### Niveles de representación de gráficos  
 Puede ser muy difícil predecir la configuración de hardware en la que la aplicación se va a ejecutar.  Sin embargo, puede ser conveniente estudiar un diseño que permita a la aplicación cambiar sin fisuras las características cuando se ejecute en distintos hardwares, para que pueda aprovechar al máximo cada configuración de hardware diferente.  
  
 Para lograrlo, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona funcionalidades que permiten determinar la capacidad gráfica de un sistema en tiempo de ejecución.  La capacidad gráfica se determina categorizando la tarjeta de vídeo en tres capas de capacidad de representación.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] expone una [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] que permite a una aplicación consultar la capa de capacidad de representación.  La aplicación puede tomar a continuación diferentes rutas de código en tiempo de ejecución en función del nivel de representación que admita el hardware.  
  
 Las características del hardware gráfico que más afectan a los niveles de representación son:  
  
-   **RAM de vídeo**: la cantidad de memoria de vídeo en el hardware gráfico determina el tamaño y el número de búferes que se pueden utilizar para la composición de gráficos.  
  
-   **Sombreador de píxeles**: un sombreador de píxeles es una función de procesamiento de gráficos que calcula los efectos por píxel.  Según la resolución de los gráficos mostrados, puede haber varios millones de píxeles que deban procesarse en cada fotograma mostrado.  
  
-   **Sombreador de vértices**: un sombreador de vértices es una función de procesamiento de gráficos que realiza operaciones matemáticas con los datos de los vértices del objeto.  
  
-   **Compatibilidad con texturas múltiples**: la compatibilidad con texturas múltiples hace referencia a la capacidad de aplicar dos o más texturas distintas durante una operación de mezcla en un objeto gráfico 3D.  El grado de compatibilidad con texturas múltiples viene determinado por el número de unidades de textura múltiple en el hardware gráfico.  
  
 El sombreador de píxeles, el sombreador de vértices y las características de texturas múltiples se utilizan para definir niveles de versión de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] específicos que, a su vez, se utilizan para definir los diferentes niveles de representación en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Las características del hardware gráfico determinan la capacidad de representación de una aplicación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  El sistema [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] define tres niveles de representación:  
  
-   **Nivel de representación 0** Sin aceleración de hardware gráfico.  El nivel de versión de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] es inferior a la versión 7.0.  
  
-   **Nivel de representación 1** Aceleración parcial del hardware gráfico.  El nivel de versión de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] es mayor o igual a la versión 7.0 y **menor** que la versión 9.0.  
  
-   **Nivel de representación 2** La mayoría de las características gráficas utilizan la aceleración de hardware gráfico.  El nivel de versión de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] es mayor o igual a la versión 9.0.  
  
 Para obtener más información sobre los niveles de representación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], consulte [Niveles de representación de gráficos](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md).  
  
## Vea también  
 [Optimizar WPF: Rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [Planear para mejorar el rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [Presentación y diseño](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [Imágenes y gráficos GDI\+](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Comportamiento de objetos](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)   
 [Recursos de aplicación](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [Enlace de datos](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Otras recomendaciones de rendimiento](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)