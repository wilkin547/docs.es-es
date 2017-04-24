---
title: "Informaci&#243;n general sobre multimedia | Microsoft Docs"
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
  - "multimedia"
  - "multimedia"
ms.assetid: feb25b15-d741-4ac3-818f-1b19f63a3562
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Informaci&#243;n general sobre multimedia
Las características multimedia de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] permiten integrar audio y vídeo en las aplicaciones para mejorar la experiencia del usuario. En este tema se presentan las características multimedia de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
   
  
<a name="mediaapi"></a>   
## API multimedia  
 Las clases <xref:System.Windows.Controls.MediaElement> y <xref:System.Windows.Media.MediaPlayer> se utilizan para presentar contenido de audio o vídeo.  Estas clases se pueden controlar interactivamente o mediante un reloj.  Estas clases pueden utilizar el control [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10 para la reproducción multimedia. La clase que se utiliza depende del escenario.  
  
 <xref:System.Windows.Controls.MediaElement> es una clase <xref:System.Windows.UIElement> compatible con [Diseño](../../../../docs/framework/wpf/advanced/layout.md) que se puede utilizar como contenido de muchos controles.  También se puede utilizar en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], así como en el código. <xref:System.Windows.Media.MediaPlayer>, por otro lado, está diseñado para los objetos <xref:System.Windows.Media.Drawing> y carece de compatibilidad de diseño.  Los objetos multimedia cargados mediante <xref:System.Windows.Media.MediaPlayer> únicamente se pueden presentar utilizando <xref:System.Windows.Media.VideoDrawing> o interactuando directamente con <xref:System.Windows.Media.DrawingContext>.  <xref:System.Windows.Media.MediaPlayer> no se puede utilizar en XAML.  
  
 Para obtener más información sobre los objetos de dibujo y el contexto de dibujo, consulte [Información general sobre objetos Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
> [!NOTE]
>  Al distribuir los objetos multimedia con la aplicación, no se puede usar ningún archivo multimedia como recurso del proyecto.  En lugar de ello, en el archivo del proyecto debe establecer en `Content` el tipo de medios y establecer `CopyToOutputDirectory` en `PreserveNewest` o `Always`.  
  
<a name="mediaplaybackmodes"></a>   
## Modos de reproducción multimedia  
  
> [!NOTE]
>  <xref:System.Windows.Controls.MediaElement> y <xref:System.Windows.Media.MediaPlayer> tienen miembros similares.  Los vínculos de esta sección hacen referencia a los miembros de la clase <xref:System.Windows.Controls.MediaElement>.  A menos que se indique específicamente, los miembros a los que se establecen vínculos en la clase <xref:System.Windows.Controls.MediaElement> también se encuentran en la clase <xref:System.Windows.Media.MediaPlayer>.  
  
 Para entender la reproducción multimedia en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], es preciso entender los distintos modos en que se pueden reproducir los objetos multimedia.  <xref:System.Windows.Controls.MediaElement> y <xref:System.Windows.Media.MediaPlayer> se pueden utilizar en dos modos multimedia diferentes, el modo independiente y el modo de reloj.  El modo multimedia se determina mediante la propiedad <xref:System.Windows.Controls.MediaElement.Clock%2A>.  Cuando <xref:System.Windows.Controls.MediaElement.Clock%2A> es `null`, el objeto multimedia está en modo independiente.  Cuando <xref:System.Windows.Controls.MediaElement.Clock%2A> no es null, el objeto multimedia está en modo de reloj.  De manera predeterminada, los objetos multimedia están en modo independiente.  
  
### Modo independiente  
 En el modo independiente, el contenido multimedia controla la reproducción multimedia.  El modo independiente habilita las opciones siguientes:  
  
-   Se puede especificar el <xref:System.Uri> del objeto multimedia directamente.  
  
-   Se puede controlar directamente la reproducción multimedia.  
  
-   Se pueden modificar las propiedades <xref:System.Windows.Controls.MediaElement.Position%2A> y <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> del objeto multimedia.  
  
 El objeto multimedia se carga estableciendo la propiedad <xref:System.Windows.Controls.MediaElement.Source%2A> del objeto <xref:System.Windows.Controls.MediaElement> o bien llamando al método <xref:System.Windows.Media.MediaPlayer.Open%2A> del objeto <xref:System.Windows.Media.MediaPlayer>.  
  
 Para controlar la reproducción multimedia en modo independiente, se pueden utilizar los métodos de control del objeto multimedia.  Los métodos de control disponibles son <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A> y <xref:System.Windows.Controls.MediaElement.Stop%2A>.  Para <xref:System.Windows.Controls.MediaElement>, el control interactivo mediante estos métodos únicamente está disponible cuando <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> está establecido en <xref:System.Windows.Controls.MediaState>.  Estos métodos no están disponibles cuando el objeto multimedia está en modo de reloj.  
  
 Consulte [Controlar un MediaElement \(Reproducir, Pausar, Detener, Volumen y Velocidad\)](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md) para obtener un ejemplo de modo independiente.  
  
### Modo de reloj  
 En el modo de reloj, <xref:System.Windows.Media.MediaTimeline> controla la reproducción multimedia.  El modo de reloj tiene las siguientes características:  
  
-   El <xref:System.Uri> del objeto multimedia se establece indirectamente a través de <xref:System.Windows.Media.MediaTimeline>.  
  
-   La reproducción multimedia se puede controlar mediante el reloj.  No se pueden utilizar los métodos de control del objeto multimedia.  
  
-   El objeto multimedia se carga estableciendo la propiedad <xref:System.Windows.Media.MediaTimeline.Source%2A> de un objeto <xref:System.Windows.Media.MediaTimeline>, creando el reloj a partir de la escala de tiempo y asignando el reloj al objeto multimedia.  El objeto multimedia también se carga de esta manera cuando el destino de un objeto <xref:System.Windows.Media.MediaTimeline> de <xref:System.Windows.Media.Animation.Storyboard> es <xref:System.Windows.Controls.MediaElement>.  
  
 Para controlar la reproducción multimedia en modo de reloj, se deben utilizar los métodos de control de <xref:System.Windows.Media.Animation.ClockController>.  <xref:System.Windows.Media.Animation.ClockController> se obtiene de la propiedad <xref:System.Windows.Media.Animation.ClockController> de <xref:System.Windows.Media.MediaClock>.  Si intenta utilizar los métodos de control de un objeto <xref:System.Windows.Controls.MediaElement> o <xref:System.Windows.Media.MediaPlayer> mientras está en modo de reloj, se producirá una excepción <xref:System.InvalidOperationException>.  
  
 Consulte [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) para obtener más información sobre relojes y escalas de tiempo.  
  
 Consulte [Controlar un control MediaElement mediante un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-by-using-a-storyboard.md) para obtener un ejemplo del modo de reloj.  
  
<a name="mediaelement"></a>   
## Clase MediaElement  
 Agregar objetos multimedia a una aplicación es tan simple como agregar un control <xref:System.Windows.Controls.MediaElement> a la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] de la aplicación y proporcionar una clase <xref:System.Uri> a los objetos multimedia que se desea incluir.  Todos los tipos de objetos multimedia que admite [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10 se admiten en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. En el ejemplo siguiente, se muestra un uso sencillo de <xref:System.Windows.Controls.MediaElement> en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
 [!code-xml[MediaElement_snip#SimpleMediaElementUsageWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaElement_snip/CSharp/SimpleUsage.xaml#simplemediaelementusagewholepage)]  
  
 En este ejemplo, el objeto multimedia se reproduce automáticamente en cuanto se carga.  Cuando el objeto multimedia ha terminado de reproducirse, se cierra el objeto multimedia y se liberan todos los recursos multimedia \(incluso la memoria de vídeo\).  Éste es el comportamiento predeterminado del objeto <xref:System.Windows.Controls.MediaElement>, controlado por las propiedades <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> y <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>.  
  
### Controlar MediaElement  
 Las propiedades <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> y <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> controlan el comportamiento de <xref:System.Windows.Controls.MediaElement> cuando <xref:System.Windows.FrameworkElement.IsLoaded%2A> es `true` o `false`, respectivamente.  La enumeración <xref:System.Windows.Controls.MediaState> que establece el estado de las propiedades afecta al comportamiento de reproducción multimedia.  Por ejemplo, el valor predeterminado de <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> es <xref:System.Windows.Controls.MediaState> y el valor predeterminado de <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> es <xref:System.Windows.Controls.MediaState>.  Esto significa que, tan pronto como se carga <xref:System.Windows.Controls.MediaElement> y se completa el [preprocesamiento](GTMT), el objeto multimedia empieza a reproducirse.  Cuando se completa la reproducción, se cierra el objeto multimedia y se liberan todos los recursos multimedia.  
  
 Las propiedades <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> y <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> no son la única manera de controlar la reproducción multimedia.  En el modo de reloj, el reloj puede controlar <xref:System.Windows.Controls.MediaElement> y los métodos de control interactivos poseen el control cuando <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> es <xref:System.Windows.Controls.MediaState>.  <xref:System.Windows.Controls.MediaElement> administra esta competición por obtener el control evaluando las prioridades siguientes.  
  
1.  <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>.  Vigente cuando el objeto multimedia no está cargado.  Garantiza que todos los recursos multimedia se liberen de manera predeterminada, aunque haya un <xref:System.Windows.Media.MediaClock> asociado a <xref:System.Windows.Controls.MediaElement>.  
  
2.  <xref:System.Windows.Media.MediaClock>.  Vigente cuando el objeto multimedia tiene <xref:System.Windows.Controls.MediaElement.Clock%2A>.  Si se descarga el objeto multimedia, <xref:System.Windows.Media.MediaClock> surtirá efecto mientras que <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> sea <xref:System.Windows.Controls.MediaState>.  El modo de reloj siempre invalida el comportamiento de carga de <xref:System.Windows.Controls.MediaElement>.  
  
3.  <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>.  Vigente cuando el objeto multimedia está cargado.  
  
4.  Métodos de control interactivos.  Vigentes cuando <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> es <xref:System.Windows.Controls.MediaState>.  Los métodos de control disponibles son <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A> y <xref:System.Windows.Controls.MediaElement.Stop%2A>.  
  
### Mostrar MediaElement  
 Para mostrar <xref:System.Windows.Controls.MediaElement>, debe tener contenido que representar, y sus propiedades <xref:System.Windows.FrameworkElement.ActualWidth%2A> y <xref:System.Windows.FrameworkElement.ActualHeight%2A> estarán establecidas en cero hasta que se cargue el contenido.  Para contenido de sólo audio, estas propiedades siempre son cero.  Para el contenido de vídeo, una vez que se inicia el evento <xref:System.Windows.Controls.MediaElement.MediaOpened>, las propiedades <xref:System.Windows.FrameworkElement.ActualWidth%2A> y <xref:System.Windows.FrameworkElement.ActualHeight%2A> informarán del tamaño del objeto multimedia cargado.  Esto significa que hasta que se cargue el objeto multimedia, <xref:System.Windows.Controls.MediaElement> no ocupará ningún espacio físico en la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] a menos que se establezcan las propiedades <xref:System.Windows.FrameworkElement.Width%2A> o <xref:System.Windows.FrameworkElement.Height%2A>.  
  
 Establecer las propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> hará que los objetos multimedia se expandan para rellenar el área proporcionada para <xref:System.Windows.Controls.MediaElement>.  Para conservar la [relación de aspecto](GTMT) original del objeto multimedia, debe establecer la propiedad <xref:System.Windows.FrameworkElement.Width%2A> o <xref:System.Windows.FrameworkElement.Height%2A>, pero no ambas.  Establecer la propiedad <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> hará que los objetos multimedia se presenten en un tamaño de elemento fijo, lo que podría no ser deseable.  
  
 Para evitar tener un elemento de tamaño fijo, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)][puede preprocesar](GTMT) el objeto multimedia.  Para ello, establezca <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> en <xref:System.Windows.Controls.MediaState> o en <xref:System.Windows.Controls.MediaState>.  En el estado <xref:System.Windows.Controls.MediaState>, los objetos multimedia se preprocesarán y presentarán en el primer fotograma.  En el estado <xref:System.Windows.Controls.MediaState>, los objetos multimedia se [preprocesarán](GTMT) y comenzarán a reproducirse.  
  
<a name="mediaplayer"></a>   
## Clase MediaPlayer  
 Mientras que la clase <xref:System.Windows.Controls.MediaElement> es un elemento de marco de trabajo, la clase <xref:System.Windows.Media.MediaPlayer> está diseñada para su uso en objetos <xref:System.Windows.Media.Drawing>.  Se utilizan objetos de dibujo cuando se pueden sacrificar las características de marco de trabajo para obtener mejoras de rendimiento o cuando se necesitan las características de <xref:System.Windows.Freezable>.  <xref:System.Windows.Media.MediaPlayer> permite aprovechar estas características y, al mismo tiempo, proporcionar contenido multimedia en las aplicaciones.  Al igual que <xref:System.Windows.Controls.MediaElement>, <xref:System.Windows.Media.MediaPlayer> se puede utilizar en modo independiente o en modo de reloj, pero no tiene los estados de carga y descarga del objeto <xref:System.Windows.Controls.MediaElement>.  Esto reduce la complejidad del control de la reproducción de <xref:System.Windows.Media.MediaPlayer>.  
  
### Controlar MediaPlayer  
 Dado que <xref:System.Windows.Media.MediaPlayer> no tiene estado, únicamente hay dos maneras de controlar la reproducción multimedia.  
  
1.  Métodos de control interactivos.  Vigentes en el modo independiente \(la propiedad <xref:System.Windows.Media.MediaPlayer.Clock%2A> es `null`\).  
  
2.  <xref:System.Windows.Media.MediaClock>.  Vigente cuando el objeto multimedia tiene <xref:System.Windows.Media.MediaPlayer.Clock%2A>.  
  
### Mostrar MediaPlayer  
 Técnicamente, <xref:System.Windows.Media.MediaPlayer> no se puede mostrar, puesto que no tiene ninguna representación física.  Sin embargo, se puede utilizar para presentar los objetos multimedia en <xref:System.Windows.Media.Drawing> mediante la clase <xref:System.Windows.Media.VideoDrawing>.  En el siguiente ejemplo se muestra cómo utilizar una clase <xref:System.Windows.Media.VideoDrawing> para mostrar objetos multimedia.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Consulte [Información general sobre objetos Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md) para obtener más información sobre los objetos <xref:System.Windows.Media.Drawing>.  
  
## Vea también  
 <xref:System.Windows.Media.DrawingGroup>   
 [Diseño](../../../../docs/framework/wpf/advanced/layout.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)