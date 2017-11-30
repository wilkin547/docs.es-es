---
title: "Información general sobre multimedia"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multimedia [WPF]
- media [WPF]
ms.assetid: feb25b15-d741-4ac3-818f-1b19f63a3562
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7097f5bd58573315681c61d0380e58638a4c4fb1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="multimedia-overview"></a>Información general sobre multimedia
Las características multimedia de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] le permiten integrar audio y vídeo en las aplicaciones para mejorar la experiencia del usuario. En este tema se presentan las características multimedia de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 
  
<a name="mediaapi"></a>   
## <a name="media-api"></a>API multimedia  
 El <xref:System.Windows.Controls.MediaElement> y <xref:System.Windows.Media.MediaPlayer> clases se utilizan para presentar el contenido de audio o vídeo. Estas clases se pueden controlar de manera interactiva o mediante un reloj. Estas clases pueden usar el control [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10 para la reproducción multimedia. La clase que se usa depende del escenario.  
  
 <xref:System.Windows.Controls.MediaElement>es un <xref:System.Windows.UIElement> que es compatible con la [diseño](../../../../docs/framework/wpf/advanced/layout.md) y puede utilizarse como el contenido de muchos controles. También se puede usar en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y en el código. <xref:System.Windows.Media.MediaPlayer>, por otro lado, está diseñado para <xref:System.Windows.Media.Drawing> objetos y no tiene compatibilidad con el diseño. Medio cargado con un <xref:System.Windows.Media.MediaPlayer> sólo se pueden presentar con un <xref:System.Windows.Media.VideoDrawing> o al interactuar directamente con un <xref:System.Windows.Media.DrawingContext>. <xref:System.Windows.Media.MediaPlayer>no se pueden utilizar en XAML.  
  
 Para más información sobre los objetos de dibujo y el contexto de dibujo, consulte [Información general sobre objetos Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
> [!NOTE]
>  Al distribuir elementos multimedia con la aplicación, no puede usar un archivo multimedia como recurso del proyecto. En el archivo de proyecto, debe establecer en su lugar el tipo de elemento multimedia en `Content` y establecer `CopyToOutputDirectory` en `PreserveNewest` o `Always`.  
  
<a name="mediaplaybackmodes"></a>   
## <a name="media-playback-modes"></a>Modos de reproducción multimedia  
  
> [!NOTE]
>  Ambos <xref:System.Windows.Controls.MediaElement> y <xref:System.Windows.Media.MediaPlayer> tienen miembros similares. Los vínculos de esta sección hacen referencia a la <xref:System.Windows.Controls.MediaElement> miembros de clase. A menos que se indique lo contrario, los miembros vinculados a en el <xref:System.Windows.Controls.MediaElement> clase también puede encontrarse en la <xref:System.Windows.Media.MediaPlayer> clase.  
  
 Para entender la reproducción multimedia en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], es preciso entender los distintos modos en que se pueden reproducir los elementos multimedia. Ambos <xref:System.Windows.Controls.MediaElement> y <xref:System.Windows.Media.MediaPlayer> puede utilizarse en dos modos multimedia diferentes, el modo independiente y el modo de reloj. El modo de medios viene determinado por la <xref:System.Windows.Controls.MediaElement.Clock%2A> propiedad. Cuando <xref:System.Windows.Controls.MediaElement.Clock%2A> es `null`, el objeto multimedia está en modo independiente. Cuando el <xref:System.Windows.Controls.MediaElement.Clock%2A> es distinto de null, el objeto multimedia está en modo de reloj. De manera predeterminada, los objetos multimedia están en modo independiente.  
  
### <a name="independent-mode"></a>Modo independiente  
 En el modo independiente, el contenido multimedia controla la reproducción multimedia. El modo independiente habilita las opciones siguientes:  
  
-   Del medio <xref:System.Uri> puede especificarse directamente.  
  
-   La reproducción multimedia se puede controlar directamente.  
  
-   Del medio <xref:System.Windows.Controls.MediaElement.Position%2A> y <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> propiedades se pueden modificar.  
  
 Medio deseado se cargue, ya sea estableciendo la <xref:System.Windows.Controls.MediaElement> del objeto <xref:System.Windows.Controls.MediaElement.Source%2A> propiedad o mediante una llamada a la <xref:System.Windows.Media.MediaPlayer> del objeto <xref:System.Windows.Media.MediaPlayer.Open%2A> método.  
  
 Para controlar la reproducción multimedia en el modo independiente, se pueden usar los métodos de control del objeto multimedia. Los métodos de control disponibles son <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A>, y <xref:System.Windows.Controls.MediaElement.Stop%2A>. Para <xref:System.Windows.Controls.MediaElement>, control interactivo mediante estos métodos solo está disponible cuando la <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> está establecido en <xref:System.Windows.Controls.MediaState.Manual>. Estos métodos no están disponible cuando el objeto multimedia está en el modo de reloj.  
  
 Consulte [Control de un MediaElement (Reproducir, Pausar, Detener, Volumen y Velocidad)](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md) para ver un ejemplo del modo independiente.  
  
### <a name="clock-mode"></a>Modo de reloj  
 En el modo de reloj, un <xref:System.Windows.Media.MediaTimeline> controla la reproducción de medios. El modo de reloj tiene las características siguientes:  
  
-   Del medio <xref:System.Uri> se establece indirectamente a través de un <xref:System.Windows.Media.MediaTimeline>.  
  
-   El reloj puede controlar la reproducción multimedia. No se pueden usar los métodos de control del objeto multimedia.  
  
-   Medio deseado se cargue estableciendo un <xref:System.Windows.Media.MediaTimeline> del objeto <xref:System.Windows.Media.MediaTimeline.Source%2A> propiedad, creando el reloj de la escala de tiempo y asignando el reloj al objeto multimedia. Multimedia también se carga de esta manera cuando un <xref:System.Windows.Media.MediaTimeline> dentro de un <xref:System.Windows.Media.Animation.Storyboard> destinos un <xref:System.Windows.Controls.MediaElement>.  
  
 Para controlar la reproducción de multimedia en el modo de reloj, el <xref:System.Windows.Media.Animation.ClockController> se deben usar los métodos de control. A <xref:System.Windows.Media.Animation.ClockController> se obtiene de la <xref:System.Windows.Media.Animation.ClockController> propiedad de la <xref:System.Windows.Media.MediaClock>. Si intenta utilizar los métodos de control de uno de ellos un <xref:System.Windows.Controls.MediaElement> o <xref:System.Windows.Media.MediaPlayer> objeto en el modo de reloj, un <xref:System.InvalidOperationException> se producirá.  
  
 Consulte [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) para más información sobre los relojes y las escalas de tiempo.  
  
 Consulte [Control de un control MediaElement mediante un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-by-using-a-storyboard.md) para ver un ejemplo del modo de reloj.  
  
<a name="mediaelement"></a>   
## <a name="mediaelement-class"></a>Clase MediaElement  
 Agregar multimedia a una aplicación es tan sencillo como agregar una <xref:System.Windows.Controls.MediaElement> el control a la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] de la aplicación y proporcionar un <xref:System.Uri> a los medios que se va a incluir. Todos los tipos de elemento multimedia que admite [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10 se admiten en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. En el ejemplo siguiente se muestra un uso simple de la <xref:System.Windows.Controls.MediaElement> en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
 [!code-xaml[MediaElement_snip#SimpleMediaElementUsageWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaElement_snip/CSharp/SimpleUsage.xaml#simplemediaelementusagewholepage)]  
  
 En este ejemplo, el elemento multimedia se reproduce automáticamente en cuanto se carga. Cuando el elemento multimedia termina de reproducirse se cierra y se liberan todos los recursos multimedia (incluso la memoria de vídeo). Éste es el comportamiento predeterminado de la <xref:System.Windows.Controls.MediaElement> objeto y se controla mediante la <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> y <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> propiedades.  
  
### <a name="controlling-a-mediaelement"></a>Control de MediaElement  
 El <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> y <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> propiedades controlan el comportamiento de la <xref:System.Windows.Controls.MediaElement> cuando <xref:System.Windows.FrameworkElement.IsLoaded%2A> es `true` o `false`, respectivamente. El <xref:System.Windows.Controls.MediaState> se establecen las propiedades que afectan al comportamiento de reproducción multimedia. Por ejemplo, el valor predeterminado <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> es <xref:System.Windows.Controls.MediaState.Play> y el valor predeterminado <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> es <xref:System.Windows.Controls.MediaState.Close>. Esto significa que tan pronto como el <xref:System.Windows.Controls.MediaElement> se carga y la espera se haya completado, los medios empiece a reproducirse. Cuando se completa la reproducción, el elemento multimedia se cierra y se liberan todos los recursos multimedia.  
  
 El <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> y <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> propiedades no son la única manera de controlar la reproducción multimedia. En el modo de reloj, el reloj puede controlar la <xref:System.Windows.Controls.MediaElement> y los métodos de control interactivo tiene el control cuando el <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> es <xref:System.Windows.Controls.MediaState.Manual>. <xref:System.Windows.Controls.MediaElement>controla esta competencia por control evaluando las prioridades siguientes.  
  
1.  <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>. Vigente cuando el elemento multimedia está descargado. Esto garantiza que se liberan todos los recursos multimedia de forma predeterminada, incluso cuando una <xref:System.Windows.Media.MediaClock> está asociado con el <xref:System.Windows.Controls.MediaElement>.  
  
2.  <xref:System.Windows.Media.MediaClock>. En su lugar al medio tiene un <xref:System.Windows.Controls.MediaElement.Clock%2A>. Si se descarga, media la <xref:System.Windows.Media.MediaClock> surtirán efecto hasta la <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> es <xref:System.Windows.Controls.MediaState.Manual>. Modo de reloj siempre invalida el comportamiento de carga de la <xref:System.Windows.Controls.MediaElement>.  
  
3.  <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>. Vigente cuando el elemento multimedia está cargado.  
  
4.  Métodos de control interactivos. En lugar de cuando <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> es <xref:System.Windows.Controls.MediaState.Manual>. Los métodos de control disponibles son <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A>, y <xref:System.Windows.Controls.MediaElement.Stop%2A>.  
  
### <a name="displaying-a-mediaelement"></a>Visualización de MediaElement  
 Para mostrar un <xref:System.Windows.Controls.MediaElement> debe tener contenido que debe representarse y tendrá su <xref:System.Windows.FrameworkElement.ActualWidth%2A> y <xref:System.Windows.FrameworkElement.ActualHeight%2A> propiedades se establecen en cero hasta que se cargue el contenido. Para contenido de solo audio, estas propiedades siempre son cero. Contenido de vídeo, una vez el <xref:System.Windows.Controls.MediaElement.MediaOpened> se ha producido el evento de la <xref:System.Windows.FrameworkElement.ActualWidth%2A> y <xref:System.Windows.FrameworkElement.ActualHeight%2A> informará el tamaño del objeto multimedia cargado. Esto significa que hasta que se carga media, la <xref:System.Windows.Controls.MediaElement> no ocupará ningún espacio físico en el [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] a menos que la <xref:System.Windows.FrameworkElement.Width%2A> o <xref:System.Windows.FrameworkElement.Height%2A> se establecen propiedades.  
  
 Si se establecen las <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades hará que el medio se ajusta para rellenar el área proporcionada para el <xref:System.Windows.Controls.MediaElement>. Para conservar la relación de aspecto original del elemento multimedia, ya sea el <xref:System.Windows.FrameworkElement.Width%2A> o <xref:System.Windows.FrameworkElement.Height%2A> propiedad debe establecerse en conjunto, pero no ambos. Si se establecen las <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades hará que el medio presente en un tamaño de elemento fixed puede no ser deseable.  
  
 Para evitar tener un elemento de tamaño fijo, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] puede preprocesar el elemento multimedia. Esto se hace estableciendo el <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> como <xref:System.Windows.Controls.MediaState.Play> o <xref:System.Windows.Controls.MediaState.Pause>. En un <xref:System.Windows.Controls.MediaState.Pause> de estado, el medio se preprocesará y presentará el primer fotograma. En un <xref:System.Windows.Controls.MediaState.Play> de estado, se preprocesará y empezar a reproducir el medio.  
  
<a name="mediaplayer"></a>   
## <a name="mediaplayer-class"></a>Clase MediaPlayer  
 Mientras que la <xref:System.Windows.Controls.MediaElement> clase es un elemento de marco, el <xref:System.Windows.Media.MediaPlayer> clase está diseñada para usarse en <xref:System.Windows.Media.Drawing> objetos. Los objetos de dibujo se utilizan cuando se pueden sacrificar las características de nivel de marco de trabajo para obtener ventajas de rendimiento o cuando necesite <xref:System.Windows.Freezable> características. <xref:System.Windows.Media.MediaPlayer>le permite aprovechar las ventajas de estas características al proporcionar contenido multimedia en las aplicaciones. Al igual que <xref:System.Windows.Controls.MediaElement>, <xref:System.Windows.Media.MediaPlayer> pueden usarse en independiente o no de reloj modo pero no tiene la <xref:System.Windows.Controls.MediaElement> objeto de la descarga y Estados de carga. Esto reduce la complejidad de control de reproducción de la <xref:System.Windows.Media.MediaPlayer>.  
  
### <a name="controlling-mediaplayer"></a>Control de MediaPlayer  
 Dado que <xref:System.Windows.Media.MediaPlayer> es sin estado, hay solo dos formas de controlar la reproducción multimedia.  
  
1.  Métodos de control interactivos. En su lugar en el modo independiente (`null` <xref:System.Windows.Media.MediaPlayer.Clock%2A> propiedad).  
  
2.  <xref:System.Windows.Media.MediaClock>. En su lugar al medio tiene un <xref:System.Windows.Media.MediaPlayer.Clock%2A>.  
  
### <a name="displaying-a-mediaplayer"></a>Visualización de MediaPlayer  
 Técnicamente, un <xref:System.Windows.Media.MediaPlayer> no se puede mostrar porque no tiene ninguna representación física. Sin embargo, se puede utilizar para presentar los objetos multimedia en una <xref:System.Windows.Media.Drawing> mediante la <xref:System.Windows.Media.VideoDrawing> clase. En el ejemplo siguiente se muestra el uso de un <xref:System.Windows.Media.VideoDrawing> para mostrar los medios.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Consulte la [información general de objetos de dibujo](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md) para obtener más información acerca de <xref:System.Windows.Media.Drawing> objetos.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.DrawingGroup>  
 [Diseño](../../../../docs/framework/wpf/advanced/layout.md)  
 [Temas de procedimientos](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)
