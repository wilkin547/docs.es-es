---
title: "Help Systems in Windows Forms Applications | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Help, adding to Windows applications"
  - "Windows applications, providing Help systems"
  - "What's This? Help"
  - "Help, Windows Forms"
  - "HelpProvider component [Windows Forms], providing Help in Windows applications"
ms.assetid: 2a96a278-432c-41fc-9e3c-5bfedf5e1267
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Help Systems in Windows Forms Applications
Una de las ventajas más importantes que un programador de aplicaciones puede ofrecer a los usuarios es un sistema de Ayuda eficaz.  Será su referencia cuando estén confundidos o desorientados.  Proporcionar un sistema de Ayuda en una aplicación basada en Windows se realiza de forma muy sencilla con el formulario [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md).  
  
## Diferentes tipos de Ayuda  
 El componente <xref:System.Windows.Forms.HelpProvider> del formulario Windows Forms se utiliza para asociar un archivo de Ayuda HTML Help 1.x \(ya sea un archivo .chm, generado con HTML Help Workshop, o con un archivo .htm\) con su aplicación basada en Windows.  El componente <xref:System.Windows.Forms.HelpProvider> se puede utilizar para proporcionar Ayuda contextual a controles en los formularios Windows Forms o a controles específicos.  Además, el componente <xref:System.Windows.Forms.HelpProvider> puede abrir un archivo de Ayuda en áreas específicas, como la página principal de una tabla de contenido, un índice o una función de búsqueda.  Para obtener información general sobre el componente <xref:System.Windows.Forms.HelpProvider>, vea [Información general sobre el componente HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-overview-windows-forms.md).  Para obtener más información sobre cómo se usa el componente <xref:System.Windows.Forms.HelpProvider> para mostrar Ayuda emergente en los formularios Windows Forms, vea [Cómo: Mostrar ayuda emergente](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md).  Para obtener información sobre cómo usar el componente <xref:System.Windows.Forms.ToolTip> para mostrar Ayuda específica del control, vea [Controlar la ayuda mediante información sobre herramientas](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md).  
  
 Se puede generar archivos HTML Help 1.x con HTML Help Workshop.  Para obtener más información sobre la Ayuda HTML, vea el tema "HTML Help Workshop" u otros temas sobre "HTML Help" en MSDN.  
  
## Vea también  
 [Integrar la Ayuda de usuario en formularios Windows Forms](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)   
 [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md)   
 [ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)   
 [Información general sobre formularios Windows Forms](../../../../docs/framework/winforms/windows-forms-overview.md)   
 [Windows Forms](../../../../docs/framework/winforms/index.md)