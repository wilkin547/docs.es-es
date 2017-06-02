---
title: "Informaci&#243;n general sobre el control LinkLabel (formularios Windows Forms) | Microsoft Docs"
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
  - "LinkLabel"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Label (control) [Windows Forms], acerca del control Label"
  - "LinkLabel (control) [Windows Forms], acerca del control LinkLabel"
  - "vínculos, LinkLabel (control)"
ms.assetid: 9e248549-10ca-43a3-bb5e-60f583d369f1
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Informaci&#243;n general sobre el control LinkLabel (formularios Windows Forms)
El control <xref:System.Windows.Forms.LinkLabel> de formularios Windows Forms permite agregar vínculos de estilo Web a aplicaciones de Windows Forms.  Puede utilizar el control <xref:System.Windows.Forms.LinkLabel> para todo aquello para lo que pueda utilizar el control <xref:System.Windows.Forms.Label>. También puede establecer parte del texto como un vínculo a un archivo, una carpeta o una página Web.  
  
## Qué se puede hacer con el control LinkLabel  
 Además de todas las propiedades, métodos y eventos del control <xref:System.Windows.Forms.Label>, el control <xref:System.Windows.Forms.LinkLabel> posee propiedades para hipervínculos y colores de vínculo.  La propiedad <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> establece el área del texto que activa el vínculo.  Las propiedades <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> y <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> establecen los colores del vínculo.  El evento <xref:System.Windows.Forms.LinkLabel.LinkClicked> determina qué ocurre cuando se selecciona el texto del vínculo.  
  
 El uso más simple del control <xref:System.Windows.Forms.LinkLabel> es utilizarlo para mostrar un único vínculo mediante la propiedad <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, aunque también se pueden mostrar varios hipervínculos con la propiedad <xref:System.Windows.Forms.LinkLabel.Links%2A>.  La propiedad <xref:System.Windows.Forms.LinkLabel.Links%2A> que permite obtener acceso a una colección de vínculos.  También puede especificar los datos en la propiedad <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> de cada objeto <xref:System.Windows.Forms.LinkLabel.Link> individual.  El valor de la propiedad <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> se puede usar para almacenar la ubicación de un archivo con el fin de mostrar la dirección de un sitio Web.  
  
## Vea también  
 <xref:System.Windows.Forms.LinkLabel>   
 [Información general sobre el control Label](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)   
 [Cómo: Establecer vínculos con un objeto o página Web mediante el control LinkLabel de formularios Windows Forms](../../../../docs/framework/winforms/controls/link-to-an-object-or-web-page-with-wf-linklabel-control.md)   
 [Cómo: Cambiar la apariencia del control LinkLabel de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)