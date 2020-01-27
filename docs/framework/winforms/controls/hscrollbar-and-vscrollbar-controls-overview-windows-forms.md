---
title: Información general sobre los controles HScrollBar y VScrollBar
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
ms.openlocfilehash: abe0c8da9723f17cb80715454f6ab7297724a21f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728160"
---
# <a name="hscrollbar-and-vscrollbar-controls-overview-windows-forms"></a>Introducción a los controles HScrollBar y VScrollBar (formularios Windows Forms)
Windows Forms <xref:System.Windows.Forms.ScrollBar> controles se usan para facilitar la navegación a través de una larga lista de elementos o una gran cantidad de información desplazándose horizontal o verticalmente dentro de una aplicación o un control. Las barras de desplazamiento son un elemento común de la interfaz de Windows, por lo que el control <xref:System.Windows.Forms.ScrollBar> se usa a menudo con controles que no derivan de la clase <xref:System.Windows.Forms.ScrollableControl>. Del mismo modo, muchos desarrolladores optan por incorporar el control <xref:System.Windows.Forms.ScrollBar> al crear sus propios controles de usuario.  
  
 Los controles <xref:System.Windows.Forms.HScrollBar> (horizontal) y <xref:System.Windows.Forms.VScrollBar> (vertical) funcionan independientemente de otros controles y tienen su propio conjunto de eventos, propiedades y métodos. <xref:System.Windows.Forms.ScrollBar> controles no son los mismos que las barras de desplazamiento integradas que están asociadas a cuadros de texto, cuadros de lista, cuadros combinados o formularios MDI (el control <xref:System.Windows.Forms.TextBox> tiene una propiedad <xref:System.Windows.Forms.TextBox.ScrollBars%2A> para mostrar u ocultar las barras de desplazamiento que están asociadas al control).  
  
 Los controles <xref:System.Windows.Forms.ScrollBar> utilizan el evento <xref:System.Windows.Forms.ScrollBar.Scroll> para supervisar el movimiento del cuadro de desplazamiento (a veces denominado control de posición) a lo largo de la barra de desplazamiento. El uso del evento <xref:System.Windows.Forms.ScrollBar.Scroll> proporciona acceso al valor de la barra de desplazamiento mientras se arrastra.  
  
## <a name="value-property"></a>Propiedad Value  
 La propiedad <xref:System.Windows.Forms.ScrollBar.Value%2A> (que, de forma predeterminada, es 0) es un valor `integer` que corresponde a la posición del cuadro de desplazamiento en la barra de desplazamiento. Cuando la posición del cuadro de desplazamiento está en el valor mínimo, se mueve a la posición situada más a la izquierda (para las barras de desplazamiento horizontal) o a la posición superior (para las barras de desplazamiento verticales). Cuando el cuadro de desplazamiento está en el valor máximo, el cuadro de desplazamiento se desplaza a la posición más a la derecha o en la parte inferior. Del mismo modo, un valor que se encuentra entre la parte inferior y la parte superior del intervalo coloca el borde inicial del cuadro de desplazamiento en el centro de la barra de desplazamiento.  
  
 Además de usar los clics del mouse para cambiar el valor de la barra de desplazamiento, un usuario también puede arrastrar el cuadro de desplazamiento a cualquier punto de la barra. El valor resultante depende de la posición del cuadro de desplazamiento, pero siempre está dentro del intervalo del <xref:System.Windows.Forms.ScrollBar.Minimum%2A> para <xref:System.Windows.Forms.ScrollBar.Maximum%2A> propiedades establecidas por el usuario.  
  
## <a name="largechange-and-smallchange-properties"></a>Propiedades LargeChange y SmallChange  
 Cuando el usuario presiona la tecla RE PÁG o AV PÁG o hace clic en la pista de la barra de desplazamiento en cualquier lado del cuadro de desplazamiento, la propiedad <xref:System.Windows.Forms.ScrollBar.Value%2A> cambia según el valor establecido en la propiedad <xref:System.Windows.Forms.ScrollBar.LargeChange%2A>.  
  
 Cuando el usuario presiona una de las teclas de dirección o hace clic en uno de los botones de la barra de desplazamiento, la propiedad <xref:System.Windows.Forms.ScrollBar.Value%2A> cambia según el valor establecido en la propiedad <xref:System.Windows.Forms.ScrollBar.SmallChange%2A>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.HScrollBar>
- <xref:System.Windows.Forms.VScrollBar>
- [Controles que se utilizan en Windows Forms](controls-to-use-on-windows-forms.md)
