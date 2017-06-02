---
title: "Informaci&#243;n general del control Panel (formularios Windows Forms) | Microsoft Docs"
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
  - "Panel"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "agrupar controles, Panel (control)"
  - "Panel (control) [Windows Forms], acerca del control Panel"
ms.assetid: b6b83636-2c39-4dad-89d6-f0fa41049a74
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Informaci&#243;n general del control Panel (formularios Windows Forms)
Los controles <xref:System.Windows.Forms.Panel> de Windows Forms se utilizan para proporcionar un agrupamiento identificable para otros controles.  Normalmente, los paneles se utilizan para subdividir un formulario por funciones.  Por ejemplo, podría tener un formulario de pedido que especifique opciones de envío, como el servicio de transporte urgente que se va a utilizar.  Agrupar todas las opciones en un panel ofrece al usuario una pista visual lógica.  En tiempo de diseño todos los controles se pueden mover fácilmente; cuando se mueve el control <xref:System.Windows.Forms.Panel>, todos los controles que contiene se desplazan también.  Se puede obtener acceso a los controles agrupados en un panel mediante su propiedad <xref:System.Windows.Forms.Control.Controls%2A>.  Esta propiedad devuelve una colección de instancias <xref:System.Windows.Forms.Control>, por lo que normalmente necesitará convertir un control recuperado de esta manera a su tipo específico.  
  
## Panel frente a GroupBox  
 Los controles <xref:System.Windows.Forms.Panel> y <xref:System.Windows.Forms.GroupBox> son similares; sin embargo, el control <xref:System.Windows.Forms.Panel> es el único de los dos que puede tener barras de desplazamiento y el control <xref:System.Windows.Forms.GroupBox> es el único de los dos que muestra una leyenda.  
  
## Propiedades principales  
 Para mostrar barras de desplazamiento, establezca la propiedad <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> en `true`.  Para personalizar la apariencia del panel, establezca las propiedades <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A> y <xref:System.Windows.Forms.Panel.BorderStyle%2A>.  Para obtener más información sobre las propiedades <xref:System.Windows.Forms.Control.BackColor%2A> y <xref:System.Windows.Forms.Control.BackgroundImage%2A>, vea [Cómo: Establecer el fondo de un panel](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md).  La propiedad <xref:System.Windows.Forms.Panel.BorderStyle%2A> determina si el panel está rodeado por un borde invisible \(<xref:System.Windows.Forms.BorderStyle>\), una línea simple \(<xref:System.Windows.Forms.BorderStyle>\) o una línea sombreada \(<xref:System.Windows.Forms.BorderStyle>\).  
  
## Vea también  
 <xref:System.Windows.Forms.Panel>   
 [Control GroupBox](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md)   
 [Cómo: Agrupar controles con el control Panel de Windows Forms mediante el Diseñador](../../../../docs/framework/winforms/controls/group-controls-with-wf-panel-control-using-the-designer.md)   
 [Cómo: Establecer el fondo de un control Panel de formularios Windows Forms mediante el Diseñador](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel-using-the-designer.md)