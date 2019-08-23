---
title: Procedimiento Controlar interactivamente un reloj
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controlling clocks interactively [WPF]
- clocks [WPF], controlling interactively
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
ms.openlocfilehash: 2d18f395974750a6b85458f636a27f6101e7978f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951345"
---
# <a name="how-to-interactively-control-a-clock"></a>Procedimiento Controlar interactivamente un reloj
La <xref:System.Windows.Media.Animation.Clock> propiedad de <xref:System.Windows.Media.Animation.ClockController> un objeto permite iniciar, pausar, reanudar, buscar, avanzar el reloj hasta su período de relleno y detener el reloj interactivamente. Solo se puede controlar interactivamente el reloj raíz de un árbol de control de tiempo.  
  
> [!NOTE]
> Hay otras maneras de controlar interactivamente animaciones que no requieren que trabaje directamente con los relojes: también puede usar guiones gráficos. Los guiones gráficos se admiten tanto en el marcado como en el código. Para obtener un ejemplo, vea [animar una propiedad mediante un guión gráfico](how-to-animate-a-property-by-using-a-storyboard.md) o la [información general sobre animaciones](animation-overview.md).  
  
 En el ejemplo siguiente, se usan varios botones para controlar interactivamente un reloj de animación.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a>Vea también

- [Animar una propiedad utilizando un guión gráfico](how-to-animate-a-property-by-using-a-storyboard.md)
- [Información general sobre animaciones](animation-overview.md)
