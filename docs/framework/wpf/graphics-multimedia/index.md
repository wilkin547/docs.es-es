---
title: Gráficos y multimedia
description: Descubra las características multimedia de Windows Presentation Foundation (WPF). Agregue gráficos, efectos de transición, sonido y vídeo a sus aplicaciones.
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
ms.openlocfilehash: ba52e78564484f7714ab0035a5e1861766b72bbf
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853681"
---
# <a name="graphics-and-multimedia"></a>Gráficos y multimedia

<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ofrece compatibilidad con multimedia, gráficos vectoriales, animaciones y creación de contenido, lo que permite a los desarrolladores crear fácilmente interfaces de usuario y contenido interesantes. Con Visual Studio, puede crear gráficos vectoriales o animaciones complejas e integrar los elementos multimedia en las aplicaciones.

En este tema se presentan las características de gráficos, animaciones y elementos multimedia de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], que le permiten agregar gráficos, efectos de transición, sonido y vídeo a las aplicaciones.

> [!NOTE]
> Se recomienda encarecidamente no usar los tipos WPF en un servicio de Windows. Si intenta usar tipos WPF en un servicio de Windows, puede que el servicio no funcione como se espera.

<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>

## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a>Novedades de gráficos y multimedia en WPF 4

Se han efectuado varios cambios relacionados con los gráficos y animaciones.

- Redondeo del diseño

  Cuando el borde de un objeto queda en medio de un dispositivo de píxeles, el sistema de gráficos independiente de los ppp puede crear artefactos de representación tales como bordes borrosos o semitransparentes. Versiones anteriores de WPF incluían el ajuste de píxeles para ayudar a controlar este caso. Silverlight 2 introdujo el redondeo del diseño, que es otra manera de mover elementos para que los bordes queden dentro de límites de píxeles enteros. WPF admite ahora el redondeo del diseño con la <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> propiedad adjunta en <xref:System.Windows.FrameworkElement> .

- Composición almacenada en caché

  Mediante el uso de las nuevas <xref:System.Windows.Media.BitmapCache> <xref:System.Windows.Media.BitmapCacheBrush> clases y, puede almacenar en caché una parte compleja del árbol visual como un mapa de bits y mejorar considerablemente el tiempo de representación. El mapa de bits sigue respondiendo a la entrada del usuario, como clics del mouse, y se puede pintar en otros elementos, exactamente igual que cualquier pincel.

- Compatibilidad con el sombreador de píxeles 3

  WPF 4 se basa en la <xref:System.Windows.Media.Effects.ShaderEffect> compatibilidad introducida en wpf 3,5 SP1 al permitir que las aplicaciones escriban efectos mediante el sombreador de píxeles (PS) versión 3,0. El modelo de sombreador PS 3.0 es más sofisticado que el PS 2.0, lo que permite incluso crear más efectos en hardware compatible.

- Funciones de aceleración

  Puede mejorar las animaciones con funciones de aceleración que proporcionan mayor control sobre el comportamiento de las animaciones. Por ejemplo, puede aplicar <xref:System.Windows.Media.Animation.ElasticEase> a una animación para dar un comportamiento elástico a la animación. Para obtener más información, vea los tipos de aceleración en el <xref:System.Windows.Media.Animation> espacio de nombres.

<a name="graphics_and_rendering"></a>

## <a name="graphics-and-rendering"></a>Gráficos y representación

WPF incluye compatibilidad con gráficos 2D de alta calidad. La funcionalidad incluye pinceles, geometrías, imágenes, formas y transformaciones. Para más información, consulte [Graphics](graphics.md) (Gráficos). La representación de elementos gráficos se basa en la <xref:System.Windows.Media.Visual> clase. La estructura de objetos visuales en la pantalla se describe en el árbol visual. Para más información, consulte [Información general sobre la representación de gráficos en WPF](wpf-graphics-rendering-overview.md).

### <a name="2d-shapes"></a>Formas 2D

WPF proporciona una biblioteca de formas 2D dibujadas con más frecuencia, como rectángulos y elipses, que se muestran en la siguiente ilustración.

![Diagrama que muestra puntos suspensivos y rectángulos.](./media/index/two-deminsional-shapes-ellipses-rectangles.png)

Estas formas intrínsecas de WPF no son solo formas: son elementos programables que implementan muchas de las características que se esperan de los controles más comunes, entre los que se incluyen la entrada del mouse y del teclado. En el ejemplo siguiente se muestra cómo controlar el evento que se <xref:System.Windows.UIElement.MouseUp> genera al hacer clic en un <xref:System.Windows.Shapes.Ellipse> elemento.

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

![Un cuadro de mensaje que indica "hizo clic en la elipse!"](./media/index/messagebox-text-output.png)

Para obtener más información, consulte [Información general sobre formas y dibujo básico en WPF](shapes-and-basic-drawing-in-wpf-overview.md). Para obtener un ejemplo introductorio, vea [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements) (Ejemplo de elementos de forma).

### <a name="2d-geometries"></a>Geometrías 2D

Cuando las formas 2D que proporciona WPF no son suficientes, puede usar la compatibilidad de WPF con las geometrías y las rutas de acceso para crear las suyas propias. En la ilustración siguiente se muestra cómo puede utilizar las geometrías para crear formas, como un pincel de dibujo, y para recortar otros elementos de WPF.

![Captura de pantalla que muestra cómo se pueden usar las geometrías para crear formas.](./media/index/use-geometries-create-shapes.png)

Para obtener más información, vea [información general sobre geometría](geometry-overview.md). Para obtener un ejemplo introductorio, vea [Ejemplo de geometrías](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).

### <a name="2d-effects"></a>Efectos 2D

WPF proporciona una biblioteca de clases 2D que puede usar para crear una gran variedad de efectos. La capacidad de representación en 2D de WPF proporciona la capacidad de pintar [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementos que tienen degradados, mapas de bits, dibujos y vídeos, y para manipularlos mediante la rotación, el escalado y el sesgo. En la ilustración siguiente se proporciona un ejemplo de los muchos efectos que puede lograr mediante el uso de pinceles de WPF.

![Ilustración que muestra los diferentes pinceles y elementos de dibujo de WPF.](./media/index/brushes-paint-elements.png)

Para obtener más información, vea [información general sobre pinceles de WPF](wpf-brushes-overview.md). Para obtener un ejemplo introductorio, vea [Ejemplo de pinceles](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).

<a name="rendering"></a>

## <a name="3d-rendering"></a>Representación en 3D

WPF proporciona un conjunto de capacidades de representación en 3D que se integran con la compatibilidad con gráficos 2D en WPF para que pueda crear un diseño, y visualización de datos más emocionantes [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] . En un extremo del espectro, WPF permite representar imágenes 2D en las superficies de las formas 3D, que se muestran en la siguiente ilustración.

![Captura de pantalla de un ejemplo que muestra formas 3D con texturas diferentes.](./media/index/visual-three-dimensional-shape.png)

Para obtener más información, consulte [información general sobre gráficos 3D](3-d-graphics-overview.md). Para obtener un ejemplo introductorio, vea [ejemplo de sólidos 3D](https://go.microsoft.com/fwlink/?LinkID=159964).

<a name="animation"></a>

## <a name="animation"></a>Animación

Use la animación para hacer que los controles y elementos crezcan, vibren, giren o se desvanezcan, crear atractivas transiciones de página y mucho más. Dado que WPF permite animar la mayoría de las propiedades, no solo puede animar la mayoría de los objetos de WPF, sino que también puede usar WPF para animar objetos personalizados que cree.

![Captura de pantalla de un cubo animado.](./media/index/animate-custom-objects.png)

Para obtener más información, vea [información general sobre animaciones](animation-overview.md). Para obtener un ejemplo introductorio, vea [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples) (Galería de ejemplos de animación).

<a name="media"></a>

## <a name="media"></a>Multimedia

Las imágenes, el vídeo y el audio son maneras de ofrecer experiencias de usuario e información con mucho contenido multimedia.

### <a name="images"></a>Imágenes

Las imágenes, que incluyen iconos, fondos e incluso partes de animaciones, constituyen una pieza esencial de la mayoría de las aplicaciones. Como a menudo necesita usar imágenes, WPF expone la capacidad de trabajar con ellas de varias maneras. En la ilustración siguiente se muestra tan solo una de esas maneras.

![Captura de pantalla de ejemplo de aplicación de estilo](../controls/media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")

Para obtener más información, vea [información general sobre imágenes](imaging-overview.md).

### <a name="video-and-audio"></a>Vídeo y audio

Una característica fundamental de las capacidades de gráficos de WPF es proporcionar compatibilidad nativa para trabajar con multimedia, que incluye vídeo y audio. En el siguiente ejemplo se muestra cómo insertar un reproductor multimedia en una aplicación.

```xaml
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />
```

<xref:System.Windows.Controls.MediaElement>es capaz de reproducir vídeo y audio, y es lo suficientemente extensible como para permitir la creación sencilla de interfaces de IU personalizadas.

Para más información, consulte [Información general sobre multimedia](multimedia-overview.md).

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Media3D>
- [Imágenes y gráficos 2D](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Información general sobre formas y dibujo básico en WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Información general sobre el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md)
- [Pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md)
- [Temas "Cómo..." de animación y control de tiempo](animation-and-timing-how-to-topics.md)
- [Información general sobre gráficos 3D](3-d-graphics-overview.md)
- [Información general sobre multimedia](multimedia-overview.md)
