---
title: Posición de un control Popup
ms.date: 03/30/2017
helpviewer_keywords:
- popups [WPF]
- Popup control [WPF], placing
- placing popups [WPF]
- positioning popups [WPF]
ms.assetid: fbf642e9-f670-4efd-a7af-a67468a1c8e1
ms.openlocfilehash: 1c377e62ffd334638031baee4d4831ac5a31acf3
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243263"
---
# <a name="popup-placement-behavior"></a>Posición de un control Popup
Un <xref:System.Windows.Controls.Primitives.Popup> control muestra el contenido en una ventana independiente que flota sobre una aplicación. Puede especificar la posición <xref:System.Windows.Controls.Primitives.Popup> de un pariente de un control, <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>el <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>ratón <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>o la pantalla utilizando las propiedades , , , y <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> .  Estas propiedades trabajan juntas para darle flexibilidad a <xref:System.Windows.Controls.Primitives.Popup>la medida de especificar la posición del archivo .  
  
> [!NOTE]
> Las <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.ContextMenu> clases y también definen estas cinco propiedades y se comportan de forma similar.  

<a name="Positioning"></a>
## <a name="positioning-the-popup"></a>Posicionamiento del elemento Popup  
 La colocación <xref:System.Windows.Controls.Primitives.Popup> de a <xref:System.Windows.UIElement> puede ser relativa a una o a toda la pantalla.  En el ejemplo <xref:System.Windows.Controls.Primitives.Popup> siguiente se crean <xref:System.Windows.UIElement>cuatro controles relativos a una imagen, en este caso. Todos los <xref:System.Windows.Controls.Primitives.Popup> controles <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> tienen la `image1`propiedad <xref:System.Windows.Controls.Primitives.Popup> establecida en , pero cada uno tiene un valor diferente para la propiedad placement.  
  
 [!code-xaml[PopupPositionSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#3)]  
  
 La siguiente ilustración muestra <xref:System.Windows.Controls.Primitives.Popup> la imagen y los controles  
  
 ![Imagen con cuatro controles Popup](./media/popup-placement-behavior/popup-placement-intro.png "Imagen con cuatro ventanas emergentes")
  
 En este ejemplo sencillo se <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> muestra cómo establecer <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>las <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>propiedades <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> y, pero mediante el <xref:System.Windows.Controls.Primitives.Popup> uso de las propiedades , , y, tiene aún más control sobre dónde se coloca el.  
  
<a name="Definitions"></a>
## <a name="definitions-of-terms-the-anatomy-of-a-popup"></a>Definiciones de términos: la anatomía de un elemento Popup  
 Los siguientes términos son <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>útiles <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>para comprender cómo las propiedades <xref:System.Windows.Controls.Primitives.Popup>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, , y <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> :  
  
- Objeto de destino  
  
- Área de destino  
  
- Origen de destino  
  
- Punto de alineación del elemento Popup  
  
 Estos términos proporcionan una manera conveniente de <xref:System.Windows.Controls.Primitives.Popup> hacer referencia a varios aspectos del control y con el que está asociado.  
  
### <a name="target-object"></a>Objeto de destino  
 El objeto de *destino* <xref:System.Windows.Controls.Primitives.Popup> es el elemento al que está asociado. Si <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> se establece la propiedad, especifica el objeto de destino.  Si <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> no se establece <xref:System.Windows.Controls.Primitives.Popup> y tiene un elemento primario, el elemento primario es el objeto de destino.  Si no <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> hay ningún valor ni padre, no <xref:System.Windows.Controls.Primitives.Popup> hay ningún objeto de destino y se coloca en relación con la pantalla.  
  
 En el ejemplo <xref:System.Windows.Controls.Primitives.Popup> siguiente se crea <xref:System.Windows.Controls.Canvas>un que es el elemento secundario de un archivo .  El ejemplo no <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> establece la <xref:System.Windows.Controls.Primitives.Popup>propiedad en el archivo . El valor <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> predeterminado <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom?displayProperty=nameWithType>para <xref:System.Windows.Controls.Primitives.Popup> es , <xref:System.Windows.Controls.Canvas>por lo que aparece debajo del archivo .  
  
 [!code-xaml[PopupPositionSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#1)]  
  
 La siguiente ilustración <xref:System.Windows.Controls.Primitives.Popup> muestra que se <xref:System.Windows.Controls.Canvas>coloca en relación con el archivo .  
  
 ![Control Popup sin PlacementTarget](./media/popup-placement-behavior/popup-placement-no-placement-target.png "Popup sin PlacementTarget.")  

 En el ejemplo <xref:System.Windows.Controls.Primitives.Popup> siguiente se crea <xref:System.Windows.Controls.Canvas>un que <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> es el `ellipse1`elemento secundario de un <xref:System.Windows.Shapes.Ellipse>, pero esta vez se establece en , por lo que la ventana emergente aparece debajo del archivo .  
  
 [!code-xaml[PopupPositionSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#2)]  
  
 La siguiente ilustración <xref:System.Windows.Controls.Primitives.Popup> muestra que se <xref:System.Windows.Shapes.Ellipse>coloca en relación con el archivo .  
  
 ![Control Popup colocado en relación con una elipse](./media/popup-placement-behavior/popup-placement-with-placement-target.png "Control Popup con PlacementTarget")
  
> [!NOTE]
> Para <xref:System.Windows.Controls.ToolTip>, el <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> valor <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>predeterminado de es .  Para <xref:System.Windows.Controls.ContextMenu>, el <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> valor <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>predeterminado de es . Estos valores se explican más adelante, en "Trabajo en conjunto de las propiedades".  
  
### <a name="target-area"></a>Área de destino  
 El *área de destino* es el <xref:System.Windows.Controls.Primitives.Popup> área de la pantalla con la que se trata. En los ejemplos <xref:System.Windows.Controls.Primitives.Popup> anteriores, el se alinea con los límites del <xref:System.Windows.Controls.Primitives.Popup> objeto de destino, pero <xref:System.Windows.Controls.Primitives.Popup> en algunos casos, el se alinea con otros límites, incluso si el tiene un objeto de destino.  Si <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se establece la propiedad, el área de destino es diferente de los límites del objeto de destino.  
  
 En el ejemplo <xref:System.Windows.Controls.Canvas> siguiente se crean <xref:System.Windows.Shapes.Rectangle> dos <xref:System.Windows.Controls.Primitives.Popup>objetos, cada uno de los cuales contiene un archivo y un archivo .  En ambos casos, el <xref:System.Windows.Controls.Primitives.Popup> objeto <xref:System.Windows.Controls.Canvas>de destino para el es el archivo . El <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Canvas> primero tiene <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> el conjunto, <xref:System.Windows.Rect.X%2A> <xref:System.Windows.Rect.Y%2A>con <xref:System.Windows.Rect.Width%2A>sus <xref:System.Windows.Rect.Height%2A> propiedades , , , y establecidos en 50, 50, 50 y 100, respectivamente. El <xref:System.Windows.Controls.Primitives.Popup> en <xref:System.Windows.Controls.Canvas> el segundo <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> no tiene el conjunto.  Como resultado, el <xref:System.Windows.Controls.Primitives.Popup> primero se <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> coloca debajo de la y la segunda <xref:System.Windows.Controls.Primitives.Popup> se coloca debajo de la <xref:System.Windows.Controls.Canvas>. Cada <xref:System.Windows.Controls.Canvas> uno <xref:System.Windows.Shapes.Rectangle> también contiene un que <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> tiene los <xref:System.Windows.Controls.Primitives.Popup>mismos límites que el para el primer .  Tenga en <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> cuenta que el no crea un elemento visible en la aplicación; el ejemplo <xref:System.Windows.Shapes.Rectangle> crea a <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>para representar el archivo .  
  
 [!code-xaml[PopupPositionSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#4)]  
  
 En la ilustración siguiente se muestra el resultado del ejemplo anterior.  
  
 ![Elemento emergente con y sin PlacementRectangle](./media/popup-placement-behavior/popup-placement-placement-rectangle.png "Popup con y sin PlacementRectangle.")  

### <a name="target-origin-and-popup-alignment-point"></a>Origen de destino y punto de alineación del elemento Popup  
 El *origen de destino* y el *punto de alineación del elemento Popup* son puntos de referencia en el área de destino y el elemento emergente, respectivamente, que se usan para posicionamiento. Puede utilizar <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> las <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> propiedades y para desplazar la ventana emergente del área de destino.  El <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> y son relativos al origen de destino y al punto de alineación emergente. El valor <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> de la propiedad determina dónde se encuentran el origen de destino y el punto de alineación emergente.  
  
 En el ejemplo <xref:System.Windows.Controls.Primitives.Popup> siguiente <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> se <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> crea a y establece las propiedades y en 20.  La <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> propiedad se <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> establece en (valor predeterminado), por lo que el origen de destino es la esquina inferior <xref:System.Windows.Controls.Primitives.Popup>izquierda del área de destino y el punto de alineación emergente es la esquina superior izquierda del archivo .  
  
 [!code-xaml[PopupPositionSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#5)]  
  
 En la ilustración siguiente se muestra el resultado del ejemplo anterior.  
  
 ![Posición de un control Popup con punto de alineación de origen de destino](./media/popup-placement-behavior/popup-placement-target-origin-alignment-point.png "Popup con HorizontalOffset y VerticalOffset.")
  
<a name="How"></a>
## <a name="how-the-properties-work-together"></a>Trabajo en conjunto de las propiedades  
 Los valores <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>de <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> , , y deben considerarse juntos para averiguar el área de destino correcta, el origen de destino y el punto de alineación emergente.  Por ejemplo, si <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> el <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>valor de es , <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> no hay ningún objeto de destino, se omite y el área de destino son los límites del puntero del mouse. Por otro lado, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>si <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> es , el o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> padre determina el objeto de destino y determina el área de destino.  
  
 En la tabla siguiente se describe el objeto de destino, el área <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> de destino, <xref:System.Windows.Controls.Primitives.PlacementMode> el origen de destino y el punto de alineación emergente e indica si se utilizan para cada valor de enumeración y se utilizan.  
  
|PlacementMode|Objeto de destino|Área de destino|Origen de destino|Punto de alineación del elemento Popup|  
|-------------------|-------------------|-----------------|-------------------|---------------------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|No es aplicable. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> se omite.|La pantalla, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> o si está establecida.  Es <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> relativo a la pantalla.|La esquina superior izquierda del área de destino.|La esquina superior izquierda <xref:System.Windows.Controls.Primitives.Popup>del archivo .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|No es aplicable. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> se omite.|La pantalla, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> o si está establecida.  Es <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> relativo a la pantalla.|La esquina superior izquierda del área de destino.|La esquina superior izquierda <xref:System.Windows.Controls.Primitives.Popup>del archivo .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o padre.|El objeto de <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> destino, o si está establecido.  Es <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> relativo al objeto de destino.|La esquina inferior izquierda del área de destino.|La esquina superior izquierda <xref:System.Windows.Controls.Primitives.Popup>del archivo .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o padre.|El objeto de <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> destino, o si está establecido.  Es <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> relativo al objeto de destino.|El centro del área de destino.|El centro <xref:System.Windows.Controls.Primitives.Popup>de la .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o padre.|El objeto de <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> destino, o si está establecido.  Es <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> relativo al objeto de destino.|Definido por <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>el archivo .|Definido por <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>el archivo .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o padre.|El objeto de <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> destino, o si está establecido.  Es <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> relativo al objeto de destino.|La esquina superior izquierda del área de destino.|La esquina superior derecha <xref:System.Windows.Controls.Primitives.Popup>de la .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|No es aplicable. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> se omite.|Los límites del puntero del mouse. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se omite.|La esquina inferior izquierda del área de destino.|La esquina superior izquierda <xref:System.Windows.Controls.Primitives.Popup>del archivo .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|No es aplicable. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> se omite.|Los límites del puntero del mouse. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se omite.|La esquina superior izquierda del área de destino.|La esquina superior izquierda <xref:System.Windows.Controls.Primitives.Popup>del archivo .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o padre.|El objeto de <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> destino, o si está establecido.  Es <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> relativo al objeto de destino.|La esquina superior izquierda del área de destino.|La esquina superior izquierda <xref:System.Windows.Controls.Primitives.Popup>del archivo .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o padre.|El objeto de <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> destino, o si está establecido.  Es <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> relativo al objeto de destino.|La esquina superior izquierda del área de destino.|La esquina superior izquierda <xref:System.Windows.Controls.Primitives.Popup>del archivo .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o padre.|El objeto de <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> destino, o si está establecido.  Es <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> relativo al objeto de destino.|La esquina superior derecha del área de destino.|La esquina superior izquierda <xref:System.Windows.Controls.Primitives.Popup>del archivo .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o padre.|El objeto de <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> destino, o si está establecido.  Es <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> relativo al objeto de destino.|La esquina superior izquierda del área de destino.|La esquina inferior izquierda <xref:System.Windows.Controls.Primitives.Popup>del archivo .|  
  
 Las siguientes ilustraciones <xref:System.Windows.Controls.Primitives.Popup>muestran el área de destino , <xref:System.Windows.Controls.Primitives.PlacementMode> el origen de destino y el punto de alineación emergente para cada valor. En cada figura, el área objetivo <xref:System.Windows.Controls.Primitives.Popup> es amarilla y es azul.  
  
 ![Control Popup con ubicación Absolute o AbsolutePoint](./media/popup-placement-behavior/popup-placement-absolute.png "La colocación es Absolute o AbsolutePoint.")
  
 ![Control Popup con ubicación Bottom](./media/popup-placement-behavior/popup-placement-bottom.png "La colocación es Inferior.")
  
 ![Control Popup con ubicación Center](./media/popup-placement-behavior/popup-placement-center.png "La colocación es Centro.")
  
 ![Control Popup con ubicación Left](./media/popup-placement-behavior/popup-placement-left.png "La colocación es izquierda.")
  
 ![Control Popup con ubicación Mouse](./media/popup-placement-behavior/popup-placement-mouse.png "La colocación es ratón.")  
  
 ![Control Popup con ubicación MousePoint](./media/popup-placement-behavior/popup-placement-mousepoint.png "La colocación es MousePoint.")  
  
 ![Control Popup con ubicación Relative o RelativePoint](./media/popup-placement-behavior/popup-placement-relative.png "La ubicación es Relative o RelativePoint.")
  
 ![Control Popup con ubicación Right](./media/popup-placement-behavior/popup-placement-right.png "La colocación es correcta.")
  
 ![Control Popup con ubicación Top](./media/popup-placement-behavior/popup-placement-top.png "La colocación es Superior.")
  
<a name="When"></a>
## <a name="when-the-popup-encounters-the-edge-of-the-screen"></a>Cuando el elemento emergente llega al borde de la pantalla  
 Por razones <xref:System.Windows.Controls.Primitives.Popup> de seguridad, un no se puede ocultar por el borde de una pantalla. Una de las tres cosas <xref:System.Windows.Controls.Primitives.Popup> siguientes sucede cuando el borde de la pantalla encuentra un borde de pantalla:  
  
- La ventana emergente se realinea a lo <xref:System.Windows.Controls.Primitives.Popup>largo del borde de la pantalla que oscurecería el archivo .  
  
- El elemento emergente usa un punto de alineación del elemento Popup distinto.  
  
- El elemento emergente usa un origen de destino y un punto de alineación del elemento Popup distintos.  
  
 Estas opciones se describen más adelante en esta sección.  
  
 El comportamiento <xref:System.Windows.Controls.Primitives.Popup> de cuando se encuentra con un borde <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> de pantalla depende del valor de la propiedad y qué borde de pantalla encuentra la ventana emergente. En la tabla siguiente se <xref:System.Windows.Controls.Primitives.Popup> resume el comportamiento <xref:System.Windows.Controls.Primitives.PlacementMode> cuando se encuentra con un borde de pantalla para cada valor.  
  
|PlacementMode|Borde superior|Borde inferior|Borde izquierdo|Borde derecho|  
|-------------------|--------------|-----------------|---------------|----------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Se alinea con el borde superior.|Se alinea con el borde inferior.|Se alinea con el borde izquierdo.|Se alinea con el borde derecho.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Se alinea con el borde superior.|El punto de alineación emergente cambia a <xref:System.Windows.Controls.Primitives.Popup>la esquina inferior izquierda del archivo .|Se alinea con el borde izquierdo.|El punto de alineación emergente cambia a <xref:System.Windows.Controls.Primitives.Popup>la esquina superior derecha del archivo .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|Se alinea con el borde superior.|El origen de destino cambia a la esquina superior izquierda del área de destino y <xref:System.Windows.Controls.Primitives.Popup>el punto de alineación emergente cambia a la esquina inferior izquierda del .|Se alinea con el borde izquierdo.|Se alinea con el borde derecho.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|Se alinea con el borde superior.|Se alinea con el borde inferior.|Se alinea con el borde izquierdo.|Se alinea con el borde derecho.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|Se alinea con el borde superior.|Se alinea con el borde inferior.|El origen de destino cambia a la esquina superior derecha del área de destino y <xref:System.Windows.Controls.Primitives.Popup>el punto de alineación emergente cambia a la esquina superior izquierda del .|Se alinea con el borde derecho.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Se alinea con el borde superior.|El origen de destino cambia a la esquina superior izquierda del área de destino (los límites del puntero del <xref:System.Windows.Controls.Primitives.Popup>mouse) y el punto de alineación emergente cambia a la esquina inferior izquierda del archivo .|Se alinea con el borde izquierdo.|Se alinea con el borde derecho.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Se alinea con el borde superior.|El punto de alineación emergente cambia a <xref:System.Windows.Controls.Primitives.Popup>la esquina inferior izquierda del archivo .|Se alinea con el borde izquierdo.|El punto de alineación del elemento Popup cambia a la esquina superior derecha del elemento emergente.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|Se alinea con el borde superior.|Se alinea con el borde inferior.|Se alinea con el borde izquierdo.|Se alinea con el borde derecho.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|Se alinea con el borde superior.|El punto de alineación emergente cambia a <xref:System.Windows.Controls.Primitives.Popup>la esquina inferior izquierda del archivo .|Se alinea con el borde izquierdo.|El punto de alineación del elemento Popup cambia a la esquina superior derecha del elemento emergente.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|Se alinea con el borde superior.|Se alinea con el borde inferior.|Se alinea con el borde izquierdo.|El origen de destino cambia a la esquina superior izquierda del área de destino y <xref:System.Windows.Controls.Primitives.Popup>el punto de alineación emergente cambia a la esquina superior derecha del archivo .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|El origen de destino cambia a la esquina inferior izquierda del área de destino y <xref:System.Windows.Controls.Primitives.Popup>el punto de alineación emergente cambia a la esquina superior izquierda del archivo . En efecto, esto es <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> lo <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>mismo que cuando es .|Se alinea con el borde inferior.|Se alinea con el borde izquierdo.|Se alinea con el borde derecho.|  
  
### <a name="aligning-to-the-screen-edge"></a>Alineación con el bode de la pantalla  
 A <xref:System.Windows.Controls.Primitives.Popup> puede alinearse con el borde de la <xref:System.Windows.Controls.Primitives.Popup> pantalla reposicionando para que todo sea visible en la pantalla.  Cuando esto ocurre, la distancia entre el origen de destino <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> y <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>el punto de alineación emergente puede diferir de los valores de y . Cuando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>es <xref:System.Windows.Controls.Primitives.PlacementMode.Center>, <xref:System.Windows.Controls.Primitives.PlacementMode.Relative>, <xref:System.Windows.Controls.Primitives.Popup> o , el se alinea con cada borde de la pantalla.  Por ejemplo, supongamos <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> que <xref:System.Windows.Controls.Primitives.PlacementMode.Relative> <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> a <xref:System.Windows.Controls.Primitives.Popup> se ha establecido en 100.  Si el borde inferior de la pantalla <xref:System.Windows.Controls.Primitives.Popup>oculta <xref:System.Windows.Controls.Primitives.Popup> todo o parte de la , las reposiciones a lo largo del borde inferior de la pantalla y la distancia vertical entre el origen de destino y el punto de alineación emergente es inferior a 100. Esto se muestra en la siguiente ilustración.  
  
 ![Control Popup que se alinea con el borde de la pantalla](./media/popup-placement-behavior/popup-placement-relative-screen-edge.png "Popup se alinea con el borde de la pantalla.")
  
### <a name="changing-the-popup-alignment-point"></a>Cambio del punto de alineación del elemento Popup  
 Si <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>es <xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>, <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>, o , el punto de alineación emergente cambia cuando la ventana emergente encuentra el borde inferior o derecho de la pantalla.  
  
 La siguiente ilustración muestra que cuando el borde inferior <xref:System.Windows.Controls.Primitives.Popup>de la pantalla oculta todo o parte <xref:System.Windows.Controls.Primitives.Popup>del , el punto de alineación emergente es la esquina inferior izquierda del archivo .  
  
 ![Nuevo punto de alineación debido al borde inferior de la pantalla](./media/popup-placement-behavior/popup-placement-relative-point-screen-edge.png "Popup encuentra el borde inferior de la pantalla y cambia el punto de alineación emergente.")  

 La siguiente ilustración muestra <xref:System.Windows.Controls.Primitives.Popup> que cuando el está oculto por el borde de la <xref:System.Windows.Controls.Primitives.Popup>pantalla derecha, el punto de alineación emergente es la esquina superior derecha del archivo .  
  
 ![Nuevo punto de alineación de elemento Popup debido al borde de la pantalla](./media/popup-placement-behavior/popup-placement-relative-point-right-screen-edge.png "Popup encuentra el borde derecho de la pantalla y cambia el punto de alineación emergente.")
  
 Si <xref:System.Windows.Controls.Primitives.Popup> los bordes inferior y derecho de la pantalla, el punto de <xref:System.Windows.Controls.Primitives.Popup>alineación emergente es la esquina inferior derecha del archivo .  
  
### <a name="changing-the-target-origin-and-popup-alignment-point"></a>Cambio del origen de destino y el punto de alineación del elemento Popup  
 Cuando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>es <xref:System.Windows.Controls.Primitives.PlacementMode.Left> <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, <xref:System.Windows.Controls.Primitives.PlacementMode.Right>, <xref:System.Windows.Controls.Primitives.PlacementMode.Top>, , o , el origen de destino y el punto de alineación emergente cambian si se encuentra un borde de pantalla determinado.  El borde de la pantalla que <xref:System.Windows.Controls.Primitives.PlacementMode> hace que la posición cambie depende del valor.  
  
 La siguiente ilustración <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> muestra <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> que <xref:System.Windows.Controls.Primitives.Popup> cuando está y encuentra el borde inferior de la pantalla, el origen de destino es la <xref:System.Windows.Controls.Primitives.Popup>esquina superior izquierda del área de destino y el punto de alineación emergente es la esquina inferior izquierda del archivo .  
  
 ![Nuevo punto de alineación debido al borde inferior de la pantalla](./media/popup-placement-behavior/popup-placement-bottom-screen-edge.png "La colocación es Inferior y la ventana emergente encuentra el borde inferior de la pantalla.")
  
 La siguiente ilustración <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> muestra <xref:System.Windows.Controls.Primitives.PlacementMode.Left> que <xref:System.Windows.Controls.Primitives.Popup> cuando está y encuentra el borde de la pantalla izquierda, el origen de destino es la <xref:System.Windows.Controls.Primitives.Popup>esquina superior derecha del área de destino y el punto de alineación emergente es la esquina superior izquierda del archivo .  
  
 ![Nuevo punto de alineación debido al borde izquierdo de la pantalla](./media/popup-placement-behavior/popup-placement-left-screen-edge.png "La colocación es Izquierda y la ventana emergente encuentra el borde izquierdo de la pantalla.")  
  
 La siguiente ilustración <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> muestra <xref:System.Windows.Controls.Primitives.PlacementMode.Right> que <xref:System.Windows.Controls.Primitives.Popup> cuando está y encuentra el borde de la pantalla derecha, el origen de destino es la <xref:System.Windows.Controls.Primitives.Popup>esquina superior izquierda del área de destino y el punto de alineación emergente es la esquina superior derecha del archivo .  
  
 ![Nuevo punto de alineación debido al borde derecho de la pantalla](./media/popup-placement-behavior/popup-placement-right-screen-edge.png "La colocación es derecha y la ventana emergente se encuentra con el borde derecho de la pantalla.")  

 La siguiente ilustración <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> muestra <xref:System.Windows.Controls.Primitives.PlacementMode.Top> que <xref:System.Windows.Controls.Primitives.Popup> cuando está y encuentra el borde superior de la pantalla, el origen de destino es la <xref:System.Windows.Controls.Primitives.Popup>esquina inferior izquierda del área de destino y el punto de alineación emergente es la esquina superior izquierda del archivo .  
  
 ![Nuevo punto de alineación debido al borde superior de la pantalla](./media/popup-placement-behavior/popup-placement-top-screen-edge.png "La colocación es Superior y la ventana emergente encuentra el borde superior de la pantalla.")  
  
 La siguiente ilustración <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> muestra <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse> que <xref:System.Windows.Controls.Primitives.Popup> cuando está y encuentra el borde inferior de la pantalla, el origen de destino es la esquina superior izquierda del área <xref:System.Windows.Controls.Primitives.Popup>de destino (los límites del puntero del mouse) y el punto de alineación emergente es la esquina inferior izquierda del archivo .  
  
 ![nuevo punto de alineación debido a la proximidad del mouse con el borde de la pantalla](./media/popup-placement-behavior/popup-placement-mouse-screen-edge.png "La colocación es ratón y la ventana emergente encuentra el borde inferior de la pantalla.")
  
### <a name="customizing-popup-placement"></a>Personalización de la ubicación del elemento Popup  
 Puede personalizar el origen de destino y <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> el <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>punto de alineación emergente estableciendo la propiedad en . A continuación, defina un <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegado que devuelva un conjunto de posibles <xref:System.Windows.Controls.Primitives.Popup>puntos de ubicación y ejes primarios (en orden de preferencia) para el archivo . Se selecciona el punto que <xref:System.Windows.Controls.Primitives.Popup> muestra la parte más grande de la.  La posición <xref:System.Windows.Controls.Primitives.Popup> del se ajusta <xref:System.Windows.Controls.Primitives.Popup> automáticamente si el está oculto por el borde de la pantalla. Para ver un ejemplo, consulte cómo [especificar una posición emergente personalizada](how-to-specify-a-custom-popup-position.md).  
  
## <a name="see-also"></a>Consulte también

- [Ejemplo de colocación del control Popup](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)
