---
title: Posición de un control Popup
ms.date: 03/30/2017
helpviewer_keywords:
- popups [WPF]
- Popup control [WPF], placing
- placing popups [WPF]
- positioning popups [WPF]
ms.assetid: fbf642e9-f670-4efd-a7af-a67468a1c8e1
ms.openlocfilehash: ca984aa724cf3f076d6073aa8b8179abfb91d26c
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "69951730"
---
# <a name="popup-placement-behavior"></a>Posición de un control Popup
Un <xref:System.Windows.Controls.Primitives.Popup> control muestra el contenido en una ventana independiente que flota sobre una aplicación. Puede especificar la posición <xref:System.Windows.Controls.Primitives.Popup> de un relativo a un control, el mouse o la pantalla mediante las <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>propiedades <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>,, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>y <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> .  Estas propiedades funcionan de forma conjunta para ofrecer flexibilidad a la hora de especificar la <xref:System.Windows.Controls.Primitives.Popup>posición de.  
  
> [!NOTE]
> Las <xref:System.Windows.Controls.ToolTip> clases <xref:System.Windows.Controls.ContextMenu> y también definen estas cinco propiedades y se comportan de forma similar.  

<a name="Positioning"></a>   
## <a name="positioning-the-popup"></a>Posicionamiento del elemento Popup  
 La posición de <xref:System.Windows.Controls.Primitives.Popup> puede ser relativa <xref:System.Windows.UIElement> a o a toda la pantalla.  En el ejemplo siguiente se <xref:System.Windows.Controls.Primitives.Popup> crean cuatro controles que son relativos <xref:System.Windows.UIElement>a un, en este caso, una imagen. Todos los <xref:System.Windows.Controls.Primitives.Popup> controles tienen la <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> propiedad establecida en `image1`, pero cada uno <xref:System.Windows.Controls.Primitives.Popup> tiene un valor diferente para la propiedad Placement.  
  
 [!code-xaml[PopupPositionSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#3)]  
  
 En la ilustración siguiente se muestra la imagen <xref:System.Windows.Controls.Primitives.Popup> y los controles  
  
 ![Imagen con cuatro controles popup](./media/popup-placement-behavior/popup-placement-intro.png "Imagen con cuatro ventanas emergentes")    
  
 Este sencillo ejemplo muestra <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> cómo establecer las propiedades y <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> , pero mediante el uso de las <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>propiedades, <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> <xref:System.Windows.Controls.Primitives.Popup> y, tiene aún más control sobre dónde se coloca.  
  
<a name="Definitions"></a>   
## <a name="definitions-of-terms-the-anatomy-of-a-popup"></a>Definiciones de términos: Anatomía de un elemento emergente  
 Los siguientes términos son útiles para comprender cómo se <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>relacionan <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>las <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>propiedades, <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>,, y entre sí y <xref:System.Windows.Controls.Primitives.Popup>:  
  
- Objeto de destino  
  
- Área de destino  
  
- Origen de destino  
  
- Punto de alineación del elemento Popup  
  
 Estos términos proporcionan una manera cómoda de hacer referencia a diversos aspectos de <xref:System.Windows.Controls.Primitives.Popup> y al control con el que está asociado.  
  
### <a name="target-object"></a>Objeto de destino  
 El *objeto de destino* es el elemento al <xref:System.Windows.Controls.Primitives.Popup> que está asociado el. Si se <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> establece la propiedad, se especifica el objeto de destino.  Si <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> no se establece <xref:System.Windows.Controls.Primitives.Popup> y tiene un elemento primario, el elemento primario es el objeto de destino.  Si no hay <xref:System.Windows.Controls.Primitives.Popup> ningún valorynohayningúnelementoprimario,nohayningúnobjetodedestinoysecolocaenrelaciónconlapantalla.<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>  
  
 En el ejemplo siguiente se <xref:System.Windows.Controls.Primitives.Popup> crea un que es el elemento <xref:System.Windows.Controls.Canvas>secundario de.  En el ejemplo no se establece <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> la propiedad en. <xref:System.Windows.Controls.Primitives.Popup> El valor predeterminado de <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> es <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom?displayProperty=nameWithType>, por lo <xref:System.Windows.Controls.Primitives.Popup> que aparece debajo <xref:System.Windows.Controls.Canvas>de.  
  
 [!code-xaml[PopupPositionSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#1)]  
  
 En la ilustración siguiente <xref:System.Windows.Controls.Primitives.Popup> se muestra que se coloca en relación con. <xref:System.Windows.Controls.Canvas>  
  
 ![Control popup sin PlacementTarget](./media/popup-placement-behavior/popup-placement-no-placement-target.png "Popup sin PlacementTarget.")  

 En el ejemplo siguiente se <xref:System.Windows.Controls.Primitives.Popup> crea un que es el elemento <xref:System.Windows.Controls.Canvas>secundario de <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> , pero esta vez se establece `ellipse1` <xref:System.Windows.Shapes.Ellipse>en, por lo que el elemento emergente aparece debajo de.  
  
 [!code-xaml[PopupPositionSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#2)]  
  
 En la ilustración siguiente <xref:System.Windows.Controls.Primitives.Popup> se muestra que se coloca en relación con. <xref:System.Windows.Shapes.Ellipse>  
  
 ![Elemento popup colocado en relación con una elipse](./media/popup-placement-behavior/popup-placement-with-placement-target.png "Elemento emergente con PlacementTarget")    
  
> [!NOTE]
> En <xref:System.Windows.Controls.ToolTip>, el valor predeterminado de <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> es <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>.  En <xref:System.Windows.Controls.ContextMenu>, el valor predeterminado de <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> es <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>. Estos valores se explican más adelante, en "Trabajo en conjunto de las propiedades".  
  
### <a name="target-area"></a>Área de destino  
 El *área de destino* es el área de la pantalla con <xref:System.Windows.Controls.Primitives.Popup> la que es relativo. En los ejemplos anteriores, <xref:System.Windows.Controls.Primitives.Popup> está alineado con los límites del objeto de destino, pero en algunos casos <xref:System.Windows.Controls.Primitives.Popup> , se alinea con otros límites, incluso si <xref:System.Windows.Controls.Primitives.Popup> tiene un objeto de destino.  Si se <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> establece la propiedad, el área de destino es diferente de los límites del objeto de destino.  
  
 En el ejemplo siguiente se <xref:System.Windows.Controls.Canvas> crean dos objetos, cada uno <xref:System.Windows.Shapes.Rectangle> de los <xref:System.Windows.Controls.Primitives.Popup>cuales contiene y.  En ambos casos, el objeto de destino de <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Canvas>es. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> <xref:System.Windows.Rect.X%2A> <xref:System.Windows.Rect.Width%2A> <xref:System.Windows.Rect.Height%2A> En el primero <xref:System.Windows.Controls.Canvas> tiene el conjunto, con sus propiedades, <xref:System.Windows.Rect.Y%2A>, y establecidas en 50, 50, 50 y 100, respectivamente. <xref:System.Windows.Controls.Primitives.Popup> En el segundo <xref:System.Windows.Controls.Canvas> no tiene el <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> conjunto. <xref:System.Windows.Controls.Primitives.Popup>  Como resultado, el <xref:System.Windows.Controls.Primitives.Popup> primero se coloca debajo de <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> y el segundo <xref:System.Windows.Controls.Primitives.Popup> se coloca debajo de <xref:System.Windows.Controls.Canvas>. Cada <xref:System.Windows.Controls.Canvas> también contiene un <xref:System.Windows.Shapes.Rectangle> que tiene los <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> mismos límites que para el primero <xref:System.Windows.Controls.Primitives.Popup>.  Tenga en cuenta <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> que no crea un elemento visible en la aplicación; en el ejemplo se <xref:System.Windows.Shapes.Rectangle> crea un para <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>representar el.  
  
 [!code-xaml[PopupPositionSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#4)]  
  
 En la ilustración siguiente se muestra el resultado del ejemplo anterior.  
  
 ![Popup con y sin PlacementRectangle](./media/popup-placement-behavior/popup-placement-placement-rectangle.png "Popup con y sin PlacementRectangle.")  

### <a name="target-origin-and-popup-alignment-point"></a>Origen de destino y punto de alineación del elemento Popup  
 El *origen de destino* y el *punto de alineación del elemento Popup* son puntos de referencia en el área de destino y el elemento emergente, respectivamente, que se usan para posicionamiento. Puede usar las <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> propiedades y <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> para desplazar el elemento emergente del área de destino.  <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> Y<xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> son relativos al origen de destino y el punto de alineación del elemento Popup. El valor de la <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> propiedad determina dónde se encuentran el origen de destino y el punto de alineación del elemento Popup.  
  
 En el ejemplo siguiente se <xref:System.Windows.Controls.Primitives.Popup> crea un y <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> se <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> establecen las propiedades y en 20.  La <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> propiedad se establece en <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> (el valor predeterminado), por lo que el origen de destino es la esquina inferior izquierda del área de destino y el punto de alineación del elemento popup es la <xref:System.Windows.Controls.Primitives.Popup>esquina superior izquierda de.  
  
 [!code-xaml[PopupPositionSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#5)]  
  
 En la ilustración siguiente se muestra el resultado del ejemplo anterior.  
  
 ![Ubicación del elemento emergente con el punto de alineación de origen de destino](./media/popup-placement-behavior/popup-placement-target-origin-alignment-point.png "Popup con HorizontalOffset y VerticalOffset.")    
  
<a name="How"></a>   
## <a name="how-the-properties-work-together"></a>Trabajo en conjunto de las propiedades  
 Los valores de <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>y <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> deben considerarse juntos para averiguar el área de destino, el origen de destino y el punto de alineación del elemento popup correctos.  Por ejemplo, si el valor de <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> es <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, no hay <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ningún objeto de destino, se omite y el área de destino es los límites del puntero del mouse. Por otro lado, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> si es <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, el <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> elemento primario o determina el objeto de destino <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> y determina el área de destino.  
  
 En la tabla siguiente se describen el objeto de destino, el área de destino, el origen de destino y <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> el <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> punto de alineación del <xref:System.Windows.Controls.Primitives.PlacementMode> elemento popup, y se indica si se usan y para cada valor de enumeración.  
  
|PlacementMode|Objeto de destino|Área de destino|Origen de destino|Punto de alineación del elemento Popup|  
|-------------------|-------------------|-----------------|-------------------|---------------------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|No es aplicable. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>se omite.|La pantalla, o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> si está establecida.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> Es relativo a la pantalla.|La esquina superior izquierda del área de destino.|Esquina superior izquierda de <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|No es aplicable. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>se omite.|La pantalla, o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> si está establecida.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> Es relativo a la pantalla.|La esquina superior izquierda del área de destino.|Esquina superior izquierda de <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o primario.|Objeto de destino, o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> si está establecido.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> Es relativo al objeto de destino.|La esquina inferior izquierda del área de destino.|Esquina superior izquierda de <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o primario.|Objeto de destino, o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> si está establecido.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> Es relativo al objeto de destino.|El centro del área de destino.|Centro del <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o primario.|Objeto de destino, o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> si está establecido.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> Es relativo al objeto de destino.|Definido por el <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|Definido por el <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o primario.|Objeto de destino, o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> si está establecido.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> Es relativo al objeto de destino.|La esquina superior izquierda del área de destino.|Esquina superior derecha de <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|No es aplicable. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>se omite.|Los límites del puntero del mouse. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>se omite.|La esquina inferior izquierda del área de destino.|Esquina superior izquierda de <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|No es aplicable. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>se omite.|Los límites del puntero del mouse. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>se omite.|La esquina superior izquierda del área de destino.|Esquina superior izquierda de <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o primario.|Objeto de destino, o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> si está establecido.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> Es relativo al objeto de destino.|La esquina superior izquierda del área de destino.|Esquina superior izquierda de <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o primario.|Objeto de destino, o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> si está establecido.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> Es relativo al objeto de destino.|La esquina superior izquierda del área de destino.|Esquina superior izquierda de <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o primario.|Objeto de destino, o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> si está establecido.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> Es relativo al objeto de destino.|La esquina superior derecha del área de destino.|Esquina superior izquierda de <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o primario.|Objeto de destino, o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> si está establecido.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> Es relativo al objeto de destino.|La esquina superior izquierda del área de destino.|Esquina inferior izquierda de <xref:System.Windows.Controls.Primitives.Popup>.|  
  
 En las ilustraciones siguientes se <xref:System.Windows.Controls.Primitives.Popup>muestra el, el área de destino, el origen de destino y <xref:System.Windows.Controls.Primitives.PlacementMode> el punto de alineación del elemento popup para cada valor. En cada ilustración, el área de destino es amarilla y el <xref:System.Windows.Controls.Primitives.Popup> es azul.  
  
 Control ![popup con ubicación absoluta o AbsolutePoint](./media/popup-placement-behavior/popup-placement-absolute.png "Placement es Absolute o AbsolutePoint.")    
  
 ![Cuadro emergente con colocación inferior] La (./media/popup-placement-behavior/popup-placement-bottom.png "selección de ubicación es la parte inferior.")   
  
 ![Elemento emergente con colocación central] La (./media/popup-placement-behavior/popup-placement-center.png "selección de ubicación es centro.")    
  
 Control ![popup con ubicación izquierda] La (./media/popup-placement-behavior/popup-placement-left.png "selección de ubicación es izquierda.")   
  
 Control ![popup con ubicación del mouse] La (./media/popup-placement-behavior/popup-placement-mouse.png "selección de ubicación es mouse.")  
  
 Control ![popup con ubicación MousePoint] La (./media/popup-placement-behavior/popup-placement-mousepoint.png "selección de ubicación es MousePoint.")  
  
 ![Popup con ubicación relativa o RelativePoint] La (./media/popup-placement-behavior/popup-placement-relative.png "selección de ubicación es relativa o RelativePoint.")    
  
 Control ![popup con ubicación adecuada] La (./media/popup-placement-behavior/popup-placement-right.png "selección de ubicación es correcta.")    
  
 ![Elemento emergente con colocación superior] La (./media/popup-placement-behavior/popup-placement-top.png "selección de ubicación es Top.")    
  
<a name="When"></a>   
## <a name="when-the-popup-encounters-the-edge-of-the-screen"></a>Cuando el elemento emergente llega al borde de la pantalla  
 Por motivos de seguridad, <xref:System.Windows.Controls.Primitives.Popup> un no puede estar oculto en el borde de una pantalla. Cuando <xref:System.Windows.Controls.Primitives.Popup> encuentra un borde de pantalla, se produce una de las siguientes tres cosas:  
  
- El elemento emergente se ajusta a sí mismo a lo largo del borde de la <xref:System.Windows.Controls.Primitives.Popup>pantalla que ocultaría.  
  
- El elemento emergente usa un punto de alineación del elemento Popup distinto.  
  
- El elemento emergente usa un origen de destino y un punto de alineación del elemento Popup distintos.  
  
 Estas opciones se describen más adelante en esta sección.  
  
 El comportamiento de <xref:System.Windows.Controls.Primitives.Popup> cuando encuentra un borde de pantalla depende del valor de la <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> propiedad y del límite de la pantalla que encuentra el elemento emergente. En la tabla siguiente se resume el comportamiento <xref:System.Windows.Controls.Primitives.Popup> cuando el encuentra un borde de pantalla para <xref:System.Windows.Controls.Primitives.PlacementMode> cada valor.  
  
|PlacementMode|Borde superior|Borde inferior|Borde izquierdo|Borde derecho|  
|-------------------|--------------|-----------------|---------------|----------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Se alinea con el borde superior.|Se alinea con el borde inferior.|Se alinea con el borde izquierdo.|Se alinea con el borde derecho.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Se alinea con el borde superior.|El punto de alineación del elemento popup cambia a la esquina inferior izquierda <xref:System.Windows.Controls.Primitives.Popup>de.|Se alinea con el borde izquierdo.|El punto de alineación del elemento popup cambia a la esquina superior derecha <xref:System.Windows.Controls.Primitives.Popup>de.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|Se alinea con el borde superior.|El origen de destino cambia a la esquina superior izquierda del área de destino y el punto de alineación del elemento popup cambia a la esquina inferior izquierda <xref:System.Windows.Controls.Primitives.Popup>de.|Se alinea con el borde izquierdo.|Se alinea con el borde derecho.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|Se alinea con el borde superior.|Se alinea con el borde inferior.|Se alinea con el borde izquierdo.|Se alinea con el borde derecho.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|Se alinea con el borde superior.|Se alinea con el borde inferior.|El origen de destino cambia a la esquina superior derecha del área de destino y el punto de alineación del elemento popup cambia a la esquina superior izquierda <xref:System.Windows.Controls.Primitives.Popup>de.|Se alinea con el borde derecho.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Se alinea con el borde superior.|El origen de destino cambia a la esquina superior izquierda del área de destino (los límites del puntero del mouse) y el punto de alineación del elemento popup cambia a la esquina inferior izquierda de <xref:System.Windows.Controls.Primitives.Popup>.|Se alinea con el borde izquierdo.|Se alinea con el borde derecho.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Se alinea con el borde superior.|El punto de alineación del elemento popup cambia a la esquina inferior izquierda <xref:System.Windows.Controls.Primitives.Popup>de.|Se alinea con el borde izquierdo.|El punto de alineación del elemento Popup cambia a la esquina superior derecha del elemento emergente.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|Se alinea con el borde superior.|Se alinea con el borde inferior.|Se alinea con el borde izquierdo.|Se alinea con el borde derecho.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|Se alinea con el borde superior.|El punto de alineación del elemento popup cambia a la esquina inferior izquierda <xref:System.Windows.Controls.Primitives.Popup>de.|Se alinea con el borde izquierdo.|El punto de alineación del elemento Popup cambia a la esquina superior derecha del elemento emergente.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|Se alinea con el borde superior.|Se alinea con el borde inferior.|Se alinea con el borde izquierdo.|El origen de destino cambia a la esquina superior izquierda del área de destino y el punto de alineación del elemento popup cambia a la esquina superior derecha <xref:System.Windows.Controls.Primitives.Popup>de.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|El origen de destino cambia a la esquina inferior izquierda del área de destino y el punto de alineación del elemento popup cambia a la esquina superior izquierda <xref:System.Windows.Controls.Primitives.Popup>de. En efecto, es igual que cuando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> es. <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|Se alinea con el borde inferior.|Se alinea con el borde izquierdo.|Se alinea con el borde derecho.|  
  
### <a name="aligning-to-the-screen-edge"></a>Alineación con el bode de la pantalla  
 Un <xref:System.Windows.Controls.Primitives.Popup> puede alinearse con el borde de la pantalla cambiando de posición para que todo <xref:System.Windows.Controls.Primitives.Popup> esté visible en la pantalla.  Cuando esto ocurre, la distancia entre el origen de destino y el punto de alineación del elemento popup podría <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> diferir de los valores de y. <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> Cuando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> es <xref:System.Windows.Controls.Primitives.PlacementMode.Absolute> ,<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>o, se alineaasímismoconcadabordedelapantalla.<xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Primitives.PlacementMode.Center>  Por ejemplo, supongamos <xref:System.Windows.Controls.Primitives.Popup> que <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> tiene establecido <xref:System.Windows.Controls.Primitives.PlacementMode.Relative> en <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> y establecido en 100.  Si el borde inferior de la pantalla oculta la totalidad o parte de <xref:System.Windows.Controls.Primitives.Popup>, el cambia de <xref:System.Windows.Controls.Primitives.Popup> posición a lo largo del borde inferior de la pantalla y la distancia vertical entre el origen de destino y el punto de alineación del elemento popup es menor que 100. Esto se muestra en la siguiente ilustración.  
  
 ![Elemento emergente que se alinea con el borde de la pantalla](./media/popup-placement-behavior/popup-placement-relative-screen-edge.png "Popup se alinea con el borde de la pantalla.")    
  
### <a name="changing-the-popup-alignment-point"></a>Cambio del punto de alineación del elemento Popup  
 Si <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> es <xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>, o<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>, el punto de alineación del elemento popup cambia cuando el elemento emergente encuentra el borde inferior o derecho de la pantalla. <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>  
  
 En la ilustración siguiente se muestra que cuando el borde inferior de la pantalla oculta la totalidad <xref:System.Windows.Controls.Primitives.Popup>o parte de, el punto de alineación del elemento popup es la <xref:System.Windows.Controls.Primitives.Popup>esquina inferior izquierda de.  
  
 ![Nuevo punto de alineación debido al borde inferior de la pantalla] El (./media/popup-placement-behavior/popup-placement-relative-point-screen-edge.png "elemento emergente encuentra el borde inferior de la pantalla y cambia el punto de alineación del elemento Popup.")  

 En la ilustración siguiente se muestra que <xref:System.Windows.Controls.Primitives.Popup> cuando está oculto en el borde de la pantalla derecha, el punto de alineación del elemento popup es la <xref:System.Windows.Controls.Primitives.Popup>esquina superior derecha de.  
  
 ![Nuevo punto de alineación del elemento emergente debido al borde de la pantalla] El (./media/popup-placement-behavior/popup-placement-relative-point-right-screen-edge.png "elemento emergente encuentra el borde derecho de la pantalla y cambia el punto de alineación del elemento Popup.")    
  
 Si encuentra los bordes inferior y derecho <xref:System.Windows.Controls.Primitives.Popup>de la pantalla, el punto de alineación del elemento popup es la esquina inferior derecha de. <xref:System.Windows.Controls.Primitives.Popup>  
  
### <a name="changing-the-target-origin-and-popup-alignment-point"></a>Cambio del origen de destino y el punto de alineación del elemento Popup  
 Cuando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> es <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, ,<xref:System.Windows.Controls.Primitives.PlacementMode.Left> ,o<xref:System.Windows.Controls.Primitives.PlacementMode.Top>, el origen de destino y el punto de alineación del elemento popup cambian si se encuentra un borde de pantalla determinado. <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse> <xref:System.Windows.Controls.Primitives.PlacementMode.Right>  Borde de la pantalla que hace que la posición cambie depende del <xref:System.Windows.Controls.Primitives.PlacementMode> valor.  
  
 En la ilustración siguiente se muestra <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> que <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> cuando es <xref:System.Windows.Controls.Primitives.Popup> y encuentra el borde inferior de la pantalla, el origen de destino es la esquina superior izquierda del área de destino y el punto de alineación del elemento popup es la esquina inferior izquierda de la <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuevo punto de alineación debido al borde inferior de la pantalla](./media/popup-placement-behavior/popup-placement-bottom-screen-edge.png "La selección de ubicación es inferior y el elemento emergente encuentra el borde inferior de la pantalla.")    
  
 La siguiente ilustración muestra que cuando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> es <xref:System.Windows.Controls.Primitives.PlacementMode.Left> y <xref:System.Windows.Controls.Primitives.Popup> encuentra el borde izquierdo de la pantalla, el origen de destino es la esquina superior derecha del área de destino y el punto de alineación del elemento popup es la esquina superior izquierda del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuevo punto de alineación debido al borde izquierdo de la pantalla](./media/popup-placement-behavior/popup-placement-left-screen-edge.png "La selección de ubicación es izquierda y el elemento emergente encuentra el borde izquierdo de la pantalla.")  
  
 En la ilustración siguiente se muestra <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> que <xref:System.Windows.Controls.Primitives.PlacementMode.Right> cuando es <xref:System.Windows.Controls.Primitives.Popup> y encuentra el borde derecho de la pantalla, el origen de destino es la esquina superior izquierda del área de destino y el punto de alineación del elemento popup es la esquina superior derecha del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuevo punto de alineación debido al borde derecho de la pantalla](./media/popup-placement-behavior/popup-placement-right-screen-edge.png "La selección de ubicación es correcta y el elemento emergente encuentra el borde derecho de la pantalla.")  

 En la ilustración siguiente se muestra <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> que <xref:System.Windows.Controls.Primitives.PlacementMode.Top> , cuando <xref:System.Windows.Controls.Primitives.Popup> es y encuentra el borde superior de la pantalla, el origen de destino es la esquina inferior izquierda del área de destino y el punto de alineación del elemento popup es la esquina superior izquierda del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuevo punto de alineación debido al borde superior de la pantalla](./media/popup-placement-behavior/popup-placement-top-screen-edge.png "Placement es Top y el elemento emergente encuentra el borde superior de la pantalla.")  
  
 En la ilustración siguiente se muestra <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> que <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse> , cuando <xref:System.Windows.Controls.Primitives.Popup> es y encuentra el borde inferior de la pantalla, el origen de destino es la esquina superior izquierda del área de destino (los límites del puntero del mouse) y la alineación del elemento Popup. el punto es la esquina inferior izquierda del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![nuevo punto de alineación debido al mouse cerca del borde de la pantalla] La (./media/popup-placement-behavior/popup-placement-mouse-screen-edge.png "selección de ubicación es mouse y el elemento emergente encuentra el borde inferior de la pantalla.")    
  
### <a name="customizing-popup-placement"></a>Personalización de la ubicación del elemento Popup  
 Puede personalizar el origen de destino y el punto de alineación del elemento <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> popup estableciendo <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>la propiedad en. A continuación, <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> defina un delegado que devuelva un conjunto de posibles puntos de ubicación y ejes principales (en orden de <xref:System.Windows.Controls.Primitives.Popup>preferencia) para. El punto que muestra la parte más grande del <xref:System.Windows.Controls.Primitives.Popup> está seleccionado.  La posición de <xref:System.Windows.Controls.Primitives.Popup> se ajusta automáticamente <xref:System.Windows.Controls.Primitives.Popup> si el está oculto en el borde de la pantalla. Para ver un ejemplo, consulte cómo [especificar una posición emergente personalizada](how-to-specify-a-custom-popup-position.md).  
  
## <a name="see-also"></a>Vea también

- [Ejemplo de colocación del control Popup](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)
