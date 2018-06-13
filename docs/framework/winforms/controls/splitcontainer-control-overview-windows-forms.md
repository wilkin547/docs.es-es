---
title: Información general sobre SplitContainer (Control, formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- SplitContainer
helpviewer_keywords:
- SplitContainer control [Windows Forms], about SplitContainer control
ms.assetid: 6de5a5f7-97a5-402d-be6d-7e2785483db5
ms.openlocfilehash: 9eea7d397824e443c46acff73fe6db0e43bcfe42
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33539483"
---
# <a name="splitcontainer-control-overview-windows-forms"></a>Información general sobre SplitContainer (Control, formularios Windows Forms)
El control <xref:System.Windows.Forms.SplitContainer> de Windows Forms puede considerarse como una composición de dos paneles separados por una barra móvil. Cuando el puntero del mouse está sobre la barra, el puntero cambia de forma para mostrar que se puede mover.  
  
> [!IMPORTANT]
>  En el **cuadro de herramientas**, <xref:System.Windows.Forms.SplitContainer> control reemplaza el <xref:System.Windows.Forms.Splitter> control que había en la versión anterior de Visual Studio. El control <xref:System.Windows.Forms.SplitContainer> es mucho más preferible que el control <xref:System.Windows.Forms.Splitter>. El <xref:System.Windows.Forms.Splitter> clase todavía se incluye en el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] por compatibilidad con las aplicaciones existentes, pero recomendamos encarecidamente utilizar el <xref:System.Windows.Forms.SplitContainer> control para los nuevos proyectos.  
  
 Con el <xref:System.Windows.Forms.SplitContainer> control, puede crear interfaces de usuario complejas; a menudo, una selección en un panel determina qué objetos se muestran en el otro panel. Esta organización es muy eficaz para mostrar y explorar información. Tener dos paneles permite agregar información en las áreas y la barra o "divisor" facilita a los usuarios cambiar el tamaño de los paneles.  
  
 Más de un <xref:System.Windows.Forms.SplitContainer> control también se puede anidar, con la segunda <xref:System.Windows.Forms.SplitContainer> control orientado horizontalmente, para crear paneles superior e inferior.  
  
 Tenga en cuenta que la <xref:System.Windows.Forms.SplitContainer> control es accesible desde el teclado de forma predeterminada; los usuarios pueden presionar las teclas de dirección para mover el divisor si la <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> propiedad está establecida en `false`.  
  
 El <xref:System.Windows.Forms.SplitContainer.Orientation%2A> propiedad de la <xref:System.Windows.Forms.SplitContainer> control determina la dirección del divisor, no del propio control. Por lo tanto, cuando esta propiedad se establece en <xref:System.Windows.Forms.Orientation.Vertical>, el divisor va de arriba a abajo y crear paneles izquierdo y derecho.  
  
 Además, tenga en cuenta que el valor de la <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> propiedad varía dependiendo del valor de la <xref:System.Windows.Forms.SplitContainer.Orientation%2A> propiedad. Para obtener más información, vea <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> propiedad.  
  
 También puede restringir el tamaño y el movimiento de la <xref:System.Windows.Forms.SplitContainer> control. El <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> propiedad determina cuál de los paneles seguirá siendo el mismo tamaño después de la <xref:System.Windows.Forms.SplitContainer> control cambia de tamaño y el <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> propiedad determina si el divisor está movible mediante el teclado o mouse (ratón).  
  
> [!NOTE]
>  Incluso si la <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> propiedad está establecida en `true`, el divisor puede seguir mover mediante programación; por ejemplo, mediante el <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> propiedad.  
  
 Por último, cada panel de la <xref:System.Windows.Forms.SplitContainer> control tiene propiedades para determinar su tamaño individual.  
  
## <a name="commonly-used-properties-methods-and-events"></a>Propiedades, métodos y eventos de uso común  
  
|nombre|Descripción|  
|----------|-----------------|  
|Propiedad <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A>|Determina cuál de los paneles seguirá siendo el mismo tamaño después de la <xref:System.Windows.Forms.SplitContainer> control cambia de tamaño.|  
|Propiedad <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>|Determina si el divisor se puede mover con el teclado o mouse (ratón).|  
|Propiedad <xref:System.Windows.Forms.SplitContainer.Orientation%2A>|Determina si el divisor se colocará vertical u horizontalmente.|  
|Propiedad <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>|Determina la distancia en píxeles desde el borde izquierdo o superior de la barra de división puede mover.|  
|Propiedad <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>|Determina la distancia mínima, en píxeles, que se puede mover el divisor por el usuario.|  
|Propiedad <xref:System.Windows.Forms.SplitContainer.SplitterWidth%2A>|Determina el grosor, en píxeles, del divisor.|  
|Evento <xref:System.Windows.Forms.SplitContainer.SplitterMoving>|Se produce cuando el divisor se está moviendo.|  
|Evento <xref:System.Windows.Forms.SplitContainer.SplitterMoved>|Se produce cuando se ha movido el divisor.|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.SplitContainer>  
 [SplitContainer (control)](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)  
 [Ejemplo SplitContainer (Control)](http://msdn.microsoft.com/library/9015fad0-7108-4d85-a83a-a72d038c4f65)
