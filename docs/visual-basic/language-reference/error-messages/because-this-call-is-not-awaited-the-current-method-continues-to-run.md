---
title: Como esta llamada no es "awaited", la ejecución del método actual continuará antes de que se complete la llamada.
ms.date: 07/20/2015
f1_keywords:
- bc42358
- vbc42358
helpviewer_keywords:
- BC42358
ms.assetid: 43342515-c3c8-4155-9263-c302afabcbc2
ms.openlocfilehash: fe820b9d2157c09428903a36427d3ff5e4c0045b
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2018
ms.locfileid: "45513734"
---
# <a name="because-this-call-is-not-awaited-the-current-method-continues-to-run-before-the-call-is-completed"></a><span data-ttu-id="b1845-102">Como esta llamada no es "awaited", la ejecución del método actual continuará antes de que se complete la llamada.</span><span class="sxs-lookup"><span data-stu-id="b1845-102">Because this call is not awaited, the current method continues to run before the call is completed</span></span>
<span data-ttu-id="b1845-103">Dado que no se esperaba esta llamada, la ejecución del método actual continuará antes de que se complete la llamada.</span><span class="sxs-lookup"><span data-stu-id="b1845-103">Because this call is not awaited, execution of the current method continues before the call is completed.</span></span> <span data-ttu-id="b1845-104">Considere la posibilidad de aplicar el operador "Await" al resultado de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b1845-104">Consider applying the 'Await' operator to the result of the call.</span></span>  
  
 <span data-ttu-id="b1845-105">El método actual llama a un método asincrónico que devuelve un valor <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> y no aplica el operador [Await](../../../visual-basic/language-reference/operators/await-operator.md) al resultado.</span><span class="sxs-lookup"><span data-stu-id="b1845-105">The current method calls an async method that returns a <xref:System.Threading.Tasks.Task> or a <xref:System.Threading.Tasks.Task%601> and doesn’t apply the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator to the result.</span></span> <span data-ttu-id="b1845-106">La llamada al método asincrónico inicia una tarea asincrónica.</span><span class="sxs-lookup"><span data-stu-id="b1845-106">The call to the async method starts an asynchronous task.</span></span> <span data-ttu-id="b1845-107">Pero, dado que no se aplica un operador `Await` , el programa continúa sin esperar a que se complete la tarea.</span><span class="sxs-lookup"><span data-stu-id="b1845-107">However, because no `Await` operator is applied, the program continues without waiting for the task to complete.</span></span> <span data-ttu-id="b1845-108">En la mayoría de los casos, no se espera ese comportamiento.</span><span class="sxs-lookup"><span data-stu-id="b1845-108">In most cases, that behavior isn't expected.</span></span> <span data-ttu-id="b1845-109">Normalmente otros aspectos del método de llamada dependen de los resultados de la llamada o, como mínimo, se espera que el método llamado se complete antes de volver del método que contiene la llamada.</span><span class="sxs-lookup"><span data-stu-id="b1845-109">Usually other aspects of the calling method depend on the results of the call or, minimally, the called method is expected to complete before you return from the method that contains the call.</span></span>  
  
 <span data-ttu-id="b1845-110">Otro problema igual de importante es lo que sucede con las excepciones que se producen en el método asincrónico llamado.</span><span class="sxs-lookup"><span data-stu-id="b1845-110">An equally important issue is what happens with exceptions that are raised in the called async method.</span></span> <span data-ttu-id="b1845-111">Una excepción que aparece en un método que devuelve un valor <xref:System.Threading.Tasks.Task> o  <xref:System.Threading.Tasks.Task%601> se almacena en la tarea devuelta.</span><span class="sxs-lookup"><span data-stu-id="b1845-111">An exception that’s raised in a method that returns a <xref:System.Threading.Tasks.Task> or  <xref:System.Threading.Tasks.Task%601> is stored in the returned task.</span></span> <span data-ttu-id="b1845-112">Si no espera la tarea o comprueba explícitamente las excepciones, se perderá la excepción.</span><span class="sxs-lookup"><span data-stu-id="b1845-112">If you don't await the task or explicitly check for exceptions, the exception is lost.</span></span> <span data-ttu-id="b1845-113">Si espera la tarea, su excepción se volverá a producir.</span><span class="sxs-lookup"><span data-stu-id="b1845-113">If you await the task, its exception is rethrown.</span></span>  
  
 <span data-ttu-id="b1845-114">El procedimiento recomendado es esperar siempre la llamada.</span><span class="sxs-lookup"><span data-stu-id="b1845-114">As a best practice, you should always await the call.</span></span>  
  
 <span data-ttu-id="b1845-115">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="b1845-115">By default, this message is a warning.</span></span> <span data-ttu-id="b1845-116">Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="b1845-116">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="b1845-117">**Identificador de error:** BC42358</span><span class="sxs-lookup"><span data-stu-id="b1845-117">**Error ID:** BC42358</span></span>  
  
### <a name="to-address-this-warning"></a><span data-ttu-id="b1845-118">Para resolver esta advertencia</span><span class="sxs-lookup"><span data-stu-id="b1845-118">To address this warning</span></span>  
  
-   <span data-ttu-id="b1845-119">Considere la posibilidad de suprimir la advertencia solamente si está seguro de que no quiere esperar a que se complete la llamada asincrónica y que el método llamado no producirá excepciones.</span><span class="sxs-lookup"><span data-stu-id="b1845-119">You should consider suppressing the warning only if you're sure that you don't want to wait for the asynchronous call to complete and that the called method won't raise any exceptions.</span></span> <span data-ttu-id="b1845-120">En ese caso, puede suprimir la advertencia asignando el resultado de la tarea de la llamada a una variable.</span><span class="sxs-lookup"><span data-stu-id="b1845-120">In that case, you can suppress the warning by assigning the task result of the call to a variable.</span></span>  
  
     <span data-ttu-id="b1845-121">En el ejemplo siguiente se muestra cómo provocar la advertencia, cómo suprimirla y cómo esperar la llamada.</span><span class="sxs-lookup"><span data-stu-id="b1845-121">The following example shows how to cause the warning, how to suppress it, and how to await the call.</span></span>  
  
    ```vb  
    Async Function CallingMethodAsync() As Task  
  
        ResultsTextBox.Text &= vbCrLf & "  Entering calling method."  
  
        ' Variable delay is used to slow down the called method so that you  
        ' can distinguish between awaiting and not awaiting in the program's output.   
        ' You can adjust the value to produce the output that this topic shows   
        ' after the code.  
        Dim delay = 5000  
  
        ' Call #1.  
        ' Call an async method. Because you don't await it, its completion isn't   
        ' coordinated with the current method, CallingMethodAsync.  
        ' The following line causes the warning.  
        CalledMethodAsync(delay)  
  
        ' Call #2.  
        ' To suppress the warning without awaiting, you can assign the   
        ' returned task to a variable. The assignment doesn't change how  
        ' the program runs. However, the recommended practice is always to  
        ' await a call to an async method.  
        ' Replace Call #1 with the following line.  
        'Task delayTask = CalledMethodAsync(delay)  
  
        ' Call #3  
        ' To contrast with an awaited call, replace the unawaited call   
        ' (Call #1 or Call #2) with the following awaited call. The best   
        ' practice is to await the call.  
  
        'Await CalledMethodAsync(delay)  
  
        ' If the call to CalledMethodAsync isn't awaited, CallingMethodAsync  
        ' continues to run and, in this example, finishes its work and returns  
        ' to its caller.  
        ResultsTextBox.Text &= vbCrLf & "  Returning from calling method."  
    End Function  
  
    Async Function CalledMethodAsync(howLong As Integer) As Task  
  
        ResultsTextBox.Text &= vbCrLf & "    Entering called method, starting and awaiting Task.Delay."  
        ' Slow the process down a little so you can distinguish between awaiting  
        ' and not awaiting. Adjust the value for howLong if necessary.  
        Await Task.Delay(howLong)  
        ResultsTextBox.Text &= vbCrLf & "    Task.Delay is finished--returning from called method."  
    End Function  
    ```  
  
     <span data-ttu-id="b1845-122">En el ejemplo, si elige Call #1 o Call #2, el método asincrónico no esperado (`CalledMethodAsync`) termina después de que se completen su llamador (`CallingMethodAsync`) y el llamador del llamador (`StartButton_Click`).</span><span class="sxs-lookup"><span data-stu-id="b1845-122">In the example, if you choose Call #1 or Call #2, the unawaited async method (`CalledMethodAsync`) finishes after both its caller (`CallingMethodAsync`) and the caller's caller (`StartButton_Click`) are complete.</span></span> <span data-ttu-id="b1845-123">La última línea de la salida siguiente muestra cuándo finaliza el método llamado.</span><span class="sxs-lookup"><span data-stu-id="b1845-123">The last line in the following output shows you when the called method finishes.</span></span> <span data-ttu-id="b1845-124">La entrada y la salida del controlador de eventos que llama a `CallingMethodAsync` en el ejemplo completo se marcan en la salida.</span><span class="sxs-lookup"><span data-stu-id="b1845-124">Entry to and exit from the event handler that calls `CallingMethodAsync` in the full example are marked in the output.</span></span>  
  
    ```  
    Entering the Click event handler.  
      Entering calling method.  
        Entering called method, starting and awaiting Task.Delay.  
      Returning from calling method.  
    Exiting the Click event handler.  
        Task.Delay is finished--returning from called method.  
    ```  
  
## <a name="example"></a><span data-ttu-id="b1845-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b1845-125">Example</span></span>  
 <span data-ttu-id="b1845-126">La siguiente aplicación de Windows Presentation Foundation (WPF) contiene los métodos del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="b1845-126">The following Windows Presentation Foundation (WPF) application contains the methods from the previous example.</span></span> <span data-ttu-id="b1845-127">Los siguientes pasos sirven para configurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b1845-127">The following steps set up the application.</span></span>  
  
1.  <span data-ttu-id="b1845-128">Cree una aplicación WPF y asígnele el nombre `AsyncWarning`.</span><span class="sxs-lookup"><span data-stu-id="b1845-128">Create a WPF application, and name it `AsyncWarning`.</span></span>  
  
2.  <span data-ttu-id="b1845-129">En el Editor de código de Visual Studio, elija la pestaña **MainWindow.xaml** .</span><span class="sxs-lookup"><span data-stu-id="b1845-129">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
     <span data-ttu-id="b1845-130">Si la pestaña no está visible, abra el menú contextual de MainWindow.xaml en el **Explorador de soluciones**y elija **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="b1845-130">If the tab isn't visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **View Code**.</span></span>  
  
3.  <span data-ttu-id="b1845-131">Reemplace el código de la vista **XAML** de MainWindow.xaml por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="b1845-131">Replace the code in the **XAML** view of MainWindow.xaml with the following code.</span></span>  
  
    ```vb  
    <Window x:Class="MainWindow"  
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
            Title="MainWindow" Height="350" Width="525">  
        <Grid>  
            <Button x:Name="StartButton" Content="Start" HorizontalAlignment="Left" Margin="214,28,0,0" VerticalAlignment="Top" Width="75" HorizontalContentAlignment="Center" FontWeight="Bold" FontFamily="Aharoni" Click="StartButton_Click" />  
            <TextBox x:Name="ResultsTextBox" Margin="0,80,0,0" TextWrapping="Wrap" FontFamily="Lucida Console"/>  
        </Grid>  
    </Window>  
    ```  
  
     <span data-ttu-id="b1845-132">En la vista **Diseño** de MainWindow.xaml aparece una ventana simple que contiene un botón y un cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="b1845-132">A simple window that contains a button and a text box appears in the **Design** view of MainWindow.xaml.</span></span>  
  
     <span data-ttu-id="b1845-133">Para obtener más información sobre el Diseñador XAML, vea [Tutorial: Crear una IU usando el Diseñador XAML](/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="b1845-133">For more information about the XAML Designer, see [Creating a UI by using XAML Designer](/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span></span> <span data-ttu-id="b1845-134">Para obtener información sobre cómo crear su propia interfaz de usuario simple, vea las secciones "To create a WPF application" (Para crear una aplicación WPF) y "To design a simple WPF MainWindow" (Para diseñar una ventana MainWindow simple de WPF) de [Walkthrough: Accessing the Web by Using Async and Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) (Tutorial: Acceso a la web usando async y await).</span><span class="sxs-lookup"><span data-stu-id="b1845-134">For information about how to build your own simple UI, see the "To create a WPF application" and "To design a simple WPF MainWindow" sections of [Walkthrough: Accessing the Web by Using Async and Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>  
  
4.  <span data-ttu-id="b1845-135">Reemplace el código en el archivo MainWindow.xaml.vb por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="b1845-135">Replace the code in MainWindow.xaml.vb with the following code.</span></span>  
  
    ```vb  
    Class MainWindow   
  
        Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)  
  
            ResultsTextBox.Text &= vbCrLf & "Entering the Click event handler."  
            Await CallingMethodAsync()  
            ResultsTextBox.Text &= vbCrLf & "Exiting the Click event handler."  
        End Sub  
  
        Async Function CallingMethodAsync() As Task  
  
            ResultsTextBox.Text &= vbCrLf & "  Entering calling method."  
  
            ' Variable delay is used to slow down the called method so that you  
            ' can distinguish between awaiting and not awaiting in the program's output.   
            ' You can adjust the value to produce the output that this topic shows   
            ' after the code.  
            Dim delay = 5000  
  
            ' Call #1.  
            ' Call an async method. Because you don't await it, its completion isn't   
            ' coordinated with the current method, CallingMethodAsync.  
            ' The following line causes the warning.  
            CalledMethodAsync(delay)  
  
            ' Call #2.  
            ' To suppress the warning without awaiting, you can assign the   
            ' returned task to a variable. The assignment doesn't change how  
            ' the program runs. However, the recommended practice is always to  
            ' await a call to an async method.  
  
            ' Replace Call #1 with the following line.  
            'Task delayTask = CalledMethodAsync(delay)  
  
            ' Call #3  
            ' To contrast with an awaited call, replace the unawaited call   
            ' (Call #1 or Call #2) with the following awaited call. The best   
            ' practice is to await the call.  
  
            'Await CalledMethodAsync(delay)  
  
            ' If the call to CalledMethodAsync isn't awaited, CallingMethodAsync  
            ' continues to run and, in this example, finishes its work and returns  
            ' to its caller.  
            ResultsTextBox.Text &= vbCrLf & "  Returning from calling method."  
        End Function  
  
        Async Function CalledMethodAsync(howLong As Integer) As Task  
  
            ResultsTextBox.Text &= vbCrLf & "    Entering called method, starting and awaiting Task.Delay."  
            ' Slow the process down a little so you can distinguish between awaiting  
            ' and not awaiting. Adjust the value for howLong if necessary.  
            Await Task.Delay(howLong)  
            ResultsTextBox.Text &= vbCrLf & "    Task.Delay is finished--returning from called method."  
        End Function  
  
    End Class  
  
    ' Output  
  
    ' Entering the Click event handler.  
    '   Entering calling method.  
    '     Entering called method, starting and awaiting Task.Delay.  
    '   Returning from calling method.  
    ' Exiting the Click event handler.  
    '     Task.Delay is finished--returning from called method.  
  
    ' Output  
  
    ' Entering the Click event handler.  
    '   Entering calling method.  
    '     Entering called method, starting and awaiting Task.Delay.  
    '     Task.Delay is finished--returning from called method.  
    '   Returning from calling method.  
    ' Exiting the Click event handler.  
    ```  
  
5.  <span data-ttu-id="b1845-136">Presione la tecla F5 para ejecutar el programa y elija el botón **Inicio** .</span><span class="sxs-lookup"><span data-stu-id="b1845-136">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="b1845-137">La salida esperada aparece al final del código.</span><span class="sxs-lookup"><span data-stu-id="b1845-137">The expected output appears at the end of the code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1845-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1845-138">See also</span></span>

- [<span data-ttu-id="b1845-139">Await (operador)</span><span class="sxs-lookup"><span data-stu-id="b1845-139">Await Operator</span></span>](../../../visual-basic/language-reference/operators/await-operator.md)  
- [<span data-ttu-id="b1845-140">Programación asincrónica con Async y Await</span><span class="sxs-lookup"><span data-stu-id="b1845-140">Asynchronous Programming with Async and Await</span></span>](../../../visual-basic/programming-guide/concepts/async/index.md)
