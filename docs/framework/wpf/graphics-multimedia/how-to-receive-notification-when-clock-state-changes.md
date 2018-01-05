---
title: "Cómo: recibir una notificación cuando un reloj de &#39; s cambios de estado"
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
- clocks [WPF], notification of state changes
- notifications [WPF], clocks' state changes
ms.assetid: ecb10fc9-d0c2-45c3-b0a1-7b11baa733da
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 396e2c51894ad5ed11f8953bceb1bd36899cfc62
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-receive-notification-when-a-clock39s-state-changes"></a>Cómo: recibir una notificación cuando un reloj de &#39; s cambios de estado
Un reloj <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> evento tiene lugar cuando su <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> deja de ser válido, por ejemplo, cuando se inicia o detiene el reloj. Puede registrarse para este evento con directamente mediante un <xref:System.Windows.Media.Animation.Clock>, o puede registrar con un <xref:System.Windows.Media.Animation.Timeline>.  
  
 En el ejemplo siguiente, un <xref:System.Windows.Media.Animation.Storyboard> y dos <xref:System.Windows.Media.Animation.DoubleAnimation> objetos se usan para animar el ancho de dos rectángulos. El <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> eventos se usan para realizar escuchas de los cambios de estado de reloj.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[timingbehaviors_snip#_graphicsmm_StateExampleMarkupWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml#_graphicsmm_stateexamplemarkupwholepage)]  
  
 [!code-csharp[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml.cs#_graphicsmm_stateeventhandlers)]
 [!code-vb[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/stateexample.xaml.vb#_graphicsmm_stateeventhandlers)]  
  
 En la siguiente ilustración muestra los distintos Estados en las animaciones se especifica como la escala de tiempo primaria (*guión gráfico*) progresa.  
  
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
  
 Tenga en cuenta que *Animation1*del <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> evento se desencadena en 10 segundos, aunque su estado sigue siendo <xref:System.Windows.Media.Animation.ClockState.Active>. Eso es porque su estado cambia a 10 segundos, pero cambió de <xref:System.Windows.Media.Animation.ClockState.Active> a <xref:System.Windows.Media.Animation.ClockState.Filling> y, a continuación, de nuevo a <xref:System.Windows.Media.Animation.ClockState.Active> en el mismo paso.
