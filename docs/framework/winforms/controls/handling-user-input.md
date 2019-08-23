---
title: Controlar la introducción de datos por el usuario
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user input using code
- custom controls [Windows Forms], keyboard events using code
- custom controls [Windows Forms], mouse events using code
ms.assetid: d9b12787-86f6-4022-8e0f-e12d312c4af2
ms.openlocfilehash: f92b742c3f6feec72e5b3150204d7d984636281d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934087"
---
# <a name="handling-user-input"></a>Controlar la introducción de datos por el usuario
En este tema se describen los eventos principales del teclado y <xref:System.Windows.Forms.Control?displayProperty=nameWithType>del mouse proporcionados por. Al controlar un evento, los creadores de controles deben reemplazar el método `On`*EventName* protegido en lugar de asociar un delegado al evento. Para hacer un repaso de los eventos, vea [Provocar eventos de un componente](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).  
  
> [!NOTE]
> Si no hay ningún dato asociado a un evento, se pasa una instancia de la <xref:System.EventArgs> clase base como argumento `On`al método *eventName* .  
  
## <a name="keyboard-events"></a>Eventos de teclado  
 Los eventos de teclado comunes que el control puede controlar <xref:System.Windows.Forms.Control.KeyDown>son <xref:System.Windows.Forms.Control.KeyPress>, y <xref:System.Windows.Forms.Control.KeyUp>.  
  
|Nombre de evento|Método que se va a invalidar|Descripción del evento|  
|----------------|------------------------|--------------------------|  
|`KeyDown`|`void OnKeyDown(KeyEventArgs)`|Se produce únicamente cuando se presiona una tecla por primera vez.|  
|`KeyPress`|`void OnKeyPress`<br /><br /> `(KeyPressEventArgs)`|Se produce cada vez que se presiona una tecla. Si se mantiene presionada una tecla, <xref:System.Windows.Forms.Control.KeyPress> se genera un evento con la frecuencia de repetición definida por el sistema operativo.|  
|`KeyUp`|`void OnKeyUp(KeyEventArgs)`|Se produce cuando se suelta una tecla.|  
  
> [!NOTE]
> Controlar la entrada mediante teclado es mucho más complejo que invalidar los eventos de la tabla anterior y escapa al ámbito de este tema. Para más información, consulte [Datos proporcionados por el usuario en Windows Forms](../user-input-in-windows-forms.md).  
  
## <a name="mouse-events"></a>Eventos del mouse  
 Los eventos del mouse que el control puede controlar <xref:System.Windows.Forms.Control.MouseDown>son <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove>, y <xref:System.Windows.Forms.Control.MouseUp>.  
  
|Nombre de evento|Método que se va a invalidar|Descripción del evento|  
|----------------|------------------------|--------------------------|  
|`MouseDown`|`void OnMouseDown(MouseEventArgs)`|Se produce cuando se presiona un botón del mouse mientras el puntero del mouse está sobre el control.|  
|`MouseEnter`|`void OnMouseEnter(EventArgs)`|Se produce cuando el cursor del mouse entra por primera vez en la zona del control.|  
|`MouseHover`|`void OnMouseHover(EventArgs)`|Se produce cuando el puntero pasa por encima del control.|  
|`MouseLeave`|`void OnMouseLeave(EventArgs)`|Se produce cuando el puntero sale de la zona del control.|  
|`MouseMove`|`void OnMouseMove(MouseEventArgs)`|Se produce cuando el puntero se desplaza por la zona del control.|  
|`MouseUp`|`void OnMouseUp(MouseEventArgs)`|Se produce cuando se suelta el botón del mouse mientras el puntero está encima del control o sale de la zona del control.|  
  
 En el fragmento de código siguiente se muestra un ejemplo de <xref:System.Windows.Forms.Control.MouseDown> cómo invalidar el evento.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#7)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#7)]  
  
 En el fragmento de código siguiente se muestra un ejemplo de <xref:System.Windows.Forms.Control.MouseMove> cómo invalidar el evento.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#8)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#8)]  
  
 En el fragmento de código siguiente se muestra un ejemplo de <xref:System.Windows.Forms.Control.MouseUp> cómo invalidar el evento.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#9)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#9)]  
  
 Para obtener el código `FlashTrackBar` fuente completo del ejemplo, consulte [cómo: Cree un control de Windows Forms que muestre](how-to-create-a-windows-forms-control-that-shows-progress.md)el progreso.  
  
## <a name="see-also"></a>Vea también

- [Eventos de los controles de Windows Forms](events-in-windows-forms-controls.md)
- [Definir un evento en los controles de Windows Forms](defining-an-event-in-windows-forms-controls.md)
- [Eventos](../../../standard/events/index.md)
- [Datos proporcionados por el usuario en Windows Forms](../user-input-in-windows-forms.md)
