---
title: "Controlar la introducci&#243;n de datos por el usuario | Microsoft Docs"
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
  - "controles personalizados [Windows Forms], eventos de teclado mediante código"
  - "controles personalizados [Windows Forms], eventos del mouse mediante código"
  - "controles personalizados [Windows Forms], entrada de usuario mediante código"
ms.assetid: d9b12787-86f6-4022-8e0f-e12d312c4af2
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Controlar la introducci&#243;n de datos por el usuario
En este tema se describen los principales eventos de teclado y mouse proporcionados por <xref:System.Windows.Forms.Control?displayProperty=fullName>.  Al controlar un evento, los creadores de controles deben invalidar el método `On`*nombreDeEvento* protegido en lugar de asociar un delegado al evento.  Para hacer un repaso de los eventos, vea [Raising Events from a Component](../Topic/Raising%20Events%20from%20a%20Component.md).  
  
> [!NOTE]
>  Si no existen datos asociados a un evento, se pasa una instancia de la clase base <xref:System.EventArgs> como argumento al método `On`*nombreDeEvento*.  
  
## Eventos de teclado  
 Los eventos de teclado habituales que se pueden controlar son <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress> y <xref:System.Windows.Forms.Control.KeyUp>.  
  
|Nombre del evento|Método que se va a reemplazar|Descripción del evento|  
|-----------------------|-----------------------------------|----------------------------|  
|`KeyDown`|`void OnKeyDown(KeyEventArgs)`|Se produce únicamente cuando se presiona una tecla por primera vez.|  
|`KeyPress`|`void OnKeyPress`<br /><br /> `(KeyPressEventArgs)`|Se produce cada vez que se presiona una tecla.  Si la tecla se mantiene presionada, se produce un evento <xref:System.Windows.Forms.Control.KeyPress> a la velocidad de repetición definida por el sistema operativo.|  
|`KeyUp`|`void OnKeyUp(KeyEventArgs)`|Se produce cuando se suelta una tecla.|  
  
> [!NOTE]
>  Controlar la entrada de datos desde teclado es mucho más complejo que reemplazar los eventos de la tabla anterior y escapa al ámbito de este tema.  Para obtener más información, vea [User Input in Windows Forms](../../../../docs/framework/winforms/user-input-in-windows-forms.md).  
  
## Eventos del mouse  
 Los eventos del mouse que puede controlar el control son <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove> y <xref:System.Windows.Forms.Control.MouseUp>.  
  
|Nombre del evento|Método que se va a reemplazar|Descripción del evento|  
|-----------------------|-----------------------------------|----------------------------|  
|`MouseDown`|`void OnMouseDown(MouseEventArgs)`|Se produce cuando se presiona un botón del mouse mientras el puntero del mouse está sobre el control.|  
|`MouseEnter`|`void OnMouseEnter(EventArgs)`|Se produce cuando el cursor del mouse entra por primera vez en la zona del control.|  
|`MouseHover`|`void OnMouseHover(EventArgs)`|Se produce cuando el puntero se mantiene por encima del control.|  
|`MouseLeave`|`void OnMouseLeave(EventArgs)`|Se produce cuando el puntero sale de la zona del control.|  
|`MouseMove`|`void OnMouseMove(MouseEventArgs)`|Se produce cuando el puntero se mantiene por la zona del control.|  
|`MouseUp`|`void OnMouseUp(MouseEventArgs)`|Se produce cuando se suelta el botón del mouse mientras el puntero está encima del control o sale de la zona del control.|  
  
 En el siguiente fragmento de código se muestra un ejemplo de cómo reemplazar el evento <xref:System.Windows.Forms.Control.MouseDown>.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#7)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#7)]  
  
 En el siguiente fragmento de código se muestra un ejemplo de cómo reemplazar el evento <xref:System.Windows.Forms.Control.MouseMove>.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#8)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#8)]  
  
 En el siguiente fragmento de código se muestra un ejemplo de cómo reemplazar el evento <xref:System.Windows.Forms.Control.MouseUp>.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#9)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#9)]  
  
 Para obtener el código fuente completo del ejemplo `FlashTrackBar`, vea [Cómo: Crear un control de formularios Windows Forms que muestre el progreso](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
## Vea también  
 [Eventos de los controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)   
 [Definir un evento en los controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)   
 [Eventos](../../../../docs/standard/events/index.md)   
 [User Input in Windows Forms](../../../../docs/framework/winforms/user-input-in-windows-forms.md)