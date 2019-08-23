---
title: Procedimiento para determinar qué tecla modificadora se ha presionado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboard input
- shift keys
- events [Windows Forms], mouse
- Keys.ControlKey enumeration member
- keys [Windows Forms], control keys
- user input [Windows Forms], checking for keyboard
- keys [Windows Forms], determining last pressed
- keys [Windows Forms], shift keys
- keys [Windows Forms], modifier keys
- control keys
- keys [Windows Forms], alt keys
- alt keys
- Keys.Shift enumeration member
- events [Windows Forms], keyboard
- keyboards [Windows Forms], keyboard input
- Keys.Alt enumeration member
- modifier keys
ms.assetid: 1e184048-0ae3-4067-a200-d4ba31dbc2cb
ms.openlocfilehash: 37fa897f5a2e1c65cbd5db9189f1500e3427c920
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964312"
---
# <a name="how-to-determine-which-modifier-key-was-pressed"></a>Procedimiento para determinar qué tecla modificadora se ha presionado
Cuando cree una aplicación que acepte las pulsaciones de teclas del usuario, puede que también desee supervisar las teclas modificadoras como las teclas Mayús, ALT y CTRL. Cuando se presiona una tecla modificadora junto con otras teclas o con clics del mouse, la aplicación puede responder adecuadamente. Por ejemplo, si se presiona la letra S, esto puede dar lugar simplemente a que aparezca una "S" en la pantalla, pero si se presionan las teclas CTRL + S, se puede guardar el documento actual. Si controla el <xref:System.Windows.Forms.Control.KeyDown> evento, la <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> propiedad del <xref:System.Windows.Forms.KeyEventArgs> recibido por el controlador de eventos especifica qué teclas modificadoras se presionan. Como alternativa, la <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> propiedad de <xref:System.Windows.Forms.KeyEventArgs> especifica el carácter que se presionó, así como cualquier tecla modificadora combinada con una operación OR bit a bit. Sin embargo, si está controlando <xref:System.Windows.Forms.Control.KeyPress> el evento o un evento del mouse, el controlador de eventos no recibe esta información. En este caso, debe utilizar la <xref:System.Windows.Forms.Control.ModifierKeys%2A> propiedad de la <xref:System.Windows.Forms.Control> clase. En cualquier caso, debe realizar una operación and bit a bit del <xref:System.Windows.Forms.Keys> valor adecuado y el valor que se está probando. La <xref:System.Windows.Forms.Keys> enumeración ofrece variaciones de cada tecla modificadora, por lo que es importante que realice la operación and bit a bit con el valor correcto. Por ejemplo, la tecla Mayús se representa mediante <xref:System.Windows.Forms.Keys.Shift> <xref:System.Windows.Forms.Keys.RShiftKey> , <xref:System.Windows.Forms.Keys.ShiftKey>y <xref:System.Windows.Forms.Keys.LShiftKey> el valor correcto para probar Shift como una tecla modificadora es <xref:System.Windows.Forms.Keys.Shift>. Del mismo modo, para probar Ctrl y Alt como modificadores, debe utilizar <xref:System.Windows.Forms.Keys.Control> los <xref:System.Windows.Forms.Keys.Alt> valores y, respectivamente.  
  
> [!NOTE]
> Visual Basic los programadores también pueden tener acceso a la <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> información clave a través de la propiedad  
  
### <a name="to-determine-which-modifier-key-was-pressed"></a>Para determinar qué tecla modificadora se presionó  
  
- Use el operador `AND` bit a bit <xref:System.Windows.Forms.Control.ModifierKeys%2A> con la propiedad y un valor <xref:System.Windows.Forms.Keys> de la enumeración para determinar si se ha presionado una tecla modificadora determinada. En el ejemplo de código siguiente se muestra cómo determinar si la tecla Mayús se presiona <xref:System.Windows.Forms.Control.KeyPress> dentro de un controlador de eventos.  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.ModifierKeys%2A>
- [Entradas mediante teclado en una aplicación de Windows Forms](keyboard-input-in-a-windows-forms-application.md)
- [Procedimientos: Determinar si Bloq Mayús está activado en Visual Basic](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9c9d1fz9(v=vs.100))
