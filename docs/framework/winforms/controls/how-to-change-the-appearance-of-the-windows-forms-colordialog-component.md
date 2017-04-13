---
title: "C&#243;mo: Cambiar la apariencia del componente ColorDialog de formularios Windows Forms | Microsoft Docs"
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
  - "cuadro de diálogo de colores, apariencia de configuración"
  - "ColorDialog (componente), ejemplos"
  - "ColorDialog (componente), dar formato a la apariencia"
ms.assetid: bba4e262-1cd7-4f63-89cf-330a36f7b539
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Cambiar la apariencia del componente ColorDialog de formularios Windows Forms
Puede configurar la apariencia del componente <xref:System.Windows.Forms.ColorDialog> de formularios Windows Forms con varias de sus propiedades.  El cuadro de diálogo tiene dos secciones: una que muestra colores básicos y otra que permite al usuario la definición de colores personalizados.  
  
 La mayoría de las propiedades restringen los colores que el usuario puede seleccionar en el cuadro de diálogo.  Si se establece la propiedad <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> en `true`, el usuario puede definir colores personalizados.  La propiedad <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> es `true` si el cuadro de diálogo está expandido para definir colores personalizados; de lo contrario, el usuario debe hacer clic en el botón "Definir colores personalizados".  Cuando la propiedad <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> se establece en `true`, el cuadro de diálogo muestra todos los colores disponibles del conjunto de colores básicos.  Si la propiedad <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> se establece en `true`, el usuario no puede seleccionar colores interpolados; sólo es posible seleccionar colores sólidos.  
  
 Si la propiedad <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> se establece en `true`, aparece un botón Ayuda en el cuadro de diálogo.  Cuando el usuario hace clic en el botón Ayuda, se produce el evento <xref:System.Windows.Forms.CommonDialog.HelpRequest> del componente <xref:System.Windows.Forms.ColorDialog>.  
  
### Para configurar la apariencia del cuadro de diálogo de color  
  
1.  Establezca las propiedades <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> y <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> en los colores deseados.  
  
    ```vb  
    ColorDialog1.AllowFullOpen = True  
    ColorDialog1.AnyColor = True  
    ColorDialog1.SolidColorOnly = False  
    ColorDialog1.ShowHelp = True  
  
    ```  
  
    ```csharp  
    colorDialog1.AllowFullOpen = true;  
    colorDialog1.AnyColor = true;  
    colorDialog1.SolidColorOnly = false;  
    colorDialog1.ShowHelp = true;  
  
    ```  
  
    ```cpp  
    colorDialog1->AllowFullOpen = true;  
    colorDialog1->AnyColor = true;  
    colorDialog1->SolidColorOnly = false;  
    colorDialog1->ShowHelp = true;  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.ColorDialog>   
 [ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)   
 [Información general sobre el componente ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-overview-windows-forms.md)