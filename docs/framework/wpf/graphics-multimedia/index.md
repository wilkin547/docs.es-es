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
ms.openlocfilehash: 58ee58577b9ff71112103abb4d33c8b85d3c806f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786170"
---
# <a name="graphics-and-multimedia"></a><span data-ttu-id="138ef-102">Gráficos y multimedia</span><span class="sxs-lookup"><span data-stu-id="138ef-102">Graphics and Multimedia</span></span>

<a name="introduction"></a>
<span data-ttu-id="138ef-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona compatibilidad para la creación de contenido, lo que facilita a los desarrolladores compilar contenido e interfaces de usuario interesantes, gráficos vectoriales, animación y multimedia.</span><span class="sxs-lookup"><span data-stu-id="138ef-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] provides support for multimedia, vector graphics, animation, and content composition, making it easy for developers to build interesting user interfaces and content.</span></span> <span data-ttu-id="138ef-104">Con [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], se pueden crear gráficos vectoriales o animaciones complejas e integrar elementos multimedia en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="138ef-104">Using [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], you can create vector graphics or complex animations and integrate media into your applications.</span></span>

<span data-ttu-id="138ef-105">En este tema se presentan las características de gráficos, animaciones y elementos multimedia de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], que le permiten agregar gráficos, efectos de transición, sonido y vídeo a las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="138ef-105">This topic introduces the graphics, animation, and media features of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], which enable you to add graphics, transition effects, sound, and video to your applications.</span></span>

> [!NOTE]
> <span data-ttu-id="138ef-106">Se desaconseja totalmente el uso de tipos WPF en un servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="138ef-106">Using WPF types in a Windows service is strongly discouraged.</span></span> <span data-ttu-id="138ef-107">Si intenta usar tipos WPF en un servicio de Windows, puede que el servicio no funcione como se espera.</span><span class="sxs-lookup"><span data-stu-id="138ef-107">If you attempt to use WPF types in a Windows service, the service may not work as expected.</span></span>

<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>

## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a><span data-ttu-id="138ef-108">Novedades de gráficos y multimedia en WPF 4</span><span class="sxs-lookup"><span data-stu-id="138ef-108">What's New with Graphics and Multimedia in WPF 4</span></span>

<span data-ttu-id="138ef-109">Se han efectuado varios cambios relacionados con los gráficos y animaciones.</span><span class="sxs-lookup"><span data-stu-id="138ef-109">Several changes have been made related to graphics and animations.</span></span>

- <span data-ttu-id="138ef-110">Redondeo del diseño</span><span class="sxs-lookup"><span data-stu-id="138ef-110">Layout Rounding</span></span>

  <span data-ttu-id="138ef-111">Cuando el borde de un objeto queda en medio de un dispositivo de píxeles, el sistema de gráficos independiente de los ppp puede crear artefactos de representación tales como bordes borrosos o semitransparentes.</span><span class="sxs-lookup"><span data-stu-id="138ef-111">When an object edge falls in the middle of a pixel device, the DPI-independent graphics system can create rendering artifacts, such as blurry or semi-transparent edges.</span></span> <span data-ttu-id="138ef-112">Versiones anteriores de WPF incluían el ajuste de píxeles para ayudar a controlar este caso.</span><span class="sxs-lookup"><span data-stu-id="138ef-112">Previous versions of WPF included pixel snapping to help handle this case.</span></span> <span data-ttu-id="138ef-113">Silverlight 2 introdujo el redondeo del diseño, que es otra manera de mover elementos para que los bordes queden dentro de límites de píxeles enteros.</span><span class="sxs-lookup"><span data-stu-id="138ef-113">Silverlight 2 introduced layout rounding, which is another way to move elements so that edges fall on whole pixel boundaries.</span></span> <span data-ttu-id="138ef-114">WPF admite ahora el redondeo del diseño con el <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> de la propiedad adjunta <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="138ef-114">WPF now supports layout rounding with the <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> attached property on <xref:System.Windows.FrameworkElement>.</span></span>

- <span data-ttu-id="138ef-115">Composición almacenada en caché</span><span class="sxs-lookup"><span data-stu-id="138ef-115">Cached Composition</span></span>

  <span data-ttu-id="138ef-116">Con el nuevo <xref:System.Windows.Media.BitmapCache> y <xref:System.Windows.Media.BitmapCacheBrush> clases, puede almacenar en caché una parte compleja del árbol visual como mapa de bits y mejorar considerablemente el tiempo de representación.</span><span class="sxs-lookup"><span data-stu-id="138ef-116">By using the new <xref:System.Windows.Media.BitmapCache> and <xref:System.Windows.Media.BitmapCacheBrush> classes, you can cache a complex part of the visual tree as a bitmap and greatly improve rendering time.</span></span> <span data-ttu-id="138ef-117">El mapa de bits sigue respondiendo a la entrada del usuario, como clics del mouse, y se puede pintar en otros elementos, exactamente igual que cualquier pincel.</span><span class="sxs-lookup"><span data-stu-id="138ef-117">The bitmap remains responsive to user input, such as mouse clicks, and you can paint it onto other elements just like any brush.</span></span>

- <span data-ttu-id="138ef-118">Compatibilidad con el sombreador de píxeles 3</span><span class="sxs-lookup"><span data-stu-id="138ef-118">Pixel Shader 3 Support</span></span>

  <span data-ttu-id="138ef-119">WPF 4 se basa en la parte superior de la <xref:System.Windows.Media.Effects.ShaderEffect> compatibilidad con introducida en WPF 3.5 SP1, permitiendo que las aplicaciones escriban efectos mediante el uso de sombreador de píxeles (PS) versión 3.0.</span><span class="sxs-lookup"><span data-stu-id="138ef-119">WPF 4 builds on top of the <xref:System.Windows.Media.Effects.ShaderEffect> support introduced in WPF 3.5 SP1 by allowing applications to write effects by using Pixel Shader (PS) version 3.0.</span></span> <span data-ttu-id="138ef-120">El modelo de sombreador PS 3.0 es más sofisticado que el PS 2.0, lo que permite incluso crear más efectos en hardware compatible.</span><span class="sxs-lookup"><span data-stu-id="138ef-120">The PS 3.0 shader model is more sophisticated than PS 2.0, which allows for even more effects on supported hardware.</span></span>

- <span data-ttu-id="138ef-121">Funciones de aceleración</span><span class="sxs-lookup"><span data-stu-id="138ef-121">Easing Functions</span></span>

  <span data-ttu-id="138ef-122">Puede mejorar las animaciones con funciones de aceleración que proporcionan mayor control sobre el comportamiento de las animaciones.</span><span class="sxs-lookup"><span data-stu-id="138ef-122">You can enhance animations with easing functions, which give you additional control over the behavior of animations.</span></span> <span data-ttu-id="138ef-123">Por ejemplo, puede aplicar un <xref:System.Windows.Media.Animation.ElasticEase> a una animación para darle un comportamiento elástico.</span><span class="sxs-lookup"><span data-stu-id="138ef-123">For example, you can apply an <xref:System.Windows.Media.Animation.ElasticEase> to an animation to give the animation a springy behavior.</span></span> <span data-ttu-id="138ef-124">Para obtener más información, vea los tipos de entradas y salidas lentas en el <xref:System.Windows.Media.Animation> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="138ef-124">For more information, see the easing types in the <xref:System.Windows.Media.Animation> namespace.</span></span>

<a name="graphics_and_rendering"></a>

## <a name="graphics-and-rendering"></a><span data-ttu-id="138ef-125">Gráficos y representación</span><span class="sxs-lookup"><span data-stu-id="138ef-125">Graphics and Rendering</span></span>

<span data-ttu-id="138ef-126">WPF incluye compatibilidad con gráficos 2D de alta calidad.</span><span class="sxs-lookup"><span data-stu-id="138ef-126">WPF includes support for high quality 2-D graphics.</span></span> <span data-ttu-id="138ef-127">La funcionalidad incluye pinceles, geometrías, imágenes, formas y transformaciones.</span><span class="sxs-lookup"><span data-stu-id="138ef-127">The functionality includes brushes, geometries, images, shapes and transformations.</span></span> <span data-ttu-id="138ef-128">Para más información, consulte [Graphics](graphics.md) (Gráficos).</span><span class="sxs-lookup"><span data-stu-id="138ef-128">For more information, see [Graphics](graphics.md).</span></span> <span data-ttu-id="138ef-129">La representación de los elementos gráficos se basa en el <xref:System.Windows.Media.Visual> clase.</span><span class="sxs-lookup"><span data-stu-id="138ef-129">The rendering of graphical elements is based on the <xref:System.Windows.Media.Visual> class.</span></span> <span data-ttu-id="138ef-130">La estructura de objetos visuales en la pantalla se describe en el árbol visual.</span><span class="sxs-lookup"><span data-stu-id="138ef-130">The structure of visual objects on the screen is described by the visual tree.</span></span> <span data-ttu-id="138ef-131">Para más información, consulte [Información general sobre la representación de gráficos en WPF](wpf-graphics-rendering-overview.md).</span><span class="sxs-lookup"><span data-stu-id="138ef-131">For more information, see [WPF Graphics Rendering Overview](wpf-graphics-rendering-overview.md).</span></span>

### <a name="2-d-shapes"></a><span data-ttu-id="138ef-132">Formas 2D</span><span class="sxs-lookup"><span data-stu-id="138ef-132">2-D Shapes</span></span>

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="138ef-133">ofrece una biblioteca de formas [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] comunes dibujadas mediante vectores, como los rectángulos y las elipses que se muestran en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="138ef-133">provides a library of commonly used, vector-drawn [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] shapes, such as rectangles and ellipses, which the following illustration shows.</span></span>

![Diagrama que muestra elipses y rectángulos.](./media/index/two-deminsional-shapes-ellipses-rectangles.png)

<span data-ttu-id="138ef-135">Estas formas intrínsecas de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] no son solo formas: son elementos programables que implementan muchas de las características que se esperan de los controles más comunes, entre los que se incluyen la entrada por mouse y teclado.</span><span class="sxs-lookup"><span data-stu-id="138ef-135">These intrinsic [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] shapes are not just shapes: they are programmable elements that implement many of the features that you expect from most common controls, which include keyboard and mouse input.</span></span> <span data-ttu-id="138ef-136">El ejemplo siguiente muestra cómo controlar el <xref:System.Windows.UIElement.MouseUp> eventos accionados al hacer clic una <xref:System.Windows.Shapes.Ellipse> elemento.</span><span class="sxs-lookup"><span data-stu-id="138ef-136">The following example shows how to handle the <xref:System.Windows.UIElement.MouseUp> event raised by clicking an <xref:System.Windows.Shapes.Ellipse> element.</span></span>

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

<span data-ttu-id="138ef-137">En la ilustración siguiente se muestra el resultado del anterior marcado y código [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] subyacente.</span><span class="sxs-lookup"><span data-stu-id="138ef-137">The following illustration shows the output for the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup and code-behind.</span></span>

![Un cuadro de mensaje que dice "¡You clicked la elipse!"](./media/index/messagebox-text-output.png)

<span data-ttu-id="138ef-139">Para obtener más información, consulte [Información general sobre formas y dibujo básico en WPF](shapes-and-basic-drawing-in-wpf-overview.md).</span><span class="sxs-lookup"><span data-stu-id="138ef-139">For more information, see [Shapes and Basic Drawing in WPF Overview](shapes-and-basic-drawing-in-wpf-overview.md).</span></span> <span data-ttu-id="138ef-140">Para obtener un ejemplo introductorio, vea [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037) (Ejemplo de elementos de forma).</span><span class="sxs-lookup"><span data-stu-id="138ef-140">For an introductory sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>

### <a name="2-d-geometries"></a><span data-ttu-id="138ef-141">Geometrías 2D</span><span class="sxs-lookup"><span data-stu-id="138ef-141">2-D Geometries</span></span>

<span data-ttu-id="138ef-142">Cuando las formas [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] que [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ofrece no sean suficientes, puede usar la compatibilidad con geometrías y trazados de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] para crear sus propias formas.</span><span class="sxs-lookup"><span data-stu-id="138ef-142">When the [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] shapes that [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] provides are not sufficient, you can use [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] support for geometries and paths to create your own.</span></span> <span data-ttu-id="138ef-143">En la ilustración siguiente se muestra cómo se pueden usar geometrías para crear formas, por ejemplo, un pincel de dibujo, y para recortar otros elementos [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="138ef-143">The following illustration shows how you can use geometries to create shapes, as a drawing brush, and to clip other [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] elements.</span></span>

![Captura de pantalla que muestra cómo puede usar geometrías para crear formas.](./media/index/use-geometries-create-shapes.png)

<span data-ttu-id="138ef-145">Para más información, consulte [Información general sobre geometría](geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="138ef-145">For more information, see [Geometry Overview](geometry-overview.md).</span></span> <span data-ttu-id="138ef-146">Para obtener un ejemplo introductorio, vea [Ejemplo de geometrías](https://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="138ef-146">For an introductory sample, see [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>

### <a name="2-d-effects"></a><span data-ttu-id="138ef-147">Efectos 2D</span><span class="sxs-lookup"><span data-stu-id="138ef-147">2-D Effects</span></span>

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="138ef-148">ofrece una biblioteca de clases [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] que puede usar para crear diversos efe efectos.</span><span class="sxs-lookup"><span data-stu-id="138ef-148">provides a library of [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] classes that you can use to create a variety of effects.</span></span> <span data-ttu-id="138ef-149">La funcionalidad de representación [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ofrece la posibilidad de pintar elementos de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que tengan degradados, mapas de bits, dibujos y vídeos; así como para manipularlos mediante rotación, escalado y sesgado.</span><span class="sxs-lookup"><span data-stu-id="138ef-149">The [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] rendering capability of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] provides the ability to paint [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements that have gradients, bitmaps, drawings, and videos; and to manipulate them by using rotation, scaling, and skewing.</span></span> <span data-ttu-id="138ef-150">En la ilustración siguiente se ofrece un ejemplo de los muchos efectos que puede lograr mediante pinceles de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="138ef-150">The following illustration gives an example of the many effects you can achieve by using [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] brushes.</span></span>

![Ilustración que muestra los elementos de pintura y diferentes pinceles WPF.](./media/index/brushes-paint-elements.png)

<span data-ttu-id="138ef-152">Para obtener más información, consulte [Información general sobre pinceles de WPF](wpf-brushes-overview.md).</span><span class="sxs-lookup"><span data-stu-id="138ef-152">For more information, see [WPF Brushes Overview](wpf-brushes-overview.md).</span></span> <span data-ttu-id="138ef-153">Para obtener un ejemplo introductorio, vea [Ejemplo de pinceles](https://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="138ef-153">For an introductory sample, see [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span>

<a name="rendering"></a>

## <a name="3-d-rendering"></a><span data-ttu-id="138ef-154">Representación 3D</span><span class="sxs-lookup"><span data-stu-id="138ef-154">3-D Rendering</span></span>

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="138ef-155">ofrece un conjunto de funciones de representación [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] que se integran con la compatibilidad de gráficos [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] para que cree un diseño, una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] y una visualización de datos más interesantes.</span><span class="sxs-lookup"><span data-stu-id="138ef-155">provides a set of [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] rendering capabilities that integrate with [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] graphics support in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] in order for you to create more exciting layout, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], and data visualization.</span></span> <span data-ttu-id="138ef-156">En un extremo del espectro, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] le permite representar imágenes [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] en las superficies de formas [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)], lo que se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="138ef-156">At one end of the spectrum, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] enables you to render [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] images onto the surfaces of [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] shapes, which the following illustration demonstrates.</span></span>

![Captura de pantalla de un ejemplo que muestra las formas 3D con texturas diferentes.](./media/index/visual-three-dimensional-shape.png)

<span data-ttu-id="138ef-158">Para obtener más información, consulte [Información general sobre gráficos 3D](3-d-graphics-overview.md).</span><span class="sxs-lookup"><span data-stu-id="138ef-158">For more information, see [3-D Graphics Overview](3-d-graphics-overview.md).</span></span> <span data-ttu-id="138ef-159">Para obtener un ejemplo introductorio, vea [3-D Solids Sample](https://go.microsoft.com/fwlink/?LinkID=159964) (Ejemplo de sólidos 3D).</span><span class="sxs-lookup"><span data-stu-id="138ef-159">For an introductory sample, see [3-D Solids Sample](https://go.microsoft.com/fwlink/?LinkID=159964).</span></span>

<a name="animation"></a>

## <a name="animation"></a><span data-ttu-id="138ef-160">Animación</span><span class="sxs-lookup"><span data-stu-id="138ef-160">Animation</span></span>

<span data-ttu-id="138ef-161">Use la animación para hacer que los controles y elementos crezcan, vibren, giren o se desvanezcan, crear atractivas transiciones de página y mucho más.</span><span class="sxs-lookup"><span data-stu-id="138ef-161">Use animation to make controls and elements grow, shake, spin, and fade; and to create interesting page transitions, and more.</span></span> <span data-ttu-id="138ef-162">Dado que [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] le permite animar la mayoría de las propiedades, no solo podrá animar la mayoría de los objetos [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], también podrá usar [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] para animar objetos personalizados que haya creado.</span><span class="sxs-lookup"><span data-stu-id="138ef-162">Because [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] enables you to animate most properties, not only can you animate most [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] objects, you can also use [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] to animate custom objects that you create.</span></span>

![Captura de pantalla de un cubo animado.](./media/index/animate-custom-objects.png)

<span data-ttu-id="138ef-164">Para obtener más información, consulte [Información general sobre animaciones](animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="138ef-164">For more information, see [Animation Overview](animation-overview.md).</span></span> <span data-ttu-id="138ef-165">Para obtener un ejemplo introductorio, vea [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969) (Galería de ejemplos de animación).</span><span class="sxs-lookup"><span data-stu-id="138ef-165">For an introductory sample, see [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span></span>

<a name="media"></a>

## <a name="media"></a><span data-ttu-id="138ef-166">Multimedia</span><span class="sxs-lookup"><span data-stu-id="138ef-166">Media</span></span>

<span data-ttu-id="138ef-167">Las imágenes, el vídeo y el audio son maneras de ofrecer experiencias de usuario e información con mucho contenido multimedia.</span><span class="sxs-lookup"><span data-stu-id="138ef-167">Images, video, and audio are media-rich ways of conveying information and user experiences.</span></span>

### <a name="images"></a><span data-ttu-id="138ef-168">Imágenes</span><span class="sxs-lookup"><span data-stu-id="138ef-168">Images</span></span>

<span data-ttu-id="138ef-169">Las imágenes, que incluyen iconos, fondos e incluso partes de animaciones, constituyen una pieza esencial de la mayoría de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="138ef-169">Images, which include icons, backgrounds, and even parts of animations, are a core part of most applications.</span></span> <span data-ttu-id="138ef-170">Dado que frecuentemente tendrá que usar imágenes, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] presenta la posibilidad de trabajar con ellas de diversas maneras.</span><span class="sxs-lookup"><span data-stu-id="138ef-170">Because you frequently need to use images, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] exposes the ability to work with them in a variety of ways.</span></span> <span data-ttu-id="138ef-171">En la ilustración siguiente se muestra tan solo una de esas maneras.</span><span class="sxs-lookup"><span data-stu-id="138ef-171">The following illustration shows just one of those ways.</span></span>

<span data-ttu-id="138ef-172">![Captura de pantalla de ejemplo de aplicación de estilos](../controls/./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span><span class="sxs-lookup"><span data-stu-id="138ef-172">![Styling sample screenshot](../controls/./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span></span>

<span data-ttu-id="138ef-173">Para obtener más información, consulte [Información general sobre imágenes](imaging-overview.md).</span><span class="sxs-lookup"><span data-stu-id="138ef-173">For more information, see [Imaging Overview](imaging-overview.md).</span></span>

### <a name="video-and-audio"></a><span data-ttu-id="138ef-174">Vídeo y audio</span><span class="sxs-lookup"><span data-stu-id="138ef-174">Video and Audio</span></span>

<span data-ttu-id="138ef-175">Una característica fundamental de la funcionalidad de gráficos de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] es que ofrece compatibilidad nativa para trabajar con multimedia, lo que incluye vídeo y audio.</span><span class="sxs-lookup"><span data-stu-id="138ef-175">A core feature of the graphics capabilities of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] is to provide native support for working with multimedia, which includes video and audio.</span></span> <span data-ttu-id="138ef-176">En el siguiente ejemplo se muestra cómo insertar un reproductor multimedia en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="138ef-176">The following example shows how to insert a media player into an application.</span></span>

```xaml
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />
```

<span data-ttu-id="138ef-177"><xref:System.Windows.Controls.MediaElement> es capaz de reproducir vídeo y audio y es lo suficientemente extensible como para permitir la creación sencilla de personalizado [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)].</span><span class="sxs-lookup"><span data-stu-id="138ef-177"><xref:System.Windows.Controls.MediaElement> is capable of playing both video and audio, and is extensible enough to allow the easy creation of custom [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)].</span></span>

<span data-ttu-id="138ef-178">Para más información, consulte [Información general sobre multimedia](multimedia-overview.md).</span><span class="sxs-lookup"><span data-stu-id="138ef-178">For more information, see the [Multimedia Overview](multimedia-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="138ef-179">Vea también</span><span class="sxs-lookup"><span data-stu-id="138ef-179">See also</span></span>

- <xref:System.Windows.Media>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Media3D>
- [<span data-ttu-id="138ef-180">Imágenes y gráficos 2D</span><span class="sxs-lookup"><span data-stu-id="138ef-180">2D Graphics and Imaging</span></span>](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="138ef-181">Información general sobre formas y dibujo básico en WPF</span><span class="sxs-lookup"><span data-stu-id="138ef-181">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="138ef-182">Información general sobre el dibujo con colores sólidos y degradados</span><span class="sxs-lookup"><span data-stu-id="138ef-182">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="138ef-183">Pintar con imágenes, dibujos y elementos visuales</span><span class="sxs-lookup"><span data-stu-id="138ef-183">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="138ef-184">Temas de procedimientos de temporización y animación</span><span class="sxs-lookup"><span data-stu-id="138ef-184">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="138ef-185">Información general sobre gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="138ef-185">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="138ef-186">Información general sobre multimedia</span><span class="sxs-lookup"><span data-stu-id="138ef-186">Multimedia Overview</span></span>](multimedia-overview.md)
