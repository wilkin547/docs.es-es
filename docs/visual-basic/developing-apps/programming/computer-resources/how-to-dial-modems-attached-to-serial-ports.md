---
title: "Cómo: Marcar a través de módems conectados a puertos serie en Visual Basic"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- modems, dialing
- serial ports, dialing
- My.Computer.Ports object
ms.assetid: 3834db40-f431-45f1-b671-dc91787164b6
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0daaf35cdebac3d69ddc536124d4c86b96955b11
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-dial-modems-attached-to-serial-ports-in-visual-basic"></a><span data-ttu-id="ac077-102">Cómo: Marcar a través de módems conectados a puertos serie en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ac077-102">How to: Dial Modems Attached to Serial Ports in Visual Basic</span></span>
<span data-ttu-id="ac077-103">En este tema se describe cómo usar `My.Computer.Ports` para marcar un módem en [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac077-103">This topic describes how to use `My.Computer.Ports` to dial a modem in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
 <span data-ttu-id="ac077-104">Normalmente, el módem se conecta a uno de los puertos serie del equipo.</span><span class="sxs-lookup"><span data-stu-id="ac077-104">Typically, the modem is connected to one of the serial ports on the computer.</span></span> <span data-ttu-id="ac077-105">Para que la aplicación se comunique con el módem, debe enviar los comandos al puerto serie adecuado.</span><span class="sxs-lookup"><span data-stu-id="ac077-105">For your application to communicate with the modem, it must send commands to the appropriate serial port.</span></span>  
  
### <a name="to-dial-a-modem"></a><span data-ttu-id="ac077-106">Para llamar un módem</span><span class="sxs-lookup"><span data-stu-id="ac077-106">To dial a modem</span></span>  
  
1.  <span data-ttu-id="ac077-107">Determine a qué puerto serie está conectado el módem.</span><span class="sxs-lookup"><span data-stu-id="ac077-107">Determine which serial port the modem is connected to.</span></span> <span data-ttu-id="ac077-108">En este ejemplo se presupone que el módem está en COM1.</span><span class="sxs-lookup"><span data-stu-id="ac077-108">This example assumes the modem is on COM1.</span></span>  
  
2.  <span data-ttu-id="ac077-109">Use el método `My.Computer.Ports.OpenSerialPort` para obtener una referencia al puerto.</span><span class="sxs-lookup"><span data-stu-id="ac077-109">Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port.</span></span> <span data-ttu-id="ac077-110">Para obtener más información, consulta <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span><span class="sxs-lookup"><span data-stu-id="ac077-110">For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span></span>  
  
     <span data-ttu-id="ac077-111">El bloque `Using` permite a la aplicación cerrar el puerto serie aun cuando se genere una excepción.</span><span class="sxs-lookup"><span data-stu-id="ac077-111">The `Using` block allows the application to close the serial port even if it generates an exception.</span></span> <span data-ttu-id="ac077-112">Todo el código que manipula el puerto serie debe aparecer dentro de este bloque o dentro de un bloque `Try...Catch...Finally`.</span><span class="sxs-lookup"><span data-stu-id="ac077-112">All code that manipulates the serial port should appear within this block, or within a `Try...Catch...Finally` block.</span></span>  
  
     <span data-ttu-id="ac077-113">[!code-vb[VbVbalrMyComputer#28](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="ac077-113">[!code-vb[VbVbalrMyComputer#28](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_1.vb)]</span></span>  
  
3.  <span data-ttu-id="ac077-114">Establezca la propiedad `DtrEnable` para indicar que el equipo está listo para aceptar una transmisión de entrada procedente del módem.</span><span class="sxs-lookup"><span data-stu-id="ac077-114">Set the `DtrEnable` property to indicate that the computer is ready to accept an incoming transmission from the modem.</span></span>  
  
     <span data-ttu-id="ac077-115">[!code-vb[VbVbalrMyComputer#29](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="ac077-115">[!code-vb[VbVbalrMyComputer#29](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_2.vb)]</span></span>  
  
4.  <span data-ttu-id="ac077-116">Envíe el comando de marcar y el número de teléfono al módem a través del puerto serie por medio del método <xref:System.IO.Ports.SerialPort.Write%2A>.</span><span class="sxs-lookup"><span data-stu-id="ac077-116">Send the dial command and the phone number to the modem through the serial port by means of the <xref:System.IO.Ports.SerialPort.Write%2A> method.</span></span>  
  
     <span data-ttu-id="ac077-117">[!code-vb[VbVbalrMyComputer#30](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="ac077-117">[!code-vb[VbVbalrMyComputer#30](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_3.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac077-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac077-118">Example</span></span>  
 <span data-ttu-id="ac077-119">[!code-vb[VbVbalrMyComputer#27](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="ac077-119">[!code-vb[VbVbalrMyComputer#27](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_4.vb)]</span></span>  
  
 <span data-ttu-id="ac077-120">Este ejemplo de código también está disponible como fragmento de código de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="ac077-120">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="ac077-121">En el selector de fragmentos de código, se encuentra en **Conectividad y redes**.</span><span class="sxs-lookup"><span data-stu-id="ac077-121">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="ac077-122">Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="ac077-122">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ac077-123">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="ac077-123">Compiling the Code</span></span>  
 <span data-ttu-id="ac077-124">Este ejemplo requiere una referencia al espacio de nombres <xref:System?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="ac077-124">This example requires a reference to the <xref:System?displayProperty=fullName> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="ac077-125">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="ac077-125">Robust Programming</span></span>  
 <span data-ttu-id="ac077-126">En este ejemplo se presupone que el módem está conectado a COM1.</span><span class="sxs-lookup"><span data-stu-id="ac077-126">This example assumes the modem is connected to COM1.</span></span> <span data-ttu-id="ac077-127">Es recomendable que el código permita al usuario seleccionar el puerto serie deseado de una lista de puertos disponibles.</span><span class="sxs-lookup"><span data-stu-id="ac077-127">We recommend that your code allow the user to select the desired serial port from a list of available ports.</span></span> <span data-ttu-id="ac077-128">Para obtener más información, vea [Cómo: Mostrar los puertos serie disponibles en Visual Basic](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span><span class="sxs-lookup"><span data-stu-id="ac077-128">For more information, see [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span></span>  
  
 <span data-ttu-id="ac077-129">En este ejemplo se usa un bloque `Using` para asegurarse de que la aplicación cierra el puerto incluso si se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="ac077-129">This example uses a `Using` block to make sure that the application closes the port even if it throws an exception.</span></span> <span data-ttu-id="ac077-130">Para obtener más información, vea [Using (Instrucción)](../../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ac077-130">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
 <span data-ttu-id="ac077-131">En este ejemplo, la aplicación desconecta el puerto serie después de marcar el módem.</span><span class="sxs-lookup"><span data-stu-id="ac077-131">In this example, the application disconnects the serial port after it dials the modem.</span></span> <span data-ttu-id="ac077-132">En la realidad, querrá transferir datos al módem y desde él.</span><span class="sxs-lookup"><span data-stu-id="ac077-132">Realistically, you will want to transfer data to and from the modem.</span></span> <span data-ttu-id="ac077-133">Para obtener más información, vea [Cómo: Recibir cadenas de puertos serie](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md).</span><span class="sxs-lookup"><span data-stu-id="ac077-133">For more information, see [How to: Receive Strings From Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac077-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac077-134">See Also</span></span>  
 <span data-ttu-id="ac077-135"><xref:Microsoft.VisualBasic.Devices.Ports></span><span class="sxs-lookup"><span data-stu-id="ac077-135"><xref:Microsoft.VisualBasic.Devices.Ports></span></span>   
 <span data-ttu-id="ac077-136"><xref:System.IO.Ports.SerialPort?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="ac077-136"><xref:System.IO.Ports.SerialPort?displayProperty=fullName></span></span>   
 <span data-ttu-id="ac077-137">[Cómo: Enviar cadenas a puertos serie](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md) </span><span class="sxs-lookup"><span data-stu-id="ac077-137">[How to: Send Strings to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md) </span></span>  
 <span data-ttu-id="ac077-138">[Cómo: Recibir cadenas de puertos serie](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md) </span><span class="sxs-lookup"><span data-stu-id="ac077-138">[How to: Receive Strings From Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md) </span></span>  
 [<span data-ttu-id="ac077-139">Mostrar los puertos serie disponibles</span><span class="sxs-lookup"><span data-stu-id="ac077-139">How to: Show Available Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)

