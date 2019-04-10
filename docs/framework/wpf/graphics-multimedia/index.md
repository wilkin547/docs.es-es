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
ms.openlocfilehash: c9ddc1a1060b7d70ee7a6c9050971709a433961a
ms.sourcegitcommit: d21bee9dbd32b9540ad30f9d0e2e874227040be3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59427206"
---
# <a name="graphics-and-multimedia"></a>Gráficos y multimedia
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona compatibilidad para la creación de contenido, lo que facilita a los desarrolladores compilar contenido e interfaces de usuario interesantes, gráficos vectoriales, animación y multimedia. Con [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], se pueden crear gráficos vectoriales o animaciones complejas e integrar elementos multimedia en las aplicaciones.  
  
 En este tema se presentan las características de gráficos, animaciones y elementos multimedia de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], que le permiten agregar gráficos, efectos de transición, sonido y vídeo a las aplicaciones.  
  
> [!NOTE]
>  Se desaconseja totalmente el uso de tipos WPF en un servicio de Windows. Si intenta usar tipos WPF en un servicio de Windows, puede que el servicio no funcione como se espera.   
  
<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>   
## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a>Novedades de gráficos y multimedia en WPF 4  
 Se han efectuado varios cambios relacionados con los gráficos y animaciones.  
  
-   Redondeo del diseño  
  
     Cuando el borde de un objeto queda en medio de un dispositivo de píxeles, el sistema de gráficos independiente de los ppp puede crear artefactos de representación tales como bordes borrosos o semitransparentes. Versiones anteriores de WPF incluían el ajuste de píxeles para ayudar a controlar este caso. Silverlight 2 introdujo el redondeo del diseño, que es otra manera de mover elementos para que los bordes queden dentro de límites de píxeles enteros. WPF admite ahora el redondeo del diseño con el <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> de la propiedad adjunta <xref:System.Windows.FrameworkElement>.  
  
-   Composición almacenada en caché  
  
     Con el nuevo <xref:System.Windows.Media.BitmapCache> y <xref:System.Windows.Media.BitmapCacheBrush> clases, puede almacenar en caché una parte compleja del árbol visual como mapa de bits y mejorar considerablemente el tiempo de representación. El mapa de bits sigue respondiendo a la entrada del usuario, como clics del mouse, y se puede pintar en otros elementos, exactamente igual que cualquier pincel.  
  
-   Compatibilidad con el sombreador de píxeles 3  
  
     WPF 4 se basa en la parte superior de la <xref:System.Windows.Media.Effects.ShaderEffect> compatibilidad con introducida en WPF 3.5 SP1, permitiendo que las aplicaciones escriban efectos mediante el uso de sombreador de píxeles (PS) versión 3.0. El modelo de sombreador PS 3.0 es más sofisticado que el PS 2.0, lo que permite incluso crear más efectos en hardware compatible.  
  
-   Funciones de aceleración  
  
     Puede mejorar las animaciones con funciones de aceleración que proporcionan mayor control sobre el comportamiento de las animaciones. Por ejemplo, puede aplicar un <xref:System.Windows.Media.Animation.ElasticEase> a una animación para darle un comportamiento elástico. Para obtener más información, vea los tipos de entradas y salidas lentas en el <xref:System.Windows.Media.Animation> espacio de nombres.  
  
<a name="graphics_and_rendering"></a>   
## <a name="graphics-and-rendering"></a>Gráficos y representación  
 WPF incluye compatibilidad con gráficos 2D de alta calidad. La funcionalidad incluye pinceles, geometrías, imágenes, formas y transformaciones. Para más información, consulte [Graphics](graphics.md) (Gráficos). La representación de los elementos gráficos se basa en el <xref:System.Windows.Media.Visual> clase. La estructura de objetos visuales en la pantalla se describe en el árbol visual. Para más información, consulte [Información general sobre la representación de gráficos en WPF](wpf-graphics-rendering-overview.md).  
  
### <a name="2-d-shapes"></a>Formas 2D  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Proporciona una biblioteca de uso común, dibujadas mediante vectores [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] formas, como rectángulos y elipses que se muestra en la siguiente ilustración.  
  
 ![Diagrama que muestra elipses y rectángulos.](./media/index/two-deminsional-shapes-ellipses-rectangles.png)  
  
 Estas formas intrínsecas de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] no son solo formas: son elementos programables que implementan muchas de las características que se esperan de los controles más comunes, entre los que se incluyen la entrada por mouse y teclado. El ejemplo siguiente muestra cómo controlar el <xref:System.Windows.UIElement.MouseUp> eventos accionados al hacer clic una <xref:System.Windows.Shapes.Ellipse> elemento.  
  
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
  
 ![Un cuadro de mensaje que dice "¡You clicked la elipse!"](./media/index/messagebox-text-output.png)  
  
 Para obtener más información, consulte [Información general sobre formas y dibujo básico en WPF](shapes-and-basic-drawing-in-wpf-overview.md). Para obtener un ejemplo introductorio, vea [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037) (Ejemplo de elementos de forma).  
  
### <a name="2-d-geometries"></a>Geometrías 2D  
 Cuando las formas [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] que [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ofrece no sean suficientes, puede usar la compatibilidad con geometrías y trazados de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] para crear sus propias formas. En la ilustración siguiente se muestra cómo se pueden usar geometrías para crear formas, por ejemplo, un pincel de dibujo, y para recortar otros elementos [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 ![Captura de pantalla que muestra cómo puede usar geometrías para crear formas.](./media/index/use-geometries-create-shapes.png)  
  
 Para más información, consulte [Información general sobre geometría](geometry-overview.md). Para obtener un ejemplo introductorio, vea [Ejemplo de geometrías](https://go.microsoft.com/fwlink/?LinkID=159989).  
  
### <a name="2-d-effects"></a>Efectos 2D  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Proporciona una biblioteca de [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] clases que puede usar para crear una variedad de efectos. La funcionalidad de representación [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ofrece la posibilidad de pintar elementos de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que tengan degradados, mapas de bits, dibujos y vídeos; así como para manipularlos mediante rotación, escalado y sesgado. En la ilustración siguiente se ofrece un ejemplo de los muchos efectos que puede lograr mediante pinceles de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 ![Ilustración que muestra los elementos de pintura y diferentes pinceles WPF.](./media/index/brushes-paint-elements.png)  
  
 Para obtener más información, consulte [Información general sobre pinceles de WPF](wpf-brushes-overview.md). Para obtener un ejemplo introductorio, vea [Ejemplo de pinceles](https://go.microsoft.com/fwlink/?LinkID=159973).  
  
<a name="rendering"></a>   
## <a name="3-d-rendering"></a>Representación 3D  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Proporciona un conjunto de [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] capacidades de representación que se integran con [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] compatibilidad con gráficos en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] en orden para crear el diseño más emocionante, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]y visualización de datos. En un extremo del espectro, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] le permite representar imágenes [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] en las superficies de formas [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)], lo que se muestra en la siguiente ilustración.  
  

 ![Captura de pantalla de un ejemplo que muestra las formas 3D con texturas diferentes.](./media/index/visual-three-dimensional-shape.png)  
  
 Para obtener más información, consulte [Información general sobre gráficos 3D](3-d-graphics-overview.md). Para obtener un ejemplo introductorio, vea [3-D Solids Sample](https://go.microsoft.com/fwlink/?LinkID=159964) (Ejemplo de sólidos 3D).  
  
<a name="animation"></a>   
## <a name="animation"></a>Animación  
 Use la animación para hacer que los controles y elementos crezcan, vibren, giren o se desvanezcan, crear atractivas transiciones de página y mucho más. Dado que [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] le permite animar la mayoría de las propiedades, no solo podrá animar la mayoría de los objetos [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], también podrá usar [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] para animar objetos personalizados que haya creado.  
  
 ![Captura de pantalla de un cubo animado.](./media/index/animate-custom-objects.png)  
  
 Para obtener más información, consulte [Información general sobre animaciones](animation-overview.md). Para obtener un ejemplo introductorio, vea [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969) (Galería de ejemplos de animación).  
  
<a name="media"></a>   
## <a name="media"></a>Multimedia  
 Las imágenes, el vídeo y el audio son maneras de ofrecer experiencias de usuario e información con mucho contenido multimedia.  
  
### <a name="images"></a>Imágenes  
 Las imágenes, que incluyen iconos, fondos e incluso partes de animaciones, constituyen una pieza esencial de la mayoría de las aplicaciones. Dado que frecuentemente tendrá que usar imágenes, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] presenta la posibilidad de trabajar con ellas de diversas maneras. En la ilustración siguiente se muestra tan solo una de esas maneras.  
  
 ![Captura de pantalla de ejemplo de aplicación de estilos](../controls/./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")  
  
 Para obtener más información, consulte [Información general sobre imágenes](imaging-overview.md).  
  
### <a name="video-and-audio"></a>Vídeo y audio  
 Una característica fundamental de la funcionalidad de gráficos de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] es que ofrece compatibilidad nativa para trabajar con multimedia, lo que incluye vídeo y audio. En el siguiente ejemplo se muestra cómo insertar un reproductor multimedia en una aplicación.  
  
```xaml  
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />  
```  
  
 <xref:System.Windows.Controls.MediaElement> es capaz de reproducir vídeo y audio y es lo suficientemente extensible como para permitir la creación sencilla de personalizado [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)].  
  
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
