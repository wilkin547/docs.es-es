---
title: Información general sobre el control SplitContainer
ms.date: 03/30/2017
f1_keywords:
- SplitContainer
helpviewer_keywords:
- SplitContainer control [Windows Forms], about SplitContainer control
ms.assetid: 6de5a5f7-97a5-402d-be6d-7e2785483db5
ms.openlocfilehash: 5cb5240ed4ebe3e27c20844681068711c222e9a9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742924"
---
# <a name="splitcontainer-control-overview-windows-forms"></a>Información general sobre SplitContainer (Control, Windows Forms)
El control <xref:System.Windows.Forms.SplitContainer> de Windows Forms puede considerarse como una composición de dos paneles separados por una barra móvil. Cuando el puntero del mouse está sobre la barra, el puntero cambia de forma para mostrar que se puede mover.  
  
> [!IMPORTANT]
> En el **cuadro de herramientas**, <xref:System.Windows.Forms.SplitContainer> control reemplaza el control <xref:System.Windows.Forms.Splitter> que estaba en la versión anterior de Visual Studio. El control <xref:System.Windows.Forms.SplitContainer> es mucho más preferible que el control <xref:System.Windows.Forms.Splitter>. La clase <xref:System.Windows.Forms.Splitter> aún se incluye en .NET Framework por motivos de compatibilidad con aplicaciones existentes, pero es muy recomendable que use el control <xref:System.Windows.Forms.SplitContainer> en los nuevos proyectos.  
  
 Con el control de <xref:System.Windows.Forms.SplitContainer>, puede crear interfaces de usuario complejas. a menudo, una selección en un panel determina qué objetos se muestran en el otro panel. Esta organización es muy eficaz para mostrar y explorar información. Tener dos paneles le permite agregar información en áreas, y la barra, o "divisor", facilita a los usuarios cambiar el tamaño de los paneles.  
  
 También se puede anidar más de un control <xref:System.Windows.Forms.SplitContainer>, con el segundo control de <xref:System.Windows.Forms.SplitContainer> orientado horizontalmente, para crear paneles superiores e inferiores.  
  
 Tenga en cuenta que el control <xref:System.Windows.Forms.SplitContainer> es accesible desde el teclado de forma predeterminada; los usuarios pueden presionar las teclas de dirección para desplace el divisor si la propiedad <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> está establecida en `false`.  
  
 La propiedad <xref:System.Windows.Forms.SplitContainer.Orientation%2A> del control <xref:System.Windows.Forms.SplitContainer> determina la dirección del divisor, no del propio control. Por lo tanto, cuando esta propiedad se establece en <xref:System.Windows.Forms.Orientation.Vertical>, el divisor se ejecuta de arriba abajo y se crean los paneles izquierdo y derecho.  
  
 Además, tenga en cuenta que el valor de la propiedad <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> varía en función del valor de la propiedad <xref:System.Windows.Forms.SplitContainer.Orientation%2A>. Para obtener más información, vea <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> propiedad.  
  
 También puede restringir el tamaño y el movimiento del control de <xref:System.Windows.Forms.SplitContainer>. La propiedad <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> determina qué panel permanecerá en el mismo tamaño después de cambiar el tamaño del control <xref:System.Windows.Forms.SplitContainer>, y la propiedad <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> determina si el separador es movible por el teclado o el mouse.  
  
> [!NOTE]
> Aunque la propiedad <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> esté establecida en `true`, el divisor todavía puede moverse mediante programación; por ejemplo, mediante el uso de la propiedad <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>.  
  
 Por último, cada panel del control <xref:System.Windows.Forms.SplitContainer> tiene propiedades para determinar su tamaño individual.  
  
## <a name="commonly-used-properties-methods-and-events"></a>Propiedades, métodos y eventos de uso común  
  
|Name|Descripción|  
|----------|-----------------|  
|Propiedad<xref:System.Windows.Forms.SplitContainer.FixedPanel%2A>|Determina qué panel permanecerá en el mismo tamaño después de cambiar el tamaño del control <xref:System.Windows.Forms.SplitContainer>.|  
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
