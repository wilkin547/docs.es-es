---
title: Información general sobre multimedia
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF]
- media [WPF]
ms.assetid: feb25b15-d741-4ac3-818f-1b19f63a3562
ms.openlocfilehash: 44059fe96a0deeda18f0abd9079100b55be98e77
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929622"
---
# <a name="multimedia-overview"></a>Información general sobre multimedia
Las características multimedia de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] le permiten integrar audio y vídeo en las aplicaciones para mejorar la experiencia del usuario. En este tema se presentan las características multimedia de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="mediaapi"></a>   
## <a name="media-api"></a>API multimedia  
 Las <xref:System.Windows.Controls.MediaElement> clases <xref:System.Windows.Media.MediaPlayer> y se utilizan para presentar contenido de audio o vídeo. Estas clases se pueden controlar de manera interactiva o mediante un reloj. Estas clases pueden usar el control [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10 para la reproducción multimedia. La clase que se usa depende del escenario.  
  
 <xref:System.Windows.Controls.MediaElement>es un <xref:System.Windows.UIElement> que es compatible con el [diseño](../advanced/layout.md) y se puede usar como contenido de muchos controles. También se puede usar en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y en el código. <xref:System.Windows.Media.MediaPlayer>, por otro lado, está diseñado para objetos <xref:System.Windows.Media.Drawing> y carece de compatibilidad con el diseño. Los medios cargados <xref:System.Windows.Media.MediaPlayer> con un solo se pueden presentar <xref:System.Windows.Media.VideoDrawing> mediante o interactuando directamente con un <xref:System.Windows.Media.DrawingContext>. <xref:System.Windows.Media.MediaPlayer>no se puede usar en XAML.  
  
 Para más información sobre los objetos de dibujo y el contexto de dibujo, consulte [Información general sobre objetos Drawing](drawing-objects-overview.md).  
  
> [!NOTE]
> Al distribuir elementos multimedia con la aplicación, no puede usar un archivo multimedia como recurso del proyecto. En el archivo de proyecto, debe establecer en su lugar el tipo de elemento multimedia en `Content` y establecer `CopyToOutputDirectory` en `PreserveNewest` o `Always`.  
  
<a name="mediaplaybackmodes"></a>   
## <a name="media-playback-modes"></a>Modos de reproducción multimedia  
  
> [!NOTE]
> <xref:System.Windows.Controls.MediaElement> Y<xref:System.Windows.Media.MediaPlayer> tienen miembros similares. Los vínculos de esta sección hacen referencia a <xref:System.Windows.Controls.MediaElement> los miembros de clase. A menos que se indique específicamente, los miembros <xref:System.Windows.Controls.MediaElement> vinculados a en la clase también <xref:System.Windows.Media.MediaPlayer> se pueden encontrar en la clase.  
  
 Para entender la reproducción multimedia en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], es preciso entender los distintos modos en que se pueden reproducir los elementos multimedia. <xref:System.Windows.Controls.MediaElement> Y<xref:System.Windows.Media.MediaPlayer> se pueden usar en dos modos multimedia diferentes: modo independiente y modo de reloj. El modo multimedia viene determinado por la <xref:System.Windows.Controls.MediaElement.Clock%2A> propiedad. Cuando <xref:System.Windows.Controls.MediaElement.Clock%2A> es`null`, el objeto multimedia está en modo independiente. Cuando no <xref:System.Windows.Controls.MediaElement.Clock%2A> es null, el objeto multimedia está en modo de reloj. De manera predeterminada, los objetos multimedia están en modo independiente.  
  
### <a name="independent-mode"></a>Modo independiente  
 En el modo independiente, el contenido multimedia controla la reproducción multimedia. El modo independiente habilita las opciones siguientes:  
  
- Los elementos multimedia se puedenespecificardirectamente.<xref:System.Uri>  
  
- La reproducción multimedia se puede controlar directamente.  
  
- Se pueden <xref:System.Windows.Controls.MediaElement.Position%2A> modificar <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> las propiedades y del elemento multimedia.  
  
 Los elementos multimedia se cargan estableciendo <xref:System.Windows.Controls.MediaElement> la propiedad <xref:System.Windows.Controls.MediaElement.Source%2A> del objeto o llamando al <xref:System.Windows.Media.MediaPlayer> método del <xref:System.Windows.Media.MediaPlayer.Open%2A> objeto.  
  
 Para controlar la reproducción multimedia en el modo independiente, se pueden usar los métodos de control del objeto multimedia. Los métodos de control disponibles <xref:System.Windows.Controls.MediaElement.Play%2A>son <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A>, y <xref:System.Windows.Controls.MediaElement.Stop%2A>. Para <xref:System.Windows.Controls.MediaElement>, el <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> control interactivo que usa estos métodos solo está disponible cuando se establece <xref:System.Windows.Controls.MediaState.Manual>en. Estos métodos no están disponible cuando el objeto multimedia está en el modo de reloj.  
  
 Consulte [Control de un MediaElement (Reproducir, Pausar, Detener, Volumen y Velocidad)](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md) para ver un ejemplo del modo independiente.  
  
### <a name="clock-mode"></a>Modo de reloj  
 En el modo de reloj <xref:System.Windows.Media.MediaTimeline> , un controla la reproducción multimedia. El modo de reloj tiene las características siguientes:  
  
- Los elementos multimedia <xref:System.Windows.Media.MediaTimeline> seestablecenindirectamente<xref:System.Uri> a través de.  
  
- El reloj puede controlar la reproducción multimedia. No se pueden usar los métodos de control del objeto multimedia.  
  
- Los elementos multimedia se cargan <xref:System.Windows.Media.MediaTimeline> mediante el <xref:System.Windows.Media.MediaTimeline.Source%2A> establecimiento de la propiedad de un objeto, la creación del reloj desde la escala de tiempo y la asignación del reloj al objeto multimedia. Los elementos multimedia también se cargan de <xref:System.Windows.Media.MediaTimeline> esta manera <xref:System.Windows.Media.Animation.Storyboard> cuando un <xref:System.Windows.Controls.MediaElement>elemento dentro de tiene como destino una.  
  
 Para controlar la reproducción multimedia en el modo de <xref:System.Windows.Media.Animation.ClockController> reloj, se deben usar los métodos de control. Se <xref:System.Windows.Media.Animation.ClockController> obtiene a partir de <xref:System.Windows.Media.Animation.ClockController> la propiedad de <xref:System.Windows.Media.MediaClock>. Si intenta usar los métodos de control de un <xref:System.Windows.Controls.MediaElement> objeto o <xref:System.Windows.Media.MediaPlayer> mientras está en modo de reloj, se <xref:System.InvalidOperationException> producirá una excepción.  
  
 Consulte [Información general sobre animaciones](animation-overview.md) para más información sobre los relojes y las escalas de tiempo.  
  
 Consulte [Control de un control MediaElement mediante un guión gráfico](how-to-control-a-mediaelement-by-using-a-storyboard.md) para ver un ejemplo del modo de reloj.  
  
<a name="mediaelement"></a>   
## <a name="mediaelement-class"></a>Clase MediaElement  
 Agregar elementos multimedia a una aplicación es tan sencillo como agregar <xref:System.Windows.Controls.MediaElement> un control [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] al de la aplicación y proporcionar un <xref:System.Uri> al medio que desea incluir. Todos los tipos de elemento multimedia que admite [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10 se admiten en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. <xref:System.Windows.Controls.MediaElement> En el ejemplo siguiente se muestra un uso simple de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]en.  
  
 [!code-xaml[MediaElement_snip#SimpleMediaElementUsageWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaElement_snip/CSharp/SimpleUsage.xaml#simplemediaelementusagewholepage)]  
  
 En este ejemplo, el elemento multimedia se reproduce automáticamente en cuanto se carga. Cuando el elemento multimedia termina de reproducirse se cierra y se liberan todos los recursos multimedia (incluso la memoria de vídeo). Éste es el comportamiento predeterminado del <xref:System.Windows.Controls.MediaElement> objeto y se controla mediante las <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> propiedades y <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> .  
  
### <a name="controlling-a-mediaelement"></a>Control de MediaElement  
 Las <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> propiedades <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> y <xref:System.Windows.FrameworkElement.IsLoaded%2A> `true` controlan el comportamiento de `false`cuando es o, respectivamente. <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Controls.MediaState> Las propiedades se establecen para que afecten al comportamiento de la reproducción multimedia. Por ejemplo, el valor <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> predeterminado <xref:System.Windows.Controls.MediaState.Play> es y el <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> valor <xref:System.Windows.Controls.MediaState.Close>predeterminado es. Esto significa que, en cuanto <xref:System.Windows.Controls.MediaElement> se carga y se completa el prelanzamiento, el medio comienza a reproducirse. Cuando se completa la reproducción, el elemento multimedia se cierra y se liberan todos los recursos multimedia.  
  
 Las <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> propiedades <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> y no son la única manera de controlar la reproducción multimedia. En el modo de reloj, el reloj puede <xref:System.Windows.Controls.MediaElement> controlar y los métodos de control interactivos <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> tienen <xref:System.Windows.Controls.MediaState.Manual>el control cuando es. <xref:System.Windows.Controls.MediaElement>controla esta competición para el control mediante la evaluación de las siguientes prioridades.  
  
1. <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>. Vigente cuando el elemento multimedia está descargado. Esto garantiza que todos los recursos multimedia se liberan de forma predeterminada, <xref:System.Windows.Media.MediaClock> incluso cuando está asociado <xref:System.Windows.Controls.MediaElement>a.  
  
2. <xref:System.Windows.Media.MediaClock>. Vigente cuando el elemento multimedia tiene <xref:System.Windows.Controls.MediaElement.Clock%2A>un. Si el medio se descarga, <xref:System.Windows.Media.MediaClock> surtirá efecto mientras el <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> sea <xref:System.Windows.Controls.MediaState.Manual>. El modo de reloj siempre invalida el comportamiento cargado de <xref:System.Windows.Controls.MediaElement>.  
  
3. <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> Vigente cuando el elemento multimedia está cargado.  
  
4. Métodos de control interactivos. Se aplica cuando <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> es <xref:System.Windows.Controls.MediaState.Manual>. Los métodos de control disponibles <xref:System.Windows.Controls.MediaElement.Play%2A>son <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A>, y <xref:System.Windows.Controls.MediaElement.Stop%2A>.  
  
### <a name="displaying-a-mediaelement"></a>Visualización de MediaElement  
 Para mostrar un <xref:System.Windows.Controls.MediaElement> , debe tener contenido para representar y sus propiedades y <xref:System.Windows.FrameworkElement.ActualHeight%2A> se <xref:System.Windows.FrameworkElement.ActualWidth%2A> establecen en cero hasta que se cargue el contenido. Para contenido de solo audio, estas propiedades siempre son cero. Para el contenido de vídeo, <xref:System.Windows.Controls.MediaElement.MediaOpened> una vez que se ha <xref:System.Windows.FrameworkElement.ActualWidth%2A> generado <xref:System.Windows.FrameworkElement.ActualHeight%2A> el evento y notificará el tamaño del medio cargado. Esto significa que hasta que se cargue el medio <xref:System.Windows.Controls.MediaElement> , el no ocupará ningún espacio físico [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] en, a <xref:System.Windows.FrameworkElement.Width%2A> menos <xref:System.Windows.FrameworkElement.Height%2A> que se establezcan las propiedades o.  
  
 El establecimiento de las <xref:System.Windows.FrameworkElement.Height%2A> propiedades <xref:System.Windows.Controls.MediaElement> yharáqueloselementosmultimediaseexpandanpararellenarel<xref:System.Windows.FrameworkElement.Width%2A> área proporcionada para. Para conservar la relación de aspecto original del medio, se <xref:System.Windows.FrameworkElement.Width%2A> debe <xref:System.Windows.FrameworkElement.Height%2A> establecer la propiedad o, pero no ambos. Establecer las propiedades <xref:System.Windows.FrameworkElement.Height%2A>yhará que los elementos multimedia presenten en un tamaño de elemento fijo que puede no ser deseable. <xref:System.Windows.FrameworkElement.Width%2A>  
  
 Para evitar tener un elemento de tamaño fijo, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] puede preprocesar el elemento multimedia. Esto se hace <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> estableciendo <xref:System.Windows.Controls.MediaState.Play> en o <xref:System.Windows.Controls.MediaState.Pause>. En un <xref:System.Windows.Controls.MediaState.Pause> estado, los elementos multimedia se preprocesarán y presentarán el primer fotograma. En un <xref:System.Windows.Controls.MediaState.Play> estado, los elementos multimedia se preprocesarán y comenzarán a reproducirse.  
  
<a name="mediaplayer"></a>   
## <a name="mediaplayer-class"></a>Clase MediaPlayer  
 Donde la <xref:System.Windows.Controls.MediaElement> clase es un elemento de marco, la <xref:System.Windows.Media.MediaPlayer> clase está diseñada para utilizarse en <xref:System.Windows.Media.Drawing> objetos. Los objetos de dibujo se usan cuando se pueden sacrificar las características del nivel de marco para obtener <xref:System.Windows.Freezable> ventajas de rendimiento o cuando se necesitan características. <xref:System.Windows.Media.MediaPlayer>permite aprovechar las ventajas de estas características a la vez que se proporciona contenido multimedia en las aplicaciones. Como <xref:System.Windows.Controls.MediaElement>, <xref:System.Windows.Media.MediaPlayer> se puede usar en modo independiente o de reloj, pero no tiene <xref:System.Windows.Controls.MediaElement> los Estados de descarga y carga del objeto. Esto reduce la complejidad del control de reproducción <xref:System.Windows.Media.MediaPlayer>de.  
  
### <a name="controlling-mediaplayer"></a>Control de MediaPlayer  
 Dado <xref:System.Windows.Media.MediaPlayer> que no tiene estado, hay solo dos formas de controlar la reproducción multimedia.  
  
1. Métodos de control interactivos. En contexto, en el modo independiente`null` (<xref:System.Windows.Media.MediaPlayer.Clock%2A> propiedad).  
  
2. <xref:System.Windows.Media.MediaClock> Vigente cuando el elemento multimedia tiene <xref:System.Windows.Media.MediaPlayer.Clock%2A>un.  
  
### <a name="displaying-a-mediaplayer"></a>Visualización de MediaPlayer  
 Técnicamente, no <xref:System.Windows.Media.MediaPlayer> se puede mostrar un, ya que no tiene ninguna representación física. Sin embargo, se puede usar para presentar elementos multimedia en <xref:System.Windows.Media.Drawing> mediante la <xref:System.Windows.Media.VideoDrawing> clase. <xref:System.Windows.Media.VideoDrawing> En el siguiente ejemplo se muestra el uso de para mostrar los elementos multimedia.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Vea la información [General sobre objetos de dibujo](drawing-objects-overview.md) para <xref:System.Windows.Media.Drawing> obtener más información acerca de los objetos.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.DrawingGroup>
- [Diseño](../advanced/layout.md)
- [Temas "Cómo..."](audio-and-video-how-to-topics.md)
