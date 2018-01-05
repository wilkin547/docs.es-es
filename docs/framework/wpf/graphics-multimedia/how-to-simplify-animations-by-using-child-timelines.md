---
title: "Cómo: Simplificar animaciones utilizando objetos Timeline secundarios"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- simplifying animations by child timelines [WPF]
- animation [WPF], simplifying by child timelines
- child timelines [WPF]
ms.assetid: 8335d770-d13d-42bd-8dfa-63f92c0327e2
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0d3b8f1ca1dbf7ba5452acffc62fdf0b655c9c12
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-simplify-animations-by-using-child-timelines"></a>Cómo: Simplificar animaciones utilizando objetos Timeline secundarios
Este ejemplo muestra cómo simplificar animaciones utilizando secundarios <xref:System.Windows.Media.Animation.ParallelTimeline> objetos. A <xref:System.Windows.Media.Animation.Storyboard> es un tipo de <xref:System.Windows.Media.Animation.Timeline> que proporciona información de destino para las escalas de tiempo contiene. Use un <xref:System.Windows.Media.Animation.Storyboard> para proporcionar información, incluida la información de objeto y propiedad de destino de la escala de tiempo.  
  
 Para iniciar una animación, utilice uno o varios <xref:System.Windows.Media.Animation.ParallelTimeline> objetos como elementos secundarios anidados de un <xref:System.Windows.Media.Animation.Storyboard>. Estos <xref:System.Windows.Media.Animation.ParallelTimeline> objetos pueden contener otras animaciones y por lo tanto, pueden encapsular mejor las secuencias de control de tiempo de animaciones complejas. Por ejemplo, si va a animar un <xref:System.Windows.Controls.TextBlock> y varias formas en el mismo <xref:System.Windows.Media.Animation.Storyboard>, puede separar las animaciones para el <xref:System.Windows.Controls.TextBlock> y las formas, colocar cada uno en otro <xref:System.Windows.Media.Animation.ParallelTimeline>. Dado que cada <xref:System.Windows.Media.Animation.ParallelTimeline> tiene su propio <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> y todos los elementos secundarios de la <xref:System.Windows.Media.Animation.ParallelTimeline> comenzar en relación con este <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>, mejor se encapsula el control de tiempo.  
  
 En el ejemplo siguiente se anima dos fragmentos de texto (<xref:System.Windows.Controls.TextBlock> objetos) desde dentro del mismo <xref:System.Windows.Media.Animation.Storyboard>. A <xref:System.Windows.Media.Animation.ParallelTimeline> encapsula las animaciones de uno de los <xref:System.Windows.Controls.TextBlock> objetos.  
  
 **Nota de rendimiento:** aunque se pueden anidar <xref:System.Windows.Media.Animation.Storyboard> dentro de otras, las escalas de tiempo <xref:System.Windows.Media.Animation.ParallelTimeline>s son más adecuados para anidar porque requieren menos sobrecarga. (El <xref:System.Windows.Media.Animation.Storyboard> clase hereda de la <xref:System.Windows.Media.Animation.ParallelTimeline> clase.)  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[Timelines_snip#ParallelTimelineWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Timelines_snip/CS/ParallelTimelineExample.xaml#paralleltimelinewholepage)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Especificar HandoffBehavior entre animaciones de guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-handoffbehavior-between-storyboard-animations.md)
