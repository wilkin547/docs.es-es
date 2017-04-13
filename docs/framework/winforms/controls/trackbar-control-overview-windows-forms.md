---
title: "Informaci&#243;n general del control TrackBar (formularios Windows Forms) | Microsoft Docs"
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
  - "TrackBar"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles deslizantes, acerca de los controles deslizantes"
  - "controles deslizantes, acerca de los controles deslizantes"
  - "TrackBar (control) [Windows Forms], acerca del control TrackBar"
ms.assetid: 95910ecb-8a4c-4776-89fa-206c89ed6973
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Informaci&#243;n general del control TrackBar (formularios Windows Forms)
El control <xref:System.Windows.Forms.TrackBar> de Windows Forms \(también denominado en ocasiones control "deslizante"\) se utiliza para navegar por grandes volúmenes de información o para ajustar visualmente una configuración numérica.  El control <xref:System.Windows.Forms.TrackBar> tiene dos partes: el control de posición, también conocido como control deslizante, y las marcas de paso.  El control de posición es la parte que puede ajustarse.  Su posición corresponde a la propiedad <xref:System.Windows.Forms.TrackBar.Value%2A>.  Las marcas de paso son indicadores visuales espaciados a intervalos regulares.  La barra de seguimiento se desplaza en los incrementos que se especifiquen y puede alinearse horizontal o verticalmente.  Por ejemplo, se puede usar la barra de seguimiento para controlar la velocidad de intermitencia del cursor o la velocidad del mouse en un sistema.  
  
## Propiedades principales  
 Las propiedades principales del control <xref:System.Windows.Forms.TrackBar> son <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A> y <xref:System.Windows.Forms.TrackBar.Maximum%2A>.  <xref:System.Windows.Forms.TrackBar.TickFrequency%2A> es el espaciado de las marcas.  <xref:System.Windows.Forms.TrackBar.Minimum%2A> y <xref:System.Windows.Forms.TrackBar.Maximum%2A> son los valores mínimo y máximo que se pueden representar en la barra de seguimiento.  
  
 Hay otras dos propiedades importantes: <xref:System.Windows.Forms.TrackBar.SmallChange%2A> y <xref:System.Windows.Forms.TrackBar.LargeChange%2A>.  El valor de la propiedad <xref:System.Windows.Forms.TrackBar.SmallChange%2A> es el número de posiciones que se desplaza el control de posición como respuesta a la acción de presionar la tecla de dirección DERECHA o IZQUIERDA.  El valor de la propiedad <xref:System.Windows.Forms.TrackBar.LargeChange%2A> es el número de posiciones que se desplaza el control de posición en respuesta a la acción de presionar la tecla RE PÁG o AV PÁG, o en respuesta a la acción de hacer clic con el mouse en la barra de seguimiento a ambos lados del control de posición.  
  
## Vea también  
 <xref:System.Windows.Forms.TrackBar>   
 [TrackBar \(Control\)](../../../../docs/framework/winforms/controls/trackbar-control-windows-forms.md)