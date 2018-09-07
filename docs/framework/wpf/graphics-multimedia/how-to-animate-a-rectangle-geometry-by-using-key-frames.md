---
title: 'Cómo: Animar la geometría de un rectángulo mediante fotogramas clave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
ms.openlocfilehash: 9b4a620ea58026c3be1b09d01a595e965e4c2b45
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44078530"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a><span data-ttu-id="fb055-102">Cómo: Animar la geometría de un rectángulo mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="fb055-102">How to: Animate a Rectangle Geometry by Using Key Frames</span></span>
<span data-ttu-id="fb055-103">En este ejemplo se muestra cómo animar la <xref:System.Windows.Media.RectangleGeometry.Rect%2A> propiedad de un <xref:System.Windows.Media.RectangleGeometry> mediante fotogramas clave.</span><span class="sxs-lookup"><span data-stu-id="fb055-103">This example shows how to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb055-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fb055-104">Example</span></span>  
 <span data-ttu-id="fb055-105">En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> clase se va a animar el <xref:System.Windows.Media.RectangleGeometry.Rect%2A> propiedad de un <xref:System.Windows.Media.RectangleGeometry>.</span><span class="sxs-lookup"><span data-stu-id="fb055-105">The following example uses the <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry>.</span></span> <span data-ttu-id="fb055-106">Esta animación utiliza tres fotogramas clave de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="fb055-106">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="fb055-107">Durante los primeros dos segundos, utiliza una instancia de la <xref:System.Windows.Media.Animation.LinearRectKeyFrame> clase para animar un cambio gradual en la posición, ancho y alto de un rectángulo.</span><span class="sxs-lookup"><span data-stu-id="fb055-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearRectKeyFrame> class to animate a gradual change in the position, width, and height of a rectangle.</span></span> <span data-ttu-id="fb055-108">Los fotogramas clave lineales como <xref:System.Windows.Media.Animation.LinearRectKeyFrame> crean una transición lineal suave entre valores.</span><span class="sxs-lookup"><span data-stu-id="fb055-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearRectKeyFrame> create a smooth linear transition between values.</span></span>  
  
2.  <span data-ttu-id="fb055-109">Durante el fin de la siguiente medio segundo, utiliza una instancia de la <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> clase para reducir de repente el alto del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="fb055-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> class to suddenly decrease the height of the rectangle.</span></span> <span data-ttu-id="fb055-110">Los fotogramas clave discretos como <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> crean cambios súbitos entre los valores, es decir, la reducción del alto se produce de forma rápida y brusca.</span><span class="sxs-lookup"><span data-stu-id="fb055-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> create sudden changes between values, that is, the decrease in height occurs quickly and is not subtle.</span></span>  
  
3.  <span data-ttu-id="fb055-111">Durante los dos últimos segundos, utiliza una instancia de la <xref:System.Windows.Media.Animation.SplineRectKeyFrame> clase para cambiar el rectángulo a su tamaño y posición originales.</span><span class="sxs-lookup"><span data-stu-id="fb055-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame> class to change the rectangle back to its original size and position.</span></span> <span data-ttu-id="fb055-112">Los fotogramas clave spline como <xref:System.Windows.Media.Animation.SplineRectKeyFrame> crean una transición variable entre los valores según los valores de la <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="fb055-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineRectKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="fb055-113">En este ejemplo, el cambio comienza despacio y se acelera exponencialmente hacia el final del segmento temporal.</span><span class="sxs-lookup"><span data-stu-id="fb055-113">In this example, the change begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="fb055-114">Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="fb055-114">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb055-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb055-115">See Also</span></span>  
 <xref:System.Windows.Media.RectangleGeometry>  
 <xref:System.Windows.Media.RectangleGeometry.Rect%2A>  
 <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>  
 [<span data-ttu-id="fb055-116">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="fb055-116">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="fb055-117">Temas de procedimientos de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="fb055-117">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
