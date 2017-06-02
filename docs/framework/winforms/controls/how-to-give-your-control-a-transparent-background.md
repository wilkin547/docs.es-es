---
title: "C&#243;mo: Proporcionar un fondo transparente a un control | Microsoft Docs"
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
  - "controles personalizados [Windows Forms], fondo transparente"
  - "transparencia, controles personalizados de Windows Forms"
  - "fondos transparentes, controles personalizados"
ms.assetid: 32433e63-f4e9-4305-9857-6de3edeb944a
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# C&#243;mo: Proporcionar un fondo transparente a un control
En versiones anteriores de .NET Framework, los controles no admitían la opción de establecer fondos transparentes sin establecer primero el método <xref:System.Windows.Forms.Control.SetStyle%2A> en el constructor de formularios. En la versión actual de .NET Framework, el color de fondo de la mayoría de los controles se puede establecer como <xref:System.Drawing.Color.Transparent%2A> en la ventana **Propiedades** durante el tiempo de diseño o como código en el constructor del formulario.  
  
> [!NOTE]
>  Los controles de Windows Forms no admiten una transparencia real. El fondo de un control de Windows Forms transparente lo pinta su control primario.  
  
> [!NOTE]
>  El control <xref:System.Windows.Controls.Button> no admite un color de fondo transparente incluso si la propiedad <xref:System.Windows.Forms.ButtonBase.BackColor%2A> se estableció como <xref:System.Drawing.Color.Transparent%2A>.  
  
### Proporcionar un fondo transparente a un control  
  
-   En la ventana Propiedades, elija la propiedad <xref:System.Windows.Forms.ButtonBase.BackColor%2A> y establézcala como <xref:System.Drawing.Color.Transparent%2A>  
  
## Vea también  
 <xref:System.Drawing.Color.FromArgb%2A>   
 [Desarrollar controles personalizados de formularios Windows Forms con .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)   
 [Utilizar clases gráficas administradas](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)   
 [Cómo: Dibujar líneas opacas y semitransparentes](../../../../docs/framework/winforms/advanced/how-to-draw-opaque-and-semitransparent-lines.md)