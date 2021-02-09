---
description: 'Más información acerca de: Procedimiento: para marcar a través de módems conectados a puertos serie en Visual Basic'
title: Procedimiento para marcar a través de módems conectados a puertos serie
ms.date: 07/20/2015
helpviewer_keywords:
- modems [Visual Basic], dialing
- serial ports [Visual Basic], dialing
- My.Computer.Ports object
ms.assetid: 3834db40-f431-45f1-b671-dc91787164b6
ms.openlocfilehash: 016a3f768020c551c4f4ca7f5a097f4f1f9d07d7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797710"
---
# <a name="how-to-dial-modems-attached-to-serial-ports-in-visual-basic"></a><span data-ttu-id="d39d2-103">Cómo: Marcar a través de módems conectados a puertos serie en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d39d2-103">How to: Dial Modems Attached to Serial Ports in Visual Basic</span></span>

<span data-ttu-id="d39d2-104">En este tema se explica cómo usar `My.Computer.Ports` para llamar a un módem en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d39d2-104">This topic describes how to use `My.Computer.Ports` to dial a modem in Visual Basic.</span></span>  
  
 <span data-ttu-id="d39d2-105">Normalmente, el módem se conecta a uno de los puertos serie del equipo.</span><span class="sxs-lookup"><span data-stu-id="d39d2-105">Typically, the modem is connected to one of the serial ports on the computer.</span></span> <span data-ttu-id="d39d2-106">Para que la aplicación se comunique con el módem, debe enviar los comandos al puerto serie adecuado.</span><span class="sxs-lookup"><span data-stu-id="d39d2-106">For your application to communicate with the modem, it must send commands to the appropriate serial port.</span></span>  
  
### <a name="to-dial-a-modem"></a><span data-ttu-id="d39d2-107">Para llamar un módem</span><span class="sxs-lookup"><span data-stu-id="d39d2-107">To dial a modem</span></span>  
  
1. <span data-ttu-id="d39d2-108">Determine a qué puerto serie está conectado el módem.</span><span class="sxs-lookup"><span data-stu-id="d39d2-108">Determine which serial port the modem is connected to.</span></span> <span data-ttu-id="d39d2-109">En este ejemplo se presupone que el módem está en COM1.</span><span class="sxs-lookup"><span data-stu-id="d39d2-109">This example assumes the modem is on COM1.</span></span>  
  
2. <span data-ttu-id="d39d2-110">Use el método `My.Computer.Ports.OpenSerialPort` para obtener una referencia al puerto.</span><span class="sxs-lookup"><span data-stu-id="d39d2-110">Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port.</span></span> <span data-ttu-id="d39d2-111">Para obtener más información, vea <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span><span class="sxs-lookup"><span data-stu-id="d39d2-111">For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span></span>  
  
     <span data-ttu-id="d39d2-112">El bloque `Using` permite a la aplicación cerrar el puerto serie aun cuando se genere una excepción.</span><span class="sxs-lookup"><span data-stu-id="d39d2-112">The `Using` block allows the application to close the serial port even if it generates an exception.</span></span> <span data-ttu-id="d39d2-113">Todo el código que manipula el puerto serie debe aparecer dentro de este bloque o dentro de un bloque `Try...Catch...Finally`.</span><span class="sxs-lookup"><span data-stu-id="d39d2-113">All code that manipulates the serial port should appear within this block, or within a `Try...Catch...Finally` block.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#28)]  
  
3. <span data-ttu-id="d39d2-114">Establezca la propiedad `DtrEnable` para indicar que el equipo está listo para aceptar una transmisión de entrada procedente del módem.</span><span class="sxs-lookup"><span data-stu-id="d39d2-114">Set the `DtrEnable` property to indicate that the computer is ready to accept an incoming transmission from the modem.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#29)]  
  
4. <span data-ttu-id="d39d2-115">Envíe el comando de marcar y el número de teléfono al módem a través del puerto serie por medio del método <xref:System.IO.Ports.SerialPort.Write%2A>.</span><span class="sxs-lookup"><span data-stu-id="d39d2-115">Send the dial command and the phone number to the modem through the serial port by means of the <xref:System.IO.Ports.SerialPort.Write%2A> method.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#30)]  
  
## <a name="example"></a><span data-ttu-id="d39d2-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d39d2-116">Example</span></span>  

 [!code-vb[VbVbalrMyComputer#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#27)]  
  
 <span data-ttu-id="d39d2-117">Este ejemplo de código también está disponible como fragmento de código de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="d39d2-117">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="d39d2-118">En el selector de fragmentos de código, se encuentra en **Conectividad y redes**.</span><span class="sxs-lookup"><span data-stu-id="d39d2-118">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="d39d2-119">Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="d39d2-119">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d39d2-120">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="d39d2-120">Compiling the Code</span></span>  

 <span data-ttu-id="d39d2-121">Este ejemplo requiere una referencia al espacio de nombres <xref:System?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d39d2-121">This example requires a reference to the <xref:System?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="d39d2-122">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="d39d2-122">Robust Programming</span></span>  

 <span data-ttu-id="d39d2-123">En este ejemplo se presupone que el módem está conectado a COM1.</span><span class="sxs-lookup"><span data-stu-id="d39d2-123">This example assumes the modem is connected to COM1.</span></span> <span data-ttu-id="d39d2-124">Es recomendable que el código permita al usuario seleccionar el puerto serie deseado de una lista de puertos disponibles.</span><span class="sxs-lookup"><span data-stu-id="d39d2-124">We recommend that your code allow the user to select the desired serial port from a list of available ports.</span></span> <span data-ttu-id="d39d2-125">Para obtener más información, vea [How to: Show Available Serial Ports](how-to-show-available-serial-ports.md) (Cómo: Mostrar los puertos serie disponibles en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d39d2-125">For more information, see [How to: Show Available Serial Ports](how-to-show-available-serial-ports.md).</span></span>  
  
 <span data-ttu-id="d39d2-126">En este ejemplo se usa un bloque `Using` para asegurarse de que la aplicación cierra el puerto incluso si se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="d39d2-126">This example uses a `Using` block to make sure that the application closes the port even if it throws an exception.</span></span> <span data-ttu-id="d39d2-127">Para obtener más información, vea [Using (Instrucción)](../../../language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d39d2-127">For more information, see [Using Statement](../../../language-reference/statements/using-statement.md).</span></span>  
  
 <span data-ttu-id="d39d2-128">En este ejemplo, la aplicación desconecta el puerto serie después de marcar el módem.</span><span class="sxs-lookup"><span data-stu-id="d39d2-128">In this example, the application disconnects the serial port after it dials the modem.</span></span> <span data-ttu-id="d39d2-129">En la realidad, querrá transferir datos al módem y desde él.</span><span class="sxs-lookup"><span data-stu-id="d39d2-129">Realistically, you will want to transfer data to and from the modem.</span></span> <span data-ttu-id="d39d2-130">Para obtener más información, vea [Cómo: Recibir cadenas de puertos serie](how-to-receive-strings-from-serial-ports.md).</span><span class="sxs-lookup"><span data-stu-id="d39d2-130">For more information, see [How to: Receive Strings From Serial Ports](how-to-receive-strings-from-serial-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d39d2-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="d39d2-131">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Ports>
- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
- [<span data-ttu-id="d39d2-132">Procedimiento para enviar cadenas a puertos serie</span><span class="sxs-lookup"><span data-stu-id="d39d2-132">How to: Send Strings to Serial Ports</span></span>](how-to-send-strings-to-serial-ports.md)
- [<span data-ttu-id="d39d2-133">Procedimiento para recibir cadenas de puertos serie</span><span class="sxs-lookup"><span data-stu-id="d39d2-133">How to: Receive Strings From Serial Ports</span></span>](how-to-receive-strings-from-serial-ports.md)
- [<span data-ttu-id="d39d2-134">Procedimiento para mostrar los puertos serie disponibles</span><span class="sxs-lookup"><span data-stu-id="d39d2-134">How to: Show Available Serial Ports</span></span>](how-to-show-available-serial-ports.md)
