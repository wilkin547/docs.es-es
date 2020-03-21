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
# <a name="graphics-and-multimedia"></a>Gráficos y multimedia

<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ofrece compatibilidad con multimedia, gráficos vectoriales, animaciones y creación de contenido, lo que permite a los desarrolladores crear fácilmente interfaces de usuario y contenido interesantes. Con Visual Studio, puede crear gráficos vectoriales o animaciones complejas e integrar medios en las aplicaciones.

En este tema se presentan las características de gráficos, animaciones y elementos multimedia de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], que le permiten agregar gráficos, efectos de transición, sonido y vídeo a las aplicaciones.

> [!NOTE]
> Se recomienda encarecidamente no usar los tipos WPF en un servicio de Windows. Si intenta usar tipos WPF en un servicio de Windows, puede que el servicio no funcione como se espera.

<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>

## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a>Novedades de gráficos y multimedia en WPF 4

Se han efectuado varios cambios relacionados con los gráficos y animaciones.

- Redondeo del diseño

  Cuando el borde de un objeto queda en medio de un dispositivo de píxeles, el sistema de gráficos independiente de los ppp puede crear artefactos de representación tales como bordes borrosos o semitransparentes. Versiones anteriores de WPF incluían el ajuste de píxeles para ayudar a controlar este caso. Silverlight 2 introdujo el redondeo del diseño, que es otra manera de mover elementos para que los bordes queden dentro de límites de píxeles enteros. WPFWPF ahora admite el <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> redondeo <xref:System.Windows.FrameworkElement>de diseño con la propiedad adjunta en .

- Composición almacenada en caché

  Mediante el <xref:System.Windows.Media.BitmapCache> uso <xref:System.Windows.Media.BitmapCacheBrush> de las clases new y, puede almacenar en caché una parte compleja del árbol visual como un mapa de bits y mejorar en gran medida el tiempo de representación. El mapa de bits sigue respondiendo a la entrada del usuario, como clics del mouse, y se puede pintar en otros elementos, exactamente igual que cualquier pincel.

- Compatibilidad con el sombreador de píxeles 3

  WPF 4 se basa <xref:System.Windows.Media.Effects.ShaderEffect> en la compatibilidad introducida en WPF 3.5 SP1 al permitir que las aplicaciones escriban efectos mediante la versión 3.0 del sombreador de píxeles (PS). El modelo de sombreador PS 3.0 es más sofisticado que el PS 2.0, lo que permite incluso crear más efectos en hardware compatible.

- Funciones de aceleración

  Puede mejorar las animaciones con funciones de aceleración que proporcionan mayor control sobre el comportamiento de las animaciones. Por ejemplo, puede <xref:System.Windows.Media.Animation.ElasticEase> aplicar un a una animación para dar a la animación un comportamiento elástico. Para obtener más información, consulte los <xref:System.Windows.Media.Animation> tipos de conexión de espacio de nombres.

<a name="graphics_and_rendering"></a>

## <a name="graphics-and-rendering"></a>Gráficos y representación

WPFWPF incluye compatibilidad con gráficos 2D de alta calidad. La funcionalidad incluye pinceles, geometrías, imágenes, formas y transformaciones. Para más información, consulte [Graphics](graphics.md) (Gráficos). La representación de elementos <xref:System.Windows.Media.Visual> gráficos se basa en la clase. La estructura de objetos visuales en la pantalla se describe en el árbol visual. Para más información, consulte [Información general sobre la representación de gráficos en WPF](wpf-graphics-rendering-overview.md).

### <a name="2d-shapes"></a>Formas 2D

WPFWPF proporciona una biblioteca de formas 2D dibujadas por vectores de uso común, como rectángulos y elipses, que se muestra en la siguiente ilustración.

![Diagrama que muestra elipses y rectángulos.](./media/index/two-deminsional-shapes-ellipses-rectangles.png)

Estas formas intrínsecas de WPFWPF no son solo formas: son elementos programables que implementan muchas de las características que se esperan de los controles más comunes, que incluyen entrada de teclado y mouse. En el ejemplo siguiente <xref:System.Windows.UIElement.MouseUp> se muestra cómo controlar <xref:System.Windows.Shapes.Ellipse> el evento generado haciendo clic en un elemento.

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

En la ilustración siguiente se muestra el resultado del anterior marcado y código [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] subyacente.

![Un cuadro de mensaje que dice "¡Hiciste clic en la elipse!"](./media/index/messagebox-text-output.png)

Para obtener más información, consulte [Información general sobre formas y dibujo básico en WPF](shapes-and-basic-drawing-in-wpf-overview.md). Para obtener un ejemplo introductorio, vea [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements) (Ejemplo de elementos de forma).

### <a name="2d-geometries"></a>Geometrías 2D

Cuando las formas 2D que WPFWPF proporciona no son suficientes, puede usar la compatibilidad de WPFWPF para geometrías y rutas de acceso para crear su propia. En la siguiente ilustración se muestra cómo puede usar geometrías para crear formas, como un pincel de dibujo y para recortar otros elementos WPFWPF.

![Captura de pantalla que muestra cómo puede utilizar geometrías para crear formas.](./media/index/use-geometries-create-shapes.png)

Para obtener más información, consulte [Información general sobre geometría](geometry-overview.md). Para obtener un ejemplo introductorio, vea [Ejemplo de geometrías](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).

### <a name="2d-effects"></a>Efectos 2D

WPFWPF proporciona una biblioteca de clases 2D que puede usar para crear una variedad de efectos. La capacidad de representación 2D [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de WPFWPF proporciona la capacidad de pintar elementos que tienen degradados, mapas de bits, dibujos y vídeos; y manipularlos mediante la rotación, el escalado y el sesgo. En la siguiente ilustración se muestra un ejemplo de los muchos efectos que puede lograr mediante el uso de pinceles WPFWPF.

![Ilustración que muestra los diferentes elementos de WPFWPF y elementos de pintura.](./media/index/brushes-paint-elements.png)

Para obtener más información, vea [Información general sobre pinceles de WPF](wpf-brushes-overview.md). Para obtener un ejemplo introductorio, vea [Ejemplo de pinceles](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).

<a name="rendering"></a>

## <a name="3d-rendering"></a>Renderizado 3D

WPFWPF proporciona un conjunto de capacidades de representación 3D que se integran [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]con compatibilidad con gráficos 2D en WPFWPF para que pueda crear un diseño más emocionante y visualización de datos. En un extremo del espectro, WPFWPF permite representar imágenes 2D en las superficies de formas 3D, que se muestra en la siguiente ilustración.

![Captura de pantalla de una muestra que muestra formas 3D con diferentes texturas.](./media/index/visual-three-dimensional-shape.png)

Para obtener más información, consulte [Información general sobre gráficos 3D](3-d-graphics-overview.md). Para obtener una muestra introductoria, consulte [3D Solids Sample](https://go.microsoft.com/fwlink/?LinkID=159964).

<a name="animation"></a>

## <a name="animation"></a>Animación

Use la animación para hacer que los controles y elementos crezcan, vibren, giren o se desvanezcan, crear atractivas transiciones de página y mucho más. Dado que WPFWPF permite animar la mayoría de las propiedades, no solo puede animar la mayoría de los objetos WPFWPF, también puede usar WPFWPF para animar los objetos personalizados que cree.

![Captura de pantalla de un cubo animado.](./media/index/animate-custom-objects.png)

Para obtener más información, consulte [Información general sobre animaciones](animation-overview.md). Para obtener un ejemplo introductorio, vea [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples) (Galería de ejemplos de animación).

<a name="media"></a>

## <a name="media"></a>Multimedia

Las imágenes, el vídeo y el audio son maneras de ofrecer experiencias de usuario e información con mucho contenido multimedia.

### <a name="images"></a>Imágenes

Las imágenes, que incluyen iconos, fondos e incluso partes de animaciones, constituyen una pieza esencial de la mayoría de las aplicaciones. Dado que con frecuencia necesita usar imágenes, WPFWPF expone la capacidad de trabajar con ellos de varias maneras. En la ilustración siguiente se muestra tan solo una de esas maneras.

![Captura de pantalla de ejemplo de estilo](../controls/./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")

Para obtener más información, consulte [Información general sobre imágenes](imaging-overview.md).

### <a name="video-and-audio"></a>Vídeo y audio

Una característica principal de las capacidades gráficas de WPFWPF es proporcionar compatibilidad nativa para trabajar con multimedia, que incluye vídeo y audio. En el siguiente ejemplo se muestra cómo insertar un reproductor multimedia en una aplicación.

```xaml
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />
```

<xref:System.Windows.Controls.MediaElement>es capaz de reproducir vídeo y audio, y es lo suficientemente extensible como para permitir la fácil creación de ui personalizadas.

Para más información, consulte [Información general sobre multimedia](multimedia-overview.md).

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Media3D>
- [Imágenes y gráficos 2D](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Información general sobre formas y dibujo básico en WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Información general sobre el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md)
- [Pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md)
- [Temas "Cómo..." de animación y control de tiempo](animation-and-timing-how-to-topics.md)
- [Descripción general de los gráficos 3D](3-d-graphics-overview.md)
- [Información general sobre multimedia](multimedia-overview.md)
