---
title: "C&#243;mo: Agrupar controles RadioButton de formularios Windows Forms para que funcionen como un conjunto | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles [Windows Forms], agrupar"
  - "botones de opción, agrupar"
  - "RadioButton (control) [Windows Forms], agrupar"
  - "controles de Windows Forms, agrupar"
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Agrupar controles RadioButton de formularios Windows Forms para que funcionen como un conjunto
Los controles <xref:System.Windows.Forms.RadioButton> de formularios Windows Forms están diseñados para permitir que los usuarios elijan entre dos o más opciones, de las cuales sólo una puede asignarse a un procedimiento u objeto.  Por ejemplo, un grupo de controles <xref:System.Windows.Forms.RadioButton> puede mostrar una serie de servicios de transporte para un pedido, de los que sólo se utilizará uno.  Por lo tanto, sólo es posible seleccionar los controles <xref:System.Windows.Forms.RadioButton> uno por uno, aunque sean parte de un grupo funcional.  
  
 Para agrupar botones de radio, dibújelos dentro de un contenedor, por ejemplo, un control <xref:System.Windows.Forms.Panel>, un control <xref:System.Windows.Forms.GroupBox> o un formulario.  Todos los botones de radio que se agregan directamente a un formulario se convierten en un grupo.  Para agregar grupos independientes, deberá colocarlos dentro de paneles o cuadros de grupo.  Para obtener más información sobre paneles o cuadros de grupo, vea [Información general del control Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md) o [Información general sobre el control GroupBox](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md).  
  
### Para agrupar controles RadioButton en un conjunto, de modo que funcionen de forma independiente  
  
1.  Arrastre un control <xref:System.Windows.Forms.GroupBox> o <xref:System.Windows.Forms.Panel> desde la ficha **Windows Forms** del **Cuadro de herramientas** hasta el formulario.  
  
2.  Dibuje los controles <xref:System.Windows.Forms.RadioButton> en el control <xref:System.Windows.Forms.GroupBox> o <xref:System.Windows.Forms.Panel>.  
  
## Vea también  
 <xref:System.Windows.Forms.RadioButton>   
 [Información general sobre el control RadioButton](../../../../docs/framework/winforms/controls/radiobutton-control-overview-windows-forms.md)   
 [Información general del control Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)   
 [Información general sobre el control GroupBox](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)   
 [Información general sobre el control CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)   
 [RadioButton \(Control\)](../../../../docs/framework/winforms/controls/radiobutton-control-windows-forms.md)