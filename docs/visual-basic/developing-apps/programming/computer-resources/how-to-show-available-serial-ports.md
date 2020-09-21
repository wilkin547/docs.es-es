---
title: 'Cómo: Mostrar los puertos serie disponibles'
ms.date: 07/20/2015
helpviewer_keywords:
- serial ports, availability
- My.Computer.Ports.SerialPortNames property
- My.Computer.Ports object
- ports, serial port availability
ms.assetid: eaf2ee5a-8103-4e10-a205-ed1d4db120ba
ms.openlocfilehash: b19bdd56311ab7029fb224256d138a0dc0dd8ddc
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557351"
---
# <a name="how-to-show-available-serial-ports-in-visual-basic"></a><span data-ttu-id="e769c-102">Cómo: Mostrar los puertos serie disponibles en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e769c-102">How to: Show Available Serial Ports in Visual Basic</span></span>

<span data-ttu-id="e769c-103">En este tema se explica cómo usar `My.Computer.Ports` para mostrar los puertos serie disponibles del equipo en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e769c-103">This topic describes how to use `My.Computer.Ports` to show the available serial ports of the computer in Visual Basic.</span></span>  
  
 <span data-ttu-id="e769c-104">Para permitir al usuario seleccionar qué puerto quiere usar, los nombres de los puertos serie se colocan en un control <xref:System.Windows.Forms.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="e769c-104">To allow a user to select which port to use, the names of the serial ports are placed in a <xref:System.Windows.Forms.ListBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e769c-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e769c-105">Example</span></span>  

 <span data-ttu-id="e769c-106">Este ejemplo recorre todas las cadenas que devuelve la propiedad `My.Computer.Ports.SerialPortNames`.</span><span class="sxs-lookup"><span data-stu-id="e769c-106">This example loops over all the strings that the `My.Computer.Ports.SerialPortNames` property returns.</span></span> <span data-ttu-id="e769c-107">Estas cadenas son los nombres de los puertos serie disponibles en el equipo.</span><span class="sxs-lookup"><span data-stu-id="e769c-107">These strings are the names of the available serial ports on the computer.</span></span>  
  
 <span data-ttu-id="e769c-108">Normalmente, los usuarios seleccionan el puerto serie que la aplicación debe usar en la lista de puertos disponibles.</span><span class="sxs-lookup"><span data-stu-id="e769c-108">Typically, a user selects which serial port the application should use from the list of available ports.</span></span> <span data-ttu-id="e769c-109">En este ejemplo, los nombres de los puertos serie se almacenan en un control <xref:System.Windows.Forms.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="e769c-109">In this example, the serial port names are stored in a <xref:System.Windows.Forms.ListBox> control.</span></span> <span data-ttu-id="e769c-110">Para obtener más información, consulte [ListBox Control](/dotnet/desktop/winforms/controls/listbox-control-windows-forms) (Control ListBox).</span><span class="sxs-lookup"><span data-stu-id="e769c-110">For more information, see [ListBox Control](/dotnet/desktop/winforms/controls/listbox-control-windows-forms).</span></span>  
  
 [!code-vb[VbVbalrMyComputer#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#45)]  
  
 <span data-ttu-id="e769c-111">Este ejemplo de código también está disponible como fragmento de código de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="e769c-111">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="e769c-112">En el selector de fragmentos de código, se encuentra en **Conectividad y redes**.</span><span class="sxs-lookup"><span data-stu-id="e769c-112">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="e769c-113">Para obtener más información, vea [Code Snippets](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="e769c-113">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e769c-114">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="e769c-114">Compiling the Code</span></span>  

 <span data-ttu-id="e769c-115">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="e769c-115">This example requires:</span></span>  
  
- <span data-ttu-id="e769c-116">Una referencia de proyecto a System.Windows.Forms.dll.</span><span class="sxs-lookup"><span data-stu-id="e769c-116">A project reference to System.Windows.Forms.dll.</span></span>  
  
- <span data-ttu-id="e769c-117">Acceso a los miembros del espacio de nombres <xref:System.Windows.Forms>.</span><span class="sxs-lookup"><span data-stu-id="e769c-117">Access to the members of the <xref:System.Windows.Forms> namespace.</span></span> <span data-ttu-id="e769c-118">Agregue una instrucción `Imports` si no hay nombres de miembros completos en el código.</span><span class="sxs-lookup"><span data-stu-id="e769c-118">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="e769c-119">Para obtener más información, consulte [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="e769c-119">For more information, see [Imports Statement (.NET Namespace and Type)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
- <span data-ttu-id="e769c-120">Que su formulario tenga un control <xref:System.Windows.Forms.ListBox> denominado `ListBox1`.</span><span class="sxs-lookup"><span data-stu-id="e769c-120">That your form have a <xref:System.Windows.Forms.ListBox> control named `ListBox1`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e769c-121">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="e769c-121">Robust Programming</span></span>  

 <span data-ttu-id="e769c-122">No resulta necesario usar el control <xref:System.Windows.Forms.ListBox> para mostrar los nombres de los puertos serie disponibles.</span><span class="sxs-lookup"><span data-stu-id="e769c-122">You do not have to use the <xref:System.Windows.Forms.ListBox> control to display the available serial port names.</span></span> <span data-ttu-id="e769c-123">En su lugar, puede usar un <xref:System.Windows.Forms.ComboBox> u otro control.</span><span class="sxs-lookup"><span data-stu-id="e769c-123">Instead, you can use a <xref:System.Windows.Forms.ComboBox> or other control.</span></span> <span data-ttu-id="e769c-124">Si la aplicación no necesita una respuesta del usuario, puede usar un control <xref:System.Windows.Forms.TextBox> para mostrar la información.</span><span class="sxs-lookup"><span data-stu-id="e769c-124">If the application does not need a response from the user, you can use a <xref:System.Windows.Forms.TextBox> control to display the information.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e769c-125">Los nombres de puerto devueltos por `My.Computer.Ports.SerialPortNames` pueden ser incorrectos cuando la ejecución se realiza en Windows 98.</span><span class="sxs-lookup"><span data-stu-id="e769c-125">The port names returned by `My.Computer.Ports.SerialPortNames` may be incorrect when run on Windows 98.</span></span> <span data-ttu-id="e769c-126">Para evitar errores de aplicación, use el control de excepciones, como las instrucciones `Try...Catch...Finally` o `Using`, al usar los nombres de puerto para abrir puertos.</span><span class="sxs-lookup"><span data-stu-id="e769c-126">To prevent application errors, use exception handling, such as the `Try...Catch...Finally` statement or the `Using` statement, when using the port names to open ports.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e769c-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="e769c-127">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Ports>
- [<span data-ttu-id="e769c-128">Marcar a través de módems conectados a puertos serie</span><span class="sxs-lookup"><span data-stu-id="e769c-128">How to: Dial Modems Attached to Serial Ports</span></span>](how-to-dial-modems-attached-to-serial-ports.md)
- [<span data-ttu-id="e769c-129">Enviar cadenas a puertos serie</span><span class="sxs-lookup"><span data-stu-id="e769c-129">How to: Send Strings to Serial Ports</span></span>](how-to-send-strings-to-serial-ports.md)
- [<span data-ttu-id="e769c-130">Recibir cadenas de puertos serie</span><span class="sxs-lookup"><span data-stu-id="e769c-130">How to: Receive Strings From Serial Ports</span></span>](how-to-receive-strings-from-serial-ports.md)
