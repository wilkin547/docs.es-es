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
ms.openlocfilehash: bcc9e7f198b8a20ffe13daf6508fb8a735937652
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344680"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a><span data-ttu-id="3abf8-102">Cómo: Animar la geometría de un rectángulo mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="3abf8-102">How to: Animate a Rectangle Geometry by Using Key Frames</span></span>
<span data-ttu-id="3abf8-103">En este ejemplo se <xref:System.Windows.Media.RectangleGeometry.Rect%2A> muestra <xref:System.Windows.Media.RectangleGeometry> cómo animar la propiedad de a mediante fotogramas clave.</span><span class="sxs-lookup"><span data-stu-id="3abf8-103">This example shows how to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3abf8-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3abf8-104">Example</span></span>  
 <span data-ttu-id="3abf8-105">En el ejemplo <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> siguiente se <xref:System.Windows.Media.RectangleGeometry.Rect%2A> utiliza <xref:System.Windows.Media.RectangleGeometry>la clase para animar la propiedad de un archivo .</span><span class="sxs-lookup"><span data-stu-id="3abf8-105">The following example uses the <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry>.</span></span> <span data-ttu-id="3abf8-106">Esta animación utiliza tres fotogramas clave de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="3abf8-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="3abf8-107">Durante los dos primeros segundos, <xref:System.Windows.Media.Animation.LinearRectKeyFrame> utiliza una instancia de la clase para animar un cambio gradual en la posición, anchura y altura de un rectángulo.</span><span class="sxs-lookup"><span data-stu-id="3abf8-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearRectKeyFrame> class to animate a gradual change in the position, width, and height of a rectangle.</span></span> <span data-ttu-id="3abf8-108">Los fotogramas <xref:System.Windows.Media.Animation.LinearRectKeyFrame> clave lineales como crean una transición lineal suave entre los valores.</span><span class="sxs-lookup"><span data-stu-id="3abf8-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearRectKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="3abf8-109">Durante el final del siguiente medio segundo, <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> utiliza una instancia de la clase para disminuir repentinamente la altura del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="3abf8-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> class to suddenly decrease the height of the rectangle.</span></span> <span data-ttu-id="3abf8-110">Los fotogramas <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> clave discretos como crear cambios repentinos entre los valores, es decir, la disminución de la altura se produce rápidamente y no es sutil.</span><span class="sxs-lookup"><span data-stu-id="3abf8-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> create sudden changes between values, that is, the decrease in height occurs quickly and is not subtle.</span></span>  
  
3. <span data-ttu-id="3abf8-111">Durante los dos segundos finales, utiliza una instancia de la <xref:System.Windows.Media.Animation.SplineRectKeyFrame> clase para cambiar el rectángulo a su tamaño y posición originales.</span><span class="sxs-lookup"><span data-stu-id="3abf8-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame> class to change the rectangle back to its original size and position.</span></span> <span data-ttu-id="3abf8-112">Los fotogramas <xref:System.Windows.Media.Animation.SplineRectKeyFrame> clave de spline como crean una <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> transición variable entre los valores según los valores de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="3abf8-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineRectKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="3abf8-113">En este ejemplo, el cambio comienza despacio y se acelera exponencialmente hacia el final del segmento temporal.</span><span class="sxs-lookup"><span data-stu-id="3abf8-113">In this example, the change begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="3abf8-114">Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="3abf8-114">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3abf8-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="3abf8-115">See also</span></span>

- <xref:System.Windows.Media.RectangleGeometry>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>
- [<span data-ttu-id="3abf8-116">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="3abf8-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="3abf8-117">Temas de procedimientos de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="3abf8-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
