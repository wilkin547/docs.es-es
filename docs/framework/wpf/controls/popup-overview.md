---
title: Información general sobre el control Popup
description: Obtenga información sobre el control popup Windows Presentation Foundation, que proporciona una manera de mostrar el contenido en una ventana que flota sobre la aplicación actual.
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Popup
- Popup control [WPF], about Popup control
ms.assetid: 774f53ca-bff8-470e-9ce9-3928b4cf3d4c
ms.openlocfilehash: 84eaddc53366df6d1da1a0a005d3618268f8cce2
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167533"
---
# <a name="popup-overview"></a>Información general sobre el control Popup
El <xref:System.Windows.Controls.Primitives.Popup> control proporciona una manera de mostrar el contenido en una ventana independiente que flota sobre la ventana de la aplicación actual en relación con un elemento o una coordenada de la pantalla designados. En este tema se presenta el <xref:System.Windows.Controls.Primitives.Popup> control y se proporciona información sobre su uso.  

<a name="What_Is_a_Popup_"></a>
## <a name="what-is-a-popup"></a>¿Qué es un control Popup?  
 Un <xref:System.Windows.Controls.Primitives.Popup> control muestra el contenido en una ventana independiente relativa a un elemento o punto de la pantalla. Cuando <xref:System.Windows.Controls.Primitives.Popup> está visible, la <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> propiedad se establece en `true` .  
  
> [!NOTE]
> <xref:System.Windows.Controls.Primitives.Popup>No se abre automáticamente cuando el puntero del mouse se mueve sobre su objeto primario. Si desea que se <xref:System.Windows.Controls.Primitives.Popup> abra automáticamente, use la <xref:System.Windows.Controls.ToolTip> clase o <xref:System.Windows.Controls.ToolTipService> . Para más información, consulte [Información general de información sobre herramientas](tooltip-overview.md).  
  
<a name="APopupExample"></a>
## <a name="creating-a-popup"></a>Creación de un elemento emergente  
 En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.Primitives.Popup> control que es el elemento secundario de un <xref:System.Windows.Controls.Button> control. Dado <xref:System.Windows.Controls.Button> que un solo puede tener un elemento secundario, en este ejemplo se coloca el texto de los <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.Popup> controles y en <xref:System.Windows.Controls.StackPanel> . El contenido de <xref:System.Windows.Controls.Primitives.Popup> aparece en un <xref:System.Windows.Controls.TextBlock> control, que muestra su texto en una ventana independiente que flota sobre la ventana de la aplicación cerca del <xref:System.Windows.Controls.Button> control relacionado.  
  
 [!code-xaml[PopupSimple#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#1)]  
  
 [!code-xaml[PopupSimple#CreatePopupCodeXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#createpopupcodexaml)]  
  
<a name="PopupUses"></a>
## <a name="controls-that-implement-a-popup"></a>Controles que implementan un control Popup  
 Puede compilar <xref:System.Windows.Controls.Primitives.Popup> controles en otros controles. Los controles siguientes implementan el <xref:System.Windows.Controls.Primitives.Popup> control para usos específicos:  
  
- <xref:System.Windows.Controls.ToolTip>. Si desea crear una información sobre herramientas para un elemento, utilice las <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.ToolTipService> clases y. Para más información, consulte [Información general de información sobre herramientas](tooltip-overview.md).  
  
- <xref:System.Windows.Controls.ContextMenu>. Si desea crear un menú contextual para un elemento, utilice el <xref:System.Windows.Controls.ContextMenu> control. Para más información, consulte [Información general sobre ContextMenu](contextmenu-overview.md).  
  
- <xref:System.Windows.Controls.ComboBox>. Si desea crear un control de selección que tiene un cuadro de lista desplegable que se puede mostrar u ocultar, use el <xref:System.Windows.Controls.ComboBox> control.  
  
- <xref:System.Windows.Controls.Expander>. Si desea crear un control que muestre un encabezado con un área contraíble que muestre contenido, use el <xref:System.Windows.Controls.Expander> control. Para más información, consulte [Información general sobre el control Expander](expander-overview.md).  
  
<a name="PopupBehaviorandAppearance"></a>
## <a name="popup-behavior-and-appearance"></a>Comportamiento y apariencia del control Popup  
 El <xref:System.Windows.Controls.Primitives.Popup> control proporciona funcionalidad que permite personalizar su comportamiento y apariencia. Por ejemplo, puede establecer el comportamiento de apertura y cierre, la animación, la opacidad y los efectos de imagen, así como <xref:System.Windows.Controls.Primitives.Popup> el tamaño y la posición.  
  
<a name="OpenandCloseBehavior"></a>
### <a name="open-and-close-behavior"></a>Comportamiento de apertura y cierre  
 Un <xref:System.Windows.Controls.Primitives.Popup> control muestra su contenido cuando la <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> propiedad está establecida en `true` . De forma predeterminada, <xref:System.Windows.Controls.Primitives.Popup> permanece abierto hasta que la <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> propiedad se establece en `false` . Sin embargo, puede cambiar el comportamiento predeterminado estableciendo la <xref:System.Windows.Controls.Primitives.Popup.StaysOpen%2A> propiedad en `false` . Al establecer esta propiedad en `false` , la <xref:System.Windows.Controls.Primitives.Popup> ventana de contenido tiene la captura del mouse. El <xref:System.Windows.Controls.Primitives.Popup> pierde la captura del mouse y la ventana se cierra cuando se produce un evento del mouse fuera de la <xref:System.Windows.Controls.Primitives.Popup> ventana.  
  
 Los <xref:System.Windows.Controls.Primitives.Popup.Opened> <xref:System.Windows.Controls.Primitives.Popup.Closed> eventos y se generan cuando la <xref:System.Windows.Controls.Primitives.Popup> ventana de contenido está abierta o cerrada.  
  
<a name="Animation"></a>
### <a name="animation"></a>Animación  
 El <xref:System.Windows.Controls.Primitives.Popup> control tiene compatibilidad integrada con las animaciones que normalmente están asociadas a comportamientos como el fundido y la deslizamiento. Puede activar estas animaciones estableciendo la <xref:System.Windows.Controls.Primitives.Popup.PopupAnimation%2A> propiedad en un <xref:System.Windows.Controls.Primitives.PopupAnimation> valor de enumeración. Para <xref:System.Windows.Controls.Primitives.Popup> que las animaciones funcionen correctamente, debe establecer la <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> propiedad en `true` .  
  
 También puede aplicar animaciones como <xref:System.Windows.Media.Animation.Storyboard> al <xref:System.Windows.Controls.Primitives.Popup> control.  
  
<a name="OpacityandBitmapEffects"></a>
### <a name="opacity-and-bitmap-effects"></a>Opacidad y efectos de imagen  
 La <xref:System.Windows.UIElement.Opacity%2A> propiedad de un <xref:System.Windows.Controls.Primitives.Popup> control no tiene ningún efecto en su contenido. De forma predeterminada, la <xref:System.Windows.Controls.Primitives.Popup> ventana de contenido es opaca. Para crear un transparente <xref:System.Windows.Controls.Primitives.Popup> , establezca la <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> propiedad en `true` .  
  
 El contenido de no <xref:System.Windows.Controls.Primitives.Popup> hereda efectos de imagen, como <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> , que se establecen directamente en el <xref:System.Windows.Controls.Primitives.Popup> control o en cualquier otro elemento de la ventana primaria. Para que los efectos de imagen aparezcan en el contenido de <xref:System.Windows.Controls.Primitives.Popup> , debe establecer el efecto de imagen directamente en su contenido. Por ejemplo, si el elemento secundario de un <xref:System.Windows.Controls.Primitives.Popup> es <xref:System.Windows.Controls.StackPanel> , establezca el efecto de imagen en <xref:System.Windows.Controls.StackPanel> .  
  
<a name="PopupSize"></a>
### <a name="popup-size"></a>Tamaño del control Popup  
 De forma predeterminada, <xref:System.Windows.Controls.Primitives.Popup> se ajusta automáticamente a su contenido. Cuando se produce el ajuste automático de tamaño, se pueden ocultar algunos efectos de imagen, ya que el tamaño predeterminado del área de pantalla que se define para el <xref:System.Windows.Controls.Primitives.Popup> contenido no proporciona espacio suficiente para que se muestren los efectos de imagen.  
  
 <xref:System.Windows.Controls.Primitives.Popup>también se puede ocultar el contenido al establecer un <xref:System.Windows.UIElement.RenderTransform%2A> en el contenido de. En este escenario, es posible que se oculte algún contenido si el contenido del transformado se <xref:System.Windows.Controls.Primitives.Popup> extiende más allá del área del original <xref:System.Windows.Controls.Primitives.Popup> . Si un efecto o transformación de un mapa de bits requiere más espacio, puede definir un margen alrededor del <xref:System.Windows.Controls.Primitives.Popup> contenido con el fin de proporcionar más área para el control.  
  
<a name="DefiningPopupPosition"></a>
## <a name="defining-the-popup-position"></a>Definición de la posición del control Popup  
 Puede colocar un elemento emergente mediante el establecimiento de las <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> propiedades,, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> , <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> y <xref:System.Windows.Controls.Primitives.Popup.VerticalOffsetProperty> . Para más información, consulte [Posición de un control Popup](popup-placement-behavior.md). Cuando <xref:System.Windows.Controls.Primitives.Popup> se muestra en la pantalla, no cambia de posición si se cambia la posición de su elemento primario.  
  
<a name="CustomizingPopupPlacement"></a>
### <a name="customizing-popup-placement"></a>Personalización de la ubicación del elemento Popup  
 Puede personalizar la ubicación de un <xref:System.Windows.Controls.Primitives.Popup> control especificando un conjunto de coordenadas que son relativas al <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> donde desea <xref:System.Windows.Controls.Primitives.Popup> que aparezca.  
  
 Para personalizar la selección de ubicación, establezca la <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> propiedad en <xref:System.Windows.Controls.Primitives.PlacementMode.Custom> . A continuación, defina un <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegado que devuelva un conjunto de posibles puntos de ubicación y ejes principales (en orden de preferencia) para <xref:System.Windows.Controls.Primitives.Popup> . El punto que muestra la parte más grande del <xref:System.Windows.Controls.Primitives.Popup> se selecciona automáticamente. Para ver un ejemplo, consulte cómo [especificar una posición emergente personalizada](how-to-specify-a-custom-popup-position.md).  
  
<a name="PopupandtheVisualTree"></a>
## <a name="popup-and-the-visual-tree"></a>Control Popup y árbol visual  
 Un <xref:System.Windows.Controls.Primitives.Popup> control no tiene su propio árbol visual; en su lugar, devuelve un tamaño de 0 (cero) cuando <xref:System.Windows.Controls.Primitives.Popup.MeasureOverride%2A> se llama al método para <xref:System.Windows.Controls.Primitives.Popup> . Sin embargo, al establecer la <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> propiedad de <xref:System.Windows.Controls.Primitives.Popup> en `true` , se crea una nueva ventana con su propio árbol visual. La nueva ventana contiene el <xref:System.Windows.Controls.Primitives.Popup.Child%2A> contenido de <xref:System.Windows.Controls.Primitives.Popup> . El ancho y el alto de la ventana nueva no pueden superar en más de un 75 por ciento el ancho o el alto de la pantalla.  
  
 El <xref:System.Windows.Controls.Primitives.Popup> control mantiene una referencia a su <xref:System.Windows.Controls.Primitives.Popup.Child%2A> contenido como un elemento secundario lógico. Cuando se crea la nueva ventana, el contenido de <xref:System.Windows.Controls.Primitives.Popup> se convierte en un elemento secundario visual de la ventana y sigue siendo el elemento secundario lógico de <xref:System.Windows.Controls.Primitives.Popup> . Por el contrario, <xref:System.Windows.Controls.Primitives.Popup> sigue siendo el elemento primario lógico de su <xref:System.Windows.Controls.Primitives.Popup.Child%2A> contenido.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.Primitives.Popup>
- <xref:System.Windows.Controls.Primitives.PopupPrimaryAxis>
- <xref:System.Windows.Controls.Primitives.PlacementMode>
- <xref:System.Windows.Controls.Primitives.CustomPopupPlacement>
- <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [Temas "Cómo..."](popup-how-to-topics.md)
- [Temas "Cómo..."](tooltip-how-to-topics.md)
