---
title: Información general sobre el control TrackBar
ms.date: 03/30/2017
f1_keywords:
- TrackBar
helpviewer_keywords:
- sliders [Windows Forms], about sliders
- TrackBar control [Windows Forms], about TrackBar control
- slider controls [Windows Forms], about slider controls
ms.assetid: 95910ecb-8a4c-4776-89fa-206c89ed6973
ms.openlocfilehash: 6901405100df4633c84850757f55b756bc9a0199
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741461"
---
# <a name="trackbar-control-overview-windows-forms"></a>Información general del control TrackBar (formularios Windows Forms)
El control de <xref:System.Windows.Forms.TrackBar> de Windows Forms (también conocido como control de "control deslizante") se utiliza para desplazarse por una gran cantidad de información o para ajustar visualmente una configuración numérica. El control <xref:System.Windows.Forms.TrackBar> tiene dos partes: el control de posición, también conocido como control deslizante y las marcas de graduación. El control Thumb es la parte que se puede ajustar. Su posición corresponde a la propiedad <xref:System.Windows.Forms.TrackBar.Value%2A>. Las marcas de graduación son indicadores visuales que se espacian a intervalos regulares. La barra de desplazamiento se mueve en incrementos que se especifican y se pueden alinear horizontal o verticalmente. Por ejemplo, puede usar la barra de seguimiento para controlar la velocidad de intermitencia del cursor o la velocidad del mouse para un sistema.  
  
## <a name="key-properties"></a>Propiedades clave  
 Las propiedades clave del control <xref:System.Windows.Forms.TrackBar> son <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A>y <xref:System.Windows.Forms.TrackBar.Maximum%2A>. <xref:System.Windows.Forms.TrackBar.TickFrequency%2A> es el espaciado de los tics. <xref:System.Windows.Forms.TrackBar.Minimum%2A> y <xref:System.Windows.Forms.TrackBar.Maximum%2A> son los valores más pequeños y mayores que se pueden representar en la barra de seguimiento.  
  
 Otras dos propiedades importantes son <xref:System.Windows.Forms.TrackBar.SmallChange%2A> y <xref:System.Windows.Forms.TrackBar.LargeChange%2A>. El valor de la propiedad <xref:System.Windows.Forms.TrackBar.SmallChange%2A> es el número de posiciones que el control de posición se mueve en respuesta a la tecla de flecha izquierda o derecha presionada. El valor de la propiedad <xref:System.Windows.Forms.TrackBar.LargeChange%2A> es el número de posiciones que el control de posición se mueve en respuesta a la pulsación de la tecla RE PÁG o Av Pág, o en respuesta a los clics del mouse en la barra de seguimiento en cualquier lado del control.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.TrackBar>
- [TrackBar (control)](trackbar-control-windows-forms.md)
