---
title: Introducción a los controles HScrollBar y VScrollBar (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- HScrollBar
- VScrollBar
helpviewer_keywords:
- ScrollBar control [Windows Forms]
- HScrollBar control [Windows Forms], about HScrollBar
- VScrollBar control [Windows Forms], about VScrollBar control
- ScrollBar control [Windows Forms], about ScrollBar control
- scroll bars [Windows Forms], about scroll bars
ms.assetid: 8b307679-1cae-41d8-99aa-3d1efd207cd6
ms.openlocfilehash: cba28acf7e8594cd8eef88436ddde86efacada36
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714104"
---
# <a name="hscrollbar-and-vscrollbar-controls-overview-windows-forms"></a>Introducción a los controles HScrollBar y VScrollBar (formularios Windows Forms)
Windows Forms <xref:System.Windows.Forms.ScrollBar> controles se usan para proporcionar la fácil navegación a través de una larga lista de elementos o una gran cantidad de información, ya sea horizontal o verticalmente dentro de una aplicación o control. Las barras de desplazamiento son un elemento común de la interfaz de Windows, por lo que la <xref:System.Windows.Forms.ScrollBar> control suele utilizarse con controles que no se derivan de la <xref:System.Windows.Forms.ScrollableControl> clase. De forma similar, muchos programadores eligen incorporar el <xref:System.Windows.Forms.ScrollBar> controlar al crear sus propios controles de usuario.  
  
 El <xref:System.Windows.Forms.HScrollBar> (horizontal) y <xref:System.Windows.Forms.VScrollBar> controles (verticales) funcionan independientemente de otros controles y tienen su propio conjunto de eventos, propiedades y métodos. <xref:System.Windows.Forms.ScrollBar> controles no son los mismos que las barras de desplazamiento integradas que están asociadas a los cuadros de texto, cuadros de lista, cuadros combinados o formularios MDI (el <xref:System.Windows.Forms.TextBox> control tiene un <xref:System.Windows.Forms.TextBox.ScrollBars%2A> propiedad para mostrar u ocultar las barras de desplazamiento que están asociadas al control).  
  
 El <xref:System.Windows.Forms.ScrollBar> controles usan la <xref:System.Windows.Forms.ScrollBar.Scroll> evento para supervisar el movimiento del cuadro de desplazamiento (denominado en ocasiones, el control de posición) a lo largo de la barra de desplazamiento. Mediante el <xref:System.Windows.Forms.ScrollBar.Scroll> evento proporciona acceso al valor de la barra de desplazamiento tal como se está arrastrando.  
  
## <a name="value-property"></a>Propiedad Value  
 El <xref:System.Windows.Forms.ScrollBar.Value%2A> propiedad (que, de forma predeterminada, es 0) es un `integer` valor correspondiente a la posición del cuadro de desplazamiento en la barra de desplazamiento. Cuando la posición del cuadro de desplazamiento está en el valor mínimo, se mueve a la posición más a la izquierda (para las barras de desplazamiento horizontal) o la posición superior (para las barras de desplazamiento vertical). Cuando el cuadro de desplazamiento está en el valor máximo, los movimientos del cuadro de desplazamiento a la derecha o la posición inferior. De forma similar, un valor a medio camino entre la parte inferior y superior del intervalo sitúa el borde inicial del cuadro de desplazamiento en el medio de la barra de desplazamiento.  
  
 Además de usar clics del mouse para cambiar el valor de la barra de desplazamiento, un usuario también puede arrastrar el cuadro de desplazamiento a cualquier momento a lo largo de la barra. El valor resultante depende de la posición del cuadro de desplazamiento, aunque siempre resulta dentro del intervalo de la <xref:System.Windows.Forms.ScrollBar.Minimum%2A> a <xref:System.Windows.Forms.ScrollBar.Maximum%2A> propiedades establecidas por el usuario.  
  
## <a name="largechange-and-smallchange-properties"></a>Propiedades de SmallChange y LargeChange  
 Cuando el usuario presiona la tecla RE PÁG o AV PÁG o hace clic en la barra de desplazamiento en cualquier lado del cuadro de desplazamiento, el <xref:System.Windows.Forms.ScrollBar.Value%2A> los cambios de propiedad según el valor establecido en el <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> propiedad.  
  
 Cuando el usuario presiona uno de la flecha de claves o hace clic en uno de los botones de barra de desplazamiento, el <xref:System.Windows.Forms.ScrollBar.Value%2A> los cambios de propiedad según el valor establecido en el <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> propiedad.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.HScrollBar>
- <xref:System.Windows.Forms.VScrollBar>
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
