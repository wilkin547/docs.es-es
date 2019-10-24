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
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "69951730"
---
# <a name="popup-placement-behavior"></a>Posición de un control Popup
Un control <xref:System.Windows.Controls.Primitives.Popup> muestra el contenido en una ventana independiente que flota sobre una aplicación. Puede especificar la posición de un <xref:System.Windows.Controls.Primitives.Popup> relativo a un control, el mouse o la pantalla mediante las propiedades <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>y <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>.  Estas propiedades funcionan de forma conjunta para ofrecer flexibilidad a la hora de especificar la posición del <xref:System.Windows.Controls.Primitives.Popup>.  
  
> [!NOTE]
> Las clases <xref:System.Windows.Controls.ToolTip> y <xref:System.Windows.Controls.ContextMenu> también definen estas cinco propiedades y se comportan de forma similar.  

<a name="Positioning"></a>   
## <a name="positioning-the-popup"></a>Posicionamiento del elemento Popup  
 La colocación de un <xref:System.Windows.Controls.Primitives.Popup> puede ser relativa a un <xref:System.Windows.UIElement> o a toda la pantalla.  En el ejemplo siguiente se crean cuatro controles <xref:System.Windows.Controls.Primitives.Popup> que son relativos a un <xref:System.Windows.UIElement>, en este caso, una imagen. Todos los controles <xref:System.Windows.Controls.Primitives.Popup> tienen la propiedad <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> establecida en `image1`, pero cada <xref:System.Windows.Controls.Primitives.Popup> tiene un valor diferente para la propiedad Placement.  
  
 [!code-xaml[PopupPositionSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#3)]  
  
 En la ilustración siguiente se muestra la imagen y los controles <xref:System.Windows.Controls.Primitives.Popup>  
  
 ![Imagen con cuatro controles Popup](./media/popup-placement-behavior/popup-placement-intro.png "Imagen con cuatro ventanas emergentes")    
  
 Este sencillo ejemplo muestra cómo establecer las propiedades <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> y <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, pero con las propiedades <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>y <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>, tiene incluso más control sobre dónde se coloca el <xref:System.Windows.Controls.Primitives.Popup>.  
  
<a name="Definitions"></a>   
## <a name="definitions-of-terms-the-anatomy-of-a-popup"></a>Definiciones de términos: la anatomía de un elemento Popup  
 Los siguientes términos son útiles para comprender cómo se relacionan las propiedades <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>y <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> entre sí y el <xref:System.Windows.Controls.Primitives.Popup>:  
  
- Objeto de destino  
  
- Área de destino  
  
- Origen de destino  
  
- Punto de alineación del elemento Popup  
  
 Estos términos proporcionan una manera cómoda de hacer referencia a diversos aspectos del <xref:System.Windows.Controls.Primitives.Popup> y al control con el que está asociado.  
  
### <a name="target-object"></a>Objeto de destino  
 El *objeto de destino* es el elemento al que está asociado el <xref:System.Windows.Controls.Primitives.Popup>. Si se establece la propiedad <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, especifica el objeto de destino.  Si no se establece <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> y el <xref:System.Windows.Controls.Primitives.Popup> tiene un elemento primario, el elemento primario es el objeto de destino.  Si no hay ningún valor <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> y no hay ningún elemento primario, no hay ningún objeto de destino y el <xref:System.Windows.Controls.Primitives.Popup> se coloca en relación con la pantalla.  
  
 En el ejemplo siguiente se crea un <xref:System.Windows.Controls.Primitives.Popup> que es el elemento secundario de un <xref:System.Windows.Controls.Canvas>.  En el ejemplo no se establece la propiedad <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> en el <xref:System.Windows.Controls.Primitives.Popup>. El valor predeterminado para <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> es <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom?displayProperty=nameWithType>, por lo que el <xref:System.Windows.Controls.Primitives.Popup> aparece debajo del <xref:System.Windows.Controls.Canvas>.  
  
 [!code-xaml[PopupPositionSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#1)]  
  
 En la ilustración siguiente se muestra que el <xref:System.Windows.Controls.Primitives.Popup> se coloca en relación con la <xref:System.Windows.Controls.Canvas>.  
  
 ![Control Popup sin PlacementTarget](./media/popup-placement-behavior/popup-placement-no-placement-target.png "Popup sin PlacementTarget.")  

 En el ejemplo siguiente se crea un <xref:System.Windows.Controls.Primitives.Popup> que es el elemento secundario de un <xref:System.Windows.Controls.Canvas>, pero esta vez el <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> se establece en `ellipse1`, por lo que el elemento emergente aparece debajo de la <xref:System.Windows.Shapes.Ellipse>.  
  
 [!code-xaml[PopupPositionSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#2)]  
  
 En la ilustración siguiente se muestra que el <xref:System.Windows.Controls.Primitives.Popup> se coloca en relación con la <xref:System.Windows.Shapes.Ellipse>.  
  
 ![Control Popup colocado en relación con una elipse](./media/popup-placement-behavior/popup-placement-with-placement-target.png "Control Popup con PlacementTarget")    
  
> [!NOTE]
> Por <xref:System.Windows.Controls.ToolTip>, el valor predeterminado de <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> es <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>.  Por <xref:System.Windows.Controls.ContextMenu>, el valor predeterminado de <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> es <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>. Estos valores se explican más adelante, en "Trabajo en conjunto de las propiedades".  
  
### <a name="target-area"></a>Área de destino  
 El *área de destino* es el área de la pantalla con la que el <xref:System.Windows.Controls.Primitives.Popup> es relativo. En los ejemplos anteriores, el <xref:System.Windows.Controls.Primitives.Popup> está alineado con los límites del objeto de destino, pero en algunos casos, el <xref:System.Windows.Controls.Primitives.Popup> se alinea con otros límites, incluso si el <xref:System.Windows.Controls.Primitives.Popup> tiene un objeto de destino.  Si se establece la propiedad <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, el área de destino es diferente de los límites del objeto de destino.  
  
 En el ejemplo siguiente se crean dos objetos <xref:System.Windows.Controls.Canvas>, cada uno de los cuales contiene un <xref:System.Windows.Shapes.Rectangle> y un <xref:System.Windows.Controls.Primitives.Popup>.  En ambos casos, el objeto de destino del <xref:System.Windows.Controls.Primitives.Popup> es el <xref:System.Windows.Controls.Canvas>. El <xref:System.Windows.Controls.Primitives.Popup> del primer <xref:System.Windows.Controls.Canvas> tiene el <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> establecido, con las propiedades <xref:System.Windows.Rect.X%2A>, <xref:System.Windows.Rect.Y%2A>, <xref:System.Windows.Rect.Width%2A>y <xref:System.Windows.Rect.Height%2A> establecidas en 50, 50, 50 y 100, respectivamente. El <xref:System.Windows.Controls.Primitives.Popup> del segundo <xref:System.Windows.Controls.Canvas> no tiene el <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> establecido.  Como resultado, el primer <xref:System.Windows.Controls.Primitives.Popup> se coloca debajo del <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> y el segundo <xref:System.Windows.Controls.Primitives.Popup> se coloca debajo del <xref:System.Windows.Controls.Canvas>. Cada <xref:System.Windows.Controls.Canvas> también contiene un <xref:System.Windows.Shapes.Rectangle> que tiene los mismos límites que el <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> para el primer <xref:System.Windows.Controls.Primitives.Popup>.  Tenga en cuenta que la <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> no crea un elemento visible en la aplicación; en el ejemplo se crea un <xref:System.Windows.Shapes.Rectangle> para representar el <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.  
  
 [!code-xaml[PopupPositionSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#4)]  
  
 En la ilustración siguiente se muestra el resultado del ejemplo anterior.  
  
 ![Control Popup con y sin PlacementRectangle](./media/popup-placement-behavior/popup-placement-placement-rectangle.png "Popup con y sin PlacementRectangle.")  

### <a name="target-origin-and-popup-alignment-point"></a>Origen de destino y punto de alineación del elemento Popup  
 El *origen de destino* y el *punto de alineación del elemento Popup* son puntos de referencia en el área de destino y el elemento emergente, respectivamente, que se usan para posicionamiento. Puede usar las propiedades <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> y <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> para desplazar el elemento emergente desde el área de destino.  Los <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> y <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> son relativos al origen de destino y el punto de alineación del elemento Popup. El valor de la propiedad <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> determina dónde se encuentran el origen de destino y el punto de alineación del elemento Popup.  
  
 En el ejemplo siguiente se crea una <xref:System.Windows.Controls.Primitives.Popup> y se establecen las propiedades <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> y <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> en 20.  La propiedad <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> está establecida en <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> (el valor predeterminado), por lo que el origen de destino es la esquina inferior izquierda del área de destino y el punto de alineación del elemento popup es la esquina superior izquierda de la <xref:System.Windows.Controls.Primitives.Popup>.  
  
 [!code-xaml[PopupPositionSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#5)]  
  
 En la ilustración siguiente se muestra el resultado del ejemplo anterior.  
  
 ![Posición de un control Popup con punto de alineación de origen de destino](./media/popup-placement-behavior/popup-placement-target-origin-alignment-point.png "Popup con HorizontalOffset y VerticalOffset.")    
  
<a name="How"></a>   
## <a name="how-the-properties-work-together"></a>Trabajo en conjunto de las propiedades  
 Los valores de <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> y <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> deben considerarse juntos para averiguar el área de destino, el origen de destino y el punto de alineación del elemento popup correctos.  Por ejemplo, si el valor de <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> es <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, no hay ningún objeto de destino, se omite el <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> y el área de destino son los límites del puntero del mouse. Por otro lado, si <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> es <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, el <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o el elemento primario determina el objeto de destino y <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> determina el área de destino.  
  
 En la tabla siguiente se describen el objeto de destino, el área de destino, el origen de destino y el punto de alineación del elemento popup y se indica si se utilizan <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> y <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> para cada valor de enumeración <xref:System.Windows.Controls.Primitives.PlacementMode>.  
  
|PlacementMode|Objeto de destino|Área de destino|Origen de destino|Punto de alineación del elemento Popup|  
|-------------------|-------------------|-----------------|-------------------|---------------------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|No disponible. se omite <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>.|La pantalla o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> si está establecida.  La <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> es relativa a la pantalla.|La esquina superior izquierda del área de destino.|Esquina superior izquierda de la <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|No disponible. se omite <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>.|La pantalla o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> si está establecida.  La <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> es relativa a la pantalla.|La esquina superior izquierda del área de destino.|Esquina superior izquierda de la <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o Parent.|Objeto de destino o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> si se establece.  El <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> es relativo al objeto de destino.|La esquina inferior izquierda del área de destino.|Esquina superior izquierda de la <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o Parent.|Objeto de destino o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> si se establece.  El <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> es relativo al objeto de destino.|El centro del área de destino.|Centro del <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o Parent.|Objeto de destino o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> si se establece.  El <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> es relativo al objeto de destino.|Definido por el <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|Definido por el <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o Parent.|Objeto de destino o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> si se establece.  El <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> es relativo al objeto de destino.|La esquina superior izquierda del área de destino.|Esquina superior derecha del <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|No disponible. se omite <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>.|Los límites del puntero del mouse. se omite <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.|La esquina inferior izquierda del área de destino.|Esquina superior izquierda de la <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|No disponible. se omite <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>.|Los límites del puntero del mouse. se omite <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.|La esquina superior izquierda del área de destino.|Esquina superior izquierda de la <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o Parent.|Objeto de destino o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> si se establece.  El <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> es relativo al objeto de destino.|La esquina superior izquierda del área de destino.|Esquina superior izquierda de la <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o Parent.|Objeto de destino o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> si se establece.  El <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> es relativo al objeto de destino.|La esquina superior izquierda del área de destino.|Esquina superior izquierda de la <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o Parent.|Objeto de destino o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> si se establece.  El <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> es relativo al objeto de destino.|La esquina superior derecha del área de destino.|Esquina superior izquierda de la <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o Parent.|Objeto de destino o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> si se establece.  El <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> es relativo al objeto de destino.|La esquina superior izquierda del área de destino.|Esquina inferior izquierda de la <xref:System.Windows.Controls.Primitives.Popup>.|  
  
 En las ilustraciones siguientes se muestra el <xref:System.Windows.Controls.Primitives.Popup>, el área de destino, el origen de destino y el punto de alineación del elemento popup para cada valor de <xref:System.Windows.Controls.Primitives.PlacementMode>. En cada ilustración, el área de destino es amarilla y el <xref:System.Windows.Controls.Primitives.Popup> es azul.  
  
 ![Control Popup con ubicación Absolute o AbsolutePoint](./media/popup-placement-behavior/popup-placement-absolute.png "Placement es Absolute o AbsolutePoint.")    
  
 ![Control Popup con ubicación Bottom](./media/popup-placement-behavior/popup-placement-bottom.png "La selección de ubicación es la parte inferior.")   
  
 ![Control Popup con ubicación Center](./media/popup-placement-behavior/popup-placement-center.png "La selección de ubicación es centro.")    
  
 ![Control Popup con ubicación Left](./media/popup-placement-behavior/popup-placement-left.png "La selección de ubicación es izquierda.")   
  
 ![Control Popup con ubicación Mouse](./media/popup-placement-behavior/popup-placement-mouse.png "La selección de ubicación es mouse.")  
  
 ![Control Popup con ubicación MousePoint](./media/popup-placement-behavior/popup-placement-mousepoint.png "La selección de ubicación es MousePoint.")  
  
 ![Control Popup con ubicación Relative o RelativePoint](./media/popup-placement-behavior/popup-placement-relative.png "La selección de ubicación es relativa o RelativePoint.")    
  
 ![Control Popup con ubicación Right](./media/popup-placement-behavior/popup-placement-right.png "La selección de ubicación es correcta.")    
  
 ![Control Popup con ubicación Top](./media/popup-placement-behavior/popup-placement-top.png "La selección de ubicación es Top.")    
  
<a name="When"></a>   
## <a name="when-the-popup-encounters-the-edge-of-the-screen"></a>Cuando el elemento emergente llega al borde de la pantalla  
 Por motivos de seguridad, un <xref:System.Windows.Controls.Primitives.Popup> no puede ocultarse en el borde de una pantalla. Una de las siguientes tres cosas sucede cuando el <xref:System.Windows.Controls.Primitives.Popup> encuentra un borde de pantalla:  
  
- El elemento emergente se ajusta a sí mismo a lo largo del margen de la pantalla que ocultaría el <xref:System.Windows.Controls.Primitives.Popup>.  
  
- El elemento emergente usa un punto de alineación del elemento Popup distinto.  
  
- El elemento emergente usa un origen de destino y un punto de alineación del elemento Popup distintos.  
  
 Estas opciones se describen más adelante en esta sección.  
  
 El comportamiento del <xref:System.Windows.Controls.Primitives.Popup> cuando encuentra un borde de pantalla depende del valor de la propiedad <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> y del borde de la pantalla que encuentra el elemento emergente. En la tabla siguiente se resume el comportamiento cuando el <xref:System.Windows.Controls.Primitives.Popup> encuentra un borde de pantalla para cada valor <xref:System.Windows.Controls.Primitives.PlacementMode>.  
  
|PlacementMode|Borde superior|Borde inferior|Borde izquierdo|Borde derecho|  
|-------------------|--------------|-----------------|---------------|----------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Se alinea con el borde superior.|Se alinea con el borde inferior.|Se alinea con el borde izquierdo.|Se alinea con el borde derecho.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Se alinea con el borde superior.|El punto de alineación del elemento popup cambia a la esquina inferior izquierda del <xref:System.Windows.Controls.Primitives.Popup>.|Se alinea con el borde izquierdo.|El punto de alineación del elemento popup cambia a la esquina superior derecha del <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|Se alinea con el borde superior.|El origen de destino cambia a la esquina superior izquierda del área de destino y el punto de alineación del elemento popup cambia a la esquina inferior izquierda del <xref:System.Windows.Controls.Primitives.Popup>.|Se alinea con el borde izquierdo.|Se alinea con el borde derecho.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|Se alinea con el borde superior.|Se alinea con el borde inferior.|Se alinea con el borde izquierdo.|Se alinea con el borde derecho.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|Se alinea con el borde superior.|Se alinea con el borde inferior.|El origen de destino cambia a la esquina superior derecha del área de destino y el punto de alineación del elemento popup cambia a la esquina superior izquierda del <xref:System.Windows.Controls.Primitives.Popup>.|Se alinea con el borde derecho.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Se alinea con el borde superior.|El origen de destino cambia a la esquina superior izquierda del área de destino (los límites del puntero del mouse) y el punto de alineación del elemento popup cambia a la esquina inferior izquierda del <xref:System.Windows.Controls.Primitives.Popup>.|Se alinea con el borde izquierdo.|Se alinea con el borde derecho.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Se alinea con el borde superior.|El punto de alineación del elemento popup cambia a la esquina inferior izquierda del <xref:System.Windows.Controls.Primitives.Popup>.|Se alinea con el borde izquierdo.|El punto de alineación del elemento Popup cambia a la esquina superior derecha del elemento emergente.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|Se alinea con el borde superior.|Se alinea con el borde inferior.|Se alinea con el borde izquierdo.|Se alinea con el borde derecho.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|Se alinea con el borde superior.|El punto de alineación del elemento popup cambia a la esquina inferior izquierda del <xref:System.Windows.Controls.Primitives.Popup>.|Se alinea con el borde izquierdo.|El punto de alineación del elemento Popup cambia a la esquina superior derecha del elemento emergente.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|Se alinea con el borde superior.|Se alinea con el borde inferior.|Se alinea con el borde izquierdo.|El origen de destino cambia a la esquina superior izquierda del área de destino y el punto de alineación del elemento popup cambia a la esquina superior derecha del <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|El origen de destino cambia a la esquina inferior izquierda del área de destino y el punto de alineación del elemento popup cambia a la esquina superior izquierda del <xref:System.Windows.Controls.Primitives.Popup>. En efecto, es el mismo que cuando se <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom><xref:System.Windows.Controls.Primitives.Popup.Placement%2A>.|Se alinea con el borde inferior.|Se alinea con el borde izquierdo.|Se alinea con el borde derecho.|  
  
### <a name="aligning-to-the-screen-edge"></a>Alineación con el bode de la pantalla  
 Un <xref:System.Windows.Controls.Primitives.Popup> se puede alinear al borde de la pantalla cambiando su posición para que todo el <xref:System.Windows.Controls.Primitives.Popup> esté visible en la pantalla.  Cuando esto ocurre, la distancia entre el origen de destino y el punto de alineación del elemento popup podría diferir de los valores de <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> y <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>. Cuando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> se <xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>, <xref:System.Windows.Controls.Primitives.PlacementMode.Center>o <xref:System.Windows.Controls.Primitives.PlacementMode.Relative>, el <xref:System.Windows.Controls.Primitives.Popup> se alinea a sí mismo con cada borde de la pantalla.  Por ejemplo, supongamos que un <xref:System.Windows.Controls.Primitives.Popup> tiene <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> establecido en <xref:System.Windows.Controls.Primitives.PlacementMode.Relative> y <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> establecido en 100.  Si el borde inferior de la pantalla oculta la totalidad o parte del <xref:System.Windows.Controls.Primitives.Popup>, el <xref:System.Windows.Controls.Primitives.Popup> cambia de posición a lo largo del borde inferior de la pantalla y la distancia vertical entre el origen de destino y el punto de alineación del elemento popup es menor que 100. Esto se muestra en la siguiente ilustración.  
  
 ![Control Popup que se alinea con el borde de la pantalla](./media/popup-placement-behavior/popup-placement-relative-screen-edge.png "Popup se alinea con el borde de la pantalla.")    
  
### <a name="changing-the-popup-alignment-point"></a>Cambio del punto de alineación del elemento Popup  
 Si <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> es <xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>, <xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>o <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>, el punto de alineación del elemento popup cambia cuando el elemento emergente encuentra el borde inferior o derecho de la pantalla.  
  
 En la ilustración siguiente se muestra que cuando el borde inferior de la pantalla oculta la totalidad o parte de la <xref:System.Windows.Controls.Primitives.Popup>, el punto de alineación del elemento popup es la esquina inferior izquierda del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuevo punto de alineación debido al borde inferior de la pantalla](./media/popup-placement-behavior/popup-placement-relative-point-screen-edge.png "El elemento emergente encuentra el borde inferior de la pantalla y cambia el punto de alineación del elemento Popup.")  

 En la ilustración siguiente se muestra que cuando la <xref:System.Windows.Controls.Primitives.Popup> está oculta en el borde derecho de la pantalla, el punto de alineación del elemento popup es la esquina superior derecha del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuevo punto de alineación de elemento Popup debido al borde de la pantalla](./media/popup-placement-behavior/popup-placement-relative-point-right-screen-edge.png "El elemento emergente encuentra el borde derecho de la pantalla y cambia el punto de alineación del elemento Popup.")    
  
 Si el <xref:System.Windows.Controls.Primitives.Popup> encuentra los bordes inferior y derecho de la pantalla, el punto de alineación del elemento popup es la esquina inferior derecha de la <xref:System.Windows.Controls.Primitives.Popup>.  
  
### <a name="changing-the-target-origin-and-popup-alignment-point"></a>Cambio del origen de destino y el punto de alineación del elemento Popup  
 Cuando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> se <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, <xref:System.Windows.Controls.Primitives.PlacementMode.Left>, <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, <xref:System.Windows.Controls.Primitives.PlacementMode.Right> o <xref:System.Windows.Controls.Primitives.PlacementMode.Top>, el origen de destino y el punto de alineación del elemento popup cambian si se encuentra un borde de pantalla determinado.  El borde de la pantalla que hace que cambie la posición depende del valor de <xref:System.Windows.Controls.Primitives.PlacementMode>.  
  
 En la ilustración siguiente se muestra que, cuando se <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> y el <xref:System.Windows.Controls.Primitives.Popup> encuentra el borde inferior de la pantalla, el origen de destino es la esquina superior izquierda del área de destino y el punto de alineación del elemento popup es la esquina inferior izquierda de la <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuevo punto de alineación debido al borde inferior de la pantalla](./media/popup-placement-behavior/popup-placement-bottom-screen-edge.png "La selección de ubicación es inferior y el elemento emergente encuentra el borde inferior de la pantalla.")    
  
 En la ilustración siguiente se muestra que cuando se <xref:System.Windows.Controls.Primitives.PlacementMode.Left> <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> y el <xref:System.Windows.Controls.Primitives.Popup> encuentra el borde izquierdo de la pantalla, el origen de destino es la esquina superior derecha del área de destino y el punto de alineación del elemento popup es la esquina superior izquierda del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuevo punto de alineación debido al borde izquierdo de la pantalla](./media/popup-placement-behavior/popup-placement-left-screen-edge.png "La selección de ubicación es izquierda y el elemento emergente encuentra el borde izquierdo de la pantalla.")  
  
 En la ilustración siguiente se muestra que, cuando se <xref:System.Windows.Controls.Primitives.PlacementMode.Right> <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> y el <xref:System.Windows.Controls.Primitives.Popup> encuentra el borde derecho de la pantalla, el origen de destino es la esquina superior izquierda del área de destino y el punto de alineación del elemento popup es la esquina superior derecha del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuevo punto de alineación debido al borde derecho de la pantalla](./media/popup-placement-behavior/popup-placement-right-screen-edge.png "La selección de ubicación es correcta y el elemento emergente encuentra el borde derecho de la pantalla.")  

 En la ilustración siguiente se muestra que cuando se <xref:System.Windows.Controls.Primitives.PlacementMode.Top> <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> y el <xref:System.Windows.Controls.Primitives.Popup> encuentra el borde superior de la pantalla, el origen de destino es la esquina inferior izquierda del área de destino y el punto de alineación del elemento popup es la esquina superior izquierda del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuevo punto de alineación debido al borde superior de la pantalla](./media/popup-placement-behavior/popup-placement-top-screen-edge.png "Placement es Top y el elemento emergente encuentra el borde superior de la pantalla.")  
  
 En la ilustración siguiente se muestra que, cuando se <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse> <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> y el <xref:System.Windows.Controls.Primitives.Popup> encuentra el borde inferior de la pantalla, el origen de destino es la esquina superior izquierda del área de destino (los límites del puntero del mouse) y el punto de alineación del elemento popup es la parte inferior izquierda esquina del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![nuevo punto de alineación debido a la proximidad del mouse con el borde de la pantalla](./media/popup-placement-behavior/popup-placement-mouse-screen-edge.png "La selección de ubicación es mouse y el elemento emergente encuentra el borde inferior de la pantalla.")    
  
### <a name="customizing-popup-placement"></a>Personalización de la ubicación del elemento Popup  
 Puede personalizar el origen de destino y el punto de alineación del elemento popup estableciendo la propiedad <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> en <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>. A continuación, defina un delegado de <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> que devuelva un conjunto de posibles puntos de colocación y ejes principales (en orden de preferencia) para el <xref:System.Windows.Controls.Primitives.Popup>. Se selecciona el punto que muestra la parte más grande del <xref:System.Windows.Controls.Primitives.Popup>.  La posición del <xref:System.Windows.Controls.Primitives.Popup> se ajusta automáticamente si el <xref:System.Windows.Controls.Primitives.Popup> está oculto en el borde de la pantalla. Para ver un ejemplo, consulte cómo [especificar una posición emergente personalizada](how-to-specify-a-custom-popup-position.md).  
  
## <a name="see-also"></a>Vea también

- [Ejemplo de colocación del control Popup](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)
