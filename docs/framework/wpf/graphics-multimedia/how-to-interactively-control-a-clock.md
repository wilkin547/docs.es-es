---
title: "Cómo: Controlar interactivamente un reloj"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controlling clocks interactively [WPF]
- clocks [WPF], controlling interactively
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d24a5154607bf535cbf995705332092bb86ca02e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-interactively-control-a-clock"></a>Cómo: Controlar interactivamente un reloj
A <xref:System.Windows.Media.Animation.Clock> del objeto <xref:System.Windows.Media.Animation.ClockController> propiedad le permite interactivamente iniciar, pausar, reanudar, buscar, avanzar el reloj hasta su período de relleno y detener el reloj. Solo el reloj de raíz de un árbol de control de tiempo puede controlarse de forma interactiva.  
  
> [!NOTE]
>  Hay otras maneras de controlar interactivamente las animaciones que no requieran que trabajar directamente con relojes: también puede utilizar guiones gráficos. Guiones gráficos se admiten en código y marcado. Para obtener un ejemplo, vea [animar una propiedad mediante un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) o [información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 En el ejemplo siguiente, se utilizan varios botones para controlar interactivamente un reloj de animación.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a>Vea también  
 [Animar una propiedad utilizando un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
