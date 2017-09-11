---
title: "Cómo: Mostrar los puertos serie disponibles en Visual Basic"
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
- serial ports, availability
- My.Computer.Ports.SerialPortNames property
- My.Computer.Ports object
- ports, serial port availability
ms.assetid: eaf2ee5a-8103-4e10-a205-ed1d4db120ba
caps.latest.revision: 20
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
ms.openlocfilehash: bab6177c788a847b46586db19a525c1a1b36476d
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-show-available-serial-ports-in-visual-basic"></a><span data-ttu-id="8457c-102">Cómo: Mostrar los puertos serie disponibles en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8457c-102">How to: Show Available Serial Ports in Visual Basic</span></span>
<span data-ttu-id="8457c-103">En este tema se describe cómo usar `My.Computer.Ports` para mostrar los puertos serie disponibles del equipo en [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8457c-103">This topic describes how to use `My.Computer.Ports` to show the available serial ports of the computer in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
 <span data-ttu-id="8457c-104">Para permitir al usuario seleccionar qué puerto quiere usar, los nombres de los puertos serie se colocan en un control <xref:System.Windows.Forms.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="8457c-104">To allow a user to select which port to use, the names of the serial ports are placed in a <xref:System.Windows.Forms.ListBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8457c-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8457c-105">Example</span></span>  
 <span data-ttu-id="8457c-106">Este ejemplo recorre todas las cadenas que devuelve la propiedad `My.Computer.Ports.SerialPortNames`.</span><span class="sxs-lookup"><span data-stu-id="8457c-106">This example loops over all the strings that the `My.Computer.Ports.SerialPortNames` property returns.</span></span> <span data-ttu-id="8457c-107">Estas cadenas son los nombres de los puertos serie disponibles en el equipo.</span><span class="sxs-lookup"><span data-stu-id="8457c-107">These strings are the names of the available serial ports on the computer.</span></span>  
  
 <span data-ttu-id="8457c-108">Normalmente, los usuarios seleccionan el puerto serie que la aplicación debe usar en la lista de puertos disponibles.</span><span class="sxs-lookup"><span data-stu-id="8457c-108">Typically, a user selects which serial port the application should use from the list of available ports.</span></span> <span data-ttu-id="8457c-109">En este ejemplo, los nombres de los puertos serie se almacenan en un control <xref:System.Windows.Forms.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="8457c-109">In this example, the serial port names are stored in a <xref:System.Windows.Forms.ListBox> control.</span></span> <span data-ttu-id="8457c-110">Para obtener más información, consulte [ListBox Control](../../../../framework/winforms/controls/listbox-control-windows-forms.md) (Control ListBox).</span><span class="sxs-lookup"><span data-stu-id="8457c-110">For more information, see [ListBox Control](../../../../framework/winforms/controls/listbox-control-windows-forms.md).</span></span>  
  
 <span data-ttu-id="8457c-111">[!code-vb[VbVbalrMyComputer#45](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-show-available-serial-ports_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8457c-111">[!code-vb[VbVbalrMyComputer#45](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-show-available-serial-ports_1.vb)]</span></span>  
  
 <span data-ttu-id="8457c-112">Este ejemplo de código también está disponible como fragmento de código de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="8457c-112">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="8457c-113">En el selector de fragmentos de código, se encuentra en **Conectividad y redes**.</span><span class="sxs-lookup"><span data-stu-id="8457c-113">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="8457c-114">Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="8457c-114">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8457c-115">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="8457c-115">Compiling the Code</span></span>  
 <span data-ttu-id="8457c-116">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="8457c-116">This example requires:</span></span>  
  
-   <span data-ttu-id="8457c-117">Una referencia de proyecto a System.Windows.Forms.dll.</span><span class="sxs-lookup"><span data-stu-id="8457c-117">A project reference to System.Windows.Forms.dll.</span></span>  
  
-   <span data-ttu-id="8457c-118">Acceso a los miembros del espacio de nombres <xref:System.Windows.Forms>.</span><span class="sxs-lookup"><span data-stu-id="8457c-118">Access to the members of the <xref:System.Windows.Forms> namespace.</span></span> <span data-ttu-id="8457c-119">Agregue una instrucción `Imports` si no hay nombres de miembros completos en el código.</span><span class="sxs-lookup"><span data-stu-id="8457c-119">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="8457c-120">Para obtener más información, consulte [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="8457c-120">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
-   <span data-ttu-id="8457c-121">Que su formulario tenga un control <xref:System.Windows.Forms.ListBox> denominado `ListBox1`.</span><span class="sxs-lookup"><span data-stu-id="8457c-121">That your form have a <xref:System.Windows.Forms.ListBox> control named `ListBox1`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="8457c-122">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="8457c-122">Robust Programming</span></span>  
 <span data-ttu-id="8457c-123">No resulta necesario usar el control <xref:System.Windows.Forms.ListBox> para mostrar los nombres de los puertos serie disponibles.</span><span class="sxs-lookup"><span data-stu-id="8457c-123">You do not have to use the <xref:System.Windows.Forms.ListBox> control to display the available serial port names.</span></span> <span data-ttu-id="8457c-124">En su lugar, puede usar un <xref:System.Windows.Forms.ComboBox> u otro control.</span><span class="sxs-lookup"><span data-stu-id="8457c-124">Instead, you can use a <xref:System.Windows.Forms.ComboBox> or other control.</span></span> <span data-ttu-id="8457c-125">Si la aplicación no necesita una respuesta del usuario, puede usar un control <xref:System.Windows.Forms.TextBox> para mostrar la información.</span><span class="sxs-lookup"><span data-stu-id="8457c-125">If the application does not need a response from the user, you can use a <xref:System.Windows.Forms.TextBox> control to display the information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8457c-126">Los nombres de puerto devueltos por `My.Computer.Ports.SerialPortNames` pueden ser incorrectos cuando la ejecución se realiza en Windows 98.</span><span class="sxs-lookup"><span data-stu-id="8457c-126">The port names returned by `My.Computer.Ports.SerialPortNames` may be incorrect when run on Windows 98.</span></span> <span data-ttu-id="8457c-127">Para evitar errores de aplicación, use el control de excepciones, como las instrucciones `Try...Catch...Finally` o `Using`, al usar los nombres de puerto para abrir puertos.</span><span class="sxs-lookup"><span data-stu-id="8457c-127">To prevent application errors, use exception handling, such as the `Try...Catch...Finally` statement or the `Using` statement, when using the port names to open ports.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8457c-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="8457c-128">See Also</span></span>  
 <span data-ttu-id="8457c-129"><xref:Microsoft.VisualBasic.Devices.Ports></span><span class="sxs-lookup"><span data-stu-id="8457c-129"><xref:Microsoft.VisualBasic.Devices.Ports></span></span>   
 <span data-ttu-id="8457c-130">[Cómo: Marcar a través de módems conectados a puertos serie](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md) </span><span class="sxs-lookup"><span data-stu-id="8457c-130">[How to: Dial Modems Attached to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md) </span></span>  
 <span data-ttu-id="8457c-131">[Cómo: Enviar cadenas a puertos serie](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md) </span><span class="sxs-lookup"><span data-stu-id="8457c-131">[How to: Send Strings to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md) </span></span>  
 [<span data-ttu-id="8457c-132">Recibir cadenas de puertos serie</span><span class="sxs-lookup"><span data-stu-id="8457c-132">How to: Receive Strings From Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)

