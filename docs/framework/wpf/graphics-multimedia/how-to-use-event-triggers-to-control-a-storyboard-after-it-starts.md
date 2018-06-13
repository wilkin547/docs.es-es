---
title: 'Cómo: Utilizar desencadenadores de eventos para controlar un guión gráfico después de su inicio'
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: c864668026c4f8bb58a4d6c4c36f96fb07445a9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561299"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a>Cómo: Utilizar desencadenadores de eventos para controlar un guión gráfico después de su inicio
Este ejemplo muestra cómo controlar un <xref:System.Windows.Media.Animation.Storyboard> después de iniciarse. Para iniciar un <xref:System.Windows.Media.Animation.Storyboard> utilizando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], utilice <xref:System.Windows.Media.Animation.BeginStoryboard>, que distribuye las animaciones a los objetos y propiedades que se animan y, a continuación, inicia el guión gráfico. Si asigna <xref:System.Windows.Media.Animation.BeginStoryboard> un nombre mediante la especificación de su <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> propiedad, permite que un guión gráfico controlable. A continuación, podrá controlar interactivamente el guión gráfico después de iniciarse.  
  
 Utilice las siguientes acciones de guión gráfico junto con <xref:System.Windows.EventTrigger> objetos que se va a controlar un guión gráfico.  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard>: Se detiene el guión gráfico.  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard>: Se reanuda un guión gráfico en pausa.  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Cambia la velocidad del guión gráfico.  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Hace avanzar un guión gráfico hasta el final de su período de relleno, si lo tiene.  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard>: Detiene el guión gráfico.  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard>: Quita el guión gráfico para liberar recursos.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza acciones de guión gráfico controlable para controlar interactivamente un guión gráfico.  
  
 **Nota:** para ver un ejemplo de control de un guión gráfico mediante código, vea [controlar un guión gráfico después de que se inicia utilizando sus métodos interactivos](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md).  
  
 [!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]  
  
 Para obtener ejemplos adicionales, consulte la [Animation Example Gallery](http://go.microsoft.com/fwlink/?LinkID=159969).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.Animation.ResumeStoryboard>  
 <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>  
 <xref:System.Windows.Media.Animation.SkipStoryboardToFill>  
 <xref:System.Windows.Media.Animation.PauseStoryboard>  
 <xref:System.Windows.Media.Animation.StopStoryboard>  
 <xref:System.Windows.Media.Animation.SeekStoryboard>  
 [Controlar un guión gráfico una vez iniciado usando métodos interactivos](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md)  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Información general sobre objetos Storyboard ](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
