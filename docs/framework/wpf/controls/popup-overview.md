---
title: Información general sobre el control Popup
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Popup
- Popup control [WPF], about Popup control
ms.assetid: 774f53ca-bff8-470e-9ce9-3928b4cf3d4c
ms.openlocfilehash: 911130d52744c5ba54750f214829a5d1900e083c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185951"
---
# <a name="popup-overview"></a>Información general sobre el control Popup
El <xref:System.Windows.Controls.Primitives.Popup> control proporciona una manera de mostrar contenido en una ventana independiente que flota sobre la ventana de aplicación actual en relación con un elemento designado o una coordenada de pantalla. En este tema <xref:System.Windows.Controls.Primitives.Popup> se presenta el control y se proporciona información sobre su uso.  

<a name="What_Is_a_Popup_"></a>
## <a name="what-is-a-popup"></a>¿Qué es un control Popup?  
 Un <xref:System.Windows.Controls.Primitives.Popup> control muestra contenido en una ventana independiente en relación con un elemento o punto de la pantalla. Cuando <xref:System.Windows.Controls.Primitives.Popup> la es <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> visible, la `true`propiedad se establece en .  
  
> [!NOTE]
> A <xref:System.Windows.Controls.Primitives.Popup> no se abre automáticamente cuando el puntero del mouse se mueve sobre su objeto primario. Si desea <xref:System.Windows.Controls.Primitives.Popup> que se abra <xref:System.Windows.Controls.ToolTip> automáticamente, utilice la clase o. <xref:System.Windows.Controls.ToolTipService> Para más información, consulte [Información general de información sobre herramientas](tooltip-overview.md).  
  
<a name="APopupExample"></a>
## <a name="creating-a-popup"></a>Creación de un elemento emergente  
 En el ejemplo siguiente <xref:System.Windows.Controls.Primitives.Popup> se muestra cómo definir <xref:System.Windows.Controls.Button> un control que es el elemento secundario de un control. Dado <xref:System.Windows.Controls.Button> que a solo puede tener un elemento <xref:System.Windows.Controls.Button> secundario, <xref:System.Windows.Controls.Primitives.Popup> en <xref:System.Windows.Controls.StackPanel>este ejemplo se coloca el texto de los controles y los controles en un archivo . El contenido <xref:System.Windows.Controls.Primitives.Popup> de la <xref:System.Windows.Controls.TextBlock> aparece en un control, que muestra su texto en <xref:System.Windows.Controls.Button> una ventana independiente que flota sobre la ventana de la aplicación cerca del control relacionado.  
  
 [!code-xaml[PopupSimple#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#1)]  
  
 [!code-xaml[PopupSimple#CreatePopupCodeXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#createpopupcodexaml)]  
  
<a name="PopupUses"></a>
## <a name="controls-that-implement-a-popup"></a>Controles que implementan un control Popup  
 Puede crear <xref:System.Windows.Controls.Primitives.Popup> controles en otros controles. Los siguientes controles <xref:System.Windows.Controls.Primitives.Popup> implementan el control para usos específicos:  
  
- <xref:System.Windows.Controls.ToolTip>. Si desea crear una información sobre herramientas <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.ToolTipService> para un elemento, utilice las clases y. Para más información, consulte [Información general de información sobre herramientas](tooltip-overview.md).  
  
- <xref:System.Windows.Controls.ContextMenu>. Si desea crear un menú contextual para <xref:System.Windows.Controls.ContextMenu> un elemento, utilice el control. Para más información, consulte [Información general sobre ContextMenu](contextmenu-overview.md).  
  
- <xref:System.Windows.Controls.ComboBox>. Si desea crear un control de selección que tenga un cuadro de lista <xref:System.Windows.Controls.ComboBox> desplegable que se puede mostrar u ocultar, utilice el control.  
  
- <xref:System.Windows.Controls.Expander>. Si desea crear un control que muestre un encabezado con un área <xref:System.Windows.Controls.Expander> contraíble que muestre contenido, utilice el control. Para más información, consulte [Información general sobre el control Expander](expander-overview.md).  
  
<a name="PopupBehaviorandAppearance"></a>
## <a name="popup-behavior-and-appearance"></a>Comportamiento y apariencia del control Popup  
 El <xref:System.Windows.Controls.Primitives.Popup> control proporciona funcionalidad que le permite personalizar su comportamiento y apariencia. Por ejemplo, puede establecer el comportamiento de apertura y cierre, la animación, la opacidad y los efectos de mapa de bits, y <xref:System.Windows.Controls.Primitives.Popup> el tamaño y la posición.  
  
<a name="OpenandCloseBehavior"></a>
### <a name="open-and-close-behavior"></a>Comportamiento de apertura y cierre  
 Un <xref:System.Windows.Controls.Primitives.Popup> control muestra su <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> contenido cuando `true`la propiedad se establece en . De forma <xref:System.Windows.Controls.Primitives.Popup> predeterminada, permanece <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> abierto hasta `false`que la propiedad se establece en . Sin embargo, puede cambiar el <xref:System.Windows.Controls.Primitives.Popup.StaysOpen%2A> comportamiento `false`predeterminado estableciendo la propiedad en . Al establecer esta `false`propiedad <xref:System.Windows.Controls.Primitives.Popup> en , la ventana de contenido tiene captura del mouse. La <xref:System.Windows.Controls.Primitives.Popup> captura del mouse pierde y la ventana se <xref:System.Windows.Controls.Primitives.Popup> cierra cuando se produce un evento del mouse fuera de la ventana.  
  
 Los <xref:System.Windows.Controls.Primitives.Popup.Opened> <xref:System.Windows.Controls.Primitives.Popup.Closed> eventos y se <xref:System.Windows.Controls.Primitives.Popup> generan cuando la ventana de contenido está abierta o cerrada.  
  
<a name="Animation"></a>
### <a name="animation"></a>Animación  
 El <xref:System.Windows.Controls.Primitives.Popup> control tiene compatibilidad integrada para las animaciones que normalmente están asociadas con comportamientos como fade-in y slide-in. Puede activar estas animaciones estableciendo <xref:System.Windows.Controls.Primitives.Popup.PopupAnimation%2A> la <xref:System.Windows.Controls.Primitives.PopupAnimation> propiedad en un valor de enumeración. Para <xref:System.Windows.Controls.Primitives.Popup> que las animaciones funcionen <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> correctamente, debe establecer la propiedad en `true`.  
  
 También puede aplicar animaciones <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Controls.Primitives.Popup> como al control.  
  
<a name="OpacityandBitmapEffects"></a>
### <a name="opacity-and-bitmap-effects"></a>Opacidad y efectos de imagen  
 La <xref:System.Windows.UIElement.Opacity%2A> propiedad <xref:System.Windows.Controls.Primitives.Popup> de un control no tiene ningún efecto en su contenido. De forma <xref:System.Windows.Controls.Primitives.Popup> predeterminada, la ventana de contenido es opaca. Para crear <xref:System.Windows.Controls.Primitives.Popup>un transparente, establezca la propiedad en <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> `true`.  
  
 El contenido <xref:System.Windows.Controls.Primitives.Popup> de a no hereda <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>efectos de mapa <xref:System.Windows.Controls.Primitives.Popup> de bits, como , que se establecen directamente en el control o en cualquier otro elemento de la ventana primaria. Para que los efectos de <xref:System.Windows.Controls.Primitives.Popup>mapa de bits aparezcan en el contenido de un , debe establecer el efecto de mapa de bits directamente en su contenido. Por ejemplo, si el <xref:System.Windows.Controls.Primitives.Popup> elemento <xref:System.Windows.Controls.StackPanel>secundario de a <xref:System.Windows.Controls.StackPanel>es un , establezca el efecto de mapa de bits en el archivo .  
  
<a name="PopupSize"></a>
### <a name="popup-size"></a>Tamaño del control Popup  
 De forma <xref:System.Windows.Controls.Primitives.Popup> predeterminada, a se ajusta automáticamente a su contenido. Cuando se produce el tamaño automático, algunos efectos de mapa de bits <xref:System.Windows.Controls.Primitives.Popup> pueden estar ocultos porque el tamaño predeterminado del área de pantalla que se define para el contenido no proporciona suficiente espacio para que se muestren los efectos de mapa de bits.  
  
 <xref:System.Windows.Controls.Primitives.Popup>el contenido también se puede <xref:System.Windows.UIElement.RenderTransform%2A> ocultar al establecer un contenido. En este escenario, es posible que se osconeste algún contenido si el contenido de lo transformado <xref:System.Windows.Controls.Primitives.Popup> se extiende más allá del área del archivo . <xref:System.Windows.Controls.Primitives.Popup> Si un efecto o transformación de mapa de bits <xref:System.Windows.Controls.Primitives.Popup> requiere más espacio, puede definir un margen alrededor del contenido para proporcionar más área para el control.  
  
<a name="DefiningPopupPosition"></a>
## <a name="defining-the-popup-position"></a>Definición de la posición del control Popup  
 Puede colocar una ventana emergente <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>estableciendo <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>las <xref:System.Windows.Controls.Primitives.Popup.VerticalOffsetProperty> propiedades , , <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, , y . Para más información, consulte [Posición de un control Popup](popup-placement-behavior.md). Cuando <xref:System.Windows.Controls.Primitives.Popup> se muestra en la pantalla, no se reposiciona si se vuelve a colocar su elemento primario.  
  
<a name="CustomizingPopupPlacement"></a>
### <a name="customizing-popup-placement"></a>Personalización de la ubicación del elemento Popup  
 Puede personalizar la ubicación <xref:System.Windows.Controls.Primitives.Popup> de un control especificando un conjunto <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> de coordenadas <xref:System.Windows.Controls.Primitives.Popup> relativas al lugar donde desea que aparezca.  
  
 Para personalizar la <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ubicación, <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>establezca la propiedad en . A continuación, defina un <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegado que devuelva un conjunto de posibles <xref:System.Windows.Controls.Primitives.Popup>puntos de ubicación y ejes primarios (en orden de preferencia) para el archivo . El punto que muestra la <xref:System.Windows.Controls.Primitives.Popup> parte más grande de la se selecciona automáticamente. Para ver un ejemplo, consulte cómo [especificar una posición emergente personalizada](how-to-specify-a-custom-popup-position.md).  
  
<a name="PopupandtheVisualTree"></a>
## <a name="popup-and-the-visual-tree"></a>Control Popup y árbol visual  
 Un <xref:System.Windows.Controls.Primitives.Popup> control no tiene su propio árbol visual; en su lugar devuelve un tamaño <xref:System.Windows.Controls.Primitives.Popup.MeasureOverride%2A> de <xref:System.Windows.Controls.Primitives.Popup> 0 (cero) cuando se llama al método para. Sin embargo, <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> al <xref:System.Windows.Controls.Primitives.Popup> establecer `true`la propiedad de en , se crea una nueva ventana con su propio árbol visual. La nueva ventana <xref:System.Windows.Controls.Primitives.Popup.Child%2A> contiene <xref:System.Windows.Controls.Primitives.Popup>el contenido de . El ancho y el alto de la ventana nueva no pueden superar en más de un 75 por ciento el ancho o el alto de la pantalla.  
  
 El <xref:System.Windows.Controls.Primitives.Popup> control mantiene una <xref:System.Windows.Controls.Primitives.Popup.Child%2A> referencia a su contenido como un elemento secundario lógico. Cuando se crea la nueva <xref:System.Windows.Controls.Primitives.Popup> ventana, el contenido de se convierte en <xref:System.Windows.Controls.Primitives.Popup>un elemento secundario visual de la ventana y sigue siendo el elemento secundario lógico de . Por el <xref:System.Windows.Controls.Primitives.Popup> contrario, sigue siendo <xref:System.Windows.Controls.Primitives.Popup.Child%2A> el elemento primario lógico de su contenido.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Controls.Primitives.Popup>
- <xref:System.Windows.Controls.Primitives.PopupPrimaryAxis>
- <xref:System.Windows.Controls.Primitives.PlacementMode>
- <xref:System.Windows.Controls.Primitives.CustomPopupPlacement>
- <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [Temas de información](popup-how-to-topics.md)
- [Temas de información](tooltip-how-to-topics.md)
