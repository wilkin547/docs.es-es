---
title: 'Cómo: Animar un objeto mediante fotogramas clave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: 7dc49bc6b3f9156507cb821bfc32b269365b206c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558545"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a><span data-ttu-id="7e798-102">Cómo: Animar un objeto mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="7e798-102">How to: Animate an Object by Using Key Frames</span></span>
<span data-ttu-id="7e798-103">Este ejemplo muestra cómo animar un objeto, que en este ejemplo es el <xref:System.Windows.Controls.Page.Background%2A> propiedad de un <xref:System.Windows.Controls.Page> control, mediante el uso de fotogramas clave.</span><span class="sxs-lookup"><span data-stu-id="7e798-103">This example shows how to animate an object, which in this example is the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e798-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7e798-104">Example</span></span>  
 <span data-ttu-id="7e798-105">En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> clase animar color cambia para el <xref:System.Windows.Controls.Page.Background%2A> propiedad de un <xref:System.Windows.Controls.Page> control.</span><span class="sxs-lookup"><span data-stu-id="7e798-105">The following example uses the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class to animate color changes for the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control.</span></span> <span data-ttu-id="7e798-106">La animación de ejemplo cambia a un pincel de fondo diferente a intervalos regulares.</span><span class="sxs-lookup"><span data-stu-id="7e798-106">The example animation changes to a different background brush at regular intervals.</span></span> <span data-ttu-id="7e798-107">Esta animación usa la <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> clase para crear tres fotogramas clave diferentes.</span><span class="sxs-lookup"><span data-stu-id="7e798-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> class to create three different key frames.</span></span> <span data-ttu-id="7e798-108">La animación usa fotogramas clave de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="7e798-108">The animation uses key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="7e798-109">Al final del primer segundo, anima una instancia de la <xref:System.Windows.Media.LinearGradientBrush> clase.</span><span class="sxs-lookup"><span data-stu-id="7e798-109">At the end of the first second, animates an instance of the <xref:System.Windows.Media.LinearGradientBrush> class.</span></span> <span data-ttu-id="7e798-110">En esta sección del ejemplo se aplica un degradado lineal al color de fondo para que el color pasa de amarillo a naranja y a rojo.</span><span class="sxs-lookup"><span data-stu-id="7e798-110">This section of the example applies a linear gradient to the background color so that the color transitions from yellow to orange to red.</span></span>  
  
2.  <span data-ttu-id="7e798-111">Al final del segundo siguiente, anima una instancia de la <xref:System.Windows.Media.RadialGradientBrush> clase.</span><span class="sxs-lookup"><span data-stu-id="7e798-111">At the end of the next second, animates an instance of the <xref:System.Windows.Media.RadialGradientBrush> class.</span></span> <span data-ttu-id="7e798-112">En esta sección del ejemplo se aplica un degradado radial al color de fondo para que el color pasa de blanco a azul y a negro.</span><span class="sxs-lookup"><span data-stu-id="7e798-112">This section of the example applies a radial gradient to the background color so that the color transitions from white to blue to black.</span></span>  
  
3.  <span data-ttu-id="7e798-113">Al final del tercer segundo, anima una instancia de la <xref:System.Windows.Media.DrawingBrush> clase.</span><span class="sxs-lookup"><span data-stu-id="7e798-113">At the end of the third second, animates an instance of the <xref:System.Windows.Media.DrawingBrush> class.</span></span> <span data-ttu-id="7e798-114">Esta sección del ejemplo aplica un patrón de cuadros bicolores al fondo.</span><span class="sxs-lookup"><span data-stu-id="7e798-114">This section of the example applies a checkerboard pattern to the background.</span></span>  
  
4.  <span data-ttu-id="7e798-115">La animación comienza de nuevo y se repite indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="7e798-115">The animation begins again and repeats indefinitely.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7e798-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> es el único tipo de fotograma clave que puede usar con la <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> clase.</span><span class="sxs-lookup"><span data-stu-id="7e798-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> is the only type of key frame that you can use with the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class.</span></span> <span data-ttu-id="7e798-117">Fotogramas clave como <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> crean cambios repentinos en valores, es decir, los cambios de color en este ejemplo se producen de repente.</span><span class="sxs-lookup"><span data-stu-id="7e798-117">Key frames like <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> create sudden changes in values, that is, the color changes in this example occur suddenly.</span></span>  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="7e798-118">Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](http://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="7e798-118">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e798-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e798-119">See Also</span></span>  
 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>  
 <xref:System.Windows.Controls.Page.Background%2A>  
 <xref:System.Windows.Controls.Page>  
 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>  
 <xref:System.Windows.Media.LinearGradientBrush>  
 <xref:System.Windows.Media.RadialGradientBrush>  
 <xref:System.Windows.Media.DrawingBrush>  
 [<span data-ttu-id="7e798-120">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="7e798-120">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="7e798-121">Temas de procedimientos de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="7e798-121">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
