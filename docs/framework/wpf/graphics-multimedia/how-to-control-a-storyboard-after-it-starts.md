---
title: Procedimiento Controlar un guión gráfico después de su inicio
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
ms.openlocfilehash: de30cfdb49df721cb4d6845dc67464e8a5b61f93
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855867"
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a>Procedimiento Controlar un guión gráfico después de su inicio

En este ejemplo se muestra cómo usar el código para <xref:System.Windows.Media.Animation.Storyboard> controlar una después de haberse iniciado. Para controlar un guion gráfico [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]en, <xref:System.Windows.Trigger> use <xref:System.Windows.TriggerAction> los objetos y; para obtener un ejemplo, vea [usar desencadenadores de eventos para controlar un guión gráfico después de su inicio](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).

Para iniciar un guion gráfico, use su <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> método, que distribuye las animaciones del guión gráfico a las propiedades que animan e inicia el guión gráfico.

Para que se pueda controlar un guión gráfico, use <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> el método y especifique **true** como el segundo parámetro. Después, puede usar los métodos interactivos del guión gráfico para pausar, reanudar, buscar, detener, acelerar o ralentizar el guión gráfico, o bien avanzar hasta su período de relleno. A continuación se muestra una lista de los métodos interactivos del guión gráfico:

- <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Pausa el guion gráfico.

- <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Reanuda un guion gráfico en pausa.

- <xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Establece la velocidad interactiva del guión gráfico.

- <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Busca el guion gráfico en la ubicación especificada.

- <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Busca el guión gráfico en la ubicación especificada. A diferencia del <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> método, esta operación se procesa antes del siguiente paso.

- <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Hace avanzar el guión gráfico hasta su período de relleno, si tiene uno.

- <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Detiene el guion gráfico.

En el ejemplo siguiente, se usan varios métodos de guion gráfico para controlar interactivamente un guión gráfico.

> [!NOTE]
> Para ver un ejemplo de cómo controlar un guión gráfico mediante desencadenadores con, consulte [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [usar desencadenadores de eventos para controlar un guión gráfico después de su inicio](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).

## <a name="example"></a>Ejemplo

[!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
[!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]

## <a name="see-also"></a>Vea también

- [Utilizar desencadenadores de eventos para controlar un guión gráfico después de su inicio](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
