---
title: "C&#243;mo: Definir un bot&#243;n de formularios Windows Forms como el bot&#243;n Cancelar | Microsoft Docs"
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
  - "control de botón [Windows Forms], designar como botón para cancelar"
  - "botones, botones para cancelar"
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Definir un bot&#243;n de formularios Windows Forms como el bot&#243;n Cancelar
En cualquier Windows Form, se puede designar un control <xref:System.Windows.Forms.Button> como el botón que se utiliza para cancelar.  Siempre que el usuario presione la tecla ESC hará clic en el botón para cancelar, independientemente del control del formulario que tenga el foco.  Habitualmente, este botón se programa para permitir que el usuario salga rápidamente de una operación sin confirmar ninguna acción.  
  
### Para designar el botón para cancelar  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.Form.CancelButton%2A> en el control <xref:System.Windows.Forms.Button> apropiado.  
  
    ```vb  
    Private Sub SetCancelButton(ByVal myCancelBtn As Button)  
       Me.CancelButton = myCancelBtn  
    End Sub  
    ```  
  
    ```csharp  
    private void SetCancelButton(Button myCancelBtn)  
    {  
       this.CancelButton = myCancelBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetCancelButton(Button ^ myCancelBtn)  
       {  
          this->CancelButton = myCancelBtn;  
       }  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.Form.CancelButton%2A>   
 [Información general sobre el control Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)   
 [Maneras de seleccionar un control Button de formularios Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)   
 [Cómo: Responder a clics de botones en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)   
 [Cómo: Designar un botón de formularios Windows Forms como botón para aceptar](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-accept-button.md)   
 [Button \(Control\)](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)