---
title: 'Cómo: Determinar qué tecla modificadora se presionó'
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
ms.openlocfilehash: f73dea640bc2059353b2a250188b901f360ea750
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44202042"
---
# <a name="how-to-determine-which-modifier-key-was-pressed"></a>Cómo: Determinar qué tecla modificadora se presionó
Cuando se crea una aplicación que acepte las pulsaciones del usuario, también puede supervisar las teclas modificadoras como las teclas MAYÚS, ALT y CTRL. Cuando se presiona una tecla modificadora en combinación con otras claves, o con clics del mouse, la aplicación puede responder adecuadamente. Por ejemplo, si se presiona la letra S, simplemente puede provocar una "s" en la pantalla, pero si se presionan las teclas CTRL + S, es posible que se puede guardar el documento actual. Si controla el <xref:System.Windows.Forms.Control.KeyDown> eventos, el <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> propiedad de la <xref:System.Windows.Forms.KeyEventArgs> recibidos por el evento de controlador especifica se presionan las teclas modificadoras que. Como alternativa, el <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> propiedad de <xref:System.Windows.Forms.KeyEventArgs> especifica el carácter que se presionó, así como las teclas modificadoras que se combina con una operación OR bit a bit. Sin embargo, si está controlando el <xref:System.Windows.Forms.Control.KeyPress> evento o un evento del mouse, el controlador de eventos no recibe esta información. En este caso, debe usar el <xref:System.Windows.Forms.Control.ModifierKeys%2A> propiedad de la <xref:System.Windows.Forms.Control> clase. En cualquier caso, debe realizar una operación AND bit a bit de adecuado <xref:System.Windows.Forms.Keys> valor y el valor que se está probando. El <xref:System.Windows.Forms.Keys> enumeración ofrece las variaciones de cada clave de modificador, por lo que es importante que realice el bit a bit y con el valor correcto. Por ejemplo, la tecla MAYÚS está representado por <xref:System.Windows.Forms.Keys.Shift>, <xref:System.Windows.Forms.Keys.ShiftKey>, <xref:System.Windows.Forms.Keys.RShiftKey> y <xref:System.Windows.Forms.Keys.LShiftKey> el valor correcto para probar la ya es una tecla modificadora MAYÚS <xref:System.Windows.Forms.Keys.Shift>. De forma similar, debe usar probar para CTRL y ALT como modificadores del <xref:System.Windows.Forms.Keys.Control> y <xref:System.Windows.Forms.Keys.Alt> valores, respectivamente.  
  
> [!NOTE]
>  Los programadores de Visual Basic también pueden acceder a información clave a través de la <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> propiedad  
  
### <a name="to-determine-which-modifier-key-was-pressed"></a>Para determinar qué tecla modificadora se presionó  
  
-   Utilice el bit a bit `AND` operador con el <xref:System.Windows.Forms.Control.ModifierKeys%2A> propiedad y un valor de la <xref:System.Windows.Forms.Keys> enumeración para determinar si se presiona una tecla modificadora determinada. El ejemplo de código siguiente muestra cómo determinar si se presiona la tecla MAYÚS dentro de un <xref:System.Windows.Forms.Control.KeyPress> controlador de eventos.  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Keys>  
 <xref:System.Windows.Forms.Control.ModifierKeys%2A>  
 [Entradas mediante teclado en una aplicación de Windows Forms](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)  
 [Cómo: determinar si BLOQ MAYÚS está activado en Visual Basic](https://msdn.microsoft.com/library/91e60f5c-dd61-4222-ba5f-39af803afd8c)
