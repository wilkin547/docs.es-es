---
title: "C&#243;mo: Hacer un control no visible en tiempo de ejecuci&#243;n | Microsoft Docs"
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
  - "controles [Windows Forms], convertir en invisible en tiempo de ejecución"
  - "controles personalizados [Windows Forms], invisibles"
  - "controles invisibles"
  - "tiempo de ejecución, hacer que los controles sean invisibles"
  - "controles de usuario [Windows Forms], invisibles"
ms.assetid: 69eb2e72-32f5-4f79-a157-c2c5f60c1628
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Hacer un control no visible en tiempo de ejecuci&#243;n
Hay ocasiones en las que quizá desee crear un control de usuario que sea invisible en tiempo de ejecución.  Por ejemplo, un control que sea un reloj despertador puede ser invisible excepto cuando suene la alarma.  Esto se consigue fácilmente estableciendo la propiedad <xref:System.Windows.Forms.Control.Visible%2A>.  Si la propiedad <xref:System.Windows.Forms.Control.Visible%2A> es `true`, el control aparecerá de la forma habitual.  Si es `false`, el control estará oculto.  Aunque el código del control puede seguir ejecutándose mientras está invisible, no se puede interactuar con el control a través de la interfaz de usuario.  Si desea crear un control invisible que responda a los datos proporcionados por el usuario \(por ejemplo, a los clic del mouse\), debe crear un control transparente.  Para obtener más información, vea [Proporcionar un fondo transparente a un control](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md).  
  
### Hacer un control no visible en tiempo de ejecución  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.Control.Visible%2A> en `false`.  
  
    ```vb  
    ' To set the Visible property from within your object's own code.  
    Me.Visible = False  
    ' To set the Visible property from another object.  
    myControl1.Visible = False  
  
    ```  
  
    ```csharp  
    // To set the Visible property from within your object's own code.  
    this.Visible = false;  
    // To set the Visible property from another object.  
    myControl1.Visible = false;  
  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.Control.Visible%2A>   
 [Desarrollar controles personalizados de formularios Windows Forms con .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)   
 [Cómo: Proporcionar un fondo transparente a un control](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)