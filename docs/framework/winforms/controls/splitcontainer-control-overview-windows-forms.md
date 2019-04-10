---
title: Información general sobre SplitContainer (Control, formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- SplitContainer
helpviewer_keywords:
- SplitContainer control [Windows Forms], about SplitContainer control
ms.assetid: 6de5a5f7-97a5-402d-be6d-7e2785483db5
ms.openlocfilehash: 4afdd764b2f6ef7f15e8bd26459f0fa4c7d345e1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59219426"
---
# <a name="splitcontainer-control-overview-windows-forms"></a>Información general sobre SplitContainer (Control, formularios Windows Forms)
El control <xref:System.Windows.Forms.SplitContainer> de Windows Forms puede considerarse como una composición de dos paneles separados por una barra móvil. Cuando el puntero del mouse está sobre la barra, el puntero cambia de forma para mostrar que se puede mover.  
  
> [!IMPORTANT]
>  En el **cuadro de herramientas**, <xref:System.Windows.Forms.SplitContainer> control reemplaza el <xref:System.Windows.Forms.Splitter> control que había en la versión anterior de Visual Studio. El control <xref:System.Windows.Forms.SplitContainer> es mucho más preferible que el control <xref:System.Windows.Forms.Splitter>. El <xref:System.Windows.Forms.Splitter> clase aún se incluye en el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para ofrecer compatibilidad con aplicaciones existentes, pero se recomienda encarecidamente utilizar el <xref:System.Windows.Forms.SplitContainer> control para nuevos proyectos.  
  
 Con el <xref:System.Windows.Forms.SplitContainer> control, puede crear interfaces de usuario complejas; a menudo, una selección en un panel determina qué objetos se muestran en el otro panel. Esta organización es muy eficaz para mostrar y explorar información. Tener dos paneles permite agregar información en las áreas y la barra o "divisor" facilita la tarea para que los usuarios cambiar el tamaño de los paneles.  
  
 Más de un <xref:System.Windows.Forms.SplitContainer> control también se pueden anidar, con la segunda <xref:System.Windows.Forms.SplitContainer> control orientado horizontalmente, para crear paneles de la parte superior e inferior.  
  
 Tenga en cuenta que el <xref:System.Windows.Forms.SplitContainer> control es accesible desde el teclado de manera predeterminada, los usuarios pueden presionar las teclas de dirección para mover el divisor si la <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> propiedad está establecida en `false`.  
  
 El <xref:System.Windows.Forms.SplitContainer.Orientation%2A> propiedad de la <xref:System.Windows.Forms.SplitContainer> control determina la dirección del divisor, no del propio control. Por lo tanto, cuando esta propiedad se establece en <xref:System.Windows.Forms.Orientation.Vertical>, el divisor se ejecuta de arriba hacia abajo, creación de paneles izquierdos y derecho.  
  
 Además, tenga en cuenta que el valor de la <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> propiedad varía dependiendo del valor de la <xref:System.Windows.Forms.SplitContainer.Orientation%2A> propiedad. Para obtener más información, consulte <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> propiedad.  
  
 También puede restringir el tamaño y el movimiento de la <xref:System.Windows.Forms.SplitContainer> control. El <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> propiedad determina qué panel seguirá siendo el mismo tamaño después de la <xref:System.Windows.Forms.SplitContainer> control cambia de tamaño y el <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> propiedad determina si el divisor es móvil mediante el teclado o mouse.  
  
> [!NOTE]
>  Incluso si la <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> propiedad está establecida en `true`, el divisor todavía se puede mover mediante programación; por ejemplo, mediante el uso de la <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> propiedad.  
  
 Por último, cada panel de la <xref:System.Windows.Forms.SplitContainer> control tiene propiedades para determinar su tamaño individual.  
  
## <a name="commonly-used-properties-methods-and-events"></a>Propiedades, métodos y eventos de uso común  
  
|Name|Descripción|  
|----------|-----------------|  
|<xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> propiedad|Determina qué panel seguirá siendo el mismo tamaño después de la <xref:System.Windows.Forms.SplitContainer> control cambia de tamaño.|  
|<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> propiedad|Determina si el divisor se puede mover con el teclado o mouse (ratón).|  
|<xref:System.Windows.Forms.SplitContainer.Orientation%2A> propiedad|Determina si el divisor se organiza verticalmente u horizontalmente.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> propiedad|Determina la distancia en píxeles desde el borde izquierdo o superior a la barra de división movible.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> propiedad|Determina la distancia mínima en píxeles, que el usuario puede mover el divisor.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterWidth%2A> propiedad|Determina el grosor, en píxeles, del divisor.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterMoving> evento|Se produce cuando se mueve el divisor.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterMoved> evento|Se produce cuando se ha movido el divisor.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.SplitContainer>
- [Control SplitContainer](splitcontainer-control-windows-forms.md)
- [Ejemplo SplitContainer (Control)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/0ffz7d1b(v=vs.90))
