---
title: 'Cómo: Marcar a través de módems conectados a puertos serie'
ms.date: 07/20/2015
helpviewer_keywords:
- modems [Visual Basic], dialing
- serial ports [Visual Basic], dialing
- My.Computer.Ports object
ms.assetid: 3834db40-f431-45f1-b671-dc91787164b6
ms.openlocfilehash: e55ce6399dae435fbd5b2f730d4d0848c98d8955
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363272"
---
# <a name="how-to-dial-modems-attached-to-serial-ports-in-visual-basic"></a><span data-ttu-id="86bfb-102">Cómo: Marcar a través de módems conectados a puertos serie en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="86bfb-102">How to: Dial Modems Attached to Serial Ports in Visual Basic</span></span>

<span data-ttu-id="86bfb-103">En este tema se explica cómo usar `My.Computer.Ports` para llamar a un módem en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="86bfb-103">This topic describes how to use `My.Computer.Ports` to dial a modem in Visual Basic.</span></span>  
  
 <span data-ttu-id="86bfb-104">Normalmente, el módem se conecta a uno de los puertos serie del equipo.</span><span class="sxs-lookup"><span data-stu-id="86bfb-104">Typically, the modem is connected to one of the serial ports on the computer.</span></span> <span data-ttu-id="86bfb-105">Para que la aplicación se comunique con el módem, debe enviar los comandos al puerto serie adecuado.</span><span class="sxs-lookup"><span data-stu-id="86bfb-105">For your application to communicate with the modem, it must send commands to the appropriate serial port.</span></span>  
  
### <a name="to-dial-a-modem"></a><span data-ttu-id="86bfb-106">Para llamar un módem</span><span class="sxs-lookup"><span data-stu-id="86bfb-106">To dial a modem</span></span>  
  
1. <span data-ttu-id="86bfb-107">Determine a qué puerto serie está conectado el módem.</span><span class="sxs-lookup"><span data-stu-id="86bfb-107">Determine which serial port the modem is connected to.</span></span> <span data-ttu-id="86bfb-108">En este ejemplo se presupone que el módem está en COM1.</span><span class="sxs-lookup"><span data-stu-id="86bfb-108">This example assumes the modem is on COM1.</span></span>  
  
2. <span data-ttu-id="86bfb-109">Use el método `My.Computer.Ports.OpenSerialPort` para obtener una referencia al puerto.</span><span class="sxs-lookup"><span data-stu-id="86bfb-109">Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port.</span></span> <span data-ttu-id="86bfb-110">Para obtener más información, consulta <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span><span class="sxs-lookup"><span data-stu-id="86bfb-110">For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span></span>  
  
     <span data-ttu-id="86bfb-111">El bloque `Using` permite a la aplicación cerrar el puerto serie aunque se genere una excepción.</span><span class="sxs-lookup"><span data-stu-id="86bfb-111">The `Using` block allows the application to close the serial port even if it generates an exception.</span></span> <span data-ttu-id="86bfb-112">Todo el código que manipula el puerto serie debe aparecer dentro de este bloque o dentro de un bloque `Try...Catch...Finally`.</span><span class="sxs-lookup"><span data-stu-id="86bfb-112">All code that manipulates the serial port should appear within this block, or within a `Try...Catch...Finally` block.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#28)]  
  
3. <span data-ttu-id="86bfb-113">Establezca la propiedad `DtrEnable` para indicar que el equipo está listo para aceptar una transmisión de entrada procedente del módem.</span><span class="sxs-lookup"><span data-stu-id="86bfb-113">Set the `DtrEnable` property to indicate that the computer is ready to accept an incoming transmission from the modem.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#29)]  
  
4. <span data-ttu-id="86bfb-114">Envíe el comando de marcar y el número de teléfono al módem a través del puerto serie por medio del método <xref:System.IO.Ports.SerialPort.Write%2A>.</span><span class="sxs-lookup"><span data-stu-id="86bfb-114">Send the dial command and the phone number to the modem through the serial port by means of the <xref:System.IO.Ports.SerialPort.Write%2A> method.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#30)]  
  
## <a name="example"></a><span data-ttu-id="86bfb-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="86bfb-115">Example</span></span>  

 [!code-vb[VbVbalrMyComputer#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#27)]  
  
 <span data-ttu-id="86bfb-116">Este ejemplo de código también está disponible como fragmento de código de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="86bfb-116">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="86bfb-117">En el selector de fragmentos de código, se encuentra en **Conectividad y redes**.</span><span class="sxs-lookup"><span data-stu-id="86bfb-117">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="86bfb-118">Para obtener más información, vea [Code Snippets](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="86bfb-118">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="86bfb-119">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="86bfb-119">Compiling the Code</span></span>  

 <span data-ttu-id="86bfb-120">Este ejemplo requiere una referencia al espacio de nombres <xref:System?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="86bfb-120">This example requires a reference to the <xref:System?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="86bfb-121">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="86bfb-121">Robust Programming</span></span>  

 <span data-ttu-id="86bfb-122">En este ejemplo se presupone que el módem está conectado a COM1.</span><span class="sxs-lookup"><span data-stu-id="86bfb-122">This example assumes the modem is connected to COM1.</span></span> <span data-ttu-id="86bfb-123">Es recomendable que el código permita al usuario seleccionar el puerto serie deseado de una lista de puertos disponibles.</span><span class="sxs-lookup"><span data-stu-id="86bfb-123">We recommend that your code allow the user to select the desired serial port from a list of available ports.</span></span> <span data-ttu-id="86bfb-124">Para obtener más información, vea [Cómo: Mostrar los puertos serie disponibles en Visual Basic](how-to-show-available-serial-ports.md).</span><span class="sxs-lookup"><span data-stu-id="86bfb-124">For more information, see [How to: Show Available Serial Ports](how-to-show-available-serial-ports.md).</span></span>  
  
 <span data-ttu-id="86bfb-125">En este ejemplo se usa un bloque `Using` para asegurarse de que la aplicación cierra el puerto incluso si se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="86bfb-125">This example uses a `Using` block to make sure that the application closes the port even if it throws an exception.</span></span> <span data-ttu-id="86bfb-126">Para obtener más información, vea [Using (Instrucción)](../../../language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="86bfb-126">For more information, see [Using Statement](../../../language-reference/statements/using-statement.md).</span></span>  
  
 <span data-ttu-id="86bfb-127">En este ejemplo, la aplicación desconecta el puerto serie después de marcar el módem.</span><span class="sxs-lookup"><span data-stu-id="86bfb-127">In this example, the application disconnects the serial port after it dials the modem.</span></span> <span data-ttu-id="86bfb-128">En la realidad, querrá transferir datos al módem y desde él.</span><span class="sxs-lookup"><span data-stu-id="86bfb-128">Realistically, you will want to transfer data to and from the modem.</span></span> <span data-ttu-id="86bfb-129">Para obtener más información, vea [Cómo: Recibir cadenas de puertos serie](how-to-receive-strings-from-serial-ports.md).</span><span class="sxs-lookup"><span data-stu-id="86bfb-129">For more information, see [How to: Receive Strings From Serial Ports](how-to-receive-strings-from-serial-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86bfb-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="86bfb-130">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Ports>
- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
- [<span data-ttu-id="86bfb-131">Enviar cadenas a puertos serie</span><span class="sxs-lookup"><span data-stu-id="86bfb-131">How to: Send Strings to Serial Ports</span></span>](how-to-send-strings-to-serial-ports.md)
- [<span data-ttu-id="86bfb-132">Recibir cadenas de puertos serie</span><span class="sxs-lookup"><span data-stu-id="86bfb-132">How to: Receive Strings From Serial Ports</span></span>](how-to-receive-strings-from-serial-ports.md)
- [<span data-ttu-id="86bfb-133">Mostrar los puertos serie disponibles</span><span class="sxs-lookup"><span data-stu-id="86bfb-133">How to: Show Available Serial Ports</span></span>](how-to-show-available-serial-ports.md)
