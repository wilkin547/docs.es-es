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
# <a name="how-to-simplify-animations-by-using-child-timelines"></a><span data-ttu-id="ebbbc-102">Cómo: Simplificar animaciones utilizando objetos Timeline secundarios</span><span class="sxs-lookup"><span data-stu-id="ebbbc-102">How to: Simplify Animations by Using Child Timelines</span></span>
<span data-ttu-id="ebbbc-103">Este ejemplo muestra cómo simplificar animaciones utilizando secundarios <xref:System.Windows.Media.Animation.ParallelTimeline> objetos.</span><span class="sxs-lookup"><span data-stu-id="ebbbc-103">This example shows how to simplify animations by using child <xref:System.Windows.Media.Animation.ParallelTimeline> objects.</span></span> <span data-ttu-id="ebbbc-104">A <xref:System.Windows.Media.Animation.Storyboard> es un tipo de <xref:System.Windows.Media.Animation.Timeline> que proporciona información de destino para las escalas de tiempo contiene.</span><span class="sxs-lookup"><span data-stu-id="ebbbc-104">A <xref:System.Windows.Media.Animation.Storyboard> is a type of <xref:System.Windows.Media.Animation.Timeline> that provides targeting information for the timelines it contains.</span></span> <span data-ttu-id="ebbbc-105">Use un <xref:System.Windows.Media.Animation.Storyboard> para proporcionar información, incluida la información de objeto y propiedad de destino de la escala de tiempo.</span><span class="sxs-lookup"><span data-stu-id="ebbbc-105">Use a <xref:System.Windows.Media.Animation.Storyboard> to provide timeline targeting information, including object and property information.</span></span>  
  
 <span data-ttu-id="ebbbc-106">Para iniciar una animación, utilice uno o varios <xref:System.Windows.Media.Animation.ParallelTimeline> objetos como elementos secundarios anidados de un <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="ebbbc-106">To begin an animation, use one or more <xref:System.Windows.Media.Animation.ParallelTimeline> objects as nested child elements of a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="ebbbc-107">Estos <xref:System.Windows.Media.Animation.ParallelTimeline> objetos pueden contener otras animaciones y por lo tanto, pueden encapsular mejor las secuencias de control de tiempo de animaciones complejas.</span><span class="sxs-lookup"><span data-stu-id="ebbbc-107">These <xref:System.Windows.Media.Animation.ParallelTimeline> objects can contain other animations and therefore, can better encapsulate the timing sequences in complex animations.</span></span> <span data-ttu-id="ebbbc-108">Por ejemplo, si va a animar un <xref:System.Windows.Controls.TextBlock> y varias formas en el mismo <xref:System.Windows.Media.Animation.Storyboard>, puede separar las animaciones para el <xref:System.Windows.Controls.TextBlock> y las formas, colocar cada uno en otro <xref:System.Windows.Media.Animation.ParallelTimeline>.</span><span class="sxs-lookup"><span data-stu-id="ebbbc-108">For example, if you are animating a <xref:System.Windows.Controls.TextBlock> and several shapes in the same <xref:System.Windows.Media.Animation.Storyboard>, you can separate the animations for the <xref:System.Windows.Controls.TextBlock> and the shapes, putting each into a separate <xref:System.Windows.Media.Animation.ParallelTimeline>.</span></span> <span data-ttu-id="ebbbc-109">Dado que cada <xref:System.Windows.Media.Animation.ParallelTimeline> tiene su propio <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> y todos los elementos secundarios de la <xref:System.Windows.Media.Animation.ParallelTimeline> comenzar en relación con este <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>, mejor se encapsula el control de tiempo.</span><span class="sxs-lookup"><span data-stu-id="ebbbc-109">Because each <xref:System.Windows.Media.Animation.ParallelTimeline> has its own <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> and all child elements of the <xref:System.Windows.Media.Animation.ParallelTimeline> begin relative to this <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>, timing is better encapsulated.</span></span>  
  
 <span data-ttu-id="ebbbc-110">En el ejemplo siguiente se anima dos fragmentos de texto (<xref:System.Windows.Controls.TextBlock> objetos) desde dentro del mismo <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="ebbbc-110">The following example animates two pieces of text (<xref:System.Windows.Controls.TextBlock> objects) from within the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="ebbbc-111">A <xref:System.Windows.Media.Animation.ParallelTimeline> encapsula las animaciones de uno de los <xref:System.Windows.Controls.TextBlock> objetos.</span><span class="sxs-lookup"><span data-stu-id="ebbbc-111">A <xref:System.Windows.Media.Animation.ParallelTimeline> encapsulates the animations of one of the <xref:System.Windows.Controls.TextBlock> objects.</span></span>  
  
 <span data-ttu-id="ebbbc-112">**Nota de rendimiento:** aunque se pueden anidar <xref:System.Windows.Media.Animation.Storyboard> dentro de otras, las escalas de tiempo <xref:System.Windows.Media.Animation.ParallelTimeline>s son más adecuados para anidar porque requieren menos sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="ebbbc-112">**Performance Note:** Although you can nest <xref:System.Windows.Media.Animation.Storyboard> timelines inside each other, <xref:System.Windows.Media.Animation.ParallelTimeline>s are more suitable for nesting because they require less overhead.</span></span> <span data-ttu-id="ebbbc-113">(El <xref:System.Windows.Media.Animation.Storyboard> clase hereda de la <xref:System.Windows.Media.Animation.ParallelTimeline> clase.)</span><span class="sxs-lookup"><span data-stu-id="ebbbc-113">(The <xref:System.Windows.Media.Animation.Storyboard> class inherits from the <xref:System.Windows.Media.Animation.ParallelTimeline> class.)</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebbbc-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ebbbc-114">Example</span></span>  
 [!code-xaml[Timelines_snip#ParallelTimelineWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Timelines_snip/CS/ParallelTimelineExample.xaml#paralleltimelinewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="ebbbc-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ebbbc-115">See Also</span></span>  
 [<span data-ttu-id="ebbbc-116">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="ebbbc-116">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="ebbbc-117">Especificar HandoffBehavior entre animaciones de guión gráfico</span><span class="sxs-lookup"><span data-stu-id="ebbbc-117">Specify HandoffBehavior Between Storyboard Animations</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-handoffbehavior-between-storyboard-animations.md)
