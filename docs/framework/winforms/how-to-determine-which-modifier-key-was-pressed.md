---
title: "Cómo: Determinar qué tecla modificadora se presionó"
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
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d5f749d22c09d166e81ea08068f760f24960ec83
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-determine-which-modifier-key-was-pressed"></a><span data-ttu-id="90ef3-102">Cómo: Determinar qué tecla modificadora se presionó</span><span class="sxs-lookup"><span data-stu-id="90ef3-102">How to: Determine Which Modifier Key Was Pressed</span></span>
<span data-ttu-id="90ef3-103">Cuando se crea una aplicación que acepte pulsaciones de teclas del usuario, también puede supervisar las teclas modificadoras como las teclas MAYÚS, ALT y CTRL.</span><span class="sxs-lookup"><span data-stu-id="90ef3-103">When you create an application that accepts the user's keystrokes, you may also want to monitor for modifier keys such as the SHIFT, ALT, and CTRL keys.</span></span> <span data-ttu-id="90ef3-104">Cuando se presiona una tecla modificadora en combinación con otras teclas o con clics del mouse, la aplicación pueda responder correctamente.</span><span class="sxs-lookup"><span data-stu-id="90ef3-104">When a modifier key is pressed in combination with other keys, or with mouse clicks, your application can respond appropriately.</span></span> <span data-ttu-id="90ef3-105">Por ejemplo, si se presiona la letra S, esto puede hacer simplemente una "s" en la pantalla, pero si se presionan las teclas CTRL + S, se puede guardar el documento actual.</span><span class="sxs-lookup"><span data-stu-id="90ef3-105">For example, if the letter S is pressed, this may simply cause an "s" to appear on the screen, but if the keys CTRL+S are pressed, the current document may be saved.</span></span> <span data-ttu-id="90ef3-106">Si controla el <xref:System.Windows.Forms.Control.KeyDown> eventos, el <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> propiedad de la <xref:System.Windows.Forms.KeyEventArgs> recibidos por el evento controlador especifica se presionan las teclas modificadoras.</span><span class="sxs-lookup"><span data-stu-id="90ef3-106">If you handle the <xref:System.Windows.Forms.Control.KeyDown> event, the <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> property of the <xref:System.Windows.Forms.KeyEventArgs> received by the event handler specifies which modifier keys are pressed.</span></span> <span data-ttu-id="90ef3-107">Como alternativa, el <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> propiedad de <xref:System.Windows.Forms.KeyEventArgs> especifica el carácter que se presionó, así como las teclas modificadoras combinadas con una operación OR bit a bit.</span><span class="sxs-lookup"><span data-stu-id="90ef3-107">Alternatively, the <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> property of <xref:System.Windows.Forms.KeyEventArgs> specifies the character that was pressed as well as any modifier keys combined with a bitwise OR.</span></span> <span data-ttu-id="90ef3-108">Sin embargo, si está controlando el <xref:System.Windows.Forms.Control.KeyPress> evento o un evento del mouse, el controlador de eventos no recibe esta información.</span><span class="sxs-lookup"><span data-stu-id="90ef3-108">However, if you are handling the <xref:System.Windows.Forms.Control.KeyPress> event or a mouse event, the event handler does not receive this information.</span></span> <span data-ttu-id="90ef3-109">En este caso, debe usar el <xref:System.Windows.Forms.Control.ModifierKeys%2A> propiedad de la <xref:System.Windows.Forms.Control> clase.</span><span class="sxs-lookup"><span data-stu-id="90ef3-109">In this case, you must use the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property of the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="90ef3-110">En cualquier caso, debe realizar una operación AND bit a bit de los <xref:System.Windows.Forms.Keys> valor y el valor que se va a probar.</span><span class="sxs-lookup"><span data-stu-id="90ef3-110">In either case, you must perform a bitwise AND of the appropriate <xref:System.Windows.Forms.Keys> value and the value you are testing.</span></span> <span data-ttu-id="90ef3-111">El <xref:System.Windows.Forms.Keys> enumeración ofrece las variaciones de cada tecla modificadora, por lo que es importante que lleva a cabo el bit a bit y con el valor correcto.</span><span class="sxs-lookup"><span data-stu-id="90ef3-111">The <xref:System.Windows.Forms.Keys> enumeration offers variations of each modifier key, so it is important that you perform the bitwise AND with the correct value.</span></span> <span data-ttu-id="90ef3-112">Por ejemplo, la tecla MAYÚS se representa por <xref:System.Windows.Forms.Keys.Shift>, <xref:System.Windows.Forms.Keys.ShiftKey>, <xref:System.Windows.Forms.Keys.RShiftKey> y <xref:System.Windows.Forms.Keys.LShiftKey> el valor correcto para probar el desplazamiento como una tecla modificadora es <xref:System.Windows.Forms.Keys.Shift>.</span><span class="sxs-lookup"><span data-stu-id="90ef3-112">For example, the SHIFT key is represented by <xref:System.Windows.Forms.Keys.Shift>, <xref:System.Windows.Forms.Keys.ShiftKey>, <xref:System.Windows.Forms.Keys.RShiftKey> and <xref:System.Windows.Forms.Keys.LShiftKey> The correct value to test SHIFT as a modifier key is <xref:System.Windows.Forms.Keys.Shift>.</span></span> <span data-ttu-id="90ef3-113">De igual forma, debe usar probar para CTRL y ALT como modificadores del <xref:System.Windows.Forms.Keys.Control> y <xref:System.Windows.Forms.Keys.Alt> valores, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="90ef3-113">Similarly, to test for CTLR and ALT as modifiers you should use the <xref:System.Windows.Forms.Keys.Control> and <xref:System.Windows.Forms.Keys.Alt> values, respectively.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="90ef3-114">Los programadores de Visual Basic también pueden acceder a información clave a través de la <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> propiedad</span><span class="sxs-lookup"><span data-stu-id="90ef3-114">Visual Basic programmers can also access key information through the <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> property</span></span>  
  
### <a name="to-determine-which-modifier-key-was-pressed"></a><span data-ttu-id="90ef3-115">Para determinar qué tecla modificadora se presionó</span><span class="sxs-lookup"><span data-stu-id="90ef3-115">To determine which modifier key was pressed</span></span>  
  
-   <span data-ttu-id="90ef3-116">Utilice el bit a bit `AND` operador con la <xref:System.Windows.Forms.Control.ModifierKeys%2A> propiedad y un valor de la <xref:System.Windows.Forms.Keys> enumeración para determinar si se presiona una tecla modificadora determinada.</span><span class="sxs-lookup"><span data-stu-id="90ef3-116">Use the bitwise `AND` operator with the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property and a value of the <xref:System.Windows.Forms.Keys> enumeration to determine whether a particular modifier key is pressed.</span></span> <span data-ttu-id="90ef3-117">En el ejemplo de código siguiente se muestra cómo determinar si se presionó la tecla MAYÚS dentro de un <xref:System.Windows.Forms.Control.KeyPress> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="90ef3-117">The following code example shows how to determine whether the SHIFT key is pressed within a <xref:System.Windows.Forms.Control.KeyPress> event handler.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="90ef3-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="90ef3-118">See Also</span></span>  
 <xref:System.Windows.Forms.Keys>  
 <xref:System.Windows.Forms.Control.ModifierKeys%2A>  
 [<span data-ttu-id="90ef3-119">Entradas mediante teclado en una aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="90ef3-119">Keyboard Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)  
 [<span data-ttu-id="90ef3-120">Cómo: determinar si CapsLock está activado en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="90ef3-120">How to: Determine If CapsLock is On in Visual Basic</span></span>](http://msdn.microsoft.com/library/91e60f5c-dd61-4222-ba5f-39af803afd8c)
