---
title: "Cómo: Enviar cadenas a puertos serie en Visual Basic"
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
- ports, sending strings to
- strings [Visual Basic], sending to serial ports
- My.Computer.Ports object
- serial ports, sending strings to
ms.assetid: 6ebf46cd-b2d0-4b2c-9a1f-be177b22ad52
caps.latest.revision: 13
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
ms.openlocfilehash: 602b249d01252bbb1853ed02d9af86697d54b0a5
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-send-strings-to-serial-ports-in-visual-basic"></a><span data-ttu-id="a69da-102">Cómo: Enviar cadenas a puertos serie en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a69da-102">How to: Send Strings to Serial Ports in Visual Basic</span></span>
<span data-ttu-id="a69da-103">En este tema se describe cómo usar `My.Computer.Ports` para enviar cadenas a los puertos serie del equipo en [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a69da-103">This topic describes how to use `My.Computer.Ports` to send strings to the computer's serial ports in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="a69da-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a69da-104">Example</span></span>  
 <span data-ttu-id="a69da-105">En este ejemplo se envía una cadena al puerto serie COM1.</span><span class="sxs-lookup"><span data-stu-id="a69da-105">This example sends a string to the COM1 serial port.</span></span> <span data-ttu-id="a69da-106">Es posible que tenga que usar un puerto serie diferente en el equipo.</span><span class="sxs-lookup"><span data-stu-id="a69da-106">You may need to use a different serial port on your computer.</span></span>  
  
 <span data-ttu-id="a69da-107">Use el método `My.Computer.Ports.OpenSerialPort` para obtener una referencia al puerto.</span><span class="sxs-lookup"><span data-stu-id="a69da-107">Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port.</span></span> <span data-ttu-id="a69da-108">Para obtener más información, consulta <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span><span class="sxs-lookup"><span data-stu-id="a69da-108">For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span></span>  
  
 <span data-ttu-id="a69da-109">El bloque `Using` permite a la aplicación cerrar el puerto serie aun cuando se genere una excepción.</span><span class="sxs-lookup"><span data-stu-id="a69da-109">The `Using` block allows the application to close the serial port even if it generates an exception.</span></span> <span data-ttu-id="a69da-110">Todo el código que manipula el puerto serie debe aparecer dentro de este bloque o dentro un bloque `Try...Catch...Finally`.</span><span class="sxs-lookup"><span data-stu-id="a69da-110">All code that manipulates the serial port should appear within this block or within a `Try...Catch...Finally` block.</span></span>  
  
 <span data-ttu-id="a69da-111">El método <xref:System.IO.Ports.SerialPort.WriteLine%2A> envía los datos al puerto serie.</span><span class="sxs-lookup"><span data-stu-id="a69da-111">The <xref:System.IO.Ports.SerialPort.WriteLine%2A> method sends the data to the serial port.</span></span>  
  
 <span data-ttu-id="a69da-112">[!code-vb[VbVbalrMyComputer#33](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-send-strings-to-serial-ports_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a69da-112">[!code-vb[VbVbalrMyComputer#33](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-send-strings-to-serial-ports_1.vb)]</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a69da-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="a69da-113">Compiling the Code</span></span>  
  
-   <span data-ttu-id="a69da-114">En este ejemplo se presupone que el equipo usa `COM1`.</span><span class="sxs-lookup"><span data-stu-id="a69da-114">This example assumes the computer is using `COM1`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a69da-115">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="a69da-115">Robust Programming</span></span>  
 <span data-ttu-id="a69da-116">En este ejemplo se presupone que el equipo está usando `COM1`. Para obtener mayor flexibilidad, el código debe permitir al usuario seleccionar el puerto serie deseado entre una lista de puertos disponibles.</span><span class="sxs-lookup"><span data-stu-id="a69da-116">This example assumes the computer is using `COM1`; for more flexibility, the code should allow the user to select the desired serial port from a list of available ports.</span></span> <span data-ttu-id="a69da-117">Para obtener más información, vea [Cómo: Mostrar los puertos serie disponibles en Visual Basic](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span><span class="sxs-lookup"><span data-stu-id="a69da-117">For more information, see [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span></span>  
  
 <span data-ttu-id="a69da-118">En este ejemplo se usa un bloque `Using` para asegurarse de que la aplicación cierra el puerto incluso si se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="a69da-118">This example uses a `Using` block to make sure that the application closes the port even if it throws an exception.</span></span> <span data-ttu-id="a69da-119">Para obtener más información, vea [Using (Instrucción)](../../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a69da-119">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a69da-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="a69da-120">See Also</span></span>  
 <span data-ttu-id="a69da-121"><xref:Microsoft.VisualBasic.Devices.Ports></span><span class="sxs-lookup"><span data-stu-id="a69da-121"><xref:Microsoft.VisualBasic.Devices.Ports></span></span>   
 <span data-ttu-id="a69da-122"><xref:System.IO.Ports.SerialPort?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a69da-122"><xref:System.IO.Ports.SerialPort?displayProperty=fullName></span></span>   
 <span data-ttu-id="a69da-123">[Cómo: Marcar a través de módems conectados a puertos serie](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md) </span><span class="sxs-lookup"><span data-stu-id="a69da-123">[How to: Dial Modems Attached to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md) </span></span>  
 [<span data-ttu-id="a69da-124">Mostrar los puertos serie disponibles</span><span class="sxs-lookup"><span data-stu-id="a69da-124">How to: Show Available Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)

