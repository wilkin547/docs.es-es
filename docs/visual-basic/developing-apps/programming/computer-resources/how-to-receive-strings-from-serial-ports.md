---
title: "Cómo: Recibir cadenas de puertos serie en Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- serial ports, retrieving strings
- strings [Visual Basic], retrieving from serial ports
- My.Resources object
ms.assetid: 8371ce2c-e1c7-476b-a86d-9afc2614b6b7
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a58ce248404bfe4d6c55bba741b332acd7fcbf5c
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-receive-strings-from-serial-ports-in-visual-basic"></a><span data-ttu-id="a4a7d-102">Cómo: Recibir cadenas de puertos serie en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a4a7d-102">How to: Receive Strings From Serial Ports in Visual Basic</span></span>
<span data-ttu-id="a4a7d-103">En este tema se describe cómo usar `My.Computer.Ports` para recibir cadenas de los puertos serie del equipo en [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4a7d-103">This topic describes how to use `My.Computer.Ports` to receive strings from the computer's serial ports in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
### <a name="to-receive-strings-from-the-serial-port"></a><span data-ttu-id="a4a7d-104">Para recibir cadenas del puerto serie</span><span class="sxs-lookup"><span data-stu-id="a4a7d-104">To receive strings from the serial port</span></span>  
  
1.  <span data-ttu-id="a4a7d-105">Inicialice la cadena de devolución.</span><span class="sxs-lookup"><span data-stu-id="a4a7d-105">Initialize the return string.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#38](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_1.vb)]  
  
2.  <span data-ttu-id="a4a7d-106">Determine el puerto serie que debe proporcionar las cadenas.</span><span class="sxs-lookup"><span data-stu-id="a4a7d-106">Determine which serial port should provide the strings.</span></span> <span data-ttu-id="a4a7d-107">En este ejemplo se da por supuesto que es `COM1`.</span><span class="sxs-lookup"><span data-stu-id="a4a7d-107">This example assumes it is `COM1`.</span></span>  
  
3.  <span data-ttu-id="a4a7d-108">Use el método `My.Computer.Ports.OpenSerialPort` para obtener una referencia al puerto.</span><span class="sxs-lookup"><span data-stu-id="a4a7d-108">Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port.</span></span> <span data-ttu-id="a4a7d-109">Para obtener más información, consulta <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span><span class="sxs-lookup"><span data-stu-id="a4a7d-109">For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span></span>  
  
     <span data-ttu-id="a4a7d-110">El bloque `Try...Catch...Finally` permite a la aplicación cerrar el puerto serie aun cuando se genere una excepción.</span><span class="sxs-lookup"><span data-stu-id="a4a7d-110">The `Try...Catch...Finally` block allows the application to close the serial port even if it generates an exception.</span></span> <span data-ttu-id="a4a7d-111">Todo el código que manipula el puerto serie debe aparecer dentro de este bloque.</span><span class="sxs-lookup"><span data-stu-id="a4a7d-111">All code that manipulates the serial port should appear within this block.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#39](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_2.vb)]  
  
4.  <span data-ttu-id="a4a7d-112">Cree un bucle `Do` que lea líneas de texto hasta que no haya más líneas disponibles.</span><span class="sxs-lookup"><span data-stu-id="a4a7d-112">Create a `Do` loop for reading lines of text until no more lines are available.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#40](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_3.vb)]  
  
5.  <span data-ttu-id="a4a7d-113">Use el método <xref:System.IO.Ports.SerialPort.ReadLine> para leer la siguiente línea de texto disponible desde el puerto serie.</span><span class="sxs-lookup"><span data-stu-id="a4a7d-113">Use the <xref:System.IO.Ports.SerialPort.ReadLine> method to read the next available line of text from the serial port.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#41](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_4.vb)]  
  
6.  <span data-ttu-id="a4a7d-114">Use una instrucción `If` para determinar si el método <xref:System.IO.Ports.SerialPort.ReadLine> devuelve `Nothing` (lo que indica que no hay más texto disponible).</span><span class="sxs-lookup"><span data-stu-id="a4a7d-114">Use an `If` statement to determine if the <xref:System.IO.Ports.SerialPort.ReadLine> method returns `Nothing` (which means no more text is available).</span></span> <span data-ttu-id="a4a7d-115">Si devuelve `Nothing`, salga del bucle `Do`.</span><span class="sxs-lookup"><span data-stu-id="a4a7d-115">If it does return `Nothing`, exit the `Do` loop.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#42](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_5.vb)]  
  
7.  <span data-ttu-id="a4a7d-116">Agregue un bloque `Else` a la instrucción `If` para controlar el caso si la cadena se lee realmente.</span><span class="sxs-lookup"><span data-stu-id="a4a7d-116">Add an `Else` block to the `If` statement to handle the case if the string is actually read.</span></span> <span data-ttu-id="a4a7d-117">El bloque anexa la cadena del puerto serie a la cadena de devolución.</span><span class="sxs-lookup"><span data-stu-id="a4a7d-117">The block appends the string from the serial port to the return string.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#43](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_6.vb)]  
  
8.  <span data-ttu-id="a4a7d-118">Devolver la cadena.</span><span class="sxs-lookup"><span data-stu-id="a4a7d-118">Return the string.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#44](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_7.vb)]  
  
## <a name="example"></a><span data-ttu-id="a4a7d-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a4a7d-119">Example</span></span>  
 [!code-vb[VbVbalrMyComputer#37](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_8.vb)]  
  
 <span data-ttu-id="a4a7d-120">Este ejemplo de código también está disponible como fragmento de código de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="a4a7d-120">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="a4a7d-121">En el selector de fragmentos de código, se encuentra en **Conectividad y redes**.</span><span class="sxs-lookup"><span data-stu-id="a4a7d-121">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="a4a7d-122">Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="a4a7d-122">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a4a7d-123">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="a4a7d-123">Compiling the Code</span></span>  
 <span data-ttu-id="a4a7d-124">En este ejemplo se presupone que el equipo usa `COM1`.</span><span class="sxs-lookup"><span data-stu-id="a4a7d-124">This example assumes the computer is using `COM1`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a4a7d-125">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="a4a7d-125">Robust Programming</span></span>  
 <span data-ttu-id="a4a7d-126">En este ejemplo se presupone que el equipo usa `COM1`.</span><span class="sxs-lookup"><span data-stu-id="a4a7d-126">This example assumes the computer is using `COM1`.</span></span> <span data-ttu-id="a4a7d-127">Para brindar mayor flexibilidad, el código debe permitir al usuario seleccionar el puerto serie que quiera de una lista de puertos disponibles.</span><span class="sxs-lookup"><span data-stu-id="a4a7d-127">For more flexibility, the code should allow the user to select the desired serial port from a list of available ports.</span></span> <span data-ttu-id="a4a7d-128">Para obtener más información, vea [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md) (Cómo: Mostrar los puertos serie disponibles en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="a4a7d-128">For more information, see [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span></span>  
  
 <span data-ttu-id="a4a7d-129">En este ejemplo se usa un bloque `Try...Catch...Finally` para asegurarse de que la aplicación cierra el puerto y para capturar las excepciones de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="a4a7d-129">This example uses a `Try...Catch...Finally` block to make sure that the application closes the port and to catch any timeout exceptions.</span></span> <span data-ttu-id="a4a7d-130">Para obtener más información, vea [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) (Try...Catch...Finally [Instrucción, Visual Basic]).</span><span class="sxs-lookup"><span data-stu-id="a4a7d-130">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4a7d-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4a7d-131">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Ports>  
 <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>  
 [<span data-ttu-id="a4a7d-132">Marcar a través de módems conectados a puertos serie</span><span class="sxs-lookup"><span data-stu-id="a4a7d-132">How to: Dial Modems Attached to Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)  
 [<span data-ttu-id="a4a7d-133">Enviar cadenas a puertos serie</span><span class="sxs-lookup"><span data-stu-id="a4a7d-133">How to: Send Strings to Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)  
 [<span data-ttu-id="a4a7d-134">Mostrar los puertos serie disponibles</span><span class="sxs-lookup"><span data-stu-id="a4a7d-134">How to: Show Available Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)
