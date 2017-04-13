---
title: "Gr&#225;ficos y multimedia | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "animación, características"
  - "características de gráficos"
  - "multimedia, características"
  - "efectos de sonido"
  - "efectos de transición"
  - "efectos de vídeo"
ms.assetid: 1817d9dc-3d6c-46cb-afc8-63b0bae35e37
caps.latest.revision: 30
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 29
---
# Gr&#225;ficos y multimedia
<a name="introduction"></a> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona compatibilidad con multimedia, gráficos vectoriales, animación y creación de contenido, lo que facilita a los desarrolladores la compilación de interfaces de usuario y contenido interesantes.  Mediante [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], puede crear gráficos vectoriales o animaciones complejas e integrar multimedia en las aplicaciones.  
  
 En este tema se presentan las características de gráficos, animación y multimedia de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], que permite agregar gráficos, efectos de transición, sonido y vídeo a las aplicaciones.  
  
> [!NOTE]
>  Se recomienda encarecidamente no usar los tipos WPF en un servicio de Windows.  Si intenta utilizar los tipos WPF en un servicio de Windows, el servicio podría no funcionar como se espera.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>   
## Novedades de gráficos y multimedia en WPF 4  
 Se han realizado varios cambios relacionados con los gráficos y animaciones.  
  
-   Redondeo del diseño  
  
     Cuando el borde de un objeto cae en medio de un dispositivo de píxel, el sistema de gráficos independiente de los PPP puede crear artefactos de representación, como bordes borrosos o semitransparentes.  Las versiones anteriores de WPF incluían el ajuste de píxeles para ayudar a controlar este caso.  El redondeo del diseño apareció por primera vez en Silverlight 2 y constituye otra manera de mover los elementos para que los bordes estén dentro de los límites de píxeles completos.  WPF proporciona ahora soporte técnico para el redondeo del diseño con la propiedad adjunta <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> en <xref:System.Windows.FrameworkElement>.  
  
-   Composición almacenada en caché  
  
     Mediante las nuevas clases <xref:System.Windows.Media.BitmapCacheBrush> y <xref:System.Windows.Media.BitmapCache>, puede almacenar en memoria caché una parte compleja del árbol visual como un mapa de bits y mejorar considerablemente el tiempo de representación.  El mapa de bits sigue siendo sensible a la entrada del usuario, como los clics del mouse, y se puede pintar en otros elementos, igual que cualquier pincel.  
  
-   Compatibilidad con Pixel Shader 3  
  
     WPF 4 aprovecha la compatibilidad con <xref:System.Windows.Media.Effects.ShaderEffect> introducida en WPF 3.5 SP1 y permite a las aplicaciones escribir efectos mediante Pixel Shader \(PS\) versión 3.0.  El modelo del sombreador PS 3.0 es más sofisticado que PS 2.0, que permite realizar aun más efectos en el hardware compatible.  
  
-   Funciones de aceleración  
  
     Puede mejorar las animaciones con funciones de aceleración, que le dan un control adicional sobre el comportamiento de las animaciones.  Por ejemplo, puede aplicar <xref:System.Windows.Media.Animation.ElasticEase> a una animación para darle un comportamiento elástico.  Para obtener más información, consulte los tipos de aceleración en el espacio de nombres <xref:System.Windows.Media.Animation>.  
  
<a name="graphics_and_rendering"></a>   
## Gráficos y representación  
 WPF incluye compatibilidad con gráficos 2\-D de gran calidad.  La funcionalidad incluye pinceles, geometrías, imágenes, formas y transformaciones.  Para obtener más información, vea [Gráficos](../../../../docs/framework/wpf/graphics-multimedia/graphics.md).  La representación de los elementos gráficos se basa en la clase <xref:System.Windows.Media.Visual>.  La estructura de los objetos visuales de la pantalla se describe mediante el árbol visual.  Para obtener más información, vea [Información general sobre la representación de gráficos en WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).  
  
### Formas 2D  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] proporciona una biblioteca de formas [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] de uso común, dibujadas mediante vectores, tales como rectángulos y elipses que se muestran en la ilustración siguiente.  
  
 ![Elipses y rectángulos](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure4.png "WPFIntroFigure4")  
  
 Estas formas intrínsecas de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] no son solamente formas: son elementos programables que implementan muchas de las características que se esperan de la mayoría de los controles comunes, incluida la entrada de teclado y mouse.  En el siguiente ejemplo se muestra cómo controlar el evento <xref:System.Windows.UIElement.MouseUp> generado al hacer clic en un elemento <xref:System.Windows.Shapes.Ellipse>.  
  
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
  
 La ilustración siguiente muestra el resultado del marcado [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y del código subyacente anterior.  
  
 ![Ventana con el texto "ha hecho clic en la elipse"](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure12.png "WPFIntroFigure12")  
  
 Para obtener más información, vea [Información general sobre formas y dibujo básico en WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md).  Para obtener un ejemplo introductorio, vea [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
### Geometrías 2D  
 Cuando las formas [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] que proporciona [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] no sean suficientes, puede utilizar la compatibilidad de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] con geometrías y trayectorias para crear formas propias.  La ilustración siguiente muestra cómo puede utilizar geometrías para crear formas, como un pincel de dibujo, y para recortar otros elementos de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 ![Diversos usos de un trayecto](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure5.png "WPFIntroFigure5")  
  
 Para obtener más información, vea [Información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  Para obtener un ejemplo introductorio, vea [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).  
  
### Efectos 2D  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] proporciona una biblioteca de clases [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] que puede utilizar para crear diversos efectos.  La capacidad de presentación [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ofrece la capacidad de dibujar elementos [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con degradados, mapas de bits, dibujos y vídeos; también de manipularlos utilizando giro, escalado y [sesgado](GTMT).  La ilustración siguiente proporciona un ejemplo de los muchos efectos que puede lograr utilizando los pinceles de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 ![Ilustración de diferentes pinceles](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure6.png "WPFIntroFigure6")  
  
 Para obtener más información, vea [Información general sobre pinceles de WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-brushes-overview.md).  Para obtener un ejemplo introductorio, vea [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).  
  
<a name="rendering"></a>   
## Representación 3D  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] proporciona un conjunto de capacidades de representación [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] que se integran con la compatibilidad con gráficos [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] para crear interesantes diseños, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] y visualizaciones de datos.  En un extremo del espectro, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] permite representar imágenes [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] en las superficies de formas [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)], que se muestran en la siguiente ilustración.  
  
 ![Captura de pantalla de ejemplo Visual3D](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure13.png "WPFIntroFigure13")  
  
 Para obtener más información, vea [Información general sobre gráficos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md).  Para obtener un ejemplo introductorio, vea [3\-D Solids Sample](http://go.microsoft.com/fwlink/?LinkID=159964).  
  
<a name="animation"></a>   
## Animación  
 Utilice animaciones para hacer que los controles y los elementos crezcan, se agiten, giren y se desvanezcan, para crear interesantes transiciones de página y para otros efectos.  Dado que [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] permite animar la mayoría de las propiedades, no solamente podrá animar la mayoría de los objetos de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], sino que también puede utilizar [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] para animar los objetos personalizados que cree.  
  
 ![Imágenes de un cubo animado](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure7.png "WPFIntroFigure7")  
  
 Para obtener más información, consulte [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  Para obtener un ejemplo introductorio, vea [Animation Example Gallery](http://go.microsoft.com/fwlink/?LinkID=159969).  
  
<a name="media"></a>   
## Multimedia  
 Las imágenes, el vídeo y el audio son medios multimedia para la difusión de información y experiencias de usuario.  
  
### Imágenes  
 Las imágenes, entre las que se incluyen iconos, fondos e incluso partes de animaciones, son una parte básica de la mayoría de las aplicaciones.  Dado que frecuentemente necesitará utilizar imágenes, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] expone la capacidad de trabajar con ellas de diversas maneras.  La ilustración siguiente muestra solamente una de esas maneras.  
  
 ![Captura de pantalla de ejemplo de aplicación de estilos](../../../../docs/framework/wpf/controls/media/stylingintro-eventtriggers.png "StylingIntro\_EventTriggers")  
  
 Para obtener más información, consulte [Información general sobre imágenes](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md).  
  
### Vídeo y audio  
 Una característica básica de las capacidades gráficas de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] es la compatibilidad nativa para el trabajo con multimedia, lo que incluye vídeo y audio.  El ejemplo siguiente muestra cómo insertar un reproductor multimedia en una aplicación.  
  
```xaml  
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />  
```  
  
 <xref:System.Windows.Controls.MediaElement> es capaz de reproducir tanto vídeo como audio, y es lo suficientemente extensible como para permitir la creación fácil de [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] personalizadas.  
  
 Para obtener más información, vea [Información general sobre multimedia](../../../../docs/framework/wpf/graphics-multimedia/multimedia-overview.md).  
  
## Vea también  
 <xref:System.Windows.Media>   
 <xref:System.Windows.Media.Animation>   
 <xref:System.Windows.Media.Media3D>   
 [Imágenes y gráficos GDI\+](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Información general sobre formas y dibujo básico en WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)   
 [Información general sobre el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Animation and Timing](http://msdn.microsoft.com/es-es/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [3\-D Graphics](http://msdn.microsoft.com/es-es/565c1f3c-235b-47de-b05b-3b53ed63f1b8)   
 [Multimedia](http://msdn.microsoft.com/es-es/44a8dcd0-80cb-4db0-a222-87cde68c2fac)