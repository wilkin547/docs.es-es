---
title: "Controlar la introducción de datos por el usuario"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user input using code
- custom controls [Windows Forms], keyboard events using code
- custom controls [Windows Forms], mouse events using code
ms.assetid: d9b12787-86f6-4022-8e0f-e12d312c4af2
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7c3da2c4661acdb358c38fb871de70fd470f7991
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="handling-user-input"></a>Controlar la introducción de datos por el usuario
En este tema se describe los principales eventos de teclado y mouse (ratón) proporcionados por <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. Al controlar un evento, los creadores de controles deben reemplazar el método `On`*EventName* protegido en lugar de asociar un delegado al evento. Para hacer un repaso de los eventos, vea [Provocar eventos de un componente](http://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0).  
  
> [!NOTE]
>  Si no hay ningún dato asociado a un evento, una instancia de la clase base <xref:System.EventArgs> se pasa como argumento a la `On` *EventName* método.  
  
## <a name="keyboard-events"></a>Eventos de teclado  
 Los eventos de teclado habituales que pueden controlar son <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress>, y <xref:System.Windows.Forms.Control.KeyUp>.  
  
|Nombre de evento|Método que se va a invalidar|Descripción del evento|  
|----------------|------------------------|--------------------------|  
|`KeyDown`|`void OnKeyDown(KeyEventArgs)`|Se produce únicamente cuando se presiona una tecla por primera vez.|  
|`KeyPress`|`void OnKeyPress`<br /><br /> `(KeyPressEventArgs)`|Se produce cada vez que se presiona una tecla. Si está presionada una tecla, un <xref:System.Windows.Forms.Control.KeyPress> evento se desencadena en la velocidad de repetición definida por el sistema operativo.|  
|`KeyUp`|`void OnKeyUp(KeyEventArgs)`|Se produce cuando se suelta una tecla.|  
  
> [!NOTE]
>  Controlar la entrada mediante teclado es mucho más complejo que invalidar los eventos de la tabla anterior y escapa al ámbito de este tema. Para más información, consulte [Datos proporcionados por el usuario en Windows Forms](../../../../docs/framework/winforms/user-input-in-windows-forms.md).  
  
## <a name="mouse-events"></a>Eventos del mouse  
 Los eventos de mouse (ratón) que se pueden controlar son <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove>, y <xref:System.Windows.Forms.Control.MouseUp>.  
  
|Nombre de evento|Método que se va a invalidar|Descripción del evento|  
|----------------|------------------------|--------------------------|  
|`MouseDown`|`void OnMouseDown(MouseEventArgs)`|Se produce cuando se presiona un botón del mouse mientras el puntero del mouse está sobre el control.|  
|`MouseEnter`|`void OnMouseEnter(EventArgs)`|Se produce cuando el cursor del mouse entra por primera vez en la zona del control.|  
|`MouseHover`|`void OnMouseHover(EventArgs)`|Se produce cuando el puntero pasa por encima del control.|  
|`MouseLeave`|`void OnMouseLeave(EventArgs)`|Se produce cuando el puntero sale de la zona del control.|  
|`MouseMove`|`void OnMouseMove(MouseEventArgs)`|Se produce cuando el puntero se desplaza por la zona del control.|  
|`MouseUp`|`void OnMouseUp(MouseEventArgs)`|Se produce cuando se suelta el botón del mouse mientras el puntero está encima del control o sale de la zona del control.|  
  
 El fragmento de código siguiente muestra un ejemplo de cómo reemplazar el <xref:System.Windows.Forms.Control.MouseDown> eventos.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#7)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#7)]  
  
 El fragmento de código siguiente muestra un ejemplo de cómo reemplazar el <xref:System.Windows.Forms.Control.MouseMove> eventos.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#8)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#8)]  
  
 El fragmento de código siguiente muestra un ejemplo de cómo reemplazar el <xref:System.Windows.Forms.Control.MouseUp> eventos.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#9)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#9)]  
  
 Para obtener el código fuente completo del ejemplo `FlashTrackBar`, vea [Crear un control de Windows Forms que muestre el progreso](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
## <a name="see-also"></a>Vea también  
 [Eventos de los controles de Windows Forms](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)  
 [Definir un evento en los controles de Windows Forms](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)  
 [Eventos](../../../../docs/standard/events/index.md)  
 [Datos proporcionados por el usuario en Windows Forms](../../../../docs/framework/winforms/user-input-in-windows-forms.md)
