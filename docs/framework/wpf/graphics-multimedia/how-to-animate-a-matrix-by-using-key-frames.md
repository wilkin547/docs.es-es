---
title: Procedimiento Animar un objeto Matrix mediante fotogramas clave
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: 6aa3e27cdfda7597c9b6acbf2980a2774f2b667b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963023"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a><span data-ttu-id="4cf10-102">Procedimiento Animar un objeto Matrix mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="4cf10-102">How to: Animate a Matrix by Using Key Frames</span></span>
<span data-ttu-id="4cf10-103">En este ejemplo se muestra cómo animar la <xref:System.Windows.Media.MatrixTransform.Matrix%2A> propiedad de una <xref:System.Windows.Media.MatrixTransform> mediante fotogramas clave.</span><span class="sxs-lookup"><span data-stu-id="4cf10-103">This example shows how to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cf10-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4cf10-104">Example</span></span>  
 <span data-ttu-id="4cf10-105">En el ejemplo siguiente se <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> usa la clase para <xref:System.Windows.Media.MatrixTransform.Matrix%2A> animar la <xref:System.Windows.Media.MatrixTransform>propiedad de un.</span><span class="sxs-lookup"><span data-stu-id="4cf10-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="4cf10-106">En el ejemplo se <xref:System.Windows.Media.MatrixTransform> usa el objeto para transformar la apariencia y la <xref:System.Windows.Controls.Button>posición de.</span><span class="sxs-lookup"><span data-stu-id="4cf10-106">The example uses the <xref:System.Windows.Media.MatrixTransform> object to transform the appearance and position of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="4cf10-107">Esta animación usa la <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> clase para crear dos fotogramas clave y hace lo siguiente con ellos:</span><span class="sxs-lookup"><span data-stu-id="4cf10-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> class to create two key frames and does the following with them:</span></span>  
  
1. <span data-ttu-id="4cf10-108">Anima la primera <xref:System.Windows.Media.Matrix> durante los primeros 0,2 segundos.</span><span class="sxs-lookup"><span data-stu-id="4cf10-108">Animates the first <xref:System.Windows.Media.Matrix> during the first 0.2 seconds.</span></span> <span data-ttu-id="4cf10-109">En el ejemplo se <xref:System.Windows.Media.Matrix.M11%2A> cambian <xref:System.Windows.Media.Matrix.M12%2A> las propiedades y <xref:System.Windows.Media.Matrix>de.</span><span class="sxs-lookup"><span data-stu-id="4cf10-109">The example changes the <xref:System.Windows.Media.Matrix.M11%2A> and <xref:System.Windows.Media.Matrix.M12%2A> properties of the <xref:System.Windows.Media.Matrix>.</span></span> <span data-ttu-id="4cf10-110">Este cambio hace que el botón se estire y se convierta en sesgado.</span><span class="sxs-lookup"><span data-stu-id="4cf10-110">This change causes the button to stretch and become skewed.</span></span> <span data-ttu-id="4cf10-111">En el ejemplo también se <xref:System.Windows.Media.Matrix.OffsetX%2A> cambian <xref:System.Windows.Media.Matrix.OffsetY%2A> las propiedades y para que el botón cambie de posición.</span><span class="sxs-lookup"><span data-stu-id="4cf10-111">The example also changes the <xref:System.Windows.Media.Matrix.OffsetX%2A> and <xref:System.Windows.Media.Matrix.OffsetY%2A> properties so that the button changes position.</span></span>  
  
2. <span data-ttu-id="4cf10-112">Anima el segundo <xref:System.Windows.Media.Matrix> a 1,0 segundos.</span><span class="sxs-lookup"><span data-stu-id="4cf10-112">Animates the second <xref:System.Windows.Media.Matrix> at 1.0 seconds.</span></span> <span data-ttu-id="4cf10-113">El botón se mueve a otra posición mientras el botón deja de sesgarse o ajustarse.</span><span class="sxs-lookup"><span data-stu-id="4cf10-113">The button moves to another position while the button is no longer skewed or stretched.</span></span>  
  
3. <span data-ttu-id="4cf10-114">Repite la animación indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="4cf10-114">Repeats the animation indefinitely.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4cf10-115">Los fotogramas clave que <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> se derivan del objeto crean saltos súbitos entre los valores, es decir, el movimiento de la animación es entrecortado.</span><span class="sxs-lookup"><span data-stu-id="4cf10-115">Key frames that derive from the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> object create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="4cf10-116">Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="4cf10-116">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cf10-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="4cf10-117">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [<span data-ttu-id="4cf10-118">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="4cf10-118">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="4cf10-119">Temas de procedimientos de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="4cf10-119">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
