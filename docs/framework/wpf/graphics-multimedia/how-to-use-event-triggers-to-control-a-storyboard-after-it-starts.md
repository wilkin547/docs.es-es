---
title: 'Cómo: Utilizar desencadenadores de eventos para controlar un guión gráfico después de su inicio'
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: 518f5d7ea0b5dc00677489f1383814563c565145
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186702"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a>Cómo: Utilizar desencadenadores de eventos para controlar un guión gráfico después de su inicio

En este ejemplo se <xref:System.Windows.Media.Animation.Storyboard> muestra cómo controlar una después de que se inicia. Para iniciar <xref:System.Windows.Media.Animation.Storyboard> un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]mediante <xref:System.Windows.Media.Animation.BeginStoryboard>, use , que distribuye las animaciones a los objetos y propiedades que animan y, a continuación, inicia el guión gráfico. Si asigna <xref:System.Windows.Media.Animation.BeginStoryboard> un nombre especificando su <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> propiedad, lo convierte en un guión gráfico controlable. A continuación, puede controlar interactivamente el guión gráfico después de que se inicie.

Utilice las siguientes acciones <xref:System.Windows.EventTrigger> de guión gráfico junto con objetos para controlar un guión gráfico.

- <xref:System.Windows.Media.Animation.PauseStoryboard>: Pausa el guión gráfico.

- <xref:System.Windows.Media.Animation.ResumeStoryboard>: reanuda un guión gráfico en pausa.

- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Cambia la velocidad del guión gráfico.

- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: avanza un guión gráfico hasta el final de su período de relleno, si tiene uno.

- <xref:System.Windows.Media.Animation.StopStoryboard>: detiene el guión gráfico.

- <xref:System.Windows.Media.Animation.RemoveStoryboard>: elimina el guión gráfico, liberando recursos.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se usan acciones de guión gráfico controlables para controlar interactivamente un guión gráfico.

> [!NOTE]
> Para ver un ejemplo de control de un guión gráfico mediante código, vea [Controlar un guión gráfico después de que comience a usar sus métodos interactivos](how-to-control-a-storyboard-after-it-starts.md).

[!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]

Para obtener ejemplos adicionales, consulte la Galería de ejemplos de [animación](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [Controlar un guión gráfico una vez iniciado mediante métodos interactivos](how-to-control-a-storyboard-after-it-starts.md)
- [Información general sobre animaciones](animation-overview.md)
- [Información general sobre objetos Storyboard ](storyboards-overview.md)
