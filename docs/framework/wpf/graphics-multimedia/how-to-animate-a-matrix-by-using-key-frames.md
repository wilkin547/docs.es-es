---
title: 'Cómo: Animar un objeto Matrix mediante fotogramas clave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: eb596cf728f8a7cc1964963b8509f42bdd7a392a
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344914"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a><span data-ttu-id="73db5-102">Cómo: Animar un objeto Matrix mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="73db5-102">How to: Animate a Matrix by Using Key Frames</span></span>
<span data-ttu-id="73db5-103">En este ejemplo se <xref:System.Windows.Media.MatrixTransform.Matrix%2A> muestra <xref:System.Windows.Media.MatrixTransform> cómo animar la propiedad de a mediante fotogramas clave.</span><span class="sxs-lookup"><span data-stu-id="73db5-103">This example shows how to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73db5-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="73db5-104">Example</span></span>  
 <span data-ttu-id="73db5-105">En el ejemplo <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> siguiente se <xref:System.Windows.Media.MatrixTransform.Matrix%2A> utiliza <xref:System.Windows.Media.MatrixTransform>la clase para animar la propiedad de un archivo .</span><span class="sxs-lookup"><span data-stu-id="73db5-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="73db5-106">En el <xref:System.Windows.Media.MatrixTransform> ejemplo se utiliza el objeto <xref:System.Windows.Controls.Button>para transformar la apariencia y la posición de un archivo .</span><span class="sxs-lookup"><span data-stu-id="73db5-106">The example uses the <xref:System.Windows.Media.MatrixTransform> object to transform the appearance and position of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="73db5-107">Esta animación <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> utiliza la clase para crear dos fotogramas clave y hace lo siguiente con ellos:</span><span class="sxs-lookup"><span data-stu-id="73db5-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> class to create two key frames and does the following with them:</span></span>  
  
1. <span data-ttu-id="73db5-108">Anima el <xref:System.Windows.Media.Matrix> primero durante los primeros 0,2 segundos.</span><span class="sxs-lookup"><span data-stu-id="73db5-108">Animates the first <xref:System.Windows.Media.Matrix> during the first 0.2 seconds.</span></span> <span data-ttu-id="73db5-109">En el <xref:System.Windows.Media.Matrix.M11%2A> ejemplo <xref:System.Windows.Media.Matrix.M12%2A> se <xref:System.Windows.Media.Matrix>cambia el y las propiedades del archivo .</span><span class="sxs-lookup"><span data-stu-id="73db5-109">The example changes the <xref:System.Windows.Media.Matrix.M11%2A> and <xref:System.Windows.Media.Matrix.M12%2A> properties of the <xref:System.Windows.Media.Matrix>.</span></span> <span data-ttu-id="73db5-110">Este cambio hace que el botón se estire y se vuelva sesgado.</span><span class="sxs-lookup"><span data-stu-id="73db5-110">This change causes the button to stretch and become skewed.</span></span> <span data-ttu-id="73db5-111">El ejemplo también <xref:System.Windows.Media.Matrix.OffsetX%2A> <xref:System.Windows.Media.Matrix.OffsetY%2A> cambia las propiedades y para que el botón cambie de posición.</span><span class="sxs-lookup"><span data-stu-id="73db5-111">The example also changes the <xref:System.Windows.Media.Matrix.OffsetX%2A> and <xref:System.Windows.Media.Matrix.OffsetY%2A> properties so that the button changes position.</span></span>  
  
2. <span data-ttu-id="73db5-112">Anima el <xref:System.Windows.Media.Matrix> segundo a 1,0 segundos.</span><span class="sxs-lookup"><span data-stu-id="73db5-112">Animates the second <xref:System.Windows.Media.Matrix> at 1.0 seconds.</span></span> <span data-ttu-id="73db5-113">El botón se mueve a otra posición mientras el botón ya no está sesgado o estirado.</span><span class="sxs-lookup"><span data-stu-id="73db5-113">The button moves to another position while the button is no longer skewed or stretched.</span></span>  
  
3. <span data-ttu-id="73db5-114">Repite la animación indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="73db5-114">Repeats the animation indefinitely.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="73db5-115">Los fotogramas clave <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> que derivan del objeto crean saltos repentinos entre los valores, es decir, el movimiento de la animación es brusco.</span><span class="sxs-lookup"><span data-stu-id="73db5-115">Key frames that derive from the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> object create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="73db5-116">Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="73db5-116">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73db5-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="73db5-117">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [<span data-ttu-id="73db5-118">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="73db5-118">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="73db5-119">Temas de procedimientos de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="73db5-119">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
