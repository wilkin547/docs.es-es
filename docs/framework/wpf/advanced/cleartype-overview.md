---
title: Información general sobre ClearType
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], ClearType technology
- ClearType [WPF], technology
ms.assetid: 7e2392e0-75dc-463d-a716-908772782431
ms.openlocfilehash: 7bf04e7c22bf13ed681be7afb582176edc2f3072
ms.sourcegitcommit: 4b9c2d893b45d47048c6598b4182ba87759b1b59
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2019
ms.locfileid: "68484698"
---
# <a name="cleartype-overview"></a>Información general sobre ClearType
En este tema se proporciona información general sobre la tecnología [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)] que se encuentra en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  

<a name="overview"></a>   
## <a name="technology-overview"></a>Información general sobre la tecnología  
 ClearType es una tecnología de software desarrollada [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] por que mejora la legibilidad del texto en pantallas de cristal líquido (LCD) existentes, como pantallas de equipos portátiles, pantallas de Pocket PC y monitores de pantalla plana.  ClearType funciona mediante el acceso a los elementos de franjas de color vertical individuales en cada píxel de una pantalla LCD. Antes de ClearType, el menor nivel de detalle que un equipo podría mostrar era un solo píxel, pero con ClearType ejecutándose en un monitor LCD, ahora podemos mostrar características de texto tan pequeñas como una fracción de un píxel de ancho. Esta resolución adicional aumenta la nitidez de los detalles diminutos en la presentación del texto, lo que facilita la lectura durante largos períodos de tiempo.  
  
 ClearType disponible en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] es la última generación de ClearType que tiene varias mejoras con respecto a la versión [!INCLUDE[TLA#tla_gdi](../../../../includes/tlasharptla-gdi-md.md)]que se encuentra en.  
  
<a name="sub-pixel_positioning"></a>   
## <a name="sub-pixel-positioning"></a>Posicionamiento de subpíxeles  
 Una mejora significativa con respecto a la versión anterior de ClearType es el uso del posicionamiento de subpíxeles. A diferencia de la implementación de ClearType [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)]que se encuentra en, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] el ClearType que se encuentra en permite que los glifos se inicien en el píxel y no solo en el límite inicial del píxel. Debido a esta resolución adicional al posicionar los glifos, el espaciado y las proporciones de los glifos son más precisos y coherentes.  
  
 En los dos ejemplos siguientes se muestra cómo pueden comenzar los glifos en cualquier límite de subpíxel cuando se usa el posicionamiento de subpíxeles. El ejemplo de la izquierda se representa con la versión anterior del representador ClearType, que no empleaba el posicionamiento de subpíxeles. El ejemplo de la derecha se representa con la nueva versión del representador ClearType, mediante el posicionamiento de subpíxeles. Observe que todas las **e** y **l** de la imagen de la derecha se representan de manera ligeramente diferente porque cada una de ellas se inicia en un subpíxel diferente. Al ver el texto con su tamaño normal en la pantalla, esta diferencia no es apreciable debido al alto contraste de la imagen de glifo. Esto solo es posible debido al sofisticado filtrado de color que se incorpora en ClearType.  
  
 ![Texto que se muestra con dos versiones de ClearType](./media/wcpsdk-mmgraphics-text-cleartype-overview-01.png "wcpsdk_mmgraphics_text_cleartype_overview_01")  
Texto mostrado con versiones anteriores y posteriores de ClearType  
  
 En los dos ejemplos siguientes se compara la salida del representador ClearType anterior con la nueva versión del representador ClearType. El posicionamiento de subpíxeles, que se muestra a la derecha, mejora enormemente el espaciado del tipo en la pantalla, especialmente con tamaños pequeños, donde la diferencia entre un subpíxel y un píxel completo representa una proporción considerable del ancho del glifo. Observe que el espaciado entre las letras es más uniforme en la segunda imagen. La ventaja acumulativa del posicionamiento de subpíxeles en la apariencia general de una pantalla de texto aumenta considerablemente y representa una evolución significativa en la tecnología ClearType.  
  
 ![Texto mostrado con una versión anterior de ClearType](./media/wcpsdk-mmgraphics-text-cleartype-overview-02.png "wcpsdk_mmgraphics_text_cleartype_overview_02")  
Texto con versiones anteriores y posteriores de ClearType  
  
<a name="y-direction_antialiasing"></a>   
## <a name="y-direction-antialiasing"></a>Suavizado de contorno de la dirección del eje Y  
 Otra mejora de ClearType en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] es el suavizado de contorno de la dirección y. El ClearType en [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] sin suavizado de contorno de la dirección y proporciona una mejor resolución en el eje x, pero no en el eje y. En las partes superiores e inferiores de las curvas superficiales, los bordes escalonados restan valor a legibilidad.  
  
 En el ejemplo siguiente se muestra el efecto de no tener ningún suavizado de contorno de la dirección del eje Y. En este caso, los bordes escalonados de las partes superior e inferior de la carta son evidentes.  
  
 ![Texto con bordes escalonados en curvas rasas](./media/wcpsdk-mmgraphics-text-cleartype-overview-03.png "wcpsdk_mmgraphics_text_cleartype_overview_03")  
Texto con bordes escalonados en curvas suaves  
  
 ClearType en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona alisado en el nivel de la y para suavizar los bordes dentados. Esto es especialmente importante para mejorar la legibilidad de los idiomas del este asiático, cuyos ideogramas tienen una cantidad casi igual de curvas suaves horizontales y verticales.  
  
 En el ejemplo siguiente se muestra el efecto de suavizado de contorno de la dirección del eje Y. En este caso, las partes superior e inferior de la letra muestran una curva suave.  
  
 ![Texto con suavizado&#45;de&#45;contorno de dirección y ClearType](./media/wcpsdk-mmgraphics-text-cleartype-overview-04.png "wcpsdk_mmgraphics_text_cleartype_overview_04")  
Texto con función de suavizado de contorno de ClearType en la dirección del eje Y  
  
<a name="hardware_acceleration"></a>   
## <a name="hardware-acceleration"></a>Aceleración de hardware  
 ClearType en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] puede aprovechar la aceleración de hardware para mejorar el rendimiento y reducir los requisitos de carga de CPU y memoria del sistema. Mediante el uso de los sombreadores de píxeles y la memoria de vídeo de una tarjeta gráfica, ClearType proporciona una representación más rápida del texto, especialmente cuando se usa la animación.  
  
 ClearType en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] no modifica la configuración de ClearType en todo el sistema. Deshabilitar ClearType en [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] establece [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] el suavizado de contorno en el modo de escala de grises. Además, ClearType en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] no modifica la configuración del Powertoy del sintonizador [ClearType](https://www.microsoft.com/typography/ClearTypePowerToy.mspx).  
  
 Una de las decisiones de diseño de arquitectura de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] consiste en mejorar la compatibilidad del diseño independiente de la resolución con monitores de mayor resolución de PPP, cuyo uso se está generalizando. Como consecuencia, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] no admite la representación de texto con alias ni los mapas de bits de algunas fuentes del este asiático, porque ambos dependen de la resolución.  
  
<a name="further_information"></a>   
## <a name="further-information"></a>Información adicional  
 [ClearType Information](https://www.microsoft.com/typography/ClearTypeInfo.mspx) (Información de ClearType)  
  
 [ClearType Tuner PowerToy](https://www.microsoft.com/typography/ClearTypePowerToy.mspx)  
  
## <a name="see-also"></a>Vea también

- [Configuración del Registro de ClearType](cleartype-registry-settings.md)
