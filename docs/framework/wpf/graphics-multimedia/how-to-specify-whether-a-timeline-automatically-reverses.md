---
title: Procedimiento Especificar si una escala de tiempo se invierte automáticamente
ms.date: 03/30/2017
helpviewer_keywords:
- AutoReverse property of timelines [WPF]
- Timelines [WPF], AutoReverse property
ms.assetid: 1648dd90-1bee-409a-ac69-ac729867f557
ms.openlocfilehash: 0fe2d337d8afa5197475e5b9ee40950226596e8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62024669"
---
# <a name="how-to-specify-whether-a-timeline-automatically-reverses"></a>Procedimiento Especificar si una escala de tiempo se invierte automáticamente
Una escala de tiempo <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> propiedad determina si reproduce en orden inverso después de completar una iteración de avance. El ejemplo siguiente muestra varias animaciones con duración idéntico y los valores de destino, pero con diferentes <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> configuración. Para demostrar cómo el <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> propiedad se comporta con diferentes <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> , algunas animaciones están configurados para repetir. La última animación se muestra cómo el <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> propiedad funciona en escalas de tiempo anidadas.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
