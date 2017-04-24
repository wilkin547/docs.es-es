---
title: "Informaci&#243;n general sobre el control Popup | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "controles, Popup"
  - "Popup (control) [WPF], acerca de Popup (control)"
ms.assetid: 774f53ca-bff8-470e-9ce9-3928b4cf3d4c
caps.latest.revision: 34
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 33
---
# Informaci&#243;n general sobre el control Popup
El control <xref:System.Windows.Controls.Primitives.Popup> proporciona una manera de mostrar contenido en una ventana independiente que flota sobre la ventana de la aplicación actual de manera relativa a un elemento designado o a una coordenada de la pantalla.  En este tema se presenta el control <xref:System.Windows.Controls.Primitives.Popup> y se proporciona información sobre su uso.  
  
   
  
<a name="What_Is_a_Popup_"></a>   
## ¿Qué es un control Popup?  
 Un control <xref:System.Windows.Controls.Primitives.Popup> muestra el contenido en una ventana independiente de manera relativa a un elemento o punto de la pantalla.  Cuando <xref:System.Windows.Controls.Primitives.Popup> está visible, la propiedad <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> se establece en `true`.  
  
> [!NOTE]
>  <xref:System.Windows.Controls.Primitives.Popup> no se abre automáticamente cuando el puntero del mouse se mueve sobre su objeto primario.  Si desea que <xref:System.Windows.Controls.Primitives.Popup> se abra automáticamente, utilice la clase <xref:System.Windows.Controls.ToolTip> o <xref:System.Windows.Controls.ToolTipService>.  Para obtener más información, consulte [Información general de información sobre herramientas](../../../../docs/framework/wpf/controls/tooltip-overview.md).  
  
<a name="APopupExample"></a>   
## Crear un control Popup  
 En el ejemplo siguiente se muestra cómo definir un control <xref:System.Windows.Controls.Primitives.Popup> que es el elemento secundario de un control <xref:System.Windows.Controls.Button>.  Dado que <xref:System.Windows.Controls.Button> puede tener un solo elemento secundario, en este ejemplo se coloca el texto correspondiente a los controles <xref:System.Windows.Controls.Button> y <xref:System.Windows.Controls.Primitives.Popup> en un objeto <xref:System.Windows.Controls.StackPanel>.  El contenido de <xref:System.Windows.Controls.Primitives.Popup> aparece en un control <xref:System.Windows.Controls.TextBlock>, que muestra su texto en una ventana independiente que flota sobre la ventana de la aplicación cerca del control <xref:System.Windows.Controls.Button> relacionado.  
  
 [!code-xml[PopupSimple#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#1)]  
  
 [!code-xml[PopupSimple#CreatePopupCodeXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#createpopupcodexaml)]  
  
<a name="PopupUses"></a>   
## Controles que implementan un control Popup  
 Puede integrar los controles <xref:System.Windows.Controls.Primitives.Popup> en otros controles.  Los controles siguientes implementan el control <xref:System.Windows.Controls.Primitives.Popup> para usos concretos:  
  
-   <xref:System.Windows.Controls.ToolTip>.  Si desea crear una información sobre herramientas para un elemento, utilice las clases <xref:System.Windows.Controls.ToolTip> y <xref:System.Windows.Controls.ToolTipService>.  Para obtener más información, consulte [Información general de información sobre herramientas](../../../../docs/framework/wpf/controls/tooltip-overview.md).  
  
-   <xref:System.Windows.Controls.ContextMenu>.  Si desea crear un menú contextual para un elemento, utilice el control <xref:System.Windows.Controls.ContextMenu>.  Para obtener más información, consulte [Información general sobre ContextMenu](../../../../docs/framework/wpf/controls/contextmenu-overview.md).  
  
-   <xref:System.Windows.Controls.ComboBox>.  Si desea crear un control de selección que tenga un cuadro de lista desplegable que se pueda mostrar u ocultar, utilice el control <xref:System.Windows.Controls.ComboBox>.  
  
-   <xref:System.Windows.Controls.Expander>.  Si desea crear un control que muestre un encabezado con un área contraíble que muestra contenido, utilice el control <xref:System.Windows.Controls.Expander>.  Para obtener más información, consulte [Información general sobre el control Expander](../../../../docs/framework/wpf/controls/expander-overview.md).  
  
<a name="PopupBehaviorandAppearance"></a>   
## Comportamiento y aspecto del control Popup  
 El control <xref:System.Windows.Controls.Primitives.Popup> proporciona funcionalidad que permite personalizar su comportamiento y aspecto.  Por ejemplo, puede establecer su comportamiento al abrirlo y cerrarlo, animaciones, efectos de imagen y opacidad, así como el tamaño y la posición de <xref:System.Windows.Controls.Primitives.Popup>.  
  
<a name="OpenandCloseBehavior"></a>   
### Comportamiento al abrirlo y cerrarlo  
 Un control <xref:System.Windows.Controls.Primitives.Popup> muestra su contenido cuando la propiedad <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> está establecida en `true`.  De manera predeterminada, <xref:System.Windows.Controls.Primitives.Popup> permanece abierto hasta que la propiedad <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> se establece en `false`.  Sin embargo, puede cambiar el comportamiento predeterminado estableciendo la propiedad <xref:System.Windows.Controls.Primitives.Popup.StaysOpen%2A> en `false`.  Al establecer esta propiedad en `false`, la ventana de contenido de <xref:System.Windows.Controls.Primitives.Popup> tiene la captura del mouse.  <xref:System.Windows.Controls.Primitives.Popup> pierde la captura del mouse y la ventana se cierra cuando un evento del mouse se produce fuera de la ventana de <xref:System.Windows.Controls.Primitives.Popup>.  
  
 Los eventos <xref:System.Windows.Controls.Primitives.Popup.Opened> y <xref:System.Windows.Controls.Primitives.Popup.Closed> se provocan cuando la ventana de contenido de <xref:System.Windows.Controls.Primitives.Popup> se abre o se cierra.  
  
<a name="Animation"></a>   
### Animación  
 El control <xref:System.Windows.Controls.Primitives.Popup> cuenta con compatibilidad integrada para las animaciones que se suelen asociar a comportamientos tales como el fundido de entrada y el deslizamiento.  Puede activar estas animaciones estableciendo la propiedad <xref:System.Windows.Controls.Primitives.Popup.PopupAnimation%2A> en un valor de enumeración <xref:System.Windows.Controls.Primitives.PopupAnimation>.  Para que las animaciones <xref:System.Windows.Controls.Primitives.Popup> funcionen correctamente, debe establecer la propiedad <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> en `true`.  
  
 También puede aplicar animaciones tales como <xref:System.Windows.Media.Animation.Storyboard> al control <xref:System.Windows.Controls.Primitives.Popup>.  
  
<a name="OpacityandBitmapEffects"></a>   
### Efectos de imagen y opacidad  
 La propiedad <xref:System.Windows.UIElement.Opacity%2A> de un control <xref:System.Windows.Controls.Primitives.Popup> no surte ningún efecto en su contenido.  De manera predeterminada, la ventana de contenido de <xref:System.Windows.Controls.Primitives.Popup> es opaca.  Para crear un <xref:System.Windows.Controls.Primitives.Popup> transparente, establezca la propiedad <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> en `true`.  
  
 El contenido de <xref:System.Windows.Controls.Primitives.Popup> no hereda los efectos de imagen, tales como <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>, que se establecen directamente en el control <xref:System.Windows.Controls.Primitives.Popup> o en cualquier otro elemento de la ventana primaria.  Para que los efectos de imagen aparezcan en el contenido de un control <xref:System.Windows.Controls.Primitives.Popup>, debe establecerlos directamente para su contenido.  Por ejemplo, si el elemento secundario de <xref:System.Windows.Controls.Primitives.Popup> es <xref:System.Windows.Controls.StackPanel>, establezca el efecto de imagen del objeto <xref:System.Windows.Controls.StackPanel>.  
  
<a name="PopupSize"></a>   
### Tamaño del control Popup  
 De manera predeterminada, un <xref:System.Windows.Controls.Primitives.Popup> ajusta su tamaño automáticamente a su contenido.  Cuando se produce el ajuste de tamaño automático, puede ocurrir que algunos efectos de imagen queden ocultos si el tamaño predeterminado del área de pantalla que se define para el contenido de <xref:System.Windows.Controls.Primitives.Popup> no proporciona espacio suficiente para que se muestren dichos efectos.  
  
 El contenido <xref:System.Windows.Controls.Primitives.Popup> también puede quedar oculto cuando se establece una transformación <xref:System.Windows.UIElement.RenderTransform%2A> para el contenido.  En este escenario, parte del contenido puede quedar oculto si el contenido del control <xref:System.Windows.Controls.Primitives.Popup> transformado se extiende más allá del área del <xref:System.Windows.Controls.Primitives.Popup> original.  Si un efecto de imagen o una transformación requiere más espacio, puede definir un margen alrededor del contenido de <xref:System.Windows.Controls.Primitives.Popup> a fin de aumentar el área del control.  
  
<a name="DefiningPopupPosition"></a>   
## Definir la posición del control Popup  
 Puede colocar un control Popup estableciendo las propiedades <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> y <xref:System.Windows.Controls.Primitives.Popup.VerticalOffsetProperty>.  Para obtener más información, consulte [Posición de un control Popup](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).  Cuando <xref:System.Windows.Controls.Primitives.Popup> se muestra en la pantalla, no cambia de posición al cambiar de posición su elemento primario.  
  
<a name="CustomizingPopupPlacement"></a>   
### Personalizar la posición del elemento emergente  
 Puede personalizar la posición de un control <xref:System.Windows.Controls.Primitives.Popup> especificando un conjunto de coordenadas que son relativas a la propiedad <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> donde debe aparecer el control <xref:System.Windows.Controls.Primitives.Popup>.  
  
 Para personalizar la posición, establezca la propiedad <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> en <xref:System.Windows.Controls.Primitives.PlacementMode>.  Después defina un delegado de <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> que devuelva un conjunto de puntos de posición y ejes primarios \(en orden de preferencia\) posibles para <xref:System.Windows.Controls.Primitives.Popup>.  El punto que muestra la parte mayor de <xref:System.Windows.Controls.Primitives.Popup> se selecciona automáticamente.  Para obtener un ejemplo, vea [Especificar una posición emergente personalizada](../../../../docs/framework/wpf/controls/how-to-specify-a-custom-popup-position.md).  
  
<a name="PopupandtheVisualTree"></a>   
## Controles Popup y el árbol visual  
 Un control <xref:System.Windows.Controls.Primitives.Popup> no tiene su propio [árbol visual](GTMT); en cambio, devuelve un tamaño de 0 \(cero\) cuando se llama al método <xref:System.Windows.Controls.Primitives.Popup.MeasureOverride%2A> para <xref:System.Windows.Controls.Primitives.Popup>.  Sin embargo, cuando se establece la propiedad <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> de <xref:System.Windows.Controls.Primitives.Popup> en `true`, se crea una nueva ventana con su propio árbol visual.  La nueva ventana incluye el contenido de la propiedad <xref:System.Windows.Controls.Primitives.Popup.Child%2A> de <xref:System.Windows.Controls.Primitives.Popup>.  El ancho y el alto de la nueva ventana no pueden ser mayores que el 75 por ciento del ancho o el alto de la pantalla.  
  
 El control <xref:System.Windows.Controls.Primitives.Popup> mantiene una referencia al contenido de su propiedad <xref:System.Windows.Controls.Primitives.Popup.Child%2A> como un elemento secundario lógico.  Cuando se crea la nueva ventana, el contenido de <xref:System.Windows.Controls.Primitives.Popup> se convierte en un elemento secundario visual de la ventana y sigue siendo un elemento secundario lógico de <xref:System.Windows.Controls.Primitives.Popup>.  A la inversa, <xref:System.Windows.Controls.Primitives.Popup> sigue siendo el elemento primario lógico del contenido de su propiedad <xref:System.Windows.Controls.Primitives.Popup.Child%2A>.  
  
## Vea también  
 <xref:System.Windows.Controls.Primitives.Popup>   
 <xref:System.Windows.Controls.Primitives.PopupPrimaryAxis>   
 <xref:System.Windows.Controls.Primitives.PlacementMode>   
 <xref:System.Windows.Controls.Primitives.CustomPopupPlacement>   
 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>   
 <xref:System.Windows.Controls.ToolTip>   
 <xref:System.Windows.Controls.ToolTipService>   
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)