---
title: Información general sobre SplitContainer (Control, formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- SplitContainer
helpviewer_keywords:
- SplitContainer control [Windows Forms], about SplitContainer control
ms.assetid: 6de5a5f7-97a5-402d-be6d-7e2785483db5
ms.openlocfilehash: 76299d9bbd2b3eac4e765dfacf579c9979721fff
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963205"
---
# <a name="splitcontainer-control-overview-windows-forms"></a>Información general sobre SplitContainer (Control, formularios Windows Forms)
El control <xref:System.Windows.Forms.SplitContainer> de Windows Forms puede considerarse como una composición de dos paneles separados por una barra móvil. Cuando el puntero del mouse está sobre la barra, el puntero cambia de forma para mostrar que se puede mover.  
  
> [!IMPORTANT]
> En el **cuadro**de <xref:System.Windows.Forms.SplitContainer> herramientas, el <xref:System.Windows.Forms.Splitter> control reemplaza el control que estaba en la versión anterior de Visual Studio. El control <xref:System.Windows.Forms.SplitContainer> es mucho más preferible que el control <xref:System.Windows.Forms.Splitter>. La clase <xref:System.Windows.Forms.Splitter> aún se incluye en .NET Framework por motivos de compatibilidad con aplicaciones existentes, pero es muy recomendable que use el control <xref:System.Windows.Forms.SplitContainer> en los nuevos proyectos.  
  
 Con el <xref:System.Windows.Forms.SplitContainer> control, puede crear interfaces de usuario complejas; a menudo, una selección en un panel determina qué objetos se muestran en el otro panel. Esta organización es muy eficaz para mostrar y explorar información. Tener dos paneles le permite agregar información en áreas, y la barra, o "divisor", facilita a los usuarios cambiar el tamaño de los paneles.  
  
 También se puede <xref:System.Windows.Forms.SplitContainer> anidar más de un control, con el segundo <xref:System.Windows.Forms.SplitContainer> control orientado horizontalmente, para crear paneles superiores e inferiores.  
  
 Tenga en cuenta que <xref:System.Windows.Forms.SplitContainer> el control es accesible desde el teclado de forma predeterminada; los usuarios pueden presionar las teclas de dirección para <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> desplace el divisor si la propiedad está establecida en `false`.  
  
 La <xref:System.Windows.Forms.SplitContainer.Orientation%2A> propiedad<xref:System.Windows.Forms.SplitContainer> del control determina la dirección del divisor, no del propio control. Por lo tanto, cuando esta propiedad se <xref:System.Windows.Forms.Orientation.Vertical>establece en, el divisor se ejecuta de arriba abajo y se crean los paneles izquierdo y derecho.  
  
 Además, tenga en cuenta que el valor de <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> la propiedad varía en función del valor de la <xref:System.Windows.Forms.SplitContainer.Orientation%2A> propiedad. Para obtener más información, <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> vea Property.  
  
 También puede restringir el tamaño y el movimiento del <xref:System.Windows.Forms.SplitContainer> control. La <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> propiedad determina qué panel permanecerá en el mismo tamaño después <xref:System.Windows.Forms.SplitContainer> de cambiar el tamaño del control y la <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> propiedad determina si el separador es movible mediante el teclado o el mouse.  
  
> [!NOTE]
> Incluso si la <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> propiedad está establecida en `true`, el divisor todavía puede moverse mediante programación; por ejemplo, mediante la <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> propiedad.  
  
 Por último, cada panel del <xref:System.Windows.Forms.SplitContainer> control tiene propiedades para determinar su tamaño individual.  
  
## <a name="commonly-used-properties-methods-and-events"></a>Propiedades, métodos y eventos de uso común  
  
|NOMBRE|DESCRIPCIÓN|  
|----------|-----------------|  
|Propiedad<xref:System.Windows.Forms.SplitContainer.FixedPanel%2A>|Determina qué panel permanecerá en el mismo tamaño después <xref:System.Windows.Forms.SplitContainer> de cambiar el tamaño del control.|  
|Propiedad<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>|Determina si el divisor se puede moverse con el teclado o el mouse.|  
|Propiedad<xref:System.Windows.Forms.SplitContainer.Orientation%2A>|Determina si el divisor está organizado vertical u horizontalmente.|  
|Propiedad<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>|Determina la distancia en píxeles desde el borde izquierdo o superior hasta la barra divisora movible.|  
|Propiedad<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>|Determina la distancia mínima, en píxeles, que el usuario puede pasar al divisor.|  
|Propiedad<xref:System.Windows.Forms.SplitContainer.SplitterWidth%2A>|Determina el grosor, en píxeles, del divisor.|  
|Evento<xref:System.Windows.Forms.SplitContainer.SplitterMoving>|Se produce cuando se mueve el divisor.|  
|Evento<xref:System.Windows.Forms.SplitContainer.SplitterMoved>|Se produce cuando se mueve el divisor.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.SplitContainer>
- [SplitContainer (control)](splitcontainer-control-windows-forms.md)
- [Ejemplo de control SplitContainer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/0ffz7d1b(v=vs.90))
