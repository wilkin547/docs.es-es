---
title: 'Cómo: Animar un objeto mediante fotogramas clave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: 5e948b574e1b4a1c431b9495583e9579502576a8
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43416339"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a><span data-ttu-id="d3030-102">Cómo: Animar un objeto mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="d3030-102">How to: Animate an Object by Using Key Frames</span></span>
<span data-ttu-id="d3030-103">En este ejemplo se muestra cómo animar un objeto, que en este ejemplo es el <xref:System.Windows.Controls.Page.Background%2A> propiedad de un <xref:System.Windows.Controls.Page> control mediante fotogramas clave.</span><span class="sxs-lookup"><span data-stu-id="d3030-103">This example shows how to animate an object, which in this example is the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3030-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d3030-104">Example</span></span>  
 <span data-ttu-id="d3030-105">En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> clase se va a animar el color cambia para el <xref:System.Windows.Controls.Page.Background%2A> propiedad de un <xref:System.Windows.Controls.Page> control.</span><span class="sxs-lookup"><span data-stu-id="d3030-105">The following example uses the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class to animate color changes for the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control.</span></span> <span data-ttu-id="d3030-106">La animación en el ejemplo se cambia a un pincel de fondo diferente a intervalos regulares.</span><span class="sxs-lookup"><span data-stu-id="d3030-106">The example animation changes to a different background brush at regular intervals.</span></span> <span data-ttu-id="d3030-107">Esta animación usa el <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> clase para crear tres fotogramas clave diferentes.</span><span class="sxs-lookup"><span data-stu-id="d3030-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> class to create three different key frames.</span></span> <span data-ttu-id="d3030-108">La animación utiliza fotogramas clave en la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="d3030-108">The animation uses key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="d3030-109">Al final del primer segundo, anima una instancia de la <xref:System.Windows.Media.LinearGradientBrush> clase.</span><span class="sxs-lookup"><span data-stu-id="d3030-109">At the end of the first second, animates an instance of the <xref:System.Windows.Media.LinearGradientBrush> class.</span></span> <span data-ttu-id="d3030-110">En esta sección del ejemplo aplica un degradado lineal al color de fondo para que el color pasa de amarillo a naranja a rojo.</span><span class="sxs-lookup"><span data-stu-id="d3030-110">This section of the example applies a linear gradient to the background color so that the color transitions from yellow to orange to red.</span></span>  
  
2.  <span data-ttu-id="d3030-111">Al final del segundo siguiente, anima una instancia de la <xref:System.Windows.Media.RadialGradientBrush> clase.</span><span class="sxs-lookup"><span data-stu-id="d3030-111">At the end of the next second, animates an instance of the <xref:System.Windows.Media.RadialGradientBrush> class.</span></span> <span data-ttu-id="d3030-112">En esta sección del ejemplo aplica un degradado radial al color de fondo para que el color pasa de negro a azul a negro.</span><span class="sxs-lookup"><span data-stu-id="d3030-112">This section of the example applies a radial gradient to the background color so that the color transitions from white to blue to black.</span></span>  
  
3.  <span data-ttu-id="d3030-113">Al final del tercer segundo, anima una instancia de la <xref:System.Windows.Media.DrawingBrush> clase.</span><span class="sxs-lookup"><span data-stu-id="d3030-113">At the end of the third second, animates an instance of the <xref:System.Windows.Media.DrawingBrush> class.</span></span> <span data-ttu-id="d3030-114">En esta sección del ejemplo se aplica un patrón de tablero a segundo plano.</span><span class="sxs-lookup"><span data-stu-id="d3030-114">This section of the example applies a checkerboard pattern to the background.</span></span>  
  
4.  <span data-ttu-id="d3030-115">La animación comienza de nuevo y se repite indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="d3030-115">The animation begins again and repeats indefinitely.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3030-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> es el único tipo de fotograma clave que puede usar con el <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> clase.</span><span class="sxs-lookup"><span data-stu-id="d3030-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> is the only type of key frame that you can use with the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class.</span></span> <span data-ttu-id="d3030-117">Fotogramas clave como <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> crean cambios súbitos en valores, es decir, los cambios de color en este ejemplo se producen de repente.</span><span class="sxs-lookup"><span data-stu-id="d3030-117">Key frames like <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> create sudden changes in values, that is, the color changes in this example occur suddenly.</span></span>  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="d3030-118">Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="d3030-118">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3030-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3030-119">See Also</span></span>  
 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>  
 <xref:System.Windows.Controls.Page.Background%2A>  
 <xref:System.Windows.Controls.Page>  
 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>  
 <xref:System.Windows.Media.LinearGradientBrush>  
 <xref:System.Windows.Media.RadialGradientBrush>  
 <xref:System.Windows.Media.DrawingBrush>  
 [<span data-ttu-id="d3030-120">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="d3030-120">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="d3030-121">Temas de procedimientos de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="d3030-121">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
