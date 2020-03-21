---
title: Información general sobre multimedia
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF]
- media [WPF]
ms.assetid: feb25b15-d741-4ac3-818f-1b19f63a3562
ms.openlocfilehash: d4abf4d9fd324ffbf2737dc686c02e50ca1a8a5a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181884"
---
# <a name="multimedia-overview"></a>Información general sobre multimedia
Las características multimedia de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] le permiten integrar audio y vídeo en las aplicaciones para mejorar la experiencia del usuario. En este tema se presentan las características multimedia de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="mediaapi"></a>
## <a name="media-api"></a>API multimedia  
 Las <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Media.MediaPlayer> clases y se utilizan para presentar contenido de audio o vídeo. Estas clases se pueden controlar de manera interactiva o mediante un reloj. Estas clases se pueden usar en el control Del Reproductor de Microsoft Windows Media 10 para la reproducción multimedia. La clase que se usa depende del escenario.  
  
 <xref:System.Windows.Controls.MediaElement>es <xref:System.Windows.UIElement> un que es compatible con el [diseño](../advanced/layout.md) y se puede consumir como el contenido de muchos controles. También se puede usar en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y en el código. <xref:System.Windows.Media.MediaPlayer>, por otro lado, <xref:System.Windows.Media.Drawing> está diseñado para objetos y carece de soporte de diseño. Los medios <xref:System.Windows.Media.MediaPlayer> cargados mediante a <xref:System.Windows.Media.VideoDrawing> solo solo se pueden <xref:System.Windows.Media.DrawingContext>presentar mediante a o interactuando directamente con un archivo . <xref:System.Windows.Media.MediaPlayer>no se puede usar en XAML.  
  
 Para más información sobre los objetos de dibujo y el contexto de dibujo, consulte [Información general sobre objetos Drawing](drawing-objects-overview.md).  
  
> [!NOTE]
> Al distribuir elementos multimedia con la aplicación, no puede usar un archivo multimedia como recurso del proyecto. En el archivo de proyecto, debe establecer en su lugar el tipo de elemento multimedia en `Content` y establecer `CopyToOutputDirectory` en `PreserveNewest` o `Always`.  
  
<a name="mediaplaybackmodes"></a>
## <a name="media-playback-modes"></a>Modos de reproducción multimedia  
  
> [!NOTE]
> Ambos <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Media.MediaPlayer> tienen miembros similares. Los enlaces de esta <xref:System.Windows.Controls.MediaElement> sección se refieren a los miembros de la clase. A menos que se indique <xref:System.Windows.Controls.MediaElement> específicamente, los miembros vinculados a la clase también se pueden encontrar en la <xref:System.Windows.Media.MediaPlayer> clase.  
  
 Para entender la reproducción multimedia en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], es preciso entender los distintos modos en que se pueden reproducir los elementos multimedia. Ambos <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Media.MediaPlayer> y se pueden utilizar en dos modos de medios diferentes, modo independiente y modo de reloj. El modo de medios <xref:System.Windows.Controls.MediaElement.Clock%2A> viene determinado por la propiedad. Cuando <xref:System.Windows.Controls.MediaElement.Clock%2A> `null`está , el objeto multimedia está en modo independiente. Cuando <xref:System.Windows.Controls.MediaElement.Clock%2A> el es no nulo, el objeto multimedia está en modo de reloj. De manera predeterminada, los objetos multimedia están en modo independiente.  
  
### <a name="independent-mode"></a>Modo independiente  
 En el modo independiente, el contenido multimedia controla la reproducción multimedia. El modo independiente habilita las opciones siguientes:  
  
- Los medios <xref:System.Uri> se pueden especificar directamente.  
  
- La reproducción multimedia se puede controlar directamente.  
  
- Los medios <xref:System.Windows.Controls.MediaElement.Position%2A> <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> y las propiedades se pueden modificar.  
  
 El medio se carga <xref:System.Windows.Controls.MediaElement> estableciendo <xref:System.Windows.Controls.MediaElement.Source%2A> la propiedad <xref:System.Windows.Media.MediaPlayer> del objeto <xref:System.Windows.Media.MediaPlayer.Open%2A> o llamando al método del objeto.  
  
 Para controlar la reproducción multimedia en el modo independiente, se pueden usar los métodos de control del objeto multimedia. Los métodos <xref:System.Windows.Controls.MediaElement.Play%2A>de <xref:System.Windows.Controls.MediaElement.Pause%2A> <xref:System.Windows.Controls.MediaElement.Close%2A>control <xref:System.Windows.Controls.MediaElement.Stop%2A>disponibles son , , , y . Para <xref:System.Windows.Controls.MediaElement>, el control interactivo que <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> utiliza estos <xref:System.Windows.Controls.MediaState.Manual>métodos solo está disponible cuando se establece en . Estos métodos no están disponible cuando el objeto multimedia está en el modo de reloj.  
  
 Consulte [Control de un MediaElement (Reproducir, Pausar, Detener, Volumen y Velocidad)](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md) para ver un ejemplo del modo independiente.  
  
### <a name="clock-mode"></a>Modo de reloj  
 En el modo <xref:System.Windows.Media.MediaTimeline> de reloj, un control de medios de reproducción. El modo de reloj tiene las características siguientes:  
  
- Los medios <xref:System.Uri> de comunicación <xref:System.Windows.Media.MediaTimeline>se establecen indirectamente a través de un archivo .  
  
- El reloj puede controlar la reproducción multimedia. No se pueden usar los métodos de control del objeto multimedia.  
  
- Los medios se <xref:System.Windows.Media.MediaTimeline> cargan <xref:System.Windows.Media.MediaTimeline.Source%2A> estableciendo la propiedad de un objeto, creando el reloj a partir de la línea de tiempo y asignando el reloj al objeto multimedia. Los medios también se <xref:System.Windows.Media.MediaTimeline> cargan <xref:System.Windows.Media.Animation.Storyboard> de <xref:System.Windows.Controls.MediaElement>esta manera cuando un dentro de un destino es un archivo .  
  
 Para controlar la reproducción <xref:System.Windows.Media.Animation.ClockController> multimedia en modo de reloj, se deben utilizar los métodos de control. A <xref:System.Windows.Media.Animation.ClockController> se obtiene <xref:System.Windows.Media.Animation.ClockController> de la <xref:System.Windows.Media.MediaClock>propiedad de la . Si intenta utilizar los métodos <xref:System.Windows.Controls.MediaElement> de <xref:System.Windows.Media.MediaPlayer> control de a <xref:System.InvalidOperationException> u objeto mientras está en modo de reloj, se producirá un.  
  
 Consulte [Información general sobre animaciones](animation-overview.md) para más información sobre los relojes y las escalas de tiempo.  
  
 Consulte [Control de un control MediaElement mediante un guión gráfico](how-to-control-a-mediaelement-by-using-a-storyboard.md) para ver un ejemplo del modo de reloj.  
  
<a name="mediaelement"></a>
## <a name="mediaelement-class"></a>Clase MediaElement  
 Agregar medios a una aplicación es <xref:System.Windows.Controls.MediaElement> tan [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] simple como agregar <xref:System.Uri> un control a la aplicación y proporcionar un a los medios que desea incluir. Todos los tipos de medios compatibles con [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]Microsoft Windows Media Player 10 son compatibles con . En el ejemplo siguiente se <xref:System.Windows.Controls.MediaElement> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]muestra un uso sencillo de la in .  
  
 [!code-xaml[MediaElement_snip#SimpleMediaElementUsageWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaElement_snip/CSharp/SimpleUsage.xaml#simplemediaelementusagewholepage)]  
  
 En este ejemplo, el elemento multimedia se reproduce automáticamente en cuanto se carga. Cuando el elemento multimedia termina de reproducirse se cierra y se liberan todos los recursos multimedia (incluso la memoria de vídeo). Este es el comportamiento <xref:System.Windows.Controls.MediaElement> predeterminado del objeto <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> y <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> se controla mediante las propiedades y.  
  
### <a name="controlling-a-mediaelement"></a>Control de MediaElement  
 Las <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> propiedades y controlan <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.FrameworkElement.IsLoaded%2A> el `true` `false`comportamiento de la when is o , respectivamente. Las <xref:System.Windows.Controls.MediaState> propiedades se establecen para afectar al comportamiento de reproducción de medios. Por ejemplo, <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> el <xref:System.Windows.Controls.MediaState.Play> valor <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> predeterminado <xref:System.Windows.Controls.MediaState.Close>es y el valor predeterminado es . Esto significa que tan <xref:System.Windows.Controls.MediaElement> pronto como se carga y el preroll se completa, los medios comienzan a reproducirse. Cuando se completa la reproducción, el elemento multimedia se cierra y se liberan todos los recursos multimedia.  
  
 Las <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> propiedades y no son la única manera de controlar la reproducción multimedia. En el modo de reloj, el reloj puede controlar los <xref:System.Windows.Controls.MediaElement> métodos de control interactivos y tener el control cuando el <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> is <xref:System.Windows.Controls.MediaState.Manual>. <xref:System.Windows.Controls.MediaElement>controle las siguientes prioridades.  
  
1. <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>. Vigente cuando el elemento multimedia está descargado. Esto garantiza que todos los recursos multimedia <xref:System.Windows.Media.MediaClock> se liberan <xref:System.Windows.Controls.MediaElement>de forma predeterminada, incluso cuando a está asociado con el archivo .  
  
2. <xref:System.Windows.Media.MediaClock>. En su lugar <xref:System.Windows.Controls.MediaElement.Clock%2A>cuando los medios de comunicación tienen un archivo . Si se descargan <xref:System.Windows.Media.MediaClock> medios, el entrará <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> en <xref:System.Windows.Controls.MediaState.Manual>vigor siempre y cuando el es . El modo de reloj siempre <xref:System.Windows.Controls.MediaElement>anula el comportamiento cargado del archivo .  
  
3. <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>. Vigente cuando el elemento multimedia está cargado.  
  
4. Métodos de control interactivos. En su <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Manual>lugar cuando está . Los métodos <xref:System.Windows.Controls.MediaElement.Play%2A>de <xref:System.Windows.Controls.MediaElement.Pause%2A> <xref:System.Windows.Controls.MediaElement.Close%2A>control <xref:System.Windows.Controls.MediaElement.Stop%2A>disponibles son , , , y .  
  
### <a name="displaying-a-mediaelement"></a>Visualización de MediaElement  
 Para mostrar <xref:System.Windows.Controls.MediaElement> un debe tener contenido para <xref:System.Windows.FrameworkElement.ActualWidth%2A> representar <xref:System.Windows.FrameworkElement.ActualHeight%2A> y tendrá sus propiedades y se establecerán en cero hasta que se cargue el contenido. Para contenido de solo audio, estas propiedades siempre son cero. En el caso <xref:System.Windows.Controls.MediaElement.MediaOpened> del contenido de <xref:System.Windows.FrameworkElement.ActualWidth%2A> vídeo, una vez que se haya generado el evento e <xref:System.Windows.FrameworkElement.ActualHeight%2A> informará del tamaño de los medios cargados. Esto significa que hasta que <xref:System.Windows.Controls.MediaElement> se carguen los medios, <xref:System.Windows.FrameworkElement.Width%2A> el <xref:System.Windows.FrameworkElement.Height%2A> no ocupará ningún espacio físico en el [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] o propiedades se establecen.  
  
 Si se <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> establecen las propiedades y las que se <xref:System.Windows.Controls.MediaElement>estiran, el medio se estirará para rellenar el área proporcionada para el archivo . Para conservar la relación de aspecto <xref:System.Windows.FrameworkElement.Width%2A> original <xref:System.Windows.FrameworkElement.Height%2A> del medio, se debe establecer la propiedad o, pero no ambas. Establecer las <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> propiedades y hará que el medio se presente en un tamaño de elemento fijo que puede no ser deseable.  
  
 Para evitar tener un elemento de tamaño fijo, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] puede preprocesar el elemento multimedia. Esto se hace <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> estableciendo <xref:System.Windows.Controls.MediaState.Play> <xref:System.Windows.Controls.MediaState.Pause>el valor de uno o . En <xref:System.Windows.Controls.MediaState.Pause> un estado, los medios se preimplementarán y presentarán el primer fotograma. En <xref:System.Windows.Controls.MediaState.Play> un estado, los medios se prelanzarán y comenzarán a reproducirse.  
  
<a name="mediaplayer"></a>
## <a name="mediaplayer-class"></a>Clase MediaPlayer  
 Donde como <xref:System.Windows.Controls.MediaElement> la clase es <xref:System.Windows.Media.MediaPlayer> un elemento de marco <xref:System.Windows.Media.Drawing> de trabajo, la clase está diseñada para usarse en objetos. Los objetos de dibujo se utilizan cuando se pueden <xref:System.Windows.Freezable> sacrificar entidades de nivel de marco de trabajo para obtener ventajas de rendimiento o cuando se necesitan entidades. <xref:System.Windows.Media.MediaPlayer>le permite aprovechar estas características al tiempo que proporciona contenido multimedia en sus aplicaciones. Like <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Media.MediaPlayer> , se puede utilizar en modo independiente <xref:System.Windows.Controls.MediaElement> o de reloj, pero no tiene los estados descargados y cargados del objeto. Esto reduce la complejidad del <xref:System.Windows.Media.MediaPlayer>control de reproducción del archivo .  
  
### <a name="controlling-mediaplayer"></a>Control de MediaPlayer  
 Debido <xref:System.Windows.Media.MediaPlayer> a que no tiene estado, solo hay dos maneras de controlar la reproducción multimedia.  
  
1. Métodos de control interactivos. En su lugar cuando`null` <xref:System.Windows.Media.MediaPlayer.Clock%2A> está en modo independiente (propiedad).  
  
2. <xref:System.Windows.Media.MediaClock>. En su lugar <xref:System.Windows.Media.MediaPlayer.Clock%2A>cuando los medios de comunicación tienen un archivo .  
  
### <a name="displaying-a-mediaplayer"></a>Visualización de MediaPlayer  
 Técnicamente, <xref:System.Windows.Media.MediaPlayer> no se puede mostrar a ya que no tiene representación física. Sin embargo, se puede utilizar <xref:System.Windows.Media.Drawing> para <xref:System.Windows.Media.VideoDrawing> presentar medios en un uso de la clase. En el ejemplo siguiente se <xref:System.Windows.Media.VideoDrawing> muestra el uso de un para mostrar medios.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Consulte Información general sobre [objetos](drawing-objects-overview.md) de dibujo para obtener más información sobre <xref:System.Windows.Media.Drawing> los objetos.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.DrawingGroup>
- [Diseño](../advanced/layout.md)
- [Temas de información](audio-and-video-how-to-topics.md)
