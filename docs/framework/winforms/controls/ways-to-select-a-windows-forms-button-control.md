---
title: "Maneras de seleccionar un control Button de formularios Windows Forms | Microsoft Docs"
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
  - "control de botón [Windows Forms], seleccionar"
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Maneras de seleccionar un control Button de formularios Windows Forms
Puede seleccionar un botón de formularios Windows Forms de las siguientes maneras:  
  
-   Utilice el mouse para hacer clic en el botón.  
  
-   Invoque el evento <xref:System.Windows.Forms.Control.Click> del botón desde el código.  
  
-   Presione la tecla TABULADOR para desplazar el foco al botón y, a continuación, presione la tecla BARRA ESPACIADORA o ENTRAR para elegirlo.  
  
-   Presione la tecla de acceso \(ALT \+ la letra subrayada\) del botón.  Para obtener más información sobre las teclas de acceso, vea [Cómo: Crear teclas de acceso para controles de Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).  
  
-   Si se trata del botón "aceptar" del formulario, al presionar la tecla ENTRAR, se elige el botón, aunque otro control tenga el foco \(excepto si ese control es otro botón, un cuadro de texto de varias líneas o un control personalizado que acapara la tecla Entrar\).  
  
-   Si se trata del botón "Cancelar" del formulario, al presionar la tecla ESC se elegirá el botón aunque otro control tenga el foco.  
  
-   Llame al método <xref:System.Windows.Forms.Button.PerformClick%2A> para seleccionar el botón mediante programación.  
  
## Vea también  
 [Información general sobre el control Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)   
 [Cómo: Responder a clics de botones en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)   
 [Button \(Control\)](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)