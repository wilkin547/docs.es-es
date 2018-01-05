---
title: "Cómo: Animar un objeto Matrix mediante fotogramas clave"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 862e1afdcd823181dff0948fab43b1656b85f721
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a><span data-ttu-id="618d4-102">Cómo: Animar un objeto Matrix mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="618d4-102">How to: Animate a Matrix by Using Key Frames</span></span>
<span data-ttu-id="618d4-103">Este ejemplo muestra cómo animar la <xref:System.Windows.Media.MatrixTransform.Matrix%2A> propiedad de un <xref:System.Windows.Media.MatrixTransform> mediante el uso de fotogramas clave.</span><span class="sxs-lookup"><span data-stu-id="618d4-103">This example shows how to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="618d4-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="618d4-104">Example</span></span>  
 <span data-ttu-id="618d4-105">En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> clase para animar la <xref:System.Windows.Media.MatrixTransform.Matrix%2A> propiedad de un <xref:System.Windows.Media.MatrixTransform>.</span><span class="sxs-lookup"><span data-stu-id="618d4-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="618d4-106">El ejemplo se utiliza la <xref:System.Windows.Media.MatrixTransform> objeto que se va a transformar el aspecto y la posición de un <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="618d4-106">The example uses the <xref:System.Windows.Media.MatrixTransform> object to transform the appearance and position of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="618d4-107">Esta animación usa la <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> clase para crear dos fotogramas clave y realiza las siguientes acciones con ellos:</span><span class="sxs-lookup"><span data-stu-id="618d4-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> class to create two key frames and does the following with them:</span></span>  
  
1.  <span data-ttu-id="618d4-108">Anima el primer <xref:System.Windows.Media.Matrix> durante los primeros 0,2 segundos.</span><span class="sxs-lookup"><span data-stu-id="618d4-108">Animates the first <xref:System.Windows.Media.Matrix> during the first 0.2 seconds.</span></span> <span data-ttu-id="618d4-109">El ejemplo se cambia el <xref:System.Windows.Media.Matrix.M11%2A> y <xref:System.Windows.Media.Matrix.M12%2A> propiedades de la <xref:System.Windows.Media.Matrix>.</span><span class="sxs-lookup"><span data-stu-id="618d4-109">The example changes the <xref:System.Windows.Media.Matrix.M11%2A> and <xref:System.Windows.Media.Matrix.M12%2A> properties of the <xref:System.Windows.Media.Matrix>.</span></span> <span data-ttu-id="618d4-110">Este cambio hace que el botón Ajustar y se convierten en sesgado.</span><span class="sxs-lookup"><span data-stu-id="618d4-110">This change causes the button to stretch and become skewed.</span></span> <span data-ttu-id="618d4-111">El ejemplo también se cambia el <xref:System.Windows.Media.Matrix.OffsetX%2A> y <xref:System.Windows.Media.Matrix.OffsetY%2A> propiedades para que el botón cambia de posición.</span><span class="sxs-lookup"><span data-stu-id="618d4-111">The example also changes the <xref:System.Windows.Media.Matrix.OffsetX%2A> and <xref:System.Windows.Media.Matrix.OffsetY%2A> properties so that the button changes position.</span></span>  
  
2.  <span data-ttu-id="618d4-112">Anima el segundo <xref:System.Windows.Media.Matrix> en 1,0 segundo.</span><span class="sxs-lookup"><span data-stu-id="618d4-112">Animates the second <xref:System.Windows.Media.Matrix> at 1.0 seconds.</span></span> <span data-ttu-id="618d4-113">El botón se mueve a otra posición mientras el botón ya no está sesgado ni ajustado.</span><span class="sxs-lookup"><span data-stu-id="618d4-113">The button moves to another position while the button is no longer skewed or stretched.</span></span>  
  
3.  <span data-ttu-id="618d4-114">Repite indefinidamente la animación.</span><span class="sxs-lookup"><span data-stu-id="618d4-114">Repeats the animation indefinitely.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="618d4-115">Marcos que se derivan de la clave del <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> objeto crean saltos súbitos entre valores, es decir, el movimiento de la animación es irregular.</span><span class="sxs-lookup"><span data-stu-id="618d4-115">Key frames that derive from the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> object create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="618d4-116">Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](http://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="618d4-116">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="618d4-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="618d4-117">See Also</span></span>  
 <xref:System.Windows.Media.MatrixTransform.Matrix%2A>  
 <xref:System.Windows.Media.MatrixTransform>  
 [<span data-ttu-id="618d4-118">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="618d4-118">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="618d4-119">Temas de procedimientos de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="618d4-119">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
