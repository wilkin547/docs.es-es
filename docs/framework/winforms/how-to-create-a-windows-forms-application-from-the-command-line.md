---
title: Creación de una aplicación Windows Forms desde la línea de comandos
titleSuffix: ''
ms.date: 03/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, application development from command line
- Windows Forms, getting started
- Windows Forms, creating basic form
ms.assetid: 45ad3f8b-1c26-4c9f-91a9-3bb0759a47a4
ms.openlocfilehash: da6b9da53a36a44233dde4f0d1c4f147d913c7cf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739529"
---
# <a name="how-to-create-a-windows-forms-application-from-the-command-line"></a><span data-ttu-id="20e29-102">Cómo: crear una aplicación de Windows Forms desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="20e29-102">How to: Create a Windows Forms application from the command line</span></span>

<span data-ttu-id="20e29-103">Los procedimientos siguientes describen los pasos básicos que debe seguir para crear y ejecutar una aplicación de Windows Forms desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="20e29-103">The following procedures describe the basic steps that you must complete to create and run a Windows Forms application from the command line.</span></span> <span data-ttu-id="20e29-104">Visual Studio es altamente compatible con estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="20e29-104">There is extensive support for these procedures in Visual Studio.</span></span>  <span data-ttu-id="20e29-105">Vea también [Tutorial: hospedar un control de Windows Forms en WPF](../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="20e29-105">Also see [Walkthrough: Hosting a Windows Forms Control in WPF](../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>
  
## <a name="procedure"></a><span data-ttu-id="20e29-106">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="20e29-106">Procedure</span></span>  
  
#### <a name="to-create-the-form"></a><span data-ttu-id="20e29-107">Para crear el formulario</span><span class="sxs-lookup"><span data-stu-id="20e29-107">To create the form</span></span>  
  
1. <span data-ttu-id="20e29-108">En un archivo de código vacío, escriba las instrucciones `Imports` o `using` siguientes:</span><span class="sxs-lookup"><span data-stu-id="20e29-108">In an empty code file, type the following `Imports` or `using` statements:</span></span>  
  
     [!code-csharp[System.Windows.Forms.BasicForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BasicForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#2)]  
  
2. <span data-ttu-id="20e29-109">Declare una clase denominada `Form1` que herede de la clase de formulario:</span><span class="sxs-lookup"><span data-stu-id="20e29-109">Declare a class named `Form1` that inherits from the Form class:</span></span>
  
     [!code-csharp[System.Windows.Forms.BasicForm#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BasicForm#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#3)]  
  
3. <span data-ttu-id="20e29-110">Cree un constructor sin parámetros para `Form1`.</span><span class="sxs-lookup"><span data-stu-id="20e29-110">Create a parameterless constructor for `Form1`.</span></span>
  
     <span data-ttu-id="20e29-111">Agregará más código al constructor en un procedimiento posterior.</span><span class="sxs-lookup"><span data-stu-id="20e29-111">You will add more code to the constructor in a subsequent procedure.</span></span>
  
     [!code-csharp[System.Windows.Forms.BasicForm#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.BasicForm#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#4)]  
  
4. <span data-ttu-id="20e29-112">Agregue un método `Main` a la clase.</span><span class="sxs-lookup"><span data-stu-id="20e29-112">Add a `Main` method to the class.</span></span>
  
    1. <span data-ttu-id="20e29-113">Aplique el <xref:System.STAThreadAttribute> al método C# `Main` para especificar que la aplicación Windows Forms es un contenedor uniproceso.</span><span class="sxs-lookup"><span data-stu-id="20e29-113">Apply the <xref:System.STAThreadAttribute> to the C# `Main` method to specify your Windows Forms application is a single-threaded apartment.</span></span> <span data-ttu-id="20e29-114">(El atributo no es necesario en Visual Basic, ya que las aplicaciones de Windows Forms desarrolladas con Visual Basic usan de forma predeterminada un modelo de apartamento de un solo subproceso).</span><span class="sxs-lookup"><span data-stu-id="20e29-114">(The attribute is not necessary in Visual Basic, since Windows forms applications developed with Visual Basic use a single-threaded apartment model by default.)</span></span>  
  
    2. <span data-ttu-id="20e29-115">Llame a <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> para aplicar estilos de sistema operativo a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="20e29-115">Call <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> to apply operating system styles to your application.</span></span>  
  
    3. <span data-ttu-id="20e29-116">Cree una instancia del formulario y ejecútela.</span><span class="sxs-lookup"><span data-stu-id="20e29-116">Create an instance of the form and run it.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BasicForm#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.BasicForm#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#5)]  
  
#### <a name="to-compile-and-run-the-application"></a><span data-ttu-id="20e29-117">Para compilar y ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="20e29-117">To compile and run the application</span></span>  
  
1. <span data-ttu-id="20e29-118">En el símbolo del sistema de .NET Framework, vaya al directorio donde creó la clase `Form1`.</span><span class="sxs-lookup"><span data-stu-id="20e29-118">At the .NET Framework command prompt, navigate to the directory you created the `Form1` class.</span></span>  
  
2. <span data-ttu-id="20e29-119">Compile el formulario.</span><span class="sxs-lookup"><span data-stu-id="20e29-119">Compile the form.</span></span>  
  
    - <span data-ttu-id="20e29-120">Si usa C#, escriba: `csc form1.cs`</span><span class="sxs-lookup"><span data-stu-id="20e29-120">If you are using C#, type: `csc form1.cs`</span></span>  
  
         `-or-`  
  
    - <span data-ttu-id="20e29-121">Si está utilizando Visual Basic, escriba: `vbc form1.vb`</span><span class="sxs-lookup"><span data-stu-id="20e29-121">If you are using Visual Basic, type: `vbc form1.vb`</span></span>  
  
3. <span data-ttu-id="20e29-122">En el símbolo del sistema, escriba: `Form1.exe`</span><span class="sxs-lookup"><span data-stu-id="20e29-122">At the command prompt, type: `Form1.exe`</span></span>  
  
## <a name="adding-a-control-and-handling-an-event"></a><span data-ttu-id="20e29-123">Agregar un control y controlar un evento</span><span class="sxs-lookup"><span data-stu-id="20e29-123">Adding a control and handling an event</span></span>

<span data-ttu-id="20e29-124">Los pasos del procedimiento anterior muestran cómo crear un Windows Form básico que se compila y se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="20e29-124">The previous procedure steps demonstrated how to just create a basic Windows Form that compiles and runs.</span></span> <span data-ttu-id="20e29-125">El procedimiento siguiente mostrará cómo crear y agregar un control al formulario y cómo controlar un evento del control.</span><span class="sxs-lookup"><span data-stu-id="20e29-125">The next procedure will show you how to create and add a control to the form, and handle an event for the control.</span></span> <span data-ttu-id="20e29-126">Para obtener más información sobre los controles que se pueden agregar a Windows Forms, vea [controles de Windows Forms](./controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="20e29-126">For more information about the controls you can add to Windows Forms, see [Windows Forms Controls](./controls/index.md).</span></span>
  
 <span data-ttu-id="20e29-127">Además de comprender cómo se crean las aplicaciones de Windows Forms, debe conocer la programación basada en eventos y cómo controlar la entrada de datos del usuario.</span><span class="sxs-lookup"><span data-stu-id="20e29-127">In addition to understanding how to create Windows Forms applications, you should understand event-based programming and how to handle user input.</span></span> <span data-ttu-id="20e29-128">Para obtener más información, vea [crear controladores de eventos en Windows Forms](creating-event-handlers-in-windows-forms.md)y [controlar los datos proporcionados](./controls/handling-user-input.md) por el usuario.</span><span class="sxs-lookup"><span data-stu-id="20e29-128">For more information, see [Creating Event Handlers in Windows Forms](creating-event-handlers-in-windows-forms.md), and [Handling User Input](./controls/handling-user-input.md)</span></span>  
  
#### <a name="to-declare-a-button-control-and-handle-its-click-event"></a><span data-ttu-id="20e29-129">Para declarar un control de botón y controlar su evento de clic</span><span class="sxs-lookup"><span data-stu-id="20e29-129">To declare a button control and handle its click event</span></span>  
  
1. <span data-ttu-id="20e29-130">Declare un control de botón llamado `button1`.</span><span class="sxs-lookup"><span data-stu-id="20e29-130">Declare a button control named `button1`.</span></span>  
  
2. <span data-ttu-id="20e29-131">En el constructor, cree el botón y establezca sus propiedades <xref:System.Windows.Forms.Control.Size%2A>, <xref:System.Windows.Forms.Control.Location%2A> y <xref:System.Windows.Forms.Control.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="20e29-131">In the constructor, create the button and set its <xref:System.Windows.Forms.Control.Size%2A>, <xref:System.Windows.Forms.Control.Location%2A> and <xref:System.Windows.Forms.Control.Text%2A> properties.</span></span>  
  
3. <span data-ttu-id="20e29-132">Agregue el botón al formulario.</span><span class="sxs-lookup"><span data-stu-id="20e29-132">Add the button to the form.</span></span>  
  
     <span data-ttu-id="20e29-133">En el ejemplo de código siguiente se muestra cómo declarar el control de botón:</span><span class="sxs-lookup"><span data-stu-id="20e29-133">The following code example demonstrates how to declare the button control:</span></span>
  
     [!code-csharp[System.Windows.Forms.FormWithButton#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.FormWithButton#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#2)]  
  
4. <span data-ttu-id="20e29-134">Cree un método para controlar los eventos <xref:System.Windows.Forms.Control.Click> del botón.</span><span class="sxs-lookup"><span data-stu-id="20e29-134">Create a method to handle the <xref:System.Windows.Forms.Control.Click> event for the button.</span></span>  
  
5. <span data-ttu-id="20e29-135">En el controlador de eventos de clic, muestre un <xref:System.Windows.Forms.MessageBox> con el mensaje "Hello World".</span><span class="sxs-lookup"><span data-stu-id="20e29-135">In the click event handler, display a <xref:System.Windows.Forms.MessageBox> with the message, "Hello World".</span></span>  
  
     <span data-ttu-id="20e29-136">En el ejemplo de código siguiente se muestra cómo controlar el evento click del control Button:</span><span class="sxs-lookup"><span data-stu-id="20e29-136">The following code example demonstrates how to handle the button control's click event:</span></span>
  
     [!code-csharp[System.Windows.Forms.FormWithButton#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.FormWithButton#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#3)]  
  
6. <span data-ttu-id="20e29-137">Asocie el evento <xref:System.Windows.Forms.Control.Click> con el método que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="20e29-137">Associate the <xref:System.Windows.Forms.Control.Click> event with the method you created.</span></span>  
  
     <span data-ttu-id="20e29-138">En el ejemplo de código siguiente se muestra cómo asociar el evento con el método.</span><span class="sxs-lookup"><span data-stu-id="20e29-138">The following code example demonstrates how to associate the event with the method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.FormWithButton#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#4)]  
  
7. <span data-ttu-id="20e29-139">Compile y ejecute la aplicación tal y como se describe en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="20e29-139">Compile and run the application as described in the previous procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20e29-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="20e29-140">Example</span></span>  
 
<span data-ttu-id="20e29-141">El ejemplo de código siguiente es el ejemplo completo de los procedimientos anteriores:</span><span class="sxs-lookup"><span data-stu-id="20e29-141">The following code example is the complete example from the previous procedures:</span></span>
  
 [!code-csharp[System.Windows.Forms.FormWithButton#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.FormWithButton#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="20e29-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="20e29-142">See also</span></span>

- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Control>
- [<span data-ttu-id="20e29-143">Cambiar la apariencia de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="20e29-143">Changing the Appearance of Windows Forms</span></span>](changing-the-appearance-of-windows-forms.md)
- [<span data-ttu-id="20e29-144">Mejorar las aplicaciones de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="20e29-144">Enhancing Windows Forms Applications</span></span>](./advanced/index.md)
- [<span data-ttu-id="20e29-145">Introducción a los formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="20e29-145">Getting Started with Windows Forms</span></span>](getting-started-with-windows-forms.md)
