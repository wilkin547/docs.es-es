---
description: 'Más información acerca de: Procedimiento: para recibir cadenas de puertos serie en Visual Basic'
title: Procedimiento para recibir cadenas de puertos serie
ms.date: 07/20/2015
helpviewer_keywords:
- serial ports, retrieving strings
- strings [Visual Basic], retrieving from serial ports
- My.Resources object
ms.assetid: 8371ce2c-e1c7-476b-a86d-9afc2614b6b7
ms.openlocfilehash: 5e6de24392c6102b6dc613d909c827cc32f513d0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99666542"
---
# <a name="how-to-receive-strings-from-serial-ports-in-visual-basic"></a><span data-ttu-id="364b5-103">Cómo: Recibir cadenas de puertos serie en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="364b5-103">How to: Receive Strings From Serial Ports in Visual Basic</span></span>

<span data-ttu-id="364b5-104">En este tema se explica cómo usar `My.Computer.Ports` para recibir cadenas de los puertos serie del equipo en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="364b5-104">This topic describes how to use `My.Computer.Ports` to receive strings from the computer's serial ports in Visual Basic.</span></span>  
  
### <a name="to-receive-strings-from-the-serial-port"></a><span data-ttu-id="364b5-105">Para recibir cadenas del puerto serie</span><span class="sxs-lookup"><span data-stu-id="364b5-105">To receive strings from the serial port</span></span>  
  
1. <span data-ttu-id="364b5-106">Inicialice la cadena de devolución.</span><span class="sxs-lookup"><span data-stu-id="364b5-106">Initialize the return string.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#38)]  
  
2. <span data-ttu-id="364b5-107">Determine el puerto serie que debe proporcionar las cadenas.</span><span class="sxs-lookup"><span data-stu-id="364b5-107">Determine which serial port should provide the strings.</span></span> <span data-ttu-id="364b5-108">En este ejemplo se da por supuesto que es `COM1`.</span><span class="sxs-lookup"><span data-stu-id="364b5-108">This example assumes it is `COM1`.</span></span>  
  
3. <span data-ttu-id="364b5-109">Use el método `My.Computer.Ports.OpenSerialPort` para obtener una referencia al puerto.</span><span class="sxs-lookup"><span data-stu-id="364b5-109">Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port.</span></span> <span data-ttu-id="364b5-110">Para obtener más información, vea <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span><span class="sxs-lookup"><span data-stu-id="364b5-110">For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span></span>  
  
     <span data-ttu-id="364b5-111">El bloque `Try...Catch...Finally` permite a la aplicación cerrar el puerto serie aun cuando se genere una excepción.</span><span class="sxs-lookup"><span data-stu-id="364b5-111">The `Try...Catch...Finally` block allows the application to close the serial port even if it generates an exception.</span></span> <span data-ttu-id="364b5-112">Todo el código que manipula el puerto serie debe aparecer dentro de este bloque.</span><span class="sxs-lookup"><span data-stu-id="364b5-112">All code that manipulates the serial port should appear within this block.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#39)]  
  
4. <span data-ttu-id="364b5-113">Cree un bucle `Do` que lea líneas de texto hasta que no haya más líneas disponibles.</span><span class="sxs-lookup"><span data-stu-id="364b5-113">Create a `Do` loop for reading lines of text until no more lines are available.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#40)]  
  
5. <span data-ttu-id="364b5-114">Use el método <xref:System.IO.Ports.SerialPort.ReadLine> para leer la siguiente línea de texto disponible desde el puerto serie.</span><span class="sxs-lookup"><span data-stu-id="364b5-114">Use the <xref:System.IO.Ports.SerialPort.ReadLine> method to read the next available line of text from the serial port.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#41)]  
  
6. <span data-ttu-id="364b5-115">Use una instrucción `If` para determinar si el método <xref:System.IO.Ports.SerialPort.ReadLine> devuelve `Nothing` (lo que indica que no hay más texto disponible).</span><span class="sxs-lookup"><span data-stu-id="364b5-115">Use an `If` statement to determine if the <xref:System.IO.Ports.SerialPort.ReadLine> method returns `Nothing` (which means no more text is available).</span></span> <span data-ttu-id="364b5-116">Si devuelve `Nothing`, salga del bucle `Do`.</span><span class="sxs-lookup"><span data-stu-id="364b5-116">If it does return `Nothing`, exit the `Do` loop.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#42)]  
  
7. <span data-ttu-id="364b5-117">Agregue un bloque `Else` a la instrucción `If` para controlar el caso si la cadena se lee realmente.</span><span class="sxs-lookup"><span data-stu-id="364b5-117">Add an `Else` block to the `If` statement to handle the case if the string is actually read.</span></span> <span data-ttu-id="364b5-118">El bloque anexa la cadena del puerto serie a la cadena de devolución.</span><span class="sxs-lookup"><span data-stu-id="364b5-118">The block appends the string from the serial port to the return string.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#43)]  
  
8. <span data-ttu-id="364b5-119">Devolver la cadena.</span><span class="sxs-lookup"><span data-stu-id="364b5-119">Return the string.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#44)]  
  
## <a name="example"></a><span data-ttu-id="364b5-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="364b5-120">Example</span></span>  

 [!code-vb[VbVbalrMyComputer#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#37)]  
  
 <span data-ttu-id="364b5-121">Este ejemplo de código también está disponible como fragmento de código de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="364b5-121">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="364b5-122">En el selector de fragmentos de código, se encuentra en **Conectividad y redes**.</span><span class="sxs-lookup"><span data-stu-id="364b5-122">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="364b5-123">Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="364b5-123">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="364b5-124">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="364b5-124">Compiling the Code</span></span>  

 <span data-ttu-id="364b5-125">En este ejemplo se presupone que el equipo usa `COM1`.</span><span class="sxs-lookup"><span data-stu-id="364b5-125">This example assumes the computer is using `COM1`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="364b5-126">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="364b5-126">Robust Programming</span></span>  

 <span data-ttu-id="364b5-127">En este ejemplo se presupone que el equipo usa `COM1`.</span><span class="sxs-lookup"><span data-stu-id="364b5-127">This example assumes the computer is using `COM1`.</span></span> <span data-ttu-id="364b5-128">Para brindar mayor flexibilidad, el código debe permitir al usuario seleccionar el puerto serie que quiera de una lista de puertos disponibles.</span><span class="sxs-lookup"><span data-stu-id="364b5-128">For more flexibility, the code should allow the user to select the desired serial port from a list of available ports.</span></span> <span data-ttu-id="364b5-129">Para obtener más información, vea [How to: Show Available Serial Ports](how-to-show-available-serial-ports.md) (Cómo: Mostrar los puertos serie disponibles en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="364b5-129">For more information, see [How to: Show Available Serial Ports](how-to-show-available-serial-ports.md).</span></span>  
  
 <span data-ttu-id="364b5-130">En este ejemplo se usa un bloque `Try...Catch...Finally` para asegurarse de que la aplicación cierra el puerto y para capturar las excepciones de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="364b5-130">This example uses a `Try...Catch...Finally` block to make sure that the application closes the port and to catch any timeout exceptions.</span></span> <span data-ttu-id="364b5-131">Para obtener más información, vea [Instrucción Try...Catch...Finally (Visual Basic)](../../../language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="364b5-131">For more information, see [Try...Catch...Finally Statement](../../../language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="364b5-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="364b5-132">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Ports>
- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
- [<span data-ttu-id="364b5-133">Procedimiento para marcar a través de módems conectados a puertos serie</span><span class="sxs-lookup"><span data-stu-id="364b5-133">How to: Dial Modems Attached to Serial Ports</span></span>](how-to-dial-modems-attached-to-serial-ports.md)
- [<span data-ttu-id="364b5-134">Procedimiento para enviar cadenas a puertos serie</span><span class="sxs-lookup"><span data-stu-id="364b5-134">How to: Send Strings to Serial Ports</span></span>](how-to-send-strings-to-serial-ports.md)
- [<span data-ttu-id="364b5-135">Procedimiento para mostrar los puertos serie disponibles</span><span class="sxs-lookup"><span data-stu-id="364b5-135">How to: Show Available Serial Ports</span></span>](how-to-show-available-serial-ports.md)
