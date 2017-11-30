---
title: "Introducción a los controles HScrollBar y VScrollBar (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 80ec592bf83969ae57495b0df2af110b5622ea11
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="hscrollbar-and-vscrollbar-controls-overview-windows-forms"></a>Introducción a los controles HScrollBar y VScrollBar (formularios Windows Forms)
Formularios Windows Forms <xref:System.Windows.Forms.ScrollBar> controles se utilizan para proporcionar navegación fácil por una larga lista de elementos o una gran cantidad de información, ya sea horizontal o verticalmente, dentro de una aplicación o control. Barras de desplazamiento son un elemento común de la interfaz de Windows, por lo que la <xref:System.Windows.Forms.ScrollBar> control suele utilizarse con controles que no se derivan de la <xref:System.Windows.Forms.ScrollableControl> clase. De forma similar, muchos programadores eligen incorporar el <xref:System.Windows.Forms.ScrollBar> controlar al crear sus propios controles de usuario.  
  
 El <xref:System.Windows.Forms.HScrollBar> (horizontal) y <xref:System.Windows.Forms.VScrollBar> controles (verticales) operan independientemente de otros controles y tienen su propio conjunto de eventos, propiedades y métodos. <xref:System.Windows.Forms.ScrollBar>controles no son los mismos que las barras de desplazamiento integradas que se adjuntan a los cuadros de texto, cuadros de lista, cuadros combinados o formularios MDI (el <xref:System.Windows.Forms.TextBox> control tiene un <xref:System.Windows.Forms.TextBox.ScrollBars%2A> propiedad para mostrar u ocultar las barras de desplazamiento que se adjuntan al control).  
  
 El <xref:System.Windows.Forms.ScrollBar> controla el uso del <xref:System.Windows.Forms.ScrollBar.Scroll> eventos para supervisar el movimiento del cuadro de desplazamiento (denominado a veces como control de posición) a lo largo de la barra de desplazamiento. Mediante el <xref:System.Windows.Forms.ScrollBar.Scroll> evento proporciona acceso para el valor de la barra de desplazamiento tal y como se está arrastrando.  
  
## <a name="value-property"></a>Propiedad Value  
 El <xref:System.Windows.Forms.ScrollBar.Value%2A> propiedad (que, de forma predeterminada, es 0) es un `integer` valor corresponde a la posición del cuadro de desplazamiento en la barra de desplazamiento. Una vez la posición del cuadro de desplazamiento en el valor mínimo, mueve a la posición más a la izquierda (para las barras de desplazamiento horizontal) o la posición superior (para las barras de desplazamiento vertical). Cuando el cuadro de desplazamiento está en el valor máximo, los movimientos del cuadro de desplazamiento más a la derecha o posición de la parte inferior. De forma similar, un valor comprendido entre la parte inferior y superior del intervalo sitúa el borde inicial del cuadro de desplazamiento en el medio de la barra de desplazamiento.  
  
 Además de usar clics del mouse para cambiar el valor de la barra de desplazamiento, un usuario también puede arrastrar el cuadro de desplazamiento a cualquier punto a lo largo de la barra. El valor resultante depende de la posición del cuadro de desplazamiento, pero se encuentra siempre dentro del intervalo de la <xref:System.Windows.Forms.ScrollBar.Minimum%2A> a <xref:System.Windows.Forms.ScrollBar.Maximum%2A> propiedades establecidas por el usuario.  
  
## <a name="largechange-and-smallchange-properties"></a>Propiedades LargeChange y SmallChange  
 Cuando el usuario presiona la tecla RE PÁG o AV PÁG o hace clic en el recorrido de la barra de desplazamiento a cada lado del cuadro de desplazamiento, el <xref:System.Windows.Forms.ScrollBar.Value%2A> cambios de propiedad según el valor establecido en el <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> propiedad.  
  
 Cuando el usuario presiona uno de la flecha de claves o haga clic en uno de los botones de barra de desplazamiento, el <xref:System.Windows.Forms.ScrollBar.Value%2A> cambios de propiedad según el valor establecido en el <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> propiedad.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.HScrollBar>  
 <xref:System.Windows.Forms.VScrollBar>  
 [Adiciones a formularios Windows Forms para .NET Framework 2.0](http://msdn.microsoft.com/en-us/c61a923d-3d6a-4c8c-820c-e94c83f3f9a8)  
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
