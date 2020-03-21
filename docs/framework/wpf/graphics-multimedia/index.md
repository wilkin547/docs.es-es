---
title: Gráficos y multimedia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- media [WPF], features
- video effects [WPF]
- sound effects [WPF]
- animation [WPF], features
- graphics features [WPF]
- transition effects [WPF]
ms.assetid: 1817d9dc-3d6c-46cb-afc8-63b0bae35e37
ms.openlocfilehash: 8636afcc5b63b71dc729812a7f3eb4945ba49494
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112042"
---
# <a name="graphics-and-multimedia"></a><span data-ttu-id="0d5c0-102">Gráficos y multimedia</span><span class="sxs-lookup"><span data-stu-id="0d5c0-102">Graphics and Multimedia</span></span>

<a name="introduction"></a>
<span data-ttu-id="0d5c0-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ofrece compatibilidad con multimedia, gráficos vectoriales, animaciones y creación de contenido, lo que permite a los desarrolladores crear fácilmente interfaces de usuario y contenido interesantes.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] provides support for multimedia, vector graphics, animation, and content composition, making it easy for developers to build interesting user interfaces and content.</span></span> <span data-ttu-id="0d5c0-104">Con Visual Studio, puede crear gráficos vectoriales o animaciones complejas e integrar medios en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-104">Using Visual Studio, you can create vector graphics or complex animations and integrate media into your applications.</span></span>

<span data-ttu-id="0d5c0-105">En este tema se presentan las características de gráficos, animaciones y elementos multimedia de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], que le permiten agregar gráficos, efectos de transición, sonido y vídeo a las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-105">This topic introduces the graphics, animation, and media features of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], which enable you to add graphics, transition effects, sound, and video to your applications.</span></span>

> [!NOTE]
> <span data-ttu-id="0d5c0-106">Se recomienda encarecidamente no usar los tipos WPF en un servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-106">Using WPF types in a Windows service is strongly discouraged.</span></span> <span data-ttu-id="0d5c0-107">Si intenta usar tipos WPF en un servicio de Windows, puede que el servicio no funcione como se espera.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-107">If you attempt to use WPF types in a Windows service, the service may not work as expected.</span></span>

<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>

## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a><span data-ttu-id="0d5c0-108">Novedades de gráficos y multimedia en WPF 4</span><span class="sxs-lookup"><span data-stu-id="0d5c0-108">What's New with Graphics and Multimedia in WPF 4</span></span>

<span data-ttu-id="0d5c0-109">Se han efectuado varios cambios relacionados con los gráficos y animaciones.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-109">Several changes have been made related to graphics and animations.</span></span>

- <span data-ttu-id="0d5c0-110">Redondeo del diseño</span><span class="sxs-lookup"><span data-stu-id="0d5c0-110">Layout Rounding</span></span>

  <span data-ttu-id="0d5c0-111">Cuando el borde de un objeto queda en medio de un dispositivo de píxeles, el sistema de gráficos independiente de los ppp puede crear artefactos de representación tales como bordes borrosos o semitransparentes.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-111">When an object edge falls in the middle of a pixel device, the DPI-independent graphics system can create rendering artifacts, such as blurry or semi-transparent edges.</span></span> <span data-ttu-id="0d5c0-112">Versiones anteriores de WPF incluían el ajuste de píxeles para ayudar a controlar este caso.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-112">Previous versions of WPF included pixel snapping to help handle this case.</span></span> <span data-ttu-id="0d5c0-113">Silverlight 2 introdujo el redondeo del diseño, que es otra manera de mover elementos para que los bordes queden dentro de límites de píxeles enteros.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-113">Silverlight 2 introduced layout rounding, which is another way to move elements so that edges fall on whole pixel boundaries.</span></span> <span data-ttu-id="0d5c0-114">WPFWPF ahora admite el <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> redondeo <xref:System.Windows.FrameworkElement>de diseño con la propiedad adjunta en .</span><span class="sxs-lookup"><span data-stu-id="0d5c0-114">WPF now supports layout rounding with the <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> attached property on <xref:System.Windows.FrameworkElement>.</span></span>

- <span data-ttu-id="0d5c0-115">Composición almacenada en caché</span><span class="sxs-lookup"><span data-stu-id="0d5c0-115">Cached Composition</span></span>

  <span data-ttu-id="0d5c0-116">Mediante el <xref:System.Windows.Media.BitmapCache> uso <xref:System.Windows.Media.BitmapCacheBrush> de las clases new y, puede almacenar en caché una parte compleja del árbol visual como un mapa de bits y mejorar en gran medida el tiempo de representación.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-116">By using the new <xref:System.Windows.Media.BitmapCache> and <xref:System.Windows.Media.BitmapCacheBrush> classes, you can cache a complex part of the visual tree as a bitmap and greatly improve rendering time.</span></span> <span data-ttu-id="0d5c0-117">El mapa de bits sigue respondiendo a la entrada del usuario, como clics del mouse, y se puede pintar en otros elementos, exactamente igual que cualquier pincel.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-117">The bitmap remains responsive to user input, such as mouse clicks, and you can paint it onto other elements just like any brush.</span></span>

- <span data-ttu-id="0d5c0-118">Compatibilidad con el sombreador de píxeles 3</span><span class="sxs-lookup"><span data-stu-id="0d5c0-118">Pixel Shader 3 Support</span></span>

  <span data-ttu-id="0d5c0-119">WPF 4 se basa <xref:System.Windows.Media.Effects.ShaderEffect> en la compatibilidad introducida en WPF 3.5 SP1 al permitir que las aplicaciones escriban efectos mediante la versión 3.0 del sombreador de píxeles (PS).</span><span class="sxs-lookup"><span data-stu-id="0d5c0-119">WPF 4 builds on top of the <xref:System.Windows.Media.Effects.ShaderEffect> support introduced in WPF 3.5 SP1 by allowing applications to write effects by using Pixel Shader (PS) version 3.0.</span></span> <span data-ttu-id="0d5c0-120">El modelo de sombreador PS 3.0 es más sofisticado que el PS 2.0, lo que permite incluso crear más efectos en hardware compatible.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-120">The PS 3.0 shader model is more sophisticated than PS 2.0, which allows for even more effects on supported hardware.</span></span>

- <span data-ttu-id="0d5c0-121">Funciones de aceleración</span><span class="sxs-lookup"><span data-stu-id="0d5c0-121">Easing Functions</span></span>

  <span data-ttu-id="0d5c0-122">Puede mejorar las animaciones con funciones de aceleración que proporcionan mayor control sobre el comportamiento de las animaciones.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-122">You can enhance animations with easing functions, which give you additional control over the behavior of animations.</span></span> <span data-ttu-id="0d5c0-123">Por ejemplo, puede <xref:System.Windows.Media.Animation.ElasticEase> aplicar un a una animación para dar a la animación un comportamiento elástico.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-123">For example, you can apply an <xref:System.Windows.Media.Animation.ElasticEase> to an animation to give the animation a springy behavior.</span></span> <span data-ttu-id="0d5c0-124">Para obtener más información, consulte los <xref:System.Windows.Media.Animation> tipos de conexión de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-124">For more information, see the easing types in the <xref:System.Windows.Media.Animation> namespace.</span></span>

<a name="graphics_and_rendering"></a>

## <a name="graphics-and-rendering"></a><span data-ttu-id="0d5c0-125">Gráficos y representación</span><span class="sxs-lookup"><span data-stu-id="0d5c0-125">Graphics and Rendering</span></span>

<span data-ttu-id="0d5c0-126">WPFWPF incluye compatibilidad con gráficos 2D de alta calidad.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-126">WPF includes support for high quality 2D graphics.</span></span> <span data-ttu-id="0d5c0-127">La funcionalidad incluye pinceles, geometrías, imágenes, formas y transformaciones.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-127">The functionality includes brushes, geometries, images, shapes and transformations.</span></span> <span data-ttu-id="0d5c0-128">Para más información, consulte [Graphics](graphics.md) (Gráficos).</span><span class="sxs-lookup"><span data-stu-id="0d5c0-128">For more information, see [Graphics](graphics.md).</span></span> <span data-ttu-id="0d5c0-129">La representación de elementos <xref:System.Windows.Media.Visual> gráficos se basa en la clase.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-129">The rendering of graphical elements is based on the <xref:System.Windows.Media.Visual> class.</span></span> <span data-ttu-id="0d5c0-130">La estructura de objetos visuales en la pantalla se describe en el árbol visual.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-130">The structure of visual objects on the screen is described by the visual tree.</span></span> <span data-ttu-id="0d5c0-131">Para más información, consulte [Información general sobre la representación de gráficos en WPF](wpf-graphics-rendering-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0d5c0-131">For more information, see [WPF Graphics Rendering Overview](wpf-graphics-rendering-overview.md).</span></span>

### <a name="2d-shapes"></a><span data-ttu-id="0d5c0-132">Formas 2D</span><span class="sxs-lookup"><span data-stu-id="0d5c0-132">2D Shapes</span></span>

<span data-ttu-id="0d5c0-133">WPFWPF proporciona una biblioteca de formas 2D dibujadas por vectores de uso común, como rectángulos y elipses, que se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-133">WPF provides a library of commonly used, vector-drawn 2D shapes, such as rectangles and ellipses, which the following illustration shows.</span></span>

![Diagrama que muestra elipses y rectángulos.](./media/index/two-deminsional-shapes-ellipses-rectangles.png)

<span data-ttu-id="0d5c0-135">Estas formas intrínsecas de WPFWPF no son solo formas: son elementos programables que implementan muchas de las características que se esperan de los controles más comunes, que incluyen entrada de teclado y mouse.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-135">These intrinsic WPF shapes are not just shapes: they are programmable elements that implement many of the features that you expect from most common controls, which include keyboard and mouse input.</span></span> <span data-ttu-id="0d5c0-136">En el ejemplo siguiente <xref:System.Windows.UIElement.MouseUp> se muestra cómo controlar <xref:System.Windows.Shapes.Ellipse> el evento generado haciendo clic en un elemento.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-136">The following example shows how to handle the <xref:System.Windows.UIElement.MouseUp> event raised by clicking an <xref:System.Windows.Shapes.Ellipse> element.</span></span>

```xaml
<Window
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  x:Class="Window1" >
  <Ellipse Fill="LightBlue" MouseUp="ellipseButton_MouseUp" />
</Window>
```

```csharp
public partial class Window1  : Window
{
    void ellipseButton_MouseUp(object sender, MouseButtonEventArgs e)
    {
        MessageBox.Show("You clicked the ellipse!");
    }
}
```

```vb
Partial Public Class Window1
    Inherits Window
    Private Sub ellipseButton_MouseUp(ByVal sender As Object, ByVal e As MouseButtonEventArgs)
        MessageBox.Show("You clicked the ellipse!")
    End Sub
End Class
```

<span data-ttu-id="0d5c0-137">En la ilustración siguiente se muestra el resultado del anterior marcado y código [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] subyacente.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-137">The following illustration shows the output for the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup and code-behind.</span></span>

![Un cuadro de mensaje que dice "¡Hiciste clic en la elipse!"](./media/index/messagebox-text-output.png)

<span data-ttu-id="0d5c0-139">Para obtener más información, consulte [Información general sobre formas y dibujo básico en WPF](shapes-and-basic-drawing-in-wpf-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0d5c0-139">For more information, see [Shapes and Basic Drawing in WPF Overview](shapes-and-basic-drawing-in-wpf-overview.md).</span></span> <span data-ttu-id="0d5c0-140">Para obtener un ejemplo introductorio, vea [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements) (Ejemplo de elementos de forma).</span><span class="sxs-lookup"><span data-stu-id="0d5c0-140">For an introductory sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>

### <a name="2d-geometries"></a><span data-ttu-id="0d5c0-141">Geometrías 2D</span><span class="sxs-lookup"><span data-stu-id="0d5c0-141">2D Geometries</span></span>

<span data-ttu-id="0d5c0-142">Cuando las formas 2D que WPFWPF proporciona no son suficientes, puede usar la compatibilidad de WPFWPF para geometrías y rutas de acceso para crear su propia.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-142">When the 2D shapes that WPF provides are not sufficient, you can use WPF support for geometries and paths to create your own.</span></span> <span data-ttu-id="0d5c0-143">En la siguiente ilustración se muestra cómo puede usar geometrías para crear formas, como un pincel de dibujo y para recortar otros elementos WPFWPF.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-143">The following illustration shows how you can use geometries to create shapes, as a drawing brush, and to clip other WPF elements.</span></span>

![Captura de pantalla que muestra cómo puede utilizar geometrías para crear formas.](./media/index/use-geometries-create-shapes.png)

<span data-ttu-id="0d5c0-145">Para obtener más información, consulte [Información general sobre geometría](geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0d5c0-145">For more information, see [Geometry Overview](geometry-overview.md).</span></span> <span data-ttu-id="0d5c0-146">Para obtener un ejemplo introductorio, vea [Ejemplo de geometrías](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span><span class="sxs-lookup"><span data-stu-id="0d5c0-146">For an introductory sample, see [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>

### <a name="2d-effects"></a><span data-ttu-id="0d5c0-147">Efectos 2D</span><span class="sxs-lookup"><span data-stu-id="0d5c0-147">2D Effects</span></span>

<span data-ttu-id="0d5c0-148">WPFWPF proporciona una biblioteca de clases 2D que puede usar para crear una variedad de efectos.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-148">WPF provides a library of 2D classes that you can use to create a variety of effects.</span></span> <span data-ttu-id="0d5c0-149">La capacidad de representación 2D [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de WPFWPF proporciona la capacidad de pintar elementos que tienen degradados, mapas de bits, dibujos y vídeos; y manipularlos mediante la rotación, el escalado y el sesgo.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-149">The 2D rendering capability of WPF provides the ability to paint [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements that have gradients, bitmaps, drawings, and videos; and to manipulate them by using rotation, scaling, and skewing.</span></span> <span data-ttu-id="0d5c0-150">En la siguiente ilustración se muestra un ejemplo de los muchos efectos que puede lograr mediante el uso de pinceles WPFWPF.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-150">The following illustration gives an example of the many effects you can achieve by using WPF brushes.</span></span>

![Ilustración que muestra los diferentes elementos de WPFWPF y elementos de pintura.](./media/index/brushes-paint-elements.png)

<span data-ttu-id="0d5c0-152">Para obtener más información, vea [Información general sobre pinceles de WPF](wpf-brushes-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0d5c0-152">For more information, see [WPF Brushes Overview](wpf-brushes-overview.md).</span></span> <span data-ttu-id="0d5c0-153">Para obtener un ejemplo introductorio, vea [Ejemplo de pinceles](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span><span class="sxs-lookup"><span data-stu-id="0d5c0-153">For an introductory sample, see [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span>

<a name="rendering"></a>

## <a name="3d-rendering"></a><span data-ttu-id="0d5c0-154">Renderizado 3D</span><span class="sxs-lookup"><span data-stu-id="0d5c0-154">3D Rendering</span></span>

<span data-ttu-id="0d5c0-155">WPFWPF proporciona un conjunto de capacidades de representación 3D que se integran [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]con compatibilidad con gráficos 2D en WPFWPF para que pueda crear un diseño más emocionante y visualización de datos.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-155">WPF provides a set of 3D rendering capabilities that integrate with 2D graphics support in WPF in order for you to create more exciting layout, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], and data visualization.</span></span> <span data-ttu-id="0d5c0-156">En un extremo del espectro, WPFWPF permite representar imágenes 2D en las superficies de formas 3D, que se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-156">At one end of the spectrum, WPF enables you to render 2D images onto the surfaces of 3D shapes, which the following illustration demonstrates.</span></span>

![Captura de pantalla de una muestra que muestra formas 3D con diferentes texturas.](./media/index/visual-three-dimensional-shape.png)

<span data-ttu-id="0d5c0-158">Para obtener más información, consulte [Información general sobre gráficos 3D](3-d-graphics-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0d5c0-158">For more information, see [3D Graphics Overview](3-d-graphics-overview.md).</span></span> <span data-ttu-id="0d5c0-159">Para obtener una muestra introductoria, consulte [3D Solids Sample](https://go.microsoft.com/fwlink/?LinkID=159964).</span><span class="sxs-lookup"><span data-stu-id="0d5c0-159">For an introductory sample, see [3D Solids Sample](https://go.microsoft.com/fwlink/?LinkID=159964).</span></span>

<a name="animation"></a>

## <a name="animation"></a><span data-ttu-id="0d5c0-160">Animación</span><span class="sxs-lookup"><span data-stu-id="0d5c0-160">Animation</span></span>

<span data-ttu-id="0d5c0-161">Use la animación para hacer que los controles y elementos crezcan, vibren, giren o se desvanezcan, crear atractivas transiciones de página y mucho más.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-161">Use animation to make controls and elements grow, shake, spin, and fade; and to create interesting page transitions, and more.</span></span> <span data-ttu-id="0d5c0-162">Dado que WPFWPF permite animar la mayoría de las propiedades, no solo puede animar la mayoría de los objetos WPFWPF, también puede usar WPFWPF para animar los objetos personalizados que cree.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-162">Because WPF enables you to animate most properties, not only can you animate most WPF objects, you can also use WPF to animate custom objects that you create.</span></span>

![Captura de pantalla de un cubo animado.](./media/index/animate-custom-objects.png)

<span data-ttu-id="0d5c0-164">Para obtener más información, consulte [Información general sobre animaciones](animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0d5c0-164">For more information, see [Animation Overview](animation-overview.md).</span></span> <span data-ttu-id="0d5c0-165">Para obtener un ejemplo introductorio, vea [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples) (Galería de ejemplos de animación).</span><span class="sxs-lookup"><span data-stu-id="0d5c0-165">For an introductory sample, see [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>

<a name="media"></a>

## <a name="media"></a><span data-ttu-id="0d5c0-166">Multimedia</span><span class="sxs-lookup"><span data-stu-id="0d5c0-166">Media</span></span>

<span data-ttu-id="0d5c0-167">Las imágenes, el vídeo y el audio son maneras de ofrecer experiencias de usuario e información con mucho contenido multimedia.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-167">Images, video, and audio are media-rich ways of conveying information and user experiences.</span></span>

### <a name="images"></a><span data-ttu-id="0d5c0-168">Imágenes</span><span class="sxs-lookup"><span data-stu-id="0d5c0-168">Images</span></span>

<span data-ttu-id="0d5c0-169">Las imágenes, que incluyen iconos, fondos e incluso partes de animaciones, constituyen una pieza esencial de la mayoría de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-169">Images, which include icons, backgrounds, and even parts of animations, are a core part of most applications.</span></span> <span data-ttu-id="0d5c0-170">Dado que con frecuencia necesita usar imágenes, WPFWPF expone la capacidad de trabajar con ellos de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-170">Because you frequently need to use images, WPF exposes the ability to work with them in a variety of ways.</span></span> <span data-ttu-id="0d5c0-171">En la ilustración siguiente se muestra tan solo una de esas maneras.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-171">The following illustration shows just one of those ways.</span></span>

<span data-ttu-id="0d5c0-172">![Captura de pantalla de ejemplo de estilo](../controls/./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span><span class="sxs-lookup"><span data-stu-id="0d5c0-172">![Styling sample screenshot](../controls/./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span></span>

<span data-ttu-id="0d5c0-173">Para obtener más información, consulte [Información general sobre imágenes](imaging-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0d5c0-173">For more information, see [Imaging Overview](imaging-overview.md).</span></span>

### <a name="video-and-audio"></a><span data-ttu-id="0d5c0-174">Vídeo y audio</span><span class="sxs-lookup"><span data-stu-id="0d5c0-174">Video and Audio</span></span>

<span data-ttu-id="0d5c0-175">Una característica principal de las capacidades gráficas de WPFWPF es proporcionar compatibilidad nativa para trabajar con multimedia, que incluye vídeo y audio.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-175">A core feature of the graphics capabilities of WPF is to provide native support for working with multimedia, which includes video and audio.</span></span> <span data-ttu-id="0d5c0-176">En el siguiente ejemplo se muestra cómo insertar un reproductor multimedia en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-176">The following example shows how to insert a media player into an application.</span></span>

```xaml
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />
```

<span data-ttu-id="0d5c0-177"><xref:System.Windows.Controls.MediaElement>es capaz de reproducir vídeo y audio, y es lo suficientemente extensible como para permitir la fácil creación de ui personalizadas.</span><span class="sxs-lookup"><span data-stu-id="0d5c0-177"><xref:System.Windows.Controls.MediaElement> is capable of playing both video and audio, and is extensible enough to allow the easy creation of custom UIs.</span></span>

<span data-ttu-id="0d5c0-178">Para más información, consulte [Información general sobre multimedia](multimedia-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0d5c0-178">For more information, see the [Multimedia Overview](multimedia-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0d5c0-179">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0d5c0-179">See also</span></span>

- <xref:System.Windows.Media>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Media3D>
- [<span data-ttu-id="0d5c0-180">Imágenes y gráficos 2D</span><span class="sxs-lookup"><span data-stu-id="0d5c0-180">2D Graphics and Imaging</span></span>](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="0d5c0-181">Información general sobre formas y dibujo básico en WPF</span><span class="sxs-lookup"><span data-stu-id="0d5c0-181">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="0d5c0-182">Información general sobre el dibujo con colores sólidos y degradados</span><span class="sxs-lookup"><span data-stu-id="0d5c0-182">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="0d5c0-183">Pintar con imágenes, dibujos y elementos visuales</span><span class="sxs-lookup"><span data-stu-id="0d5c0-183">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="0d5c0-184">Temas "Cómo..." de animación y control de tiempo</span><span class="sxs-lookup"><span data-stu-id="0d5c0-184">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="0d5c0-185">Descripción general de los gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="0d5c0-185">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="0d5c0-186">Información general sobre multimedia</span><span class="sxs-lookup"><span data-stu-id="0d5c0-186">Multimedia Overview</span></span>](multimedia-overview.md)
