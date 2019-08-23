---
title: Procedimiento Animar un objeto mediante fotogramas clave
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: ffbe1845b634c8f94eb6a10dfa44fcf9903e0cd5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933909"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a><span data-ttu-id="16769-102">Procedimiento Animar un objeto mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="16769-102">How to: Animate an Object by Using Key Frames</span></span>
<span data-ttu-id="16769-103">En este ejemplo se muestra cómo animar un objeto, que en este ejemplo <xref:System.Windows.Controls.Page.Background%2A> es la propiedad <xref:System.Windows.Controls.Page> de un control, mediante fotogramas clave.</span><span class="sxs-lookup"><span data-stu-id="16769-103">This example shows how to animate an object, which in this example is the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16769-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="16769-104">Example</span></span>  
 <span data-ttu-id="16769-105">En el ejemplo siguiente se <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> usa la clase para animar los <xref:System.Windows.Controls.Page.Background%2A> cambios de color <xref:System.Windows.Controls.Page> de la propiedad de un control.</span><span class="sxs-lookup"><span data-stu-id="16769-105">The following example uses the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class to animate color changes for the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control.</span></span> <span data-ttu-id="16769-106">La animación de ejemplo cambia a un pincel de fondo diferente a intervalos regulares.</span><span class="sxs-lookup"><span data-stu-id="16769-106">The example animation changes to a different background brush at regular intervals.</span></span> <span data-ttu-id="16769-107">Esta animación usa la <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> clase para crear tres fotogramas clave diferentes.</span><span class="sxs-lookup"><span data-stu-id="16769-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> class to create three different key frames.</span></span> <span data-ttu-id="16769-108">La animación utiliza fotogramas clave de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="16769-108">The animation uses key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="16769-109">Al final del primer segundo, anima una instancia de la <xref:System.Windows.Media.LinearGradientBrush> clase.</span><span class="sxs-lookup"><span data-stu-id="16769-109">At the end of the first second, animates an instance of the <xref:System.Windows.Media.LinearGradientBrush> class.</span></span> <span data-ttu-id="16769-110">En esta sección del ejemplo se aplica un degradado lineal al color de fondo para que el color pase de amarillo a rojo.</span><span class="sxs-lookup"><span data-stu-id="16769-110">This section of the example applies a linear gradient to the background color so that the color transitions from yellow to orange to red.</span></span>  
  
2. <span data-ttu-id="16769-111">Al final del siguiente segundo, anima una instancia de la <xref:System.Windows.Media.RadialGradientBrush> clase.</span><span class="sxs-lookup"><span data-stu-id="16769-111">At the end of the next second, animates an instance of the <xref:System.Windows.Media.RadialGradientBrush> class.</span></span> <span data-ttu-id="16769-112">En esta sección del ejemplo se aplica un degradado radial al color de fondo para que el color pase de blanco a azul a negro.</span><span class="sxs-lookup"><span data-stu-id="16769-112">This section of the example applies a radial gradient to the background color so that the color transitions from white to blue to black.</span></span>  
  
3. <span data-ttu-id="16769-113">Al final del tercer segundo, anima una instancia de la <xref:System.Windows.Media.DrawingBrush> clase.</span><span class="sxs-lookup"><span data-stu-id="16769-113">At the end of the third second, animates an instance of the <xref:System.Windows.Media.DrawingBrush> class.</span></span> <span data-ttu-id="16769-114">En esta sección del ejemplo se aplica un patrón de tablero de ajedrez al fondo.</span><span class="sxs-lookup"><span data-stu-id="16769-114">This section of the example applies a checkerboard pattern to the background.</span></span>  
  
4. <span data-ttu-id="16769-115">La animación comienza de nuevo y se repite indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="16769-115">The animation begins again and repeats indefinitely.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="16769-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>es el único tipo de fotograma clave que se puede utilizar con <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> la clase.</span><span class="sxs-lookup"><span data-stu-id="16769-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> is the only type of key frame that you can use with the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class.</span></span> <span data-ttu-id="16769-117">Fotogramas <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> clave, como crear cambios súbitos en valores, es decir, los cambios de color de este ejemplo se producen repentinamente.</span><span class="sxs-lookup"><span data-stu-id="16769-117">Key frames like <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> create sudden changes in values, that is, the color changes in this example occur suddenly.</span></span>  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="16769-118">Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="16769-118">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16769-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="16769-119">See also</span></span>

- <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.Page.Background%2A>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- <xref:System.Windows.Media.DrawingBrush>
- [<span data-ttu-id="16769-120">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="16769-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="16769-121">Temas de procedimientos de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="16769-121">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
