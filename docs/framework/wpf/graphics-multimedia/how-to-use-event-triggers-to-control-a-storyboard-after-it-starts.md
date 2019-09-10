---
title: Procedimiento Usar desencadenadores de eventos para controlar un guión gráfico después de su inicio
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: 32591edd065a8122b84ff14102f672ccf6001d67
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855848"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a>Procedimiento Usar desencadenadores de eventos para controlar un guión gráfico después de su inicio

En este ejemplo se muestra cómo controlar <xref:System.Windows.Media.Animation.Storyboard> una después de iniciarse. Para iniciar <xref:System.Windows.Media.Animation.Storyboard> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]mediante, use <xref:System.Windows.Media.Animation.BeginStoryboard>, que distribuye las animaciones a los objetos y propiedades que se animan y, a continuación, inicia el guión gráfico. Si asigna <xref:System.Windows.Media.Animation.BeginStoryboard> un nombre mediante la especificación de su <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> propiedad, lo convierte en un guión gráfico controlable. Después, puede controlar interactivamente el guión gráfico una vez que se inicia.

Use las siguientes acciones de guion gráfico <xref:System.Windows.EventTrigger> junto con objetos para controlar un guion gráfico.

- <xref:System.Windows.Media.Animation.PauseStoryboard>: Pausa el guion gráfico.

- <xref:System.Windows.Media.Animation.ResumeStoryboard>: Reanuda un guion gráfico en pausa.

- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Cambia la velocidad del guion gráfico.

- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Hace avanzar un guión gráfico hasta el final de su período de relleno, si tiene uno.

- <xref:System.Windows.Media.Animation.StopStoryboard>: Detiene el guion gráfico.

- <xref:System.Windows.Media.Animation.RemoveStoryboard>: Quita el guión gráfico, liberando recursos.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se usan acciones de guion gráfico controlables para controlar interactivamente un guión gráfico.

> [!NOTE]
> Para ver un ejemplo de cómo controlar un guión gráfico mediante código, vea [controlar un guión gráfico después de comenzar a usar sus métodos interactivos](how-to-control-a-storyboard-after-it-starts.md).

[!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]

Para obtener más ejemplos, vea la [Galería de ejemplo de animación](https://go.microsoft.com/fwlink/?LinkID=159969).

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [Controlar un guión gráfico una vez iniciado usando métodos interactivos](how-to-control-a-storyboard-after-it-starts.md)
- [Información general sobre animaciones](animation-overview.md)
- [Información general sobre objetos Storyboard ](storyboards-overview.md)
