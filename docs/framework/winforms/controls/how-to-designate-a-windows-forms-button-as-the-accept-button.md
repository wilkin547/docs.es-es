---
title: "C&#243;mo: Designar un bot&#243;n de formularios Windows Forms como bot&#243;n para aceptar | Microsoft Docs"
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
  - "Aceptar (botón de Windows Forms)"
  - "control de botón [Windows Forms], designar como predeterminado"
  - "botones, predeterminados en formularios Windows Forms"
  - "controles de Windows Forms, botón predeterminado en un formulario"
ms.assetid: 22cc9da6-b913-4e04-9554-dee443ac5c3a
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Designar un bot&#243;n de formularios Windows Forms como bot&#243;n para aceptar
En cualquier Windows Form, se puede designar un control <xref:System.Windows.Forms.Button> como el botón que se utiliza para aceptar, también conocido como botón predeterminado.  Siempre que el usuario presione la tecla ENTRAR hará clic en el botón predeterminado, independientemente del control del formulario que tenga el foco.  
  
> [!NOTE]
>  La excepción a esta regla se da cuando el control con el foco es otro botón \(en ese caso, se presionará el botón con el foco\) o un cuadro de texto de varias líneas o un control personalizado que acapare la tecla ENTRAR.  
  
### Para designar el botón de aceptar  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.Form.AcceptButton%2A> del formulario en el control <xref:System.Windows.Forms.Button> adecuado.  
  
    ```vb  
    Private Sub SetDefault(ByVal myDefaultBtn As Button)  
      Me.AcceptButton = myDefaultBtn   
    End Sub  
    ```  
  
    ```csharp  
    private void SetDefault(Button myDefaultBtn)  
    {  
       this.AcceptButton = myDefaultBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetDefault(Button ^ myDefaultBtn)  
       {  
          this->AcceptButton = myDefaultBtn;  
       }  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.Form.AcceptButton%2A>   
 [Información general sobre el control Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)   
 [Maneras de seleccionar un control Button de formularios Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)   
 [Cómo: Responder a clics de botones en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)   
 [Cómo: Definir un botón de formularios Windows Forms como el botón Cancelar](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-cancel-button.md)   
 [Button \(Control\)](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)