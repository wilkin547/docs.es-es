---
title: "Introducci&#243;n a los controles HScrollBar y VScrollBar (formularios Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "HScrollBar"
  - "VScrollBar"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "HScrollBar (control) [Windows Forms], acerca de HScrollBar"
  - "barras de desplazamiento, acerca de barras de desplazamiento"
  - "ScrollBar (control) [Windows Forms]"
  - "ScrollBar (control) [Windows Forms], acerca del control ScrollBar"
  - "VScrollBar (control) [Windows Forms], acerca del control VScrollBar"
ms.assetid: 8b307679-1cae-41d8-99aa-3d1efd207cd6
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Introducci&#243;n a los controles HScrollBar y VScrollBar (formularios Windows Forms)
Los controles <xref:System.Windows.Forms.ScrollBar> de formularios Windows Forms se utilizan para permitir una navegación fácil por una lista de elementos o un gran volumen de información, ya sea horizontal o verticalmente, dentro de una aplicación o control.  Las barras de desplazamiento son un elemento común de la interfaz de Windows, así que el control <xref:System.Windows.Forms.ScrollBar> suele utilizarse con controles que no derivan de la clase <xref:System.Windows.Forms.ScrollableControl>.  De forma similar, muchos programadores eligen incorporar el control <xref:System.Windows.Forms.ScrollBar> cuando crean sus propios controles de usuario.  
  
 Los controles <xref:System.Windows.Forms.HScrollBar> \(horizontal\) y <xref:System.Windows.Forms.VScrollBar> \(vertical\) operan independientemente de otros controles y tienen su propio conjunto de eventos, propiedades y métodos.  Los controles <xref:System.Windows.Forms.ScrollBar> no se asemejan a las barras de desplazamiento integradas que se adjuntan a los cuadros de texto, cuadros de lista, cuadros combinados o formularios MDI \(el control <xref:System.Windows.Forms.TextBox> tiene una propiedad <xref:System.Windows.Forms.TextBox.ScrollBars%2A> para mostrar u ocultar las barras de desplazamiento adjuntas a un control\).  
  
 Los controles <xref:System.Windows.Forms.ScrollBar> utilizan el evento <xref:System.Windows.Forms.ScrollBar.Scroll> para supervisar el movimiento del cuadro de desplazamiento \(a veces conocido como control de posición\) a lo largo de la barra de desplazamiento.  El uso del evento <xref:System.Windows.Forms.ScrollBar.Scroll> proporciona acceso al valor de la barra de desplazamiento durante la operación de arrastre.  
  
## Value \(Propiedad\)  
 La propiedad <xref:System.Windows.Forms.ScrollBar.Value%2A> \(que, de forma predeterminada, es 0\) es un valor de tipo `integer` que corresponde a la posición del cuadro de desplazamiento en la barra de desplazamiento.  Cuando la posición del cuadro de desplazamiento se encuentra en el valor mínimo, se desplaza al extremo izquierdo \(en las barras de desplazamiento horizontal\) o al extremo superior \(en las barras de desplazamiento vertical\).  Cuando el cuadro de desplazamiento está en el valor máximo, el cuadro de desplazamiento se desplaza al extremo derecho o inferior.  De forma similar, un valor a medio camino entre el inferior y el superior del intervalo sitúa el margen inicial del cuadro de desplazamiento en el punto medio de la barra de desplazamiento.  
  
 Además de hacer clic con el mouse para cambiar el valor de la barra de desplazamiento, un usuario puede también arrastrar el cuadro de desplazamiento a cualquier punto de la barra.  El valor resultante depende de la posición del cuadro de desplazamiento, pero se encuentra siempre dentro del intervalo de las propiedades <xref:System.Windows.Forms.ScrollBar.Minimum%2A> a <xref:System.Windows.Forms.ScrollBar.Maximum%2A> establecido por el usuario.  
  
## Propiedades LargeChange y SmallChange  
 Cuando el usuario presiona la tecla RE PÁG o AV PÁG o hace clic en el recorrido de la barra de desplazamiento, la propiedad <xref:System.Windows.Forms.ScrollBar.Value%2A> cambia de acuerdo con el valor establecido en la propiedad <xref:System.Windows.Forms.ScrollBar.LargeChange%2A>.  
  
 Cuando el usuario presiona una de las teclas de dirección o hace clic en uno de los botones de la barra de desplazamiento, la propiedad <xref:System.Windows.Forms.ScrollBar.Value%2A> cambia de acuerdo con el valor establecido en la propiedad <xref:System.Windows.Forms.ScrollBar.SmallChange%2A>.  
  
## Vea también  
 <xref:System.Windows.Forms.HScrollBar>   
 <xref:System.Windows.Forms.VScrollBar>   
 [Adiciones a Windows Forms para .NET Framework 2.0](http://msdn.microsoft.com/es-es/c61a923d-3d6a-4c8c-820c-e94c83f3f9a8)   
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)