---
title: Filtrar Crear una aplicación de Windows Forms desde la línea de comandos
ms.date: 03/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, application development from command line
- Windows Forms, getting started
- Windows Forms, creating basic form
ms.assetid: 45ad3f8b-1c26-4c9f-91a9-3bb0759a47a4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5dc5c3425672dd71359edf61c5f8625d96ad09ce
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716951"
---
# <a name="how-to-create-a-windows-forms-application-from-the-command-line"></a><span data-ttu-id="24b34-102">Filtrar Crear una aplicación de Windows Forms desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="24b34-102">How to: Create a Windows Forms application from the command line</span></span>
<span data-ttu-id="24b34-103">Los procedimientos siguientes describen los pasos básicos que debe seguir para crear y ejecutar una aplicación de Windows Forms desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="24b34-103">The following procedures describe the basic steps that you must complete to create and run a Windows Forms application from the command line.</span></span> <span data-ttu-id="24b34-104">Visual Studio es altamente compatible con estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="24b34-104">There is extensive support for these procedures in Visual Studio.</span></span>  <span data-ttu-id="24b34-105">Consulte también [Tutorial: Control se hospeda en un Windows Forms en WPF](../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="24b34-105">Also see [Walkthrough: Hosting a Windows Forms Control in WPF](../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="24b34-106">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="24b34-106">Procedure</span></span>  
  
#### <a name="to-create-the-form"></a><span data-ttu-id="24b34-107">Para crear el formulario</span><span class="sxs-lookup"><span data-stu-id="24b34-107">To create the form</span></span>  
  
1.  <span data-ttu-id="24b34-108">En un archivo de código vacío, escriba las siguientes instrucciones import o using:</span><span class="sxs-lookup"><span data-stu-id="24b34-108">In an empty code file, type the following import or using statements:</span></span>  
  
     [!code-csharp[System.Windows.Forms.BasicForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BasicForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#2)]  
  
2.  <span data-ttu-id="24b34-109">Declare una clase llamada `Form1` que hereda de la clase Form.</span><span class="sxs-lookup"><span data-stu-id="24b34-109">Declare a class named `Form1` that inherits from the Form class.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BasicForm#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BasicForm#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#3)]  
  
3.  <span data-ttu-id="24b34-110">Cree un constructor predeterminado para `Form1`.</span><span class="sxs-lookup"><span data-stu-id="24b34-110">Create a default constructor for `Form1`.</span></span>  
  
     <span data-ttu-id="24b34-111">Agregará más código al constructor en un procedimiento posterior.</span><span class="sxs-lookup"><span data-stu-id="24b34-111">You will add more code to the constructor in a subsequent procedure.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BasicForm#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.BasicForm#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#4)]  
  
4.  <span data-ttu-id="24b34-112">Agregue un método `Main` a la clase.</span><span class="sxs-lookup"><span data-stu-id="24b34-112">Add a `Main` method to the class.</span></span>  
  
    1.  <span data-ttu-id="24b34-113">Aplicar el <xref:System.STAThreadAttribute> C# `Main` método para especificar la aplicación de Windows Forms es un contenedor uniproceso.</span><span class="sxs-lookup"><span data-stu-id="24b34-113">Apply the <xref:System.STAThreadAttribute> to the C# `Main` method to specify your Windows Forms application is a single-threaded apartment.</span></span> <span data-ttu-id="24b34-114">(El atributo no es necesario en Visual Basic, puesto que las aplicaciones de Windows forms desarrollado con el uso de Visual Basic un modelo de subprocesamiento controlado simple de forma predeterminada).</span><span class="sxs-lookup"><span data-stu-id="24b34-114">(The attribute is not necessary in Visual Basic, since Windows forms applications developed with Visual Basic use a single-threaded apartment model by default.)</span></span>  
  
    2.  <span data-ttu-id="24b34-115">Llame a <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> para aplicar estilos de sistema operativo a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="24b34-115">Call <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> to apply operating system styles to your application.</span></span>  
  
    3.  <span data-ttu-id="24b34-116">Cree una instancia del formulario y ejecútela.</span><span class="sxs-lookup"><span data-stu-id="24b34-116">Create an instance of the form and run it.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BasicForm#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.BasicForm#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#5)]  
  
#### <a name="to-compile-and-run-the-application"></a><span data-ttu-id="24b34-117">Para compilar y ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="24b34-117">To compile and run the application</span></span>  
  
1.  <span data-ttu-id="24b34-118">En el símbolo del sistema de .NET Framework, vaya al directorio donde creó la clase `Form1`.</span><span class="sxs-lookup"><span data-stu-id="24b34-118">At the .NET Framework command prompt, navigate to the directory you created the `Form1` class.</span></span>  
  
2.  <span data-ttu-id="24b34-119">Compile el formulario.</span><span class="sxs-lookup"><span data-stu-id="24b34-119">Compile the form.</span></span>  
  
    -   <span data-ttu-id="24b34-120">Si está utilizando C#, escriba: `csc form1.cs`</span><span class="sxs-lookup"><span data-stu-id="24b34-120">If you are using C#, type: `csc form1.cs`</span></span>  
  
         `-or-`  
  
    -   <span data-ttu-id="24b34-121">Si utiliza Visual Basic, escriba: `vbc form1.vb`</span><span class="sxs-lookup"><span data-stu-id="24b34-121">If you are using Visual Basic, type: `vbc form1.vb`</span></span>  
  
3.  <span data-ttu-id="24b34-122">En el símbolo del sistema, escriba: `Form1.exe`</span><span class="sxs-lookup"><span data-stu-id="24b34-122">At the command prompt, type: `Form1.exe`</span></span>  
  
## <a name="adding-a-control-and-handling-an-event"></a><span data-ttu-id="24b34-123">Agregar un control y controlar un evento</span><span class="sxs-lookup"><span data-stu-id="24b34-123">Adding a Control and Handling an Event</span></span>  
 <span data-ttu-id="24b34-124">Los pasos del procedimiento anterior muestran cómo crear un Windows Form básico que se compila y se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="24b34-124">The previous procedure steps demonstrated how to just create a basic Windows Form that compiles and runs.</span></span> <span data-ttu-id="24b34-125">El procedimiento siguiente mostrará cómo crear y agregar un control al formulario y cómo controlar un evento del control.</span><span class="sxs-lookup"><span data-stu-id="24b34-125">The next procedure will show you how to create and add a control to the form, and handle an event for the control.</span></span> <span data-ttu-id="24b34-126">Para obtener más información acerca de los controles que puede agregar a Windows Forms, consulte [controles de formularios Windows Forms](./controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="24b34-126">For more information about the controls you can add to Windows Forms, see [Windows Forms Controls](./controls/index.md).</span></span>  
  
 <span data-ttu-id="24b34-127">Además de comprender cómo se crean las aplicaciones de Windows Forms, debe conocer la programación basada en eventos y cómo controlar la entrada de datos del usuario.</span><span class="sxs-lookup"><span data-stu-id="24b34-127">In addition to understanding how to create Windows Forms applications, you should understand event-based programming and how to handle user input.</span></span> <span data-ttu-id="24b34-128">Para obtener más información, consulte [crear controladores de eventos en Windows Forms](creating-event-handlers-in-windows-forms.md), y [control proporcionados por el usuario](./controls/handling-user-input.md)</span><span class="sxs-lookup"><span data-stu-id="24b34-128">For more information, see [Creating Event Handlers in Windows Forms](creating-event-handlers-in-windows-forms.md), and [Handling User Input](./controls/handling-user-input.md)</span></span>  
  
#### <a name="to-declare-a-button-control-and-handle-its-click-event"></a><span data-ttu-id="24b34-129">Para declarar un control de botón y controlar su evento de clic</span><span class="sxs-lookup"><span data-stu-id="24b34-129">To declare a button control and handle its click event</span></span>  
  
1.  <span data-ttu-id="24b34-130">Declare un control de botón llamado `button1`.</span><span class="sxs-lookup"><span data-stu-id="24b34-130">Declare a button control named `button1`.</span></span>  
  
2.  <span data-ttu-id="24b34-131">En el constructor, cree el botón y establezca sus propiedades <xref:System.Windows.Forms.Control.Size%2A>, <xref:System.Windows.Forms.Control.Location%2A> y <xref:System.Windows.Forms.Control.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="24b34-131">In the constructor, create the button and set its <xref:System.Windows.Forms.Control.Size%2A>, <xref:System.Windows.Forms.Control.Location%2A> and <xref:System.Windows.Forms.Control.Text%2A> properties.</span></span>  
  
3.  <span data-ttu-id="24b34-132">Agregue el botón al formulario.</span><span class="sxs-lookup"><span data-stu-id="24b34-132">Add the button to the form.</span></span>  
  
     <span data-ttu-id="24b34-133">En el ejemplo de código siguiente se muestra cómo declarar el control de botón.</span><span class="sxs-lookup"><span data-stu-id="24b34-133">The following code example demonstrates how to declare the button control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.FormWithButton#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#2)]  
  
4.  <span data-ttu-id="24b34-134">Cree un método para controlar los eventos <xref:System.Windows.Forms.Control.Click> del botón.</span><span class="sxs-lookup"><span data-stu-id="24b34-134">Create a method to handle the <xref:System.Windows.Forms.Control.Click> event for the button.</span></span>  
  
5.  <span data-ttu-id="24b34-135">En el controlador de eventos de clic, muestre un <xref:System.Windows.Forms.MessageBox> con el mensaje "Hello World".</span><span class="sxs-lookup"><span data-stu-id="24b34-135">In the click event handler, display a <xref:System.Windows.Forms.MessageBox> with the message, "Hello World".</span></span>  
  
     <span data-ttu-id="24b34-136">En el ejemplo de código siguiente se muestra cómo controlar el evento de clic del control de botón.</span><span class="sxs-lookup"><span data-stu-id="24b34-136">The following code example demonstrates how to handle the button control's click event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.FormWithButton#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#3)]  
  
6.  <span data-ttu-id="24b34-137">Asocie el evento <xref:System.Windows.Forms.Control.Click> con el método que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="24b34-137">Associate the <xref:System.Windows.Forms.Control.Click> event with the method you created.</span></span>  
  
     <span data-ttu-id="24b34-138">En el ejemplo de código siguiente se muestra cómo asociar el evento con el método.</span><span class="sxs-lookup"><span data-stu-id="24b34-138">The following code example demonstrates how to associate the event with the method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.FormWithButton#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#4)]  
  
7.  <span data-ttu-id="24b34-139">Compile y ejecute la aplicación tal y como se describe en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="24b34-139">Compile and run the application as described in the previous procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24b34-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="24b34-140">Example</span></span>  
 <span data-ttu-id="24b34-141">El ejemplo de código siguiente es el ejemplo completo de los procedimientos anteriores.</span><span class="sxs-lookup"><span data-stu-id="24b34-141">Following code example is the complete example from the previous procedures.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FormWithButton#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.FormWithButton#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="24b34-142">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="24b34-142">Compiling the Code</span></span>  
  
-   <span data-ttu-id="24b34-143">Para compilar el código, siga las instrucciones del procedimiento siguiente que describen cómo compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="24b34-143">To compile the code, follow the instructions in the proceeding procedure that describe how to compile and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24b34-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="24b34-144">See also</span></span>
- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Control>
- [<span data-ttu-id="24b34-145">Cambiar la apariencia de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="24b34-145">Changing the Appearance of Windows Forms</span></span>](changing-the-appearance-of-windows-forms.md)
- [<span data-ttu-id="24b34-146">Mejorar las aplicaciones de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="24b34-146">Enhancing Windows Forms Applications</span></span>](./advanced/index.md)
- [<span data-ttu-id="24b34-147">Introducción a los formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="24b34-147">Getting Started with Windows Forms</span></span>](getting-started-with-windows-forms.md)
