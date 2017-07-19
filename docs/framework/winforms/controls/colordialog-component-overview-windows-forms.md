---
title: "Informaci&#243;n general sobre el componente ColorDialog (formularios Windows Forms) | Microsoft Docs"
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
  - "ColorDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "cuadro de diálogo de colores, acerca del cuadro de diálogo de colores"
  - "ColorDialog (componente), acerca de ColorDialog"
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Informaci&#243;n general sobre el componente ColorDialog (formularios Windows Forms)
El componente <xref:System.Windows.Forms.ColorDialog> de formularios Windows Forms es un cuadro de diálogo preconfigurado que permite que el usuario seleccione un color de una paleta y agregue colores personalizados a la paleta.  Es el mismo cuadro de diálogo que se ve en otras aplicaciones para Windows y que permite seleccionar colores.  Utilícelo dentro de la aplicación basada en Windows como una solución sencilla, en lugar de configurar un cuadro de diálogo propio.  
  
 El color seleccionado en el cuadro de diálogo se devuelve en la propiedad <xref:System.Windows.Forms.ColorDialog.Color%2A>.  Si se establece la propiedad <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> en `false`, el botón "Definir colores personalizados" se deshabilita y el usuario queda limitado a los colores predefinidos en la paleta.  Si se establece la propiedad <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> en `true`, el usuario no puede seleccionar colores interpolados.  Para que se muestre el cuadro de diálogo, llame al método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>.  
  
## Vea también  
 <xref:System.Windows.Forms.ColorDialog>   
 [ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)   
 [Controles y componentes de cuadros de diálogo](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)   
 [Cómo: Cambiar la apariencia del componente ColorDialog de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)