---
title: Información general sobre multimedia
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF]
- media [WPF]
ms.assetid: feb25b15-d741-4ac3-818f-1b19f63a3562
ms.openlocfilehash: 42d0d388e859b556d23b7fc81931cd61470ba541
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039797"
---
# <a name="multimedia-overview"></a>Información general sobre multimedia
Las características multimedia de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] le permiten integrar audio y vídeo en las aplicaciones para mejorar la experiencia del usuario. En este tema se presentan las características multimedia de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="mediaapi"></a>   
## <a name="media-api"></a>API multimedia  
 Las clases <xref:System.Windows.Controls.MediaElement> y <xref:System.Windows.Media.MediaPlayer> se utilizan para presentar contenido de audio o vídeo. Estas clases se pueden controlar de manera interactiva o mediante un reloj. Estas clases pueden usar en el control de Microsoft Windows Media Player 10 para la reproducción multimedia. La clase que se usa depende del escenario.  
  
 <xref:System.Windows.Controls.MediaElement> es un <xref:System.Windows.UIElement> compatible con el [diseño](../advanced/layout.md) y se puede consumir como el contenido de muchos controles. También se puede usar en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y en el código. por otro lado, <xref:System.Windows.Media.MediaPlayer>está diseñado para <xref:System.Windows.Media.Drawing> objetos y carece de compatibilidad con el diseño. Los medios cargados con un <xref:System.Windows.Media.MediaPlayer> solo se pueden presentar mediante un <xref:System.Windows.Media.VideoDrawing> o interactuando directamente con un <xref:System.Windows.Media.DrawingContext>. no se puede usar <xref:System.Windows.Media.MediaPlayer> en XAML.  
  
 Para más información sobre los objetos de dibujo y el contexto de dibujo, consulte [Información general sobre objetos Drawing](drawing-objects-overview.md).  
  
> [!NOTE]
> Al distribuir elementos multimedia con la aplicación, no puede usar un archivo multimedia como recurso del proyecto. En el archivo de proyecto, debe establecer en su lugar el tipo de elemento multimedia en `Content` y establecer `CopyToOutputDirectory` en `PreserveNewest` o `Always`.  
  
<a name="mediaplaybackmodes"></a>   
## <a name="media-playback-modes"></a>Modos de reproducción multimedia  
  
> [!NOTE]
> Tanto <xref:System.Windows.Controls.MediaElement> como <xref:System.Windows.Media.MediaPlayer> tienen miembros similares. Los vínculos de esta sección hacen referencia a los miembros de la clase <xref:System.Windows.Controls.MediaElement>. A menos que se indique específicamente, los miembros vinculados a en la clase <xref:System.Windows.Controls.MediaElement> también se pueden encontrar en la clase <xref:System.Windows.Media.MediaPlayer>.  
  
 Para entender la reproducción multimedia en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], es preciso entender los distintos modos en que se pueden reproducir los elementos multimedia. Tanto <xref:System.Windows.Controls.MediaElement> como <xref:System.Windows.Media.MediaPlayer> se pueden usar en dos modos de medios diferentes, el modo independiente y el modo de reloj. El modo multimedia viene determinado por la propiedad <xref:System.Windows.Controls.MediaElement.Clock%2A>. Cuando <xref:System.Windows.Controls.MediaElement.Clock%2A> se `null`, el objeto multimedia está en modo independiente. Cuando el <xref:System.Windows.Controls.MediaElement.Clock%2A> no es null, el objeto multimedia está en modo de reloj. De manera predeterminada, los objetos multimedia están en modo independiente.  
  
### <a name="independent-mode"></a>Modo independiente  
 En el modo independiente, el contenido multimedia controla la reproducción multimedia. El modo independiente habilita las opciones siguientes:  
  
- Los <xref:System.Uri> del medio se pueden especificar directamente.  
  
- La reproducción multimedia se puede controlar directamente.  
  
- Las propiedades <xref:System.Windows.Controls.MediaElement.Position%2A> y <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> del elemento multimedia se pueden modificar.  
  
 Los elementos multimedia se cargan estableciendo la propiedad <xref:System.Windows.Controls.MediaElement.Source%2A> del objeto <xref:System.Windows.Controls.MediaElement> o llamando al método <xref:System.Windows.Media.MediaPlayer.Open%2A> del objeto <xref:System.Windows.Media.MediaPlayer>.  
  
 Para controlar la reproducción multimedia en el modo independiente, se pueden usar los métodos de control del objeto multimedia. Los métodos de control disponibles son <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A>y <xref:System.Windows.Controls.MediaElement.Stop%2A>. Por <xref:System.Windows.Controls.MediaElement>, el control interactivo que usa estos métodos solo está disponible cuando el <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> está establecido en <xref:System.Windows.Controls.MediaState.Manual>. Estos métodos no están disponible cuando el objeto multimedia está en el modo de reloj.  
  
 Consulte [Control de un MediaElement (Reproducir, Pausar, Detener, Volumen y Velocidad)](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md) para ver un ejemplo del modo independiente.  
  
### <a name="clock-mode"></a>Modo de reloj  
 En el modo de reloj, una <xref:System.Windows.Media.MediaTimeline> controla la reproducción multimedia. El modo de reloj tiene las características siguientes:  
  
- El <xref:System.Uri> del elemento multimedia se establece indirectamente a través de un <xref:System.Windows.Media.MediaTimeline>.  
  
- El reloj puede controlar la reproducción multimedia. No se pueden usar los métodos de control del objeto multimedia.  
  
- Los elementos multimedia se cargan estableciendo la propiedad <xref:System.Windows.Media.MediaTimeline.Source%2A> de un objeto <xref:System.Windows.Media.MediaTimeline>, creando el reloj desde la escala de tiempo y asignando el reloj al objeto multimedia. Los elementos multimedia también se cargan de esta manera cuando una <xref:System.Windows.Media.MediaTimeline> dentro de un <xref:System.Windows.Media.Animation.Storyboard> tiene como destino una <xref:System.Windows.Controls.MediaElement>.  
  
 Para controlar la reproducción multimedia en el modo de reloj, se deben usar los métodos de control de <xref:System.Windows.Media.Animation.ClockController>. Un <xref:System.Windows.Media.Animation.ClockController> se obtiene de la propiedad <xref:System.Windows.Media.Animation.ClockController> de la <xref:System.Windows.Media.MediaClock>. Si intenta usar los métodos de control de un objeto <xref:System.Windows.Controls.MediaElement> o <xref:System.Windows.Media.MediaPlayer> mientras está en modo de reloj, se producirá una <xref:System.InvalidOperationException>.  
  
 Consulte [Información general sobre animaciones](animation-overview.md) para más información sobre los relojes y las escalas de tiempo.  
  
 Consulte [Control de un control MediaElement mediante un guión gráfico](how-to-control-a-mediaelement-by-using-a-storyboard.md) para ver un ejemplo del modo de reloj.  
  
<a name="mediaelement"></a>   
## <a name="mediaelement-class"></a>Clase MediaElement  
 Agregar medios a una aplicación es tan sencillo como agregar un control de <xref:System.Windows.Controls.MediaElement> al [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] de la aplicación y proporcionar un <xref:System.Uri> al medio que desea incluir. Todos los tipos de medios admitidos por Microsoft Windows Media Player 10 se admiten en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. En el ejemplo siguiente se muestra un uso simple del <xref:System.Windows.Controls.MediaElement> en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
 [!code-xaml[MediaElement_snip#SimpleMediaElementUsageWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaElement_snip/CSharp/SimpleUsage.xaml#simplemediaelementusagewholepage)]  
  
 En este ejemplo, el elemento multimedia se reproduce automáticamente en cuanto se carga. Cuando el elemento multimedia termina de reproducirse se cierra y se liberan todos los recursos multimedia (incluso la memoria de vídeo). Éste es el comportamiento predeterminado del objeto <xref:System.Windows.Controls.MediaElement> y se controla mediante las propiedades <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> y <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>.  
  
### <a name="controlling-a-mediaelement"></a>Control de MediaElement  
 Las propiedades <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> y <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> controlan el comportamiento de la <xref:System.Windows.Controls.MediaElement> cuando <xref:System.Windows.FrameworkElement.IsLoaded%2A> es `true` o `false`, respectivamente. El <xref:System.Windows.Controls.MediaState> las propiedades se establecen para que afecten al comportamiento de la reproducción multimedia. Por ejemplo, la <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> predeterminada es <xref:System.Windows.Controls.MediaState.Play> y se <xref:System.Windows.Controls.MediaState.Close>la <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> predeterminada. Esto significa que, tan pronto como se carga el <xref:System.Windows.Controls.MediaElement> y se completa el prelanzamiento, el medio comienza a reproducirse. Cuando se completa la reproducción, el elemento multimedia se cierra y se liberan todos los recursos multimedia.  
  
 Las propiedades <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> y <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> no son la única manera de controlar la reproducción multimedia. En el modo de reloj, el reloj puede controlar el <xref:System.Windows.Controls.MediaElement> y los métodos de control interactivos tienen control cuando se <xref:System.Windows.Controls.MediaState.Manual>la <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>. <xref:System.Windows.Controls.MediaElement> controla esta competición para el control mediante la evaluación de las siguientes prioridades.  
  
1. <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>Operador Vigente cuando el elemento multimedia está descargado. Esto garantiza que todos los recursos multimedia se liberan de forma predeterminada, incluso cuando un <xref:System.Windows.Media.MediaClock> está asociado a la <xref:System.Windows.Controls.MediaElement>.  
  
2. <xref:System.Windows.Media.MediaClock>Operador En contexto, cuando el contenido multimedia tiene una <xref:System.Windows.Controls.MediaElement.Clock%2A>. Si el medio se descarga, el <xref:System.Windows.Media.MediaClock> surtirá efecto mientras se <xref:System.Windows.Controls.MediaState.Manual>el <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>. El modo de reloj siempre invalida el comportamiento cargado del <xref:System.Windows.Controls.MediaElement>.  
  
3. <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>Operador Vigente cuando el elemento multimedia está cargado.  
  
4. Métodos de control interactivos. Se aplica cuando se <xref:System.Windows.Controls.MediaState.Manual>la <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>. Los métodos de control disponibles son <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A>y <xref:System.Windows.Controls.MediaElement.Stop%2A>.  
  
### <a name="displaying-a-mediaelement"></a>Visualización de MediaElement  
 Para mostrar una <xref:System.Windows.Controls.MediaElement> debe tener contenido para representarse y tendrá sus propiedades <xref:System.Windows.FrameworkElement.ActualWidth%2A> y <xref:System.Windows.FrameworkElement.ActualHeight%2A> establecidas en cero hasta que se cargue el contenido. Para contenido de solo audio, estas propiedades siempre son cero. En el caso de contenido de vídeo, una vez que se ha generado el evento <xref:System.Windows.Controls.MediaElement.MediaOpened>, el <xref:System.Windows.FrameworkElement.ActualWidth%2A> y <xref:System.Windows.FrameworkElement.ActualHeight%2A> informarán del tamaño del medio cargado. Esto significa que hasta que se cargue el medio, el <xref:System.Windows.Controls.MediaElement> no ocupará ningún espacio físico en el [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] a menos que se establezcan las propiedades <xref:System.Windows.FrameworkElement.Width%2A> o <xref:System.Windows.FrameworkElement.Height%2A>.  
  
 El establecimiento de las propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> hará que los elementos multimedia se expandan para rellenar el área proporcionada para el <xref:System.Windows.Controls.MediaElement>. Para conservar la relación de aspecto original del elemento multimedia, debe establecerse la propiedad <xref:System.Windows.FrameworkElement.Width%2A> o <xref:System.Windows.FrameworkElement.Height%2A>, pero no ambas. Establecer las propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> hará que los elementos multimedia presenten en un tamaño de elemento fijo que puede no ser deseable.  
  
 Para evitar tener un elemento de tamaño fijo, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] puede preprocesar el elemento multimedia. Esto se hace estableciendo el <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> en <xref:System.Windows.Controls.MediaState.Play> o <xref:System.Windows.Controls.MediaState.Pause>. En un estado <xref:System.Windows.Controls.MediaState.Pause>, el elemento multimedia se preprocesará y presentará el primer fotograma. En un estado <xref:System.Windows.Controls.MediaState.Play>, los elementos multimedia se preprocesarán y comenzarán a reproducirse.  
  
<a name="mediaplayer"></a>   
## <a name="mediaplayer-class"></a>Clase MediaPlayer  
 Mientras que la clase <xref:System.Windows.Controls.MediaElement> es un elemento de marco, la clase <xref:System.Windows.Media.MediaPlayer> está diseñada para utilizarse en objetos <xref:System.Windows.Media.Drawing>. Los objetos de dibujo se usan cuando se pueden sacrificar las características del nivel de marco para obtener ventajas de rendimiento o cuando se necesitan <xref:System.Windows.Freezable> características. <xref:System.Windows.Media.MediaPlayer> le permite aprovechar estas características a la vez que proporciona contenido multimedia en las aplicaciones. Como <xref:System.Windows.Controls.MediaElement>, <xref:System.Windows.Media.MediaPlayer> se puede usar en modo independiente o de reloj, pero no tiene los Estados de descarga y carga del objeto <xref:System.Windows.Controls.MediaElement>. Esto reduce la complejidad del control de reproducción de la <xref:System.Windows.Media.MediaPlayer>.  
  
### <a name="controlling-mediaplayer"></a>Control de MediaPlayer  
 Dado que <xref:System.Windows.Media.MediaPlayer> no tiene estado, hay solo dos maneras de controlar la reproducción multimedia.  
  
1. Métodos de control interactivos. En contexto, en el modo independiente (`null`propiedad<xref:System.Windows.Media.MediaPlayer.Clock%2A>).  
  
2. <xref:System.Windows.Media.MediaClock>Operador En contexto, cuando el contenido multimedia tiene una <xref:System.Windows.Media.MediaPlayer.Clock%2A>.  
  
### <a name="displaying-a-mediaplayer"></a>Visualización de MediaPlayer  
 Técnicamente, no se puede mostrar un <xref:System.Windows.Media.MediaPlayer> porque no tiene ninguna representación física. Sin embargo, se puede usar para presentar elementos multimedia en un <xref:System.Windows.Media.Drawing> mediante la clase <xref:System.Windows.Media.VideoDrawing>. En el ejemplo siguiente se muestra el uso de un <xref:System.Windows.Media.VideoDrawing> para mostrar los elementos multimedia.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Vea la información [General sobre objetos de dibujo](drawing-objects-overview.md) para obtener más información sobre los objetos de <xref:System.Windows.Media.Drawing>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.DrawingGroup>
- [Diseño](../advanced/layout.md)
- [Temas "Cómo..."](audio-and-video-how-to-topics.md)
