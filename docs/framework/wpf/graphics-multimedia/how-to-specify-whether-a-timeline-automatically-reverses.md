---
title: "Cómo: Especificar si una escala de tiempo se invierte automáticamente"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- AutoReverse property of timelines [WPF]
- Timelines [WPF], AutoReverse property
ms.assetid: 1648dd90-1bee-409a-ac69-ac729867f557
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2abce54905f0bb06bf983c065e064ce2dfeba932
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-specify-whether-a-timeline-automatically-reverses"></a>Cómo: Especificar si una escala de tiempo se invierte automáticamente
Una escala de tiempo <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> propiedad determina si reproduce en orden inverso después de completar una iteración de avance. El ejemplo siguiente muestra varias animaciones con idéntica duración y valores de destino, pero con diferentes <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> configuración. Para demostrar cómo <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> propiedad se comporta con diferentes <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> , algunas animaciones están configurados para repetir. La última animación se muestra cómo el <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> propiedad funciona en escalas de tiempo anidadas.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
