---
title: Información general sobre SplitContainer (Control, formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- SplitContainer
helpviewer_keywords:
- SplitContainer control [Windows Forms], about SplitContainer control
ms.assetid: 6de5a5f7-97a5-402d-be6d-7e2785483db5
ms.openlocfilehash: f6dcdbde480c1900ea488c6db3cc320b20f9f182
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591486"
---
# <a name="splitcontainer-control-overview-windows-forms"></a>Información general sobre SplitContainer (Control, formularios Windows Forms)
El control <xref:System.Windows.Forms.SplitContainer> de Windows Forms puede considerarse como una composición de dos paneles separados por una barra móvil. Cuando el puntero del mouse está sobre la barra, el puntero cambia de forma para mostrar que se puede mover.  
  
> [!IMPORTANT]
>  En el **cuadro de herramientas**, <xref:System.Windows.Forms.SplitContainer> control reemplaza el <xref:System.Windows.Forms.Splitter> control que había en la versión anterior de Visual Studio. El control <xref:System.Windows.Forms.SplitContainer> es mucho más preferible que el control <xref:System.Windows.Forms.Splitter>. La clase <xref:System.Windows.Forms.Splitter> aún se incluye en .NET Framework por motivos de compatibilidad con aplicaciones existentes, pero es muy recomendable que use el control <xref:System.Windows.Forms.SplitContainer> en los nuevos proyectos.  
  
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
|Propiedad <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A>|Determina qué panel seguirá siendo el mismo tamaño después de la <xref:System.Windows.Forms.SplitContainer> control cambia de tamaño.|  
|Propiedad <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>|Determina si el divisor se puede mover con el teclado o mouse (ratón).|  
|Propiedad <xref:System.Windows.Forms.SplitContainer.Orientation%2A>|Determina si el divisor se organiza verticalmente u horizontalmente.|  
|Propiedad <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>|Determina la distancia en píxeles desde el borde izquierdo o superior a la barra de división movible.|  
|Propiedad <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>|Determina la distancia mínima en píxeles, que el usuario puede mover el divisor.|  
|Propiedad <xref:System.Windows.Forms.SplitContainer.SplitterWidth%2A>|Determina el grosor, en píxeles, del divisor.|  
|Evento<xref:System.Windows.Forms.SplitContainer.SplitterMoving> |Se produce cuando se mueve el divisor.|  
|Evento<xref:System.Windows.Forms.SplitContainer.SplitterMoved> |Se produce cuando se ha movido el divisor.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.SplitContainer>
- [SplitContainer (control)](splitcontainer-control-windows-forms.md)
- [Ejemplo SplitContainer (Control)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/0ffz7d1b(v=vs.90))
