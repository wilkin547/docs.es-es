---
title: Procedimiento Recibir una notificación cuando cambia el estado de un reloj
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clocks [WPF], notification of state changes
- notifications [WPF], clocks' state changes
ms.assetid: ecb10fc9-d0c2-45c3-b0a1-7b11baa733da
ms.openlocfilehash: 116647b6b7df9c012ee7d5f08abd760b7f310f71
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277113"
---
# <a name="how-to-receive-notification-when-a-clocks-state-changes"></a>Procedimiento Recibir una notificación cuando cambia el estado de un reloj
Un reloj <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> evento tiene lugar cuando su <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> deja de ser válido, por ejemplo, cuando se inicia o detiene el reloj. Puede registrarse para este evento con directamente mediante un <xref:System.Windows.Media.Animation.Clock>, o bien puede registrar con un <xref:System.Windows.Media.Animation.Timeline>.  
  
 En el ejemplo siguiente, un <xref:System.Windows.Media.Animation.Storyboard> y dos <xref:System.Windows.Media.Animation.DoubleAnimation> objetos se utilizan para animar el ancho de dos rectángulos. El <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> eventos se usan para realizar escuchas de los cambios de estado de reloj.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[timingbehaviors_snip#_graphicsmm_StateExampleMarkupWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml#_graphicsmm_stateexamplemarkupwholepage)]  
  
 [!code-csharp[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml.cs#_graphicsmm_stateeventhandlers)]
 [!code-vb[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/stateexample.xaml.vb#_graphicsmm_stateeventhandlers)]  
  
 En la siguiente ilustración muestra los distintos Estados de las animaciones se especifica como la escala de tiempo primaria (*guión gráfico*) progresa.  
  
 ![Estados de reloj para guión gráfico con dos animaciones](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-3timelines.png "graphicsmm_3timelines")  
  
 La siguiente tabla muestra las horas en que *Animation1*del <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> desencadena el evento:  
  
||||||||  
|-|-|-|-|-|-|-|  
|Tiempo (segundos)|1|10|19|21|30|39|  
|Estado|Activo|Activo|Detenido|Activo|Activo|Detenido|  
  
 La siguiente tabla muestra las horas en que *Animation2*del <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> desencadena el evento:  
  
||||||||||  
|-|-|-|-|-|-|-|-|-|  
|Tiempo (segundos)|1|9|11|19|21|29|31|39|  
|Estado|Activo|Rellenar|Activo|Detenido|Activo|Rellenar|Activo|Detenido|  
  
 Tenga en cuenta que *Animation1*del <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> evento se desencadena en 10 segundos, aunque su estado sigue siendo <xref:System.Windows.Media.Animation.ClockState.Active>. Eso es porque su estado cambia a 10 segundos, pero puede cambiar de <xref:System.Windows.Media.Animation.ClockState.Active> a <xref:System.Windows.Media.Animation.ClockState.Filling> y luego volver a <xref:System.Windows.Media.Animation.ClockState.Active> en el mismo paso.
