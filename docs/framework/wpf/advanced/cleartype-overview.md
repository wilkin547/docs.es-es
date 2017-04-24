---
title: "Informaci&#243;n general sobre ClearType | Microsoft Docs"
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
  - "ClearType, tecnología"
  - "tipografía, ClearType (tecnología)"
ms.assetid: 7e2392e0-75dc-463d-a716-908772782431
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Informaci&#243;n general sobre ClearType
En este tema se proporciona información general sobre la tecnología [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)] de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
   
  
<a name="overview"></a>   
## Información general sobre la tecnología  
 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] es una tecnología de software desarrollada por [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] que mejora la legibilidad del texto en las pantallas de cristal líquido \(LCD\) existentes, tales como las de los equipos portátiles, los Pocket PC o los monitores de pantalla plana.  [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] funciona teniendo acceso a los elementos de las bandas de color verticales individuales de cada píxel de una pantalla LCD.  Antes de [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)], el menor nivel de detalle que un equipo podía mostrar era un solo píxel; sin embargo, gracias a la ejecución de [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] en un monitor LCD, ahora se puede mostrar características del texto con el ancho de una fracción de píxel.  Esta resolución adicional aumenta la nitidez de los detalles diminutos en la presentación del texto, lo que facilita mucho su lectura durante espacios de tiempo prolongados.  
  
 La tecnología [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] disponible en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] es la última generación de [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)], y presenta varias mejoras sobre la versión de [!INCLUDE[TLA#tla_gdi](../../../../includes/tlasharptla-gdi-md.md)].  
  
<a name="sub-pixel_positioning"></a>   
## Posición de subpíxel  
 Una mejora significativa con respecto a la versión anterior de [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] es el uso de la posición de subpíxel.  A diferencia de la implementación de [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] de [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)], la tecnología [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] permite que los glifos se inicien dentro del píxel, no solo en el límite inicial del píxel.  Gracias a esta resolución adicional al colocar los glifos, el espaciado y las proporciones de los glifos son más precisos y coherentes.  
  
 En los dos ejemplos siguientes se muestra cómo pueden comenzar los glifos en el límite de cualquier subpíxel cuando se utiliza la posición de subpíxel.  El ejemplo de la izquierda se ha representado utilizando la versión anterior del representador [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)], que no empleaba la posición de subpíxel.  El ejemplo de la derecha se ha representado mediante la nueva versión del representador [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)], que utiliza la posición de subpíxel.  Observe que cada letra **e** y **l** de la imagen de la derecha se representa de un modo ligeramente distinto, porque cada una se inicia en un subpíxel diferente.  Al observar el texto con su tamaño normal en la pantalla, esta diferencia no es apreciable debido al alto contraste de la imagen de glifo.  Esto solo es posible gracias al filtrado sofisticado del color incorporado en [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)].  
  
 ![Texto mostrado con dos versiones de ClearType](../../../../docs/framework/wpf/advanced/media/wcpsdk-mmgraphics-text-cleartype-overview-01.png "wcpsdk\_mmgraphics\_text\_cleartype\_overview\_01")  
Texto mostrado con versiones anteriores y posteriores de ClearType  
  
 En los dos ejemplos siguientes se compara la salida del representador [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] anterior con la nueva versión del procesador [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)].  La posición de subpíxel, que se muestra a la derecha, mejora en gran medida el espaciado de los tipos en la pantalla, sobre todo en los tamaños pequeños donde la diferencia entre un subpíxel y un píxel entero representa una proporción significativa de ancho del glifo.  Observe que el espaciado entre las letras es más uniforme en la segunda imagen.  Se aumenta significativamente la ventaja acumulativa de la posición de subpíxel para el aspecto global de una pantalla de texto, lo que representa una evolución significativa en la tecnología [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)].  
  
 ![Texto mostrado con una versión anterior de ClearType](../../../../docs/framework/wpf/advanced/media/wcpsdk-mmgraphics-text-cleartype-overview-02.png "wcpsdk\_mmgraphics\_text\_cleartype\_overview\_02")  
Texto con versiones anteriores y posteriores de ClearType  
  
<a name="y-direction_antialiasing"></a>   
## Suavizado de contorno en la dirección del eje Y  
 Otra mejora de [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] es el suavizado de contorno en la dirección del eje Y.  La tecnología [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] de [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] sin suavizado de contorno en la dirección del eje Y proporciona una mejor resolución en el eje X, pero no en el eje Y.  En las partes superior e inferior de las curvas poco marcadas, los bordes escalonados reducen su legibilidad.  
  
 En el ejemplo siguiente se muestra el efecto de no aplicar ningún suavizado de contorno en la dirección del eje Y.  En este caso, los bordes escalonados de la parte superior e inferior de la letra se aprecian con claridad.  
  
 ![Texto con bordes escalonados en curvas suaves](../../../../docs/framework/wpf/advanced/media/wcpsdk-mmgraphics-text-cleartype-overview-03.png "wcpsdk\_mmgraphics\_text\_cleartype\_overview\_03")  
Texto con bordes escalonados en curvas poco marcadas  
  
 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona el suavizado de contorno en el nivel de la dirección del eje Y para suavizar los bordes escalonados.  Es particularmente importante para mejorar la legibilidad en los idiomas del este asiático, cuyos ideogramas tienen una cantidad casi igual de curvas horizontales y verticales poco marcadas.  
  
 En el ejemplo siguiente se muestra el efecto del suavizado de contorno en la dirección del eje Y.  En este caso, las partes superior e inferior de la letra muestran una curva poco marcada.  
  
 ![Texto con función de suavizado de contorno de ClearType en la dirección del eje y](../../../../docs/framework/wpf/advanced/media/wcpsdk-mmgraphics-text-cleartype-overview-04.png "wcpsdk\_mmgraphics\_text\_cleartype\_overview\_04")  
Texto con suavizado de contorno de ClearType en la dirección del eje y  
  
<a name="hardware_acceleration"></a>   
## Aceleración de hardware  
 La tecnología [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] puede aprovechar la aceleración de hardware para mejorar el rendimiento y reducir la carga de la CPU, así como los requisitos de memoria del sistema.  [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] utiliza los sombreadores de píxeles y la memoria de vídeo de la tarjeta gráfica para proporcionar una representación más rápida del texto, en especial cuando se utiliza la animación.  
  
 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] no modifica en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] los valores de [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] para todo el sistema.  Al deshabilitar [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] en [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], se establece el suavizado de contorno de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] en el modo de escala de grises. Además, [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] no modifica los valores de [ClearType Tuner PowerToy](http://www.microsoft.com/typography/ClearTypePowerToy.mspx).  
  
 Una de las decisiones de diseño de la arquitectura de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] es que el diseño independiente de la resolución ofrezca una mejor compatibilidad con los monitores de PPP de alta resolución, cada vez más utilizados.  Como consecuencia, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] no admite la representación de texto suavizado ni los mapas de bits de algunas de las fuentes del este asiático, porque dependen de la resolución.  
  
<a name="further_information"></a>   
## Más información  
 [ClearType Information](http://www.microsoft.com/typography/ClearTypeInfo.mspx)  
  
 [ClearType Tuner PowerToy](http://www.microsoft.com/typography/ClearTypePowerToy.mspx)  
  
## Vea también  
 [Configuración del Registro de ClearType](../../../../docs/framework/wpf/advanced/cleartype-registry-settings.md)