---
title: "C&#243;mo: Agrupar controles con el control GroupBox de formularios Windows Forms | Microsoft Docs"
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
  - "GroupBox (control) [Windows Forms], agrupar controles"
  - "controles de Windows Forms, agrupar"
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Agrupar controles con el control GroupBox de formularios Windows Forms
Los controles <xref:System.Windows.Forms.GroupBox> de Windows Forms se utilizan para agrupar otros controles.  Los controles se pueden agrupar por tres motivos:  
  
-   Para crear una agrupación visual de elementos de formulario relacionados para obtener una interfaz de usuario clara.  
  
-   Para crear la agrupación de programación \(de botones de radio, por ejemplo\).  
  
-   Para mover los controles como una unidad en tiempo de diseño.  
  
### Para crear un grupo de controles  
  
1.  Dibuje un control <xref:System.Windows.Forms.GroupBox> en un formulario.  
  
2.  Agregue otros controles al cuadro de grupo; para ello, dibuje cada uno de los controles dentro del cuadro de grupo.  
  
     Si tiene controles que desee incluir en un cuadro de grupo, puede seleccionarlos todos, cortarlos al Portapapeles, seleccionar el control <xref:System.Windows.Forms.GroupBox> y, a continuación, pegarlos en el cuadro de grupo.  También puede arrastrarlos al cuadro de grupo.  
  
3.  Establezca la leyenda apropiada como valor de la propiedad <xref:System.Windows.Forms.GroupBox.Text%2A> del cuadro de grupo.  
  
## Vea también  
 <xref:System.Windows.Forms.GroupBox>   
 [Control GroupBox](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md)