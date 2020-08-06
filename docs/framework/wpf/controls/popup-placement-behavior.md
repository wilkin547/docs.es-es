---
title: Posición de un control Popup
description: Consulte cómo usar propiedades para especificar la posición de un elemento Popup de Windows Presentation Foundation en relación con un control, el mouse o la pantalla.
ms.date: 03/30/2017
helpviewer_keywords:
- popups [WPF]
- Popup control [WPF], placing
- placing popups [WPF]
- positioning popups [WPF]
ms.assetid: fbf642e9-f670-4efd-a7af-a67468a1c8e1
ms.openlocfilehash: 8184805518bc56693ead4c7d1f0e9a1bff9bff8f
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167747"
---
# <a name="popup-placement-behavior"></a>Posición de un control Popup
Los controles <xref:System.Windows.Controls.Primitives.Popup> muestran el contenido en una ventana independiente que flota sobre una aplicación. Puede especificar la posición de un elemento <xref:System.Windows.Controls.Primitives.Popup> en relación con un control, el mouse o la pantalla mediante las propiedades <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> y <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>.  Estas propiedades trabajan en conjunto para ofrecer flexibilidad a fin de especificar la posición del elemento <xref:System.Windows.Controls.Primitives.Popup>.  
  
> [!NOTE]
> Las clases <xref:System.Windows.Controls.ToolTip> y <xref:System.Windows.Controls.ContextMenu> también definen estas cinco propiedades y tienen un comportamiento similar.  

<a name="Positioning"></a>
## <a name="positioning-the-popup"></a>Posicionamiento del elemento Popup  
 La ubicación de un elemento <xref:System.Windows.Controls.Primitives.Popup> puede ser en relación con un elemento <xref:System.Windows.UIElement> o con toda la pantalla.  En el ejemplo que hay a continuación se crean cuatro controles <xref:System.Windows.Controls.Primitives.Popup> que están colocados en relación con un elemento <xref:System.Windows.UIElement>; en este caso, una imagen. Todos los controles <xref:System.Windows.Controls.Primitives.Popup> tienen la propiedad <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> establecida en `image1`, pero cada <xref:System.Windows.Controls.Primitives.Popup> tiene un valor distinto para la propiedad de ubicación.  
  
 [!code-xaml[PopupPositionSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#3)]  
  
 En la ilustración siguiente se muestran la imagen y los controles de <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Imagen con cuatro controles Popup](./media/popup-placement-behavior/popup-placement-intro.png "Imagen con cuatro elementos Popup")
  
 En este sencillo ejemplo se muestra cómo configurar las propiedades <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> y <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>. Sin embargo, usando también las propiedades <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> y <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>, dispondrá de todavía más control sobre la posición de <xref:System.Windows.Controls.Primitives.Popup>.  
  
<a name="Definitions"></a>
## <a name="definitions-of-terms-the-anatomy-of-a-popup"></a>Definiciones de términos: Anatomía de un elemento Popup  
 Los términos que se indican a continuación resultan útiles para entender de qué forma las propiedades <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> y <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> están relacionadas entre ellas y con <xref:System.Windows.Controls.Primitives.Popup>:  
  
- Objeto de destino  
  
- Área de destino  
  
- Origen de destino  
  
- Punto de alineación del elemento Popup  
  
 Estos términos proporcionan una manera cómoda de hacer referencia a varios aspectos del elemento <xref:System.Windows.Controls.Primitives.Popup> y el control con el que está asociado.  
  
### <a name="target-object"></a>Objeto de destino  
 El *objeto de destino* es el elemento con el que <xref:System.Windows.Controls.Primitives.Popup> está asociado. Si se establece la propiedad <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, esta especifica el objeto de destino.  Si no se establece <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, y <xref:System.Windows.Controls.Primitives.Popup> tiene un elemento primario, dicho elemento es el objeto de destino.  Si no existe ningún valor <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> ni ningún elemento primario, no hay objeto de destino, y el elemento <xref:System.Windows.Controls.Primitives.Popup> se coloca en relación con la pantalla.  
  
 En el ejemplo siguiente se crea un elemento <xref:System.Windows.Controls.Primitives.Popup> que es el elemento secundario de <xref:System.Windows.Controls.Canvas>.  El ejemplo no establece la propiedad <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> en <xref:System.Windows.Controls.Primitives.Popup>. El valor predeterminado de <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> es <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom?displayProperty=nameWithType>, así que <xref:System.Windows.Controls.Primitives.Popup> aparece debajo de <xref:System.Windows.Controls.Canvas>.  
  
 [!code-xaml[PopupPositionSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#1)]  
  
 En la ilustración siguiente se muestra que el elemento <xref:System.Windows.Controls.Primitives.Popup> está colocado en relación con <xref:System.Windows.Controls.Canvas>.  
  
 ![Control Popup sin PlacementTarget](./media/popup-placement-behavior/popup-placement-no-placement-target.png "Elemento Popup sin PlacementTarget.")  

 En el ejemplo siguiente se crea un elemento <xref:System.Windows.Controls.Primitives.Popup> que es el elemento secundario de <xref:System.Windows.Controls.Canvas>, pero, esta vez, <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> se establece en `ellipse1`, así que el elemento Popup aparece debajo de <xref:System.Windows.Shapes.Ellipse>.  
  
 [!code-xaml[PopupPositionSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#2)]  
  
 En la ilustración siguiente se muestra que el elemento <xref:System.Windows.Controls.Primitives.Popup> está colocado en relación con <xref:System.Windows.Shapes.Ellipse>.  
  
 ![Control Popup colocado en relación con una elipse](./media/popup-placement-behavior/popup-placement-with-placement-target.png "Control Popup con PlacementTarget")
  
> [!NOTE]
> Para <xref:System.Windows.Controls.ToolTip>, el valor predeterminado de <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> es <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>.  Para <xref:System.Windows.Controls.ContextMenu>, el valor predeterminado de <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> es <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>. Estos valores se explican más adelante, en "Trabajo en conjunto de las propiedades".  
  
### <a name="target-area"></a>Área de destino  
 El *área de destino* es la zona de la pantalla colocada en relación con <xref:System.Windows.Controls.Primitives.Popup>. En los ejemplos anteriores, el elemento <xref:System.Windows.Controls.Primitives.Popup> está alineado con los límites del objeto de destino, pero, en algunos casos, el elemento <xref:System.Windows.Controls.Primitives.Popup> está alineado con otros límites, aunque el elemento <xref:System.Windows.Controls.Primitives.Popup> tenga un objeto de destino.  Si se establece la propiedad <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, el área de destino será distinta a los límites del objeto de destino.  
  
 En el ejemplo siguiente se crean dos objetos <xref:System.Windows.Controls.Canvas>; cada uno contiene los elementos <xref:System.Windows.Shapes.Rectangle> y <xref:System.Windows.Controls.Primitives.Popup>.  En ambos casos, el objeto de destino de <xref:System.Windows.Controls.Primitives.Popup> es <xref:System.Windows.Controls.Canvas>. El elemento <xref:System.Windows.Controls.Primitives.Popup> del primer valor <xref:System.Windows.Controls.Canvas> tiene establecido <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, con las propiedades <xref:System.Windows.Rect.X%2A>, <xref:System.Windows.Rect.Y%2A>, <xref:System.Windows.Rect.Width%2A> y <xref:System.Windows.Rect.Height%2A> establecidas en 50, 50, 50 y 100, respectivamente. El elemento <xref:System.Windows.Controls.Primitives.Popup> del segundo valor <xref:System.Windows.Controls.Canvas> no tiene establecido <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.  Por lo tanto, el primer elemento <xref:System.Windows.Controls.Primitives.Popup> está ubicado debajo de <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> y el segundo <xref:System.Windows.Controls.Primitives.Popup>, debajo de <xref:System.Windows.Controls.Canvas>. Cada elemento <xref:System.Windows.Controls.Canvas> contiene también un valor <xref:System.Windows.Shapes.Rectangle> que tiene los mismos límites que <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> para el primer elemento <xref:System.Windows.Controls.Primitives.Popup>.  Debe tener en cuenta que <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> no crea ningún elemento visible en la aplicación; en el ejemplo se crea un valor <xref:System.Windows.Shapes.Rectangle> para representar <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.  
  
 [!code-xaml[PopupPositionSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#4)]  
  
 En la ilustración siguiente se muestra el resultado del ejemplo anterior.  
  
 ![Control Popup con y sin PlacementRectangle](./media/popup-placement-behavior/popup-placement-placement-rectangle.png "Elemento Popup con y sin PlacementRectangle.")  

### <a name="target-origin-and-popup-alignment-point"></a>Origen de destino y punto de alineación del elemento Popup  
 El *origen de destino* y el *punto de alineación del elemento Popup* son puntos de referencia en el área de destino y el elemento emergente, respectivamente, que se usan para posicionamiento. Puede usar las propiedades <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> y <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> para desplazar el elemento Popup del área de destino.  <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> y <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> están colocados en relación con el origen del destino y con el punto de alineación del elemento Popup. El valor de la propiedad <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> determina dónde se colocan el origen del destino y el punto de alineación del elemento Popup.  
  
 En el ejemplo siguiente se crea un elemento <xref:System.Windows.Controls.Primitives.Popup> y se establecen en 20 las propiedades <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> y <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>.  La propiedad <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> está establecida en <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> (valor predeterminado); por lo tanto, el origen del destino se sitúa en la esquina inferior izquierda del área de destino, y el punto de alineación del elemento Popup, en la esquina superior izquierda de <xref:System.Windows.Controls.Primitives.Popup>.  
  
 [!code-xaml[PopupPositionSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#5)]  
  
 En la ilustración siguiente se muestra el resultado del ejemplo anterior.  
  
 ![Posición de un control Popup con punto de alineación de origen de destino](./media/popup-placement-behavior/popup-placement-target-origin-alignment-point.png "Elemento Popup con HorizontalOffset y VerticalOffset.")
  
<a name="How"></a>
## <a name="how-the-properties-work-together"></a>Trabajo en conjunto de las propiedades  
 Los valores de <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> y <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> deben tenerse en cuenta en conjunto para poder averiguar el área de destino, el origen del destino y el punto de alineación del elemento Popup correctos.  Por ejemplo, si el valor de <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> es <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, no existe ningún objeto de destino, el elemento <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se ignora, y el área de destino representa los límites del puntero del mouse. Por otro lado, si <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> es <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, el elemento <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o el elemento primario determinan el objeto de destino, y <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> determina el área de destino.  
  
 En la tabla siguiente se describen el objeto de destino, el área de destino, el origen del destino y el punto de alineación del elemento Popup; también se indica si <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> y <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se usan para cada valor de enumeración <xref:System.Windows.Controls.Primitives.PlacementMode>.  
  
|PlacementMode|Objeto de destino|Área de destino|Origen de destino|Punto de alineación del elemento Popup|  
|-------------------|-------------------|-----------------|-------------------|---------------------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|No es aplicable. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> se pasa por alto.|Pantalla, o bien, si se establece, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.  El elemento <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> está colocado en relación con la pantalla.|La esquina superior izquierda del área de destino.|Esquina superior izquierda del elemento <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|No es aplicable. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> se pasa por alto.|Pantalla, o bien, si se establece, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.  El elemento <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> está colocado en relación con la pantalla.|La esquina superior izquierda del área de destino.|Esquina superior izquierda del elemento <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o elemento primario.|Objeto de destino, o bien, si se establece, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.  El elemento <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> está colocado en relación con el objeto de destino.|La esquina inferior izquierda del área de destino.|Esquina superior izquierda del elemento <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o elemento primario.|Objeto de destino, o bien, si se establece, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.  El elemento <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> está colocado en relación con el objeto de destino.|El centro del área de destino.|Centro de <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o elemento primario.|Objeto de destino, o bien, si se establece, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.  El elemento <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> está colocado en relación con el objeto de destino.|Definido por <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|Definido por <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o elemento primario.|Objeto de destino, o bien, si se establece, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.  El elemento <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> está colocado en relación con el objeto de destino.|La esquina superior izquierda del área de destino.|Esquina superior derecha del elemento <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|No es aplicable. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> se pasa por alto.|Los límites del puntero del mouse. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se pasa por alto.|La esquina inferior izquierda del área de destino.|Esquina superior izquierda del elemento <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|No es aplicable. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> se pasa por alto.|Los límites del puntero del mouse. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se pasa por alto.|La esquina superior izquierda del área de destino.|Esquina superior izquierda del elemento <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o elemento primario.|Objeto de destino, o bien, si se establece, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.  El elemento <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> está colocado en relación con el objeto de destino.|La esquina superior izquierda del área de destino.|Esquina superior izquierda del elemento <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o elemento primario.|Objeto de destino, o bien, si se establece, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.  El elemento <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> está colocado en relación con el objeto de destino.|La esquina superior izquierda del área de destino.|Esquina superior izquierda del elemento <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o elemento primario.|Objeto de destino, o bien, si se establece, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.  El elemento <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> está colocado en relación con el objeto de destino.|La esquina superior derecha del área de destino.|Esquina superior izquierda del elemento <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o elemento primario.|Objeto de destino, o bien, si se establece, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.  El elemento <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> está colocado en relación con el objeto de destino.|La esquina superior izquierda del área de destino.|Esquina inferior izquierda de <xref:System.Windows.Controls.Primitives.Popup>.|  
  
 En las ilustraciones siguientes se muestra el elemento <xref:System.Windows.Controls.Primitives.Popup>, el área de destino, el origen del destino y el punto de alineación del elemento Popup de cada valor <xref:System.Windows.Controls.Primitives.PlacementMode>. En cada imagen, el área de destino es amarilla, y <xref:System.Windows.Controls.Primitives.Popup> es azul.  
  
 ![Control Popup con ubicación Absolute o AbsolutePoint](./media/popup-placement-behavior/popup-placement-absolute.png "La ubicación es Absolute o AbsolutePoint.")
  
 ![Control Popup con ubicación Bottom](./media/popup-placement-behavior/popup-placement-bottom.png "La ubicación es Bottom.")
  
 ![Control Popup con ubicación Center](./media/popup-placement-behavior/popup-placement-center.png "La ubicación es Center.")
  
 ![Control Popup con ubicación Left](./media/popup-placement-behavior/popup-placement-left.png "La ubicación es Left.")
  
 ![Control Popup con ubicación Mouse](./media/popup-placement-behavior/popup-placement-mouse.png "La ubicación es Mouse.")  
  
 ![Control Popup con ubicación MousePoint](./media/popup-placement-behavior/popup-placement-mousepoint.png "La ubicación es MousePoint.")  
  
 ![Control Popup con ubicación Relative o RelativePoint](./media/popup-placement-behavior/popup-placement-relative.png "La ubicación es Relative o RelativePoint.")
  
 ![Control Popup con ubicación Right](./media/popup-placement-behavior/popup-placement-right.png "La ubicación es Right.")
  
 ![Control Popup con ubicación Top](./media/popup-placement-behavior/popup-placement-top.png "La ubicación es Top.")
  
<a name="When"></a>
## <a name="when-the-popup-encounters-the-edge-of-the-screen"></a>Cuando el elemento emergente llega al borde de la pantalla  
 Por seguridad, el borde de una pantalla no puede ocultar los elementos <xref:System.Windows.Controls.Primitives.Popup>. Se produce una de estas tres situaciones cuando <xref:System.Windows.Controls.Primitives.Popup> encuentra el borde de una pantalla:  
  
- El elemento emergente se realinea con el borde de la pantalla, lo que podría oscurecer el elemento <xref:System.Windows.Controls.Primitives.Popup>.  
  
- El elemento emergente usa un punto de alineación del elemento Popup distinto.  
  
- El elemento emergente usa un origen de destino y un punto de alineación del elemento Popup distintos.  
  
 Estas opciones se describen más adelante en esta sección.  
  
 El comportamiento de <xref:System.Windows.Controls.Primitives.Popup> al encontrar el borde de una pantalla depende del valor de la propiedad <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> y del borde que el elemento Popup encuentre. En la tabla siguiente se resume el comportamiento de <xref:System.Windows.Controls.Primitives.Popup> al encontrar un borde de pantalla para cada valor <xref:System.Windows.Controls.Primitives.PlacementMode>.  
  
|PlacementMode|Borde superior|Borde inferior|Borde izquierdo|Borde derecho|  
|-------------------|--------------|-----------------|---------------|----------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Se alinea con el borde superior.|Se alinea con el borde inferior.|Se alinea con el borde izquierdo.|Se alinea con el borde derecho.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Se alinea con el borde superior.|El punto de alineación del elemento Popup cambia a la esquina inferior izquierda de <xref:System.Windows.Controls.Primitives.Popup>.|Se alinea con el borde izquierdo.|El punto de alineación del elemento Popup cambia a la esquina superior derecha del elemento <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|Se alinea con el borde superior.|El origen del destino cambia a la esquina superior izquierda del área de destino y el punto de alineación del elemento Popup, a la esquina inferior izquierda de <xref:System.Windows.Controls.Primitives.Popup>.|Se alinea con el borde izquierdo.|Se alinea con el borde derecho.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|Se alinea con el borde superior.|Se alinea con el borde inferior.|Se alinea con el borde izquierdo.|Se alinea con el borde derecho.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|Se alinea con el borde superior.|Se alinea con el borde inferior.|El origen del destino cambia a la esquina superior derecha del área de destino y el punto de alineación del elemento Popup, a la esquina superior izquierda de <xref:System.Windows.Controls.Primitives.Popup>.|Se alinea con el borde derecho.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Se alinea con el borde superior.|El origen del destino cambia a la esquina superior izquierda del área de destino (límites del puntero del mouse) y el punto de alineación del elemento Popup, a la esquina inferior izquierda de <xref:System.Windows.Controls.Primitives.Popup>.|Se alinea con el borde izquierdo.|Se alinea con el borde derecho.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Se alinea con el borde superior.|El punto de alineación del elemento Popup cambia a la esquina inferior izquierda de <xref:System.Windows.Controls.Primitives.Popup>.|Se alinea con el borde izquierdo.|El punto de alineación del elemento Popup cambia a la esquina superior derecha del elemento emergente.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|Se alinea con el borde superior.|Se alinea con el borde inferior.|Se alinea con el borde izquierdo.|Se alinea con el borde derecho.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|Se alinea con el borde superior.|El punto de alineación del elemento Popup cambia a la esquina inferior izquierda de <xref:System.Windows.Controls.Primitives.Popup>.|Se alinea con el borde izquierdo.|El punto de alineación del elemento Popup cambia a la esquina superior derecha del elemento emergente.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|Se alinea con el borde superior.|Se alinea con el borde inferior.|Se alinea con el borde izquierdo.|El origen del destino cambia a la esquina superior izquierda del área de destino y el punto de alineación del elemento Popup, a la esquina superior derecha de <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|El origen del destino cambia a la esquina inferior izquierda del área de destino y el punto de alineación del elemento Popup cambia a la esquina superior izquierda de <xref:System.Windows.Controls.Primitives.Popup>. En efecto, es igual que cuando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> es <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>.|Se alinea con el borde inferior.|Se alinea con el borde izquierdo.|Se alinea con el borde derecho.|  
  
### <a name="aligning-to-the-screen-edge"></a>Alineación con el bode de la pantalla  
 Un elemento <xref:System.Windows.Controls.Primitives.Popup> se puede alinear con el borde de la pantalla recolocándose para que el elemento <xref:System.Windows.Controls.Primitives.Popup> entero esté visible en la pantalla.  Cuando esto ocurre, la distancia entre el origen del destino y el punto de alineación del elemento Popup podría ser distinta a los valores de <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> y <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>. Cuando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> es <xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>, <xref:System.Windows.Controls.Primitives.PlacementMode.Center> o <xref:System.Windows.Controls.Primitives.PlacementMode.Relative>, el elemento <xref:System.Windows.Controls.Primitives.Popup> se alinea con cada uno de los bordes de la pantalla.  Por ejemplo, supongamos que <xref:System.Windows.Controls.Primitives.Popup> tiene <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> establecido en <xref:System.Windows.Controls.Primitives.PlacementMode.Relative> y <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>, en 100.  Si el borde inferior de la pantalla oculta la totalidad o parte de <xref:System.Windows.Controls.Primitives.Popup>, <xref:System.Windows.Controls.Primitives.Popup> se recoloca junto al borde inferior de la pantalla y la distancia vertical entre el origen del destino y el punto de alineación del elemento Popup es menor que 100. Esto se muestra en la siguiente ilustración.  
  
 ![Control Popup que se alinea con el borde de la pantalla](./media/popup-placement-behavior/popup-placement-relative-screen-edge.png "El control Popup se alinea con el borde de la pantalla.")
  
### <a name="changing-the-popup-alignment-point"></a>Cambio del punto de alineación del elemento Popup  
 Si <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> es <xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>, <xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint> o <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>, el punto de alineación del elemento Popup cambia cuando dicho elemento encuentra el borde inferior o derecho de la pantalla.  
  
 En la ilustración siguiente se muestra que cuando el borde inferior de la pantalla oculta la totalidad o parte de <xref:System.Windows.Controls.Primitives.Popup>, el punto de alineación del elemento Popup se sitúa en la esquina inferior izquierda de <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuevo punto de alineación debido al borde inferior de la pantalla](./media/popup-placement-behavior/popup-placement-relative-point-screen-edge.png "El elemento emergente encuentra el borde inferior de la pantalla y cambia el punto de alineación del elemento Popup.")  

 En la ilustración siguiente se muestra que cuando el borde derecho de la pantalla oculta <xref:System.Windows.Controls.Primitives.Popup>, el punto de alineación del elemento Popup se sitúa en la esquina superior derecha de <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuevo punto de alineación de elemento Popup debido al borde de la pantalla](./media/popup-placement-behavior/popup-placement-relative-point-right-screen-edge.png "El elemento emergente encuentra el borde derecho de la pantalla y cambia el punto de alineación del elemento Popup.")
  
 Si <xref:System.Windows.Controls.Primitives.Popup> encuentra los bordes inferior y derecho de la pantalla, el punto de alineación del elemento Popup se sitúa en la esquina inferior derecha de <xref:System.Windows.Controls.Primitives.Popup>.  
  
### <a name="changing-the-target-origin-and-popup-alignment-point"></a>Cambio del origen de destino y el punto de alineación del elemento Popup  
 Cuando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> es <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, <xref:System.Windows.Controls.Primitives.PlacementMode.Left>, <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, <xref:System.Windows.Controls.Primitives.PlacementMode.Right> o <xref:System.Windows.Controls.Primitives.PlacementMode.Top>, el origen del destino y el punto de alineación del elemento Popup cambian si se encuentra un borde de pantalla determinado.  El borde de la pantalla que hace que la posición cambie depende del valor <xref:System.Windows.Controls.Primitives.PlacementMode>.  
  
 En la ilustración siguiente se muestra que cuando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> es <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> y <xref:System.Windows.Controls.Primitives.Popup> encuentra el borde inferior de la pantalla, el origen del destino se sitúa en la esquina superior izquierda del área de destino y el punto de alineación del elemento Popup, en la esquina inferior izquierda de <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuevo punto de alineación debido al borde inferior de la pantalla](./media/popup-placement-behavior/popup-placement-bottom-screen-edge.png "La ubicación es Bottom y el elemento emergente encuentra el borde inferior de la pantalla.")
  
 En la ilustración siguiente se muestra que cuando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> es <xref:System.Windows.Controls.Primitives.PlacementMode.Left> y <xref:System.Windows.Controls.Primitives.Popup> encuentra el borde izquierdo de la pantalla, el origen del destino se sitúa en la esquina superior derecha del área de destino y el punto de alineación del elemento Popup, en la esquina superior izquierda de <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuevo punto de alineación debido al borde izquierdo de la pantalla](./media/popup-placement-behavior/popup-placement-left-screen-edge.png "La ubicación es Left y el elemento emergente encuentra el borde izquierdo de la pantalla.")  
  
 En la ilustración siguiente se muestra que cuando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> es <xref:System.Windows.Controls.Primitives.PlacementMode.Right> y <xref:System.Windows.Controls.Primitives.Popup> encuentra el borde izquierdo de la pantalla, el origen del destino se sitúa en la esquina superior derecha del área de destino y el punto de alineación del elemento Popup, en la esquina superior derecha de <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuevo punto de alineación debido al borde derecho de la pantalla](./media/popup-placement-behavior/popup-placement-right-screen-edge.png "La ubicación es Right y el elemento emergente encuentra el borde derecho de la pantalla.")  

 En la ilustración siguiente se muestra que cuando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> es <xref:System.Windows.Controls.Primitives.PlacementMode.Top> y <xref:System.Windows.Controls.Primitives.Popup> encuentra el borde superior de la pantalla, el origen del destino se sitúa en la esquina inferior izquierda del área de destino y el punto de alineación del elemento Popup, en la esquina superior izquierda de <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuevo punto de alineación debido al borde superior de la pantalla](./media/popup-placement-behavior/popup-placement-top-screen-edge.png "La ubicación es Top y el elemento emergente encuentra el borde superior de la pantalla.")  
  
 En la ilustración siguiente se muestra que cuando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> es <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse> y <xref:System.Windows.Controls.Primitives.Popup> encuentra el borde inferior de la pantalla, el origen del destino se sitúa en la esquina superior izquierda del área de destino (límites del puntero del mouse) y el punto de alineación del elemento Popup, en la esquina inferior izquierda de <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![nuevo punto de alineación debido a la proximidad del mouse con el borde de la pantalla](./media/popup-placement-behavior/popup-placement-mouse-screen-edge.png "La ubicación es Mouse y el elemento emergente encuentra el borde inferior de la pantalla.")
  
### <a name="customizing-popup-placement"></a>Personalización de la ubicación del elemento Popup  
 Puede personalizar el origen del destino y el punto de alineación del elemento Popup estableciendo la propiedad <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> en <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>. Después, defina un delegado de <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> que devuelva un conjunto de posibles puntos de colocación y ejes principales (en orden de preferencia) para <xref:System.Windows.Controls.Primitives.Popup>. Se selecciona el punto que muestra la parte más grande del elemento <xref:System.Windows.Controls.Primitives.Popup>.  La posición de <xref:System.Windows.Controls.Primitives.Popup> se ajusta automáticamente si el borde de la pantalla oculta <xref:System.Windows.Controls.Primitives.Popup>. Para ver un ejemplo, consulte cómo [especificar una posición emergente personalizada](how-to-specify-a-custom-popup-position.md).  
  
## <a name="see-also"></a>Consulte también

- [Ejemplo de colocación del control Popup](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)
