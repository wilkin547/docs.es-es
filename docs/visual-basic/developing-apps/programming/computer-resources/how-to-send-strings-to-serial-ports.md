---
description: 'Más información acerca de: Procedimiento: para enviar cadenas a puertos serie en Visual Basic'
title: Procedimiento para enviar cadenas a puertos serie
ms.date: 07/20/2015
helpviewer_keywords:
- ports, sending strings to
- strings [Visual Basic], sending to serial ports
- My.Computer.Ports object
- serial ports, sending strings to
ms.assetid: 6ebf46cd-b2d0-4b2c-9a1f-be177b22ad52
ms.openlocfilehash: 66dedaab05090af2659701e57b37b4813447b8ef
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99666490"
---
# <a name="how-to-send-strings-to-serial-ports-in-visual-basic"></a><span data-ttu-id="a7942-103">Cómo: Enviar cadenas a puertos serie en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a7942-103">How to: Send Strings to Serial Ports in Visual Basic</span></span>

<span data-ttu-id="a7942-104">En este tema se explica cómo usar `My.Computer.Ports` para enviar cadenas a los puertos serie del equipo en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a7942-104">This topic describes how to use `My.Computer.Ports` to send strings to the computer's serial ports in Visual Basic.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7942-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a7942-105">Example</span></span>  

 <span data-ttu-id="a7942-106">En este ejemplo se envía una cadena al puerto serie COM1.</span><span class="sxs-lookup"><span data-stu-id="a7942-106">This example sends a string to the COM1 serial port.</span></span> <span data-ttu-id="a7942-107">Es posible que tenga que usar un puerto serie diferente en el equipo.</span><span class="sxs-lookup"><span data-stu-id="a7942-107">You may need to use a different serial port on your computer.</span></span>  
  
 <span data-ttu-id="a7942-108">Use el método `My.Computer.Ports.OpenSerialPort` para obtener una referencia al puerto.</span><span class="sxs-lookup"><span data-stu-id="a7942-108">Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port.</span></span> <span data-ttu-id="a7942-109">Para obtener más información, vea <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span><span class="sxs-lookup"><span data-stu-id="a7942-109">For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span></span>  
  
 <span data-ttu-id="a7942-110">El bloque `Using` permite a la aplicación cerrar el puerto serie aun cuando se genere una excepción.</span><span class="sxs-lookup"><span data-stu-id="a7942-110">The `Using` block allows the application to close the serial port even if it generates an exception.</span></span> <span data-ttu-id="a7942-111">Todo el código que manipula el puerto serie debe aparecer dentro de este bloque o dentro un bloque `Try...Catch...Finally`.</span><span class="sxs-lookup"><span data-stu-id="a7942-111">All code that manipulates the serial port should appear within this block or within a `Try...Catch...Finally` block.</span></span>  
  
 <span data-ttu-id="a7942-112">El método <xref:System.IO.Ports.SerialPort.WriteLine%2A> envía los datos al puerto serie.</span><span class="sxs-lookup"><span data-stu-id="a7942-112">The <xref:System.IO.Ports.SerialPort.WriteLine%2A> method sends the data to the serial port.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#33)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a7942-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="a7942-113">Compiling the Code</span></span>  
  
- <span data-ttu-id="a7942-114">En este ejemplo se presupone que el equipo usa `COM1`.</span><span class="sxs-lookup"><span data-stu-id="a7942-114">This example assumes the computer is using `COM1`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a7942-115">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="a7942-115">Robust Programming</span></span>  

 <span data-ttu-id="a7942-116">En este ejemplo se presupone que el equipo está usando `COM1`. Para obtener mayor flexibilidad, el código debe permitir al usuario seleccionar el puerto serie deseado entre una lista de puertos disponibles.</span><span class="sxs-lookup"><span data-stu-id="a7942-116">This example assumes the computer is using `COM1`; for more flexibility, the code should allow the user to select the desired serial port from a list of available ports.</span></span> <span data-ttu-id="a7942-117">Para obtener más información, vea [How to: Show Available Serial Ports](how-to-show-available-serial-ports.md) (Cómo: Mostrar los puertos serie disponibles en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="a7942-117">For more information, see [How to: Show Available Serial Ports](how-to-show-available-serial-ports.md).</span></span>  
  
 <span data-ttu-id="a7942-118">En este ejemplo se usa un bloque `Using` para asegurarse de que la aplicación cierra el puerto incluso si se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="a7942-118">This example uses a `Using` block to make sure that the application closes the port even if it throws an exception.</span></span> <span data-ttu-id="a7942-119">Para obtener más información, vea [Using (Instrucción)](../../../language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a7942-119">For more information, see [Using Statement](../../../language-reference/statements/using-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7942-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7942-120">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Ports>
- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
- [<span data-ttu-id="a7942-121">Procedimiento para marcar a través de módems conectados a puertos serie</span><span class="sxs-lookup"><span data-stu-id="a7942-121">How to: Dial Modems Attached to Serial Ports</span></span>](how-to-dial-modems-attached-to-serial-ports.md)
- [<span data-ttu-id="a7942-122">Procedimiento para mostrar los puertos serie disponibles</span><span class="sxs-lookup"><span data-stu-id="a7942-122">How to: Show Available Serial Ports</span></span>](how-to-show-available-serial-ports.md)
