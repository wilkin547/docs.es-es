---
title: "Gráficos y multimedia | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-4.6
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- media, features
- video effects
- sound effects
- animation, features
- graphics features
- transition effects
ms.assetid: 1817d9dc-3d6c-46cb-afc8-63b0bae35e37
caps.latest.revision: 30
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: c50b3e328998b65ec47efe6d7457b36116813c77
ms.openlocfilehash: ea78944133412f43075d8d094cd5fa93685299f9
ms.lasthandoff: 04/08/2017

---
# <a name="graphics-and-multimedia"></a>Gráficos y multimedia
<a name="introduction"></a> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ofrece compatibilidad con multimedia, gráficos vectoriales, animaciones y creación de contenido, lo que permite a los desarrolladores crear fácilmente interfaces de usuario y contenido interesantes. Con [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], se pueden crear gráficos vectoriales o animaciones complejas e integrar elementos multimedia en las aplicaciones.  
  
 En este tema se presentan las características de gráficos, animaciones y elementos multimedia de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], que le permiten agregar gráficos, efectos de transición, sonido y vídeo a las aplicaciones.  
  
> [!NOTE]
<<<<<<< HEAD
>  Se desaconseja totalmente el uso de tipos WPF en un servicio de Windows. Si intenta usar tipos WPF en un servicio de Windows, puede que el servicio no funcione como se espera.   
=======
>  Se recomienda encarecidamente no usar los tipos WPF en un servicio de Windows.  Si intenta utilizar los tipos WPF en un servicio de Windows, el servicio podría no funcionar como se espera.  
  
   
>>>>>>> 762af8e... fix build error
  
<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>   
## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a>Novedades de gráficos y multimedia en WPF 4  
 Se han efectuado varios cambios relacionados con los gráficos y animaciones.  
  
-   Redondeo del diseño  
  
     Cuando el borde de un objeto queda en medio de un dispositivo de píxeles, el sistema de gráficos independiente de los ppp puede crear artefactos de representación tales como bordes borrosos o semitransparentes. Versiones anteriores de WPF incluían el ajuste de píxeles para ayudar a controlar este caso. Silverlight 2 introdujo el redondeo del diseño, que es otra manera de mover elementos para que los bordes queden dentro de límites de píxeles enteros. WPF admite ahora el redondeo del diseño con la propiedad adjunta <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> en <xref:System.Windows.FrameworkElement>.  
  
-   Composición almacenada en caché  
  
     Con las nuevas clase <xref:System.Windows.Media.BitmapCache> y <xref:System.Windows.Media.BitmapCacheBrush>, puede almacenar en caché una parte compleja del árbol visual como mapa de bits y mejorar considerablemente el tiempo de representación. El mapa de bits sigue respondiendo a la entrada del usuario, como clics del mouse, y se puede pintar en otros elementos, exactamente igual que cualquier pincel.  
  
-   Compatibilidad con el sombreador de píxeles 3  
  
     WPF 4 se basa en la compatibilidad con el <xref:System.Windows.Media.Effects.ShaderEffect> presentado en WPF 3.5 SP1, lo que permite que las aplicaciones escriban efectos mediante el sombreador de píxeles (PS) versión 3.0. El modelo de sombreador PS 3.0 es más sofisticado que el PS 2.0, lo que permite incluso crear más efectos en hardware compatible.  
  
-   Funciones de aceleración  
  
     Puede mejorar las animaciones con funciones de aceleración que proporcionan mayor control sobre el comportamiento de las animaciones. Por ejemplo, puede aplicar un <xref:System.Windows.Media.Animation.ElasticEase> a una animación para darle un comportamiento elástico. Para más información, consulte los tipos de aceleración del espacio de nombres <xref:System.Windows.Media.Animation>.  
  
<a name="graphics_and_rendering"></a>   
## <a name="graphics-and-rendering"></a>Gráficos y representación  
 WPF incluye compatibilidad con gráficos 2D de alta calidad. La funcionalidad incluye pinceles, geometrías, imágenes, formas y transformaciones. Para más información, consulte [Graphics](../../../../docs/framework/wpf/graphics-multimedia/graphics.md) (Gráficos). La representación de elementos gráficos se basa en la clase <xref:System.Windows.Media.Visual>. La estructura de objetos visuales en la pantalla se describe en el árbol visual. Para más información, consulte [Información general sobre la representación de gráficos en WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).  
  
### <a name="2-d-shapes"></a>Formas 2D  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ofrece una biblioteca de formas [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] comunes dibujadas mediante vectores, como los rectángulos y las elipses que se muestran en la ilustración siguiente.  
  
 ![Elipses y rectángulos](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure4.PNG "WPFIntroFigure4")  
  
 Estas formas intrínsecas de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] no son solo formas: son elementos programables que implementan muchas de las características que se esperan de los controles más comunes, entre los que se incluyen la entrada por mouse y teclado. En el siguiente ejemplo se muestra cómo controlar el evento <xref:System.Windows.UIElement.MouseUp> que se genera al hacer clic en un elemento <xref:System.Windows.Shapes.Ellipse>.  
  
```xaml  
\<Window  
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
  
 ![Ventana con el texto "ha hecho clic en la elipse"](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure12.png "WPFIntroFigure12")  
  
 Para obtener más información, consulte [Información general sobre formas y dibujo básico en WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md). Para obtener un ejemplo introductorio, vea [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037) (Ejemplo de elementos de forma).  
  
### <a name="2-d-geometries"></a>Geometrías 2D  
 Cuando las formas [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] que [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ofrece no sean suficientes, puede usar la compatibilidad con geometrías y trazados de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] para crear sus propias formas. En la ilustración siguiente se muestra cómo se pueden usar geometrías para crear formas, por ejemplo, un pincel de dibujo, y para recortar otros elementos [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 ![Diversos usos de un trayecto](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure5.PNG "WPFIntroFigure5")  
  
 Para más información, consulte [Información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md). Para obtener un ejemplo introductorio, vea [Ejemplo de geometrías](http://go.microsoft.com/fwlink/?LinkID=159989).  
  
### <a name="2-d-effects"></a>Efectos 2D  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ofrece una biblioteca de clases [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] que puede usar para crear diversos efe efectos. La funcionalidad de representación [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ofrece la posibilidad de pintar elementos de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que tengan degradados, mapas de bits, dibujos y vídeos; así como para manipularlos mediante rotación, escalado y sesgado. En la ilustración siguiente se ofrece un ejemplo de los muchos efectos que puede lograr mediante pinceles de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 ![Ilustración de diferentes pinceles](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure6.PNG "WPFIntroFigure6")  
  
 Para obtener más información, consulte [Información general sobre pinceles de WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-brushes-overview.md). Para obtener un ejemplo introductorio, vea [Ejemplo de pinceles](http://go.microsoft.com/fwlink/?LinkID=159973).  
  
<a name="rendering"></a>   
## <a name="3-d-rendering"></a>Representación 3D  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ofrece un conjunto de funciones de representación [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] que se integran con la compatibilidad de gráficos [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] para que cree un diseño, una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] y una visualización de datos más interesantes. En un extremo del espectro, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] le permite representar imágenes [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] en las superficies de formas [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)], lo que se muestra en la siguiente ilustración.  
  
 ![Captura de pantalla de ejemplo de Visual3D](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure13.png "WPFIntroFigure13")  
  
 Para obtener más información, consulte [Información general sobre gráficos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md). Para obtener un ejemplo introductorio, vea [3-D Solids Sample](http://go.microsoft.com/fwlink/?LinkID=159964) (Ejemplo de sólidos 3D).  
  
<a name="animation"></a>   
## <a name="animation"></a>Animación  
 Use la animación para hacer que los controles y elementos crezcan, vibren, giren o se desvanezcan, crear atractivas transiciones de página y mucho más. Dado que [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] le permite animar la mayoría de las propiedades, no solo podrá animar la mayoría de los objetos [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], también podrá usar [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] para animar objetos personalizados que haya creado.  
  
 ![Imágenes de un cubo animado](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure7.png "WPFIntroFigure7")  
  
 Para obtener más información, consulte [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). Para obtener un ejemplo introductorio, vea [Animation Example Gallery](http://go.microsoft.com/fwlink/?LinkID=159969) (Galería de ejemplos de animación).  
  
<a name="media"></a>   
## <a name="media"></a>Multimedia  
 Las imágenes, el vídeo y el audio son maneras de ofrecer experiencias de usuario e información con mucho contenido multimedia.  
  
### <a name="images"></a>Imágenes  
 Las imágenes, que incluyen iconos, fondos e incluso partes de animaciones, constituyen una pieza esencial de la mayoría de las aplicaciones. Dado que frecuentemente tendrá que usar imágenes, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] presenta la posibilidad de trabajar con ellas de diversas maneras. En la ilustración siguiente se muestra tan solo una de esas maneras.  
  
 ![Captura de pantalla de ejemplo de aplicación de estilos](../../../../docs/framework/wpf/controls/media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")  
  
 Para obtener más información, consulte [Información general sobre imágenes](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md).  
  
### <a name="video-and-audio"></a>Vídeo y audio  
 Una característica fundamental de la funcionalidad de gráficos de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] es que ofrece compatibilidad nativa para trabajar con multimedia, lo que incluye vídeo y audio. En el siguiente ejemplo se muestra cómo insertar un reproductor multimedia en una aplicación.  
  
```xaml  
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />  
```  
  
 <xref:System.Windows.Controls.MediaElement> puede reproducir vídeo y audio, y es lo suficientemente extensible como para permitir la creación sencilla de [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] personalizadas.  
  
 Para más información, consulte [Información general sobre multimedia](../../../../docs/framework/wpf/graphics-multimedia/multimedia-overview.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media>   
 <xref:System.Windows.Media.Animation>   
 <xref:System.Windows.Media.Media3D>   
 [Imágenes y gráficos 2D](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Información general sobre formas y dibujo básico en WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)   
 [Información general sobre el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Animación y temporización](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [Gráficos 3D](http://msdn.microsoft.com/en-us/565c1f3c-235b-47de-b05b-3b53ed63f1b8)   
 [Multimedia](http://msdn.microsoft.com/en-us/44a8dcd0-80cb-4db0-a222-87cde68c2fac)
