---
title: 'Cómo: Controlar un guión gráfico una vez iniciado'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
ms.openlocfilehash: 2407de5029007748de691a3020078b1241b02fd4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561467"
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a>Cómo: Controlar un guión gráfico una vez iniciado
Este ejemplo muestra cómo utilizar código para controlar un <xref:System.Windows.Media.Animation.Storyboard> después de haberse iniciado. Para controlar un guión gráfico en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Trigger> y <xref:System.Windows.TriggerAction> objetos; para obtener un ejemplo, vea [usar desencadenadores de eventos para controlar un guión gráfico después de que se inicia](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).  
  
 Para iniciar un guión gráfico, utilice su <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> método, que distribuye las animaciones del guión gráfico para las propiedades que se animan y se inicia el guión gráfico.  
  
 Para poder controlar un guión gráfico, use la <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> método y especifique **true** como segundo parámetro. A continuación, puede usar métodos interactivos del guión gráfico para pausar, reanudar, buscar, detener, acelerar el tiempo de espera, o ralentizar el guión gráfico o avanzar a su período de relleno. La siguiente es una lista de métodos interactivos del guión gráfico:  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Se detiene el guión gráfico.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Se reanuda un guión gráfico en pausa.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Establece la velocidad interactiva del guión gráfico.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Busca el guión gráfico la ubicación especificada.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Busca en el guión gráfico a la ubicación especificada. A diferencia de la <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> (método), esta operación se procesa antes del paso siguiente.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Hace avanzar el guión gráfico hasta su período de relleno, si lo tiene.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Detiene el guión gráfico.  
  
 En el ejemplo siguiente, se usan varios métodos de guión gráfico para controlar interactivamente un guión gráfico.  
  
 **Nota:** para ver un ejemplo de control de un guión gráfico mediante desencadenadores con [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], consulte [utilizar desencadenadores de eventos para controlar un guión gráfico después de que se inicia](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
 [!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]  
  
## <a name="see-also"></a>Vea también  
 [Utilizar desencadenadores de eventos para controlar un guión gráfico después de su inicio](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
