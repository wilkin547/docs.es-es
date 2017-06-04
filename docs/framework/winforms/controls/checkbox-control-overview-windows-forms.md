---
title: "Informaci&#243;n general sobre el control CheckBox (formularios Windows Forms) | Microsoft Docs"
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
  - "CheckBox"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles enlazados, casillas"
  - "casillas, acerca de las casillas"
  - "CheckBox (control) [Windows Forms], acerca del control CheckBox"
  - "enlace de datos, CheckBox (controles)"
  - "controles enlazados a datos, casillas"
ms.assetid: 085a4e0b-9046-473f-b141-d0edddfb2ebb
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Informaci&#243;n general sobre el control CheckBox (formularios Windows Forms)
El control <xref:System.Windows.Forms.CheckBox> de Windows Forms indica si una condición determinada está activada o desactivada.  Se utiliza habitualmente para presentar al usuario una selección de tipo Sí\/No o Verdadero\/Falso.  Puede utilizar grupos de casillas para mostrar múltiples opciones entre las cuales el usuario puede elegir una o más.  
  
 El control casilla es similar al control de botón de radio, puesto que los dos se utilizan para indicar una selección realizada por el usuario.  Sólo difieren en que en un grupo de botones de radio no se puede seleccionar más de un botón de radio.  Sin embargo, en un grupo de casillas es posible seleccionar tantas casillas como se desee.  
  
 Puede conectar una casilla a elementos de una base de datos mediante enlaces simples de datos.  También puede agrupar varias casillas por medio del control <xref:System.Windows.Forms.GroupBox>.  Esto resulta útil para mejorar la apariencia visual y para el diseño de la interfaz de usuario, puesto que permite mover juntos los controles agrupados por el diseñador de formularios.  Para obtener más información, vea [Enlace de datos en Windows Forms](../../../../docs/framework/winforms/windows-forms-data-binding.md) y [Control GroupBox](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md).  
  
 El control <xref:System.Windows.Forms.CheckBox> tiene dos propiedades importantes: <xref:System.Windows.Forms.CheckBox.Checked%2A> y <xref:System.Windows.Forms.CheckBox.CheckState%2A>.  La propiedad <xref:System.Windows.Forms.CheckBox.Checked%2A> devuelve `true` o `false`.  La propiedad <xref:System.Windows.Forms.CheckBox.CheckState%2A> devuelve <xref:System.Windows.Forms.CheckState> o <xref:System.Windows.Forms.CheckState>; o bien, si la propiedad <xref:System.Windows.Forms.CheckBox.ThreeState%2A> se establece en `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> también puede devolver <xref:System.Windows.Forms.CheckState>.  En el estado indeterminado, el cuadro se muestra con un aspecto atenuado para indicar que la opción no está disponible.  
  
## Vea también  
 <xref:System.Windows.Forms.CheckBox>   
 [Cómo: Establecer opciones con los controles CheckBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)   
 [Cómo: Responder a clics en casillas de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)   
 [CheckBox \(Control\)](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)