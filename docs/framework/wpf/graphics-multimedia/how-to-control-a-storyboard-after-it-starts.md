---
title: Procedimiento Controlar un guión gráfico después de iniciarse
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
ms.openlocfilehash: 2fd9f34cdd6aac56ee5a29d972f18979292c69e0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54570153"
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a>Procedimiento Controlar un guión gráfico después de iniciarse
En este ejemplo se muestra cómo usar código para controlar un <xref:System.Windows.Media.Animation.Storyboard> después de haberse iniciado. Para controlar un guión gráfico en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], utilice <xref:System.Windows.Trigger> y <xref:System.Windows.TriggerAction> objetos; por ejemplo, vea [usar desencadenadores de eventos para controlar un guión gráfico después de su inicio](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).  
  
 Para iniciar un guión gráfico, utilice su <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> método, que distribuye las animaciones de guión gráfico a las propiedades que se animan y se inicia el guión gráfico.  
  
 Para poder controlar un guión gráfico, usa el <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> método y especifique **true** como segundo parámetro. A continuación, puede usar los métodos interactivos del guión gráfico para pausar, reanudar, buscar, detener, acelerar el tiempo de espera, o ralentizar el guión gráfico o hacer que avance hasta su período de relleno. La siguiente es una lista de los métodos interactivos del guión gráfico:  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Pausa el guión gráfico.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Reanuda un guión gráfico en pausa.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Establece la velocidad interactiva del guión gráfico.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Busca el guión gráfico de la ubicación especificada.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Busca en el guión gráfico en la ubicación especificada. A diferencia de la <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> método, esta operación se procesa antes del paso siguiente.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Hace avanzar el guión gráfico a su período de relleno, si lo tiene.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Detiene el guión gráfico.  
  
 En el ejemplo siguiente, se usan varios métodos de guión gráfico para controlar interactivamente un guión gráfico.  
  
 **Nota:** Para ver un ejemplo de controlar un guión gráfico mediante desencadenadores con [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], consulte [utilizar desencadenadores de eventos para controlar un guión gráfico después de su inicio](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
 [!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]  
  
## <a name="see-also"></a>Vea también
- [Utilizar desencadenadores de eventos para controlar un guión gráfico después de su inicio](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
