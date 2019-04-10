---
title: Filtrar para determinar qué tecla modificadora se ha presionado
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
ms.openlocfilehash: 571af49cdf82b876cfb72a7c7636874c8d155fb7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213941"
---
# <a name="how-to-determine-which-modifier-key-was-pressed"></a><span data-ttu-id="27d93-102">Filtrar para determinar qué tecla modificadora se ha presionado</span><span class="sxs-lookup"><span data-stu-id="27d93-102">How to: Determine Which Modifier Key Was Pressed</span></span>
<span data-ttu-id="27d93-103">Cuando se crea una aplicación que acepte las pulsaciones del usuario, también puede supervisar las teclas modificadoras como las teclas MAYÚS, ALT y CTRL.</span><span class="sxs-lookup"><span data-stu-id="27d93-103">When you create an application that accepts the user's keystrokes, you may also want to monitor for modifier keys such as the SHIFT, ALT, and CTRL keys.</span></span> <span data-ttu-id="27d93-104">Cuando se presiona una tecla modificadora en combinación con otras claves, o con clics del mouse, la aplicación puede responder adecuadamente.</span><span class="sxs-lookup"><span data-stu-id="27d93-104">When a modifier key is pressed in combination with other keys, or with mouse clicks, your application can respond appropriately.</span></span> <span data-ttu-id="27d93-105">Por ejemplo, si se presiona la letra S, simplemente puede provocar una "s" en la pantalla, pero si se presionan las teclas CTRL + S, es posible que se puede guardar el documento actual.</span><span class="sxs-lookup"><span data-stu-id="27d93-105">For example, if the letter S is pressed, this may simply cause an "s" to appear on the screen, but if the keys CTRL+S are pressed, the current document may be saved.</span></span> <span data-ttu-id="27d93-106">Si controla el <xref:System.Windows.Forms.Control.KeyDown> eventos, el <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> propiedad de la <xref:System.Windows.Forms.KeyEventArgs> recibidos por el evento de controlador especifica se presionan las teclas modificadoras que.</span><span class="sxs-lookup"><span data-stu-id="27d93-106">If you handle the <xref:System.Windows.Forms.Control.KeyDown> event, the <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> property of the <xref:System.Windows.Forms.KeyEventArgs> received by the event handler specifies which modifier keys are pressed.</span></span> <span data-ttu-id="27d93-107">Como alternativa, el <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> propiedad de <xref:System.Windows.Forms.KeyEventArgs> especifica el carácter que se presionó, así como las teclas modificadoras que se combina con una operación OR bit a bit.</span><span class="sxs-lookup"><span data-stu-id="27d93-107">Alternatively, the <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> property of <xref:System.Windows.Forms.KeyEventArgs> specifies the character that was pressed as well as any modifier keys combined with a bitwise OR.</span></span> <span data-ttu-id="27d93-108">Sin embargo, si está controlando el <xref:System.Windows.Forms.Control.KeyPress> evento o un evento del mouse, el controlador de eventos no recibe esta información.</span><span class="sxs-lookup"><span data-stu-id="27d93-108">However, if you are handling the <xref:System.Windows.Forms.Control.KeyPress> event or a mouse event, the event handler does not receive this information.</span></span> <span data-ttu-id="27d93-109">En este caso, debe usar el <xref:System.Windows.Forms.Control.ModifierKeys%2A> propiedad de la <xref:System.Windows.Forms.Control> clase.</span><span class="sxs-lookup"><span data-stu-id="27d93-109">In this case, you must use the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property of the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="27d93-110">En cualquier caso, debe realizar una operación AND bit a bit de adecuado <xref:System.Windows.Forms.Keys> valor y el valor que se está probando.</span><span class="sxs-lookup"><span data-stu-id="27d93-110">In either case, you must perform a bitwise AND of the appropriate <xref:System.Windows.Forms.Keys> value and the value you are testing.</span></span> <span data-ttu-id="27d93-111">El <xref:System.Windows.Forms.Keys> enumeración ofrece las variaciones de cada clave de modificador, por lo que es importante que realice el bit a bit y con el valor correcto.</span><span class="sxs-lookup"><span data-stu-id="27d93-111">The <xref:System.Windows.Forms.Keys> enumeration offers variations of each modifier key, so it is important that you perform the bitwise AND with the correct value.</span></span> <span data-ttu-id="27d93-112">Por ejemplo, la tecla MAYÚS está representado por <xref:System.Windows.Forms.Keys.Shift>, <xref:System.Windows.Forms.Keys.ShiftKey>, <xref:System.Windows.Forms.Keys.RShiftKey> y <xref:System.Windows.Forms.Keys.LShiftKey> el valor correcto para probar la ya es una tecla modificadora MAYÚS <xref:System.Windows.Forms.Keys.Shift>.</span><span class="sxs-lookup"><span data-stu-id="27d93-112">For example, the SHIFT key is represented by <xref:System.Windows.Forms.Keys.Shift>, <xref:System.Windows.Forms.Keys.ShiftKey>, <xref:System.Windows.Forms.Keys.RShiftKey> and <xref:System.Windows.Forms.Keys.LShiftKey> The correct value to test SHIFT as a modifier key is <xref:System.Windows.Forms.Keys.Shift>.</span></span> <span data-ttu-id="27d93-113">De forma similar, debe usar probar para CTRL y ALT como modificadores del <xref:System.Windows.Forms.Keys.Control> y <xref:System.Windows.Forms.Keys.Alt> valores, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="27d93-113">Similarly, to test for CTRL and ALT as modifiers you should use the <xref:System.Windows.Forms.Keys.Control> and <xref:System.Windows.Forms.Keys.Alt> values, respectively.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="27d93-114">Los programadores de Visual Basic también pueden acceder a información clave a través de la <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> propiedad</span><span class="sxs-lookup"><span data-stu-id="27d93-114">Visual Basic programmers can also access key information through the <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> property</span></span>  
  
### <a name="to-determine-which-modifier-key-was-pressed"></a><span data-ttu-id="27d93-115">Para determinar qué tecla modificadora se presionó</span><span class="sxs-lookup"><span data-stu-id="27d93-115">To determine which modifier key was pressed</span></span>  
  
-   <span data-ttu-id="27d93-116">Utilice el bit a bit `AND` operador con el <xref:System.Windows.Forms.Control.ModifierKeys%2A> propiedad y un valor de la <xref:System.Windows.Forms.Keys> enumeración para determinar si se presiona una tecla modificadora determinada.</span><span class="sxs-lookup"><span data-stu-id="27d93-116">Use the bitwise `AND` operator with the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property and a value of the <xref:System.Windows.Forms.Keys> enumeration to determine whether a particular modifier key is pressed.</span></span> <span data-ttu-id="27d93-117">El ejemplo de código siguiente muestra cómo determinar si se presiona la tecla MAYÚS dentro de un <xref:System.Windows.Forms.Control.KeyPress> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="27d93-117">The following code example shows how to determine whether the SHIFT key is pressed within a <xref:System.Windows.Forms.Control.KeyPress> event handler.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="27d93-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="27d93-118">See also</span></span>

- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.ModifierKeys%2A>
- [<span data-ttu-id="27d93-119">Entradas mediante teclado en una aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="27d93-119">Keyboard Input in a Windows Forms Application</span></span>](keyboard-input-in-a-windows-forms-application.md)
- [<span data-ttu-id="27d93-120">Filtrar Determinar que si BLOQ MAYÚS está activado en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="27d93-120">How to: Determine If CapsLock is On in Visual Basic</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9c9d1fz9(v=vs.100))
