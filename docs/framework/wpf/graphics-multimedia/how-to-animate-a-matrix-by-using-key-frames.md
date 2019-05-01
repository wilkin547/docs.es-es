---
title: Procedimiento Animar un objeto Matrix mediante fotogramas clave
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: ff5320fa5b4441ae3e0f414b274ab9118b77ec50
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62020249"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a><span data-ttu-id="1c61a-102">Procedimiento Animar un objeto Matrix mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="1c61a-102">How to: Animate a Matrix by Using Key Frames</span></span>
<span data-ttu-id="1c61a-103">En este ejemplo se muestra cómo animar la <xref:System.Windows.Media.MatrixTransform.Matrix%2A> propiedad de un <xref:System.Windows.Media.MatrixTransform> mediante fotogramas clave.</span><span class="sxs-lookup"><span data-stu-id="1c61a-103">This example shows how to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c61a-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1c61a-104">Example</span></span>  
 <span data-ttu-id="1c61a-105">En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> clase se va a animar el <xref:System.Windows.Media.MatrixTransform.Matrix%2A> propiedad de un <xref:System.Windows.Media.MatrixTransform>.</span><span class="sxs-lookup"><span data-stu-id="1c61a-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="1c61a-106">El ejemplo se usa el <xref:System.Windows.Media.MatrixTransform> objeto para transformar la apariencia y la posición de un <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="1c61a-106">The example uses the <xref:System.Windows.Media.MatrixTransform> object to transform the appearance and position of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="1c61a-107">Esta animación usa el <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> de clases para crear dos fotogramas clave y realiza las siguientes acciones con ellos:</span><span class="sxs-lookup"><span data-stu-id="1c61a-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> class to create two key frames and does the following with them:</span></span>  
  
1. <span data-ttu-id="1c61a-108">Anima el primer <xref:System.Windows.Media.Matrix> durante los primeros 0,2 segundos.</span><span class="sxs-lookup"><span data-stu-id="1c61a-108">Animates the first <xref:System.Windows.Media.Matrix> during the first 0.2 seconds.</span></span> <span data-ttu-id="1c61a-109">El ejemplo se cambia el <xref:System.Windows.Media.Matrix.M11%2A> y <xref:System.Windows.Media.Matrix.M12%2A> propiedades de la <xref:System.Windows.Media.Matrix>.</span><span class="sxs-lookup"><span data-stu-id="1c61a-109">The example changes the <xref:System.Windows.Media.Matrix.M11%2A> and <xref:System.Windows.Media.Matrix.M12%2A> properties of the <xref:System.Windows.Media.Matrix>.</span></span> <span data-ttu-id="1c61a-110">Este cambio hace que el botón Ajustar y se convierten en sesgado.</span><span class="sxs-lookup"><span data-stu-id="1c61a-110">This change causes the button to stretch and become skewed.</span></span> <span data-ttu-id="1c61a-111">El ejemplo también se cambia el <xref:System.Windows.Media.Matrix.OffsetX%2A> y <xref:System.Windows.Media.Matrix.OffsetY%2A> propiedades para que el botón cambia de posición.</span><span class="sxs-lookup"><span data-stu-id="1c61a-111">The example also changes the <xref:System.Windows.Media.Matrix.OffsetX%2A> and <xref:System.Windows.Media.Matrix.OffsetY%2A> properties so that the button changes position.</span></span>  
  
2. <span data-ttu-id="1c61a-112">Anima el segundo <xref:System.Windows.Media.Matrix> en 1,0 segundo.</span><span class="sxs-lookup"><span data-stu-id="1c61a-112">Animates the second <xref:System.Windows.Media.Matrix> at 1.0 seconds.</span></span> <span data-ttu-id="1c61a-113">El botón se mueve a otra posición mientras el botón ya no está sesgado ni ajustado.</span><span class="sxs-lookup"><span data-stu-id="1c61a-113">The button moves to another position while the button is no longer skewed or stretched.</span></span>  
  
3. <span data-ttu-id="1c61a-114">Se repite la animación indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="1c61a-114">Repeats the animation indefinitely.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c61a-115">Marcos que se derivan de la clave del <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> objeto crean saltos súbitos entre los valores, es decir, el movimiento de la animación es brusco.</span><span class="sxs-lookup"><span data-stu-id="1c61a-115">Key frames that derive from the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> object create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="1c61a-116">Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="1c61a-116">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c61a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c61a-117">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [<span data-ttu-id="1c61a-118">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="1c61a-118">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="1c61a-119">Temas de procedimientos de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="1c61a-119">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
