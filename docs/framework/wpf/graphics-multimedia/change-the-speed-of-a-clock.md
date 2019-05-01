---
title: Procedimiento Cambiar la velocidad de un reloj sin cambiar la velocidad de su escala de tiempo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- speed of Clock [WPF], changing
- clocks [WPF], changing speed of
ms.assetid: 72f36dd0-f085-445d-8589-19a83fe74f5e
ms.openlocfilehash: 19e6874b9b472cb4a5f716677f99af03f2b73b10
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010194"
---
# <a name="how-to-change-the-speed-of-a-clock-without-changing-the-speed-of-its-timeline"></a>Procedimiento Cambiar la velocidad de un reloj sin cambiar la velocidad de su escala de tiempo
Un <xref:System.Windows.Media.Animation.ClockController> del objeto <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> propiedad le permite cambiar la velocidad de un <xref:System.Windows.Media.Animation.Clock> sin alterar el <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> el reloj de <xref:System.Windows.Media.Animation.Timeline>. En el ejemplo siguiente, un <xref:System.Windows.Media.Animation.ClockController> se usa para modificar de forma interactiva el <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> de un reloj. El <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated> eventos y el reloj <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> propiedad se usa para mostrar la velocidad del reloj actual global cada vez que su interactivo <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> se cambia.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerSpeedRatioExample.cs#graphicsmmclockcontrollerspeedratioexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerspeedratioexample.vb#graphicsmmclockcontrollerspeedratioexample)]
