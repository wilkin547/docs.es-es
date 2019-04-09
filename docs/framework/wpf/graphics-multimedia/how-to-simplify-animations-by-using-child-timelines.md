---
title: Filtrar Simplificar las animaciones mediante escalas de tiempo secundarias
ms.date: 03/30/2017
helpviewer_keywords:
- simplifying animations by child timelines [WPF]
- animation [WPF], simplifying by child timelines
- child timelines [WPF]
ms.assetid: 8335d770-d13d-42bd-8dfa-63f92c0327e2
ms.openlocfilehash: 21a297208be045eea79d6f5ca6c8eac016d26345
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096399"
---
# <a name="how-to-simplify-animations-by-using-child-timelines"></a>Filtrar Simplificar las animaciones mediante escalas de tiempo secundarias
En este ejemplo se muestra cómo simplificar animaciones utilizando secundarios <xref:System.Windows.Media.Animation.ParallelTimeline> objetos. Un <xref:System.Windows.Media.Animation.Storyboard> es un tipo de <xref:System.Windows.Media.Animation.Timeline> que proporciona información de destino para las escalas de tiempo contiene. Use un <xref:System.Windows.Media.Animation.Storyboard> para proporcionar información, incluida la información de objeto y propiedad de destino de la escala de tiempo.  
  
 Para iniciar una animación, utilice uno o varios <xref:System.Windows.Media.Animation.ParallelTimeline> objetos como elementos secundarios anidados de un <xref:System.Windows.Media.Animation.Storyboard>. Estos <xref:System.Windows.Media.Animation.ParallelTimeline> objetos pueden contener otras animaciones y por lo tanto, pueden encapsular mejor las secuencias de temporización de animaciones complejas. Por ejemplo, si está animando un <xref:System.Windows.Controls.TextBlock> y varias formas en el mismo <xref:System.Windows.Media.Animation.Storyboard>, puede separar las animaciones para los <xref:System.Windows.Controls.TextBlock> y las formas y ponerlas todas en otro <xref:System.Windows.Media.Animation.ParallelTimeline>. Dado que cada <xref:System.Windows.Media.Animation.ParallelTimeline> tiene su propio <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> y todos los elementos secundarios de la <xref:System.Windows.Media.Animation.ParallelTimeline> empiezan en relación con esto <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>, se encapsula mejor la temporización.  
  
 El ejemplo siguiente anima dos partes de texto (<xref:System.Windows.Controls.TextBlock> objetos) desde dentro del mismo <xref:System.Windows.Media.Animation.Storyboard>. Un <xref:System.Windows.Media.Animation.ParallelTimeline> encapsula las animaciones de uno de los <xref:System.Windows.Controls.TextBlock> objetos.  
  
 **Nota de rendimiento:** Aunque puede anidar <xref:System.Windows.Media.Animation.Storyboard> escalas de tiempo dentro de otras, <xref:System.Windows.Media.Animation.ParallelTimeline>son más apropiadas para la anidación porque requieren menos sobrecarga. (El <xref:System.Windows.Media.Animation.Storyboard> clase hereda de la <xref:System.Windows.Media.Animation.ParallelTimeline> clase.)  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[Timelines_snip#ParallelTimelineWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Timelines_snip/CS/ParallelTimelineExample.xaml#paralleltimelinewholepage)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre animaciones](animation-overview.md)
- [Especificar HandoffBehavior entre animaciones de guión gráfico](how-to-specify-handoffbehavior-between-storyboard-animations.md)
