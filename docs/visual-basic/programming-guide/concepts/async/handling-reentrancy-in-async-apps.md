---
description: Más información acerca de cómo controlar la reentrada en aplicaciones asincrónicas (Visual Basic)
title: Controlar la reentrada en aplicaciones asincrónicas
ms.date: 07/20/2015
ms.assetid: ef3dc73d-13fb-4c5f-a686-6b84148bbffe
ms.openlocfilehash: aca917c1b22655547f155009c5877140d9ca5e43
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100425807"
---
# <a name="handling-reentrancy-in-async-apps-visual-basic"></a><span data-ttu-id="02314-103">Handling Reentrancy in Async Apps (Visual Basic) (Control de reentrada en aplicaciones asincrónicas [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="02314-103">Handling Reentrancy in Async Apps (Visual Basic)</span></span>

<span data-ttu-id="02314-104">Cuando se incluye código asincrónico en una aplicación, hay que tener en cuenta (y posiblemente evitar) la reentrada, que significa volver a especificar una operación asincrónica antes de que finalice.</span><span class="sxs-lookup"><span data-stu-id="02314-104">When you include asynchronous code in your app, you should consider and possibly prevent reentrancy, which refers to reentering an asynchronous operation before it has completed.</span></span> <span data-ttu-id="02314-105">Si no se identifican ni controlan las posibilidades de reentrada, pueden producirse resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="02314-105">If you don't identify and handle possibilities for reentrancy, it can cause unexpected results.</span></span>

> [!NOTE]
> <span data-ttu-id="02314-106">Para ejecutar el ejemplo, debe tener instalado en el equipo Visual Studio 2012 o posterior y .NET Framework 4.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="02314-106">To run the example, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

> [!NOTE]
> <span data-ttu-id="02314-107">La versión 1.2 de Seguridad de la capa de transporte (TLS) es ahora la versión mínima que se usará en el desarrollo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="02314-107">Transport Layer Security (TLS) version 1.2 is now the minimum version to use in your app development.</span></span> <span data-ttu-id="02314-108">Si la aplicación tiene como destino una versión de .NET Framework anterior a la 4.7, consulte el artículo siguiente para obtener [Prácticas recomendadas de Seguridad de la capa de transporte (TLS) con .NET Framework](../../../../framework/network-programming/tls.md).</span><span class="sxs-lookup"><span data-stu-id="02314-108">If your app targets a .NET Framework version earlier than 4.7, refer to the following article for [Transport Layer Security (TLS) best practices with the .NET Framework](../../../../framework/network-programming/tls.md).</span></span>

## <a name="recognizing-reentrancy"></a><a name="BKMK_RecognizingReentrancy"></a> <span data-ttu-id="02314-109">Reconocer la reentrada</span><span class="sxs-lookup"><span data-stu-id="02314-109">Recognizing Reentrancy</span></span>

<span data-ttu-id="02314-110">En el ejemplo de este tema, los usuarios hacen clic en un botón **Start** (Iniciar) para iniciar una aplicación asincrónica que descarga una serie de sitios web y calcula el número total de bytes que se descargan.</span><span class="sxs-lookup"><span data-stu-id="02314-110">In the example in this topic, users choose a **Start** button to initiate an asynchronous app that downloads a series of websites and calculates the total number of bytes that are downloaded.</span></span> <span data-ttu-id="02314-111">Una versión sincrónica del ejemplo respondería de la misma forma independientemente de cuántas veces un usuario elija el botón porque, tras la primera vez, el subproceso de UI omite esos eventos hasta que finaliza la ejecución de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="02314-111">A synchronous version of the example would respond the same way regardless of how many times a user chooses the button because, after the first time, the UI thread ignores those events until the app finishes running.</span></span> <span data-ttu-id="02314-112">Sin embargo, en una aplicación asincrónica, el subproceso de UI continúa respondiendo y podría volver a introducir la operación asincrónica antes de que finalice.</span><span class="sxs-lookup"><span data-stu-id="02314-112">In an asynchronous app, however, the UI thread continues to respond, and you might reenter the asynchronous operation before it has completed.</span></span>

<span data-ttu-id="02314-113">En el ejemplo siguiente se muestra la salida esperada si el usuario hace clic en el botón **Start** una sola vez.</span><span class="sxs-lookup"><span data-stu-id="02314-113">The following example shows the expected output if the user chooses the **Start** button only once.</span></span> <span data-ttu-id="02314-114">Aparece una lista de los sitios web descargados con el tamaño, en bytes, de cada sitio.</span><span class="sxs-lookup"><span data-stu-id="02314-114">A list of the downloaded websites appears with the size, in bytes, of each site.</span></span> <span data-ttu-id="02314-115">El número total de bytes aparece al final.</span><span class="sxs-lookup"><span data-stu-id="02314-115">The total number of bytes appears at the end.</span></span>

```console
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               117152
5. msdn.microsoft.com/library/hh524395.aspx                68959
6. msdn.microsoft.com/library/ms404677.aspx               197325
7. msdn.microsoft.com                                            42972
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591
```

<span data-ttu-id="02314-116">Sin embargo, si el usuario elige el botón más de una vez, el controlador de eventos se invoca repetidamente y el proceso de descarga se vuelve a introducir cada vez.</span><span class="sxs-lookup"><span data-stu-id="02314-116">However, if the user chooses the button more than once, the event handler is invoked repeatedly, and the download process is reentered each time.</span></span> <span data-ttu-id="02314-117">Como resultado, se ejecutan varias operaciones asincrónicas al mismo tiempo, la salida intercala los resultados y el número total de bytes es confuso.</span><span class="sxs-lookup"><span data-stu-id="02314-117">As a result, several asynchronous operations are running at the same time, the output interleaves the results, and the total number of bytes is confusing.</span></span>

```console
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               117152
5. msdn.microsoft.com/library/hh524395.aspx                68959
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
6. msdn.microsoft.com/library/ms404677.aspx               197325
3. msdn.microsoft.com/library/jj155761.aspx                29019
7. msdn.microsoft.com                                            42972
4. msdn.microsoft.com/library/hh290140.aspx               117152
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591

5. msdn.microsoft.com/library/hh524395.aspx                68959
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
6. msdn.microsoft.com/library/ms404677.aspx               197325
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               117152
7. msdn.microsoft.com                                            42972
5. msdn.microsoft.com/library/hh524395.aspx                68959
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591

6. msdn.microsoft.com/library/ms404677.aspx               197325
7. msdn.microsoft.com                                            42972
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591
```

<span data-ttu-id="02314-118">Al final de este tema puede revisar el código que genera este resultado.</span><span class="sxs-lookup"><span data-stu-id="02314-118">You can review the code that produces this output by scrolling to the end of this topic.</span></span> <span data-ttu-id="02314-119">Si quiere experimentar con el código, descargue la solución en el equipo local y ejecute el proyecto WebsiteDownload o use el código que aparece al final de este tema para crear su propio proyecto. Para obtener más información, vea [Revisión y ejecución de la aplicación de ejemplo](#BKMD_SettingUpTheExample).</span><span class="sxs-lookup"><span data-stu-id="02314-119">You can experiment with the code by downloading the solution to your local computer and then running the WebsiteDownload project or by using the code at the end of this topic to create your own project For more information and instructions, see [Reviewing and Running the Example App](#BKMD_SettingUpTheExample).</span></span>

## <a name="handling-reentrancy"></a><a name="BKMK_HandlingReentrancy"></a> <span data-ttu-id="02314-120">Controlar la reentrada</span><span class="sxs-lookup"><span data-stu-id="02314-120">Handling Reentrancy</span></span>

<span data-ttu-id="02314-121">La reentrada se puede controlar de varias maneras en función de lo que se desee de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="02314-121">You can handle reentrancy in a variety of ways, depending on what you want your app to do.</span></span> <span data-ttu-id="02314-122">Este tema presenta los siguientes ejemplos:</span><span class="sxs-lookup"><span data-stu-id="02314-122">This topic presents the following examples:</span></span>

- [<span data-ttu-id="02314-123">Deshabilitar el botón de inicio</span><span class="sxs-lookup"><span data-stu-id="02314-123">Disable the Start Button</span></span>](#BKMK_DisableTheStartButton)

  <span data-ttu-id="02314-124">Deshabilite el botón **Start** (Iniciar) mientras se ejecuta la operación de modo que el usuario no pueda interrumpirla.</span><span class="sxs-lookup"><span data-stu-id="02314-124">Disable the **Start** button while the operation is running so that the user can't interrupt it.</span></span>

- [<span data-ttu-id="02314-125">Cancelar y reiniciar la operación</span><span class="sxs-lookup"><span data-stu-id="02314-125">Cancel and Restart the Operation</span></span>](#BKMK_CancelAndRestart)

  <span data-ttu-id="02314-126">Cancele cualquier operación que se esté ejecutando cuando el usuario haga clic de nuevo en el botón **Start** y, después, deje que continúe la última operación solicitada.</span><span class="sxs-lookup"><span data-stu-id="02314-126">Cancel any operation that is still running when the user chooses the **Start** button again, and then let the most recently requested operation continue.</span></span>

- [<span data-ttu-id="02314-127">Ejecutar varias operaciones y poner en cola la salida</span><span class="sxs-lookup"><span data-stu-id="02314-127">Run Multiple Operations and Queue the Output</span></span>](#BKMK_RunMultipleOperations)

  <span data-ttu-id="02314-128">Permita que todas las operaciones solicitadas se ejecuten de forma asincrónica, pero coordine la presentación de salida para que los resultados de cada operación aparecen juntos y en orden.</span><span class="sxs-lookup"><span data-stu-id="02314-128">Allow all requested operations to run asynchronously, but coordinate the display of output so that the results from each operation appear together and in order.</span></span>

### <a name="disable-the-start-button"></a><a name="BKMK_DisableTheStartButton"></a> <span data-ttu-id="02314-129">Deshabilitar el botón de inicio</span><span class="sxs-lookup"><span data-stu-id="02314-129">Disable the Start Button</span></span>

<span data-ttu-id="02314-130">Puede bloquear el botón **Start** mientras se ejecuta una operación si lo deshabilita en la parte superior del controlador de eventos `StartButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="02314-130">You can block the **Start** button while an operation is running by disabling the button at the top of the `StartButton_Click` event handler.</span></span> <span data-ttu-id="02314-131">A continuación, cuando finalice la operación, puede habilitar de nuevo el botón desde un bloque `Finally` de modo que los usuarios puedan volver a ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="02314-131">You can then reenable the button from within a  `Finally` block when the operation finishes so that users can run the app again.</span></span>

<span data-ttu-id="02314-132">El código siguiente muestra estos cambios marcados con asteriscos.</span><span class="sxs-lookup"><span data-stu-id="02314-132">The following code shows these changes, which are marked with asterisks.</span></span> <span data-ttu-id="02314-133">Puede agregar los cambios al código al final de este tema, o puede descargar la aplicación finalizada de [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06) (Ejemplos asincrónicos: reentrada en aplicaciones de escritorio de .NET).</span><span class="sxs-lookup"><span data-stu-id="02314-133">You can add the changes to the code at the end of this topic, or you can download the finished app from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span> <span data-ttu-id="02314-134">El nombre del proyecto es DisableStartButton.</span><span class="sxs-lookup"><span data-stu-id="02314-134">The project name is DisableStartButton.</span></span>

```vb
Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)
    ' This line is commented out to make the results clearer in the output.
    'ResultsTextBox.Text = ""

    ' ***Disable the Start button until the downloads are complete.
    StartButton.IsEnabled = False

    Try
        Await AccessTheWebAsync()

    Catch ex As Exception
        ResultsTextBox.Text &= vbCrLf & "Downloads failed."
    ' ***Enable the Start button in case you want to run the program again.
    Finally
        StartButton.IsEnabled = True

    End Try
End Sub
```

<span data-ttu-id="02314-135">Como resultado de los cambios, el botón no responde mientras `AccessTheWebAsync` está descargando los sitios web, por lo que no se puede volver a introducir el proceso.</span><span class="sxs-lookup"><span data-stu-id="02314-135">As a result of the changes, the button doesn't respond while `AccessTheWebAsync` is downloading the websites, so the process can’t be reentered.</span></span>

### <a name="cancel-and-restart-the-operation"></a><a name="BKMK_CancelAndRestart"></a> <span data-ttu-id="02314-136">Cancelar y reiniciar la operación</span><span class="sxs-lookup"><span data-stu-id="02314-136">Cancel and Restart the Operation</span></span>

<span data-ttu-id="02314-137">En lugar de deshabilitar el botón **Start**, puede mantenerlo activo y, si el usuario vuelve a seleccionarlo, cancelar la operación que ya se está ejecutando y permitir que la última operación iniciada continúe.</span><span class="sxs-lookup"><span data-stu-id="02314-137">Instead of disabling the **Start** button, you can keep the button active but, if the user chooses that button again, cancel the operation that's already running and let the most recently started operation continue.</span></span>

<span data-ttu-id="02314-138">Para obtener más información sobre la cancelación, vea ajustar [la aplicación asincrónica (Visual Basic)](fine-tuning-your-async-application.md).</span><span class="sxs-lookup"><span data-stu-id="02314-138">For more information about cancellation, see [Fine-Tuning Your Async Application (Visual Basic)](fine-tuning-your-async-application.md).</span></span>

<span data-ttu-id="02314-139">Para configurar este escenario, haga los cambios siguientes en el código básico que se proporciona en [Revisión y ejecución de la aplicación de ejemplo](#BKMD_SettingUpTheExample).</span><span class="sxs-lookup"><span data-stu-id="02314-139">To set up this scenario, make the following changes to the basic code that is provided in [Reviewing and Running the Example App](#BKMD_SettingUpTheExample).</span></span> <span data-ttu-id="02314-140">También puede descargar la aplicación finalizada de [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06) (Ejemplos asincrónicos: reentrada en aplicaciones de escritorio de .NET).</span><span class="sxs-lookup"><span data-stu-id="02314-140">You can also download the finished app from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span> <span data-ttu-id="02314-141">El nombre de este proyecto es CancelAndRestart.</span><span class="sxs-lookup"><span data-stu-id="02314-141">The name of this project is CancelAndRestart.</span></span>

1. <span data-ttu-id="02314-142">Declare una variable de <xref:System.Threading.CancellationTokenSource>, `cts`, que esté en el ámbito de todos los métodos.</span><span class="sxs-lookup"><span data-stu-id="02314-142">Declare a <xref:System.Threading.CancellationTokenSource> variable, `cts`, that’s in scope for all methods.</span></span>

    ```vb
    Class MainWindow // Or Class MainPage

        ' *** Declare a System.Threading.CancellationTokenSource.
        Dim cts As CancellationTokenSource
    ```

2. <span data-ttu-id="02314-143">En `StartButton_Click`, determine si una operación ya está en curso.</span><span class="sxs-lookup"><span data-stu-id="02314-143">In `StartButton_Click`, determine whether an operation is already underway.</span></span> <span data-ttu-id="02314-144">Si el valor de `cts` es `Nothing` , no hay ninguna operación activa.</span><span class="sxs-lookup"><span data-stu-id="02314-144">If the value of `cts` is `Nothing`, no operation is already active.</span></span> <span data-ttu-id="02314-145">Si el valor no es `Nothing` , se cancela la operación que ya se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="02314-145">If the value isn't `Nothing`, the operation that is already running is canceled.</span></span>

    ```vb
    ' *** If a download process is already underway, cancel it.
    If cts IsNot Nothing Then
        cts.Cancel()
    End If
    ```

3. <span data-ttu-id="02314-146">Establezca `cts` en un valor diferente que represente el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="02314-146">Set `cts` to a different value that represents the current process.</span></span>

    ```vb
    ' *** Now set cts to cancel the current process if the button is chosen again.
    Dim newCTS As CancellationTokenSource = New CancellationTokenSource()
    cts = newCTS
    ```

4. <span data-ttu-id="02314-147">Al final de `StartButton_Click` , el proceso actual se completa, por lo que debe establecer el valor de `cts` en `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="02314-147">At the end of `StartButton_Click`, the current process is complete, so set the value of `cts` back to `Nothing`.</span></span>

    ```vb
    ' *** When the process completes, signal that another process can proceed.
    If cts Is newCTS Then
        cts = Nothing
    End If
    ```

<span data-ttu-id="02314-148">El código siguiente muestra todos los cambios en `StartButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="02314-148">The following code shows all the changes in `StartButton_Click`.</span></span> <span data-ttu-id="02314-149">Las adiciones se marcan con asteriscos.</span><span class="sxs-lookup"><span data-stu-id="02314-149">The additions are marked with asterisks.</span></span>

```vb
Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)

    ' This line is commented out to make the results clearer.
    'ResultsTextBox.Text = ""

    ' *** If a download process is underway, cancel it.
    If cts IsNot Nothing Then
        cts.Cancel()
    End If

    ' *** Now set cts to cancel the current process if the button is chosen again.
    Dim newCTS As CancellationTokenSource = New CancellationTokenSource()
    cts = newCTS

    Try
        ' *** Send a token to carry the message if the operation is canceled.
        Await AccessTheWebAsync(cts.Token)

    Catch ex As OperationCanceledException
        ResultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf

    Catch ex As Exception
        ResultsTextBox.Text &= vbCrLf & "Downloads failed."
    End Try

    ' *** When the process is complete, signal that another process can proceed.
    If cts Is newCTS Then
        cts = Nothing
    End If
End Sub
```

<span data-ttu-id="02314-150">En `AccessTheWebAsync`, realice los siguientes cambios.</span><span class="sxs-lookup"><span data-stu-id="02314-150">In `AccessTheWebAsync`, make the following changes.</span></span>

- <span data-ttu-id="02314-151">Agregue un parámetro para aceptar el token de cancelación de `StartButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="02314-151">Add a parameter to accept the cancellation token from `StartButton_Click`.</span></span>

- <span data-ttu-id="02314-152">Use el método <xref:System.Net.Http.HttpClient.GetAsync%2A> para descargar los sitios web porque `GetAsync` acepta un argumento <xref:System.Threading.CancellationToken>.</span><span class="sxs-lookup"><span data-stu-id="02314-152">Use the <xref:System.Net.Http.HttpClient.GetAsync%2A> method to download the websites because `GetAsync` accepts a <xref:System.Threading.CancellationToken> argument.</span></span>

- <span data-ttu-id="02314-153">Antes de llamar a `DisplayResults` para mostrar los resultados de los sitios web descargados, revise `ct` para comprobar que no se ha cancelado la operación actual.</span><span class="sxs-lookup"><span data-stu-id="02314-153">Before calling `DisplayResults` to display the results for each downloaded website, check `ct` to verify that the current operation hasn’t been canceled.</span></span>

 <span data-ttu-id="02314-154">El código siguiente muestra estos cambios marcados con asteriscos.</span><span class="sxs-lookup"><span data-stu-id="02314-154">The following code shows these changes, which are marked with asterisks.</span></span>

```vb
' *** Provide a parameter for the CancellationToken from StartButton_Click.
Private Async Function AccessTheWebAsync(ct As CancellationToken) As Task

    ' Declare an HttpClient object.
    Dim client = New HttpClient()

    ' Make a list of web addresses.
    Dim urlList As List(Of String) = SetUpURLList()

    Dim total = 0
    Dim position = 0

    For Each url In urlList
        ' *** Use the HttpClient.GetAsync method because it accepts a
        ' cancellation token.
        Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)

        ' *** Retrieve the website contents from the HttpResponseMessage.
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

        ' *** Check for cancellations before displaying information about the
        ' latest site.
        ct.ThrowIfCancellationRequested()

        position += 1
        DisplayResults(url, urlContents, position)

        ' Update the total.
        total += urlContents.Length
    Next

    ' Display the total count for all of the websites.
    ResultsTextBox.Text &=
        String.Format(vbCrLf & vbCrLf & "TOTAL bytes returned:  " & total & vbCrLf)
End Function
```

<span data-ttu-id="02314-155">Si elige el botón **iniciar** varias veces mientras se ejecuta esta aplicación, debe generar resultados similares a los siguientes:</span><span class="sxs-lookup"><span data-stu-id="02314-155">If you choose the **Start** button several times while this app is running, it should produce results that resemble the following output:</span></span>

```console
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               122505
5. msdn.microsoft.com/library/hh524395.aspx                68959
6. msdn.microsoft.com/library/ms404677.aspx               197325
Download canceled.

1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
Download canceled.

1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               117152
5. msdn.microsoft.com/library/hh524395.aspx                68959
6. msdn.microsoft.com/library/ms404677.aspx               197325
7. msdn.microsoft.com                                            42972
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591
```

<span data-ttu-id="02314-156">Para eliminar las listas parciales, quite el comentario de la primera línea de código en `StartButton_Click` para borrar el cuadro de texto cada vez que el usuario reinicie la operación.</span><span class="sxs-lookup"><span data-stu-id="02314-156">To eliminate the partial lists, uncomment the first line of code in `StartButton_Click` to clear the text box each time the user restarts the operation.</span></span>

### <a name="run-multiple-operations-and-queue-the-output"></a><a name="BKMK_RunMultipleOperations"></a> <span data-ttu-id="02314-157">Ejecutar varias operaciones y poner en cola el resultado</span><span class="sxs-lookup"><span data-stu-id="02314-157">Run Multiple Operations and Queue the Output</span></span>

<span data-ttu-id="02314-158">Este tercer ejemplo es el más complicado porque la aplicación inicia otra operación asincrónica cada vez que el usuario selecciona el botón **Start** y todas las operaciones se ejecutan hasta completarse.</span><span class="sxs-lookup"><span data-stu-id="02314-158">This third example is the most complicated in that the app starts another asynchronous operation each time that the user chooses the **Start** button, and all the operations run to completion.</span></span> <span data-ttu-id="02314-159">Todas las operaciones solicitadas descargan los sitios web de la lista de forma asincrónica, pero la salida de las operaciones se presenta de manera secuencial.</span><span class="sxs-lookup"><span data-stu-id="02314-159">All the requested operations download websites from the list asynchronously, but the output from the operations is presented sequentially.</span></span> <span data-ttu-id="02314-160">Es decir, la actividad de descarga real se intercala, según se muestra en la salida de [Reconocer la reentrada](#BKMK_RecognizingReentrancy), pero la lista de resultados de cada grupo se presenta por separado.</span><span class="sxs-lookup"><span data-stu-id="02314-160">That is, the actual downloading activity is interleaved, as the output in [Recognizing Reentrancy](#BKMK_RecognizingReentrancy) shows, but the list of results for each group is presented separately.</span></span>

<span data-ttu-id="02314-161">Las operaciones comparten una <xref:System.Threading.Tasks.Task> global, `pendingWork`, que actúa de equipo selector para el proceso de visualización.</span><span class="sxs-lookup"><span data-stu-id="02314-161">The operations share a global <xref:System.Threading.Tasks.Task>, `pendingWork`, which serves as a gatekeeper for the display process.</span></span>

<span data-ttu-id="02314-162">Puede ejecutar este ejemplo pegando los cambios en el código de la [compilación de la aplicación](#BKMK_BuildingTheApp), o puede seguir las instrucciones de [descargar la aplicación](#BKMK_DownloadingTheApp) para descargar el ejemplo y, a continuación, ejecutar el proyecto QueueResults.</span><span class="sxs-lookup"><span data-stu-id="02314-162">You can run this example by pasting the changes into the code in [Building the App](#BKMK_BuildingTheApp), or you can follow the instructions in [Downloading the App](#BKMK_DownloadingTheApp) to download the sample and then run the QueueResults project.</span></span>

<span data-ttu-id="02314-163">En la salida siguiente se muestra el resultado cuando el usuario selecciona el botón **Start** una sola vez.</span><span class="sxs-lookup"><span data-stu-id="02314-163">The following output shows the result if the user chooses the **Start** button only once.</span></span> <span data-ttu-id="02314-164">La etiqueta de letra A indica que el resultado se corresponde a la primera vez que se selecciona el botón **Start**.</span><span class="sxs-lookup"><span data-stu-id="02314-164">The letter label, A, indicates that the result is from the first time the **Start** button is chosen.</span></span> <span data-ttu-id="02314-165">Los números muestran el orden de las direcciones URL en la lista de destinos de descarga.</span><span class="sxs-lookup"><span data-stu-id="02314-165">The numbers show the order of the URLs in the list of download targets.</span></span>

```console
#Starting group A.
#Task assigned for group A.

A-1. msdn.microsoft.com/library/hh191443.aspx                87389
A-2. msdn.microsoft.com/library/aa578028.aspx               209858
A-3. msdn.microsoft.com/library/jj155761.aspx                30870
A-4. msdn.microsoft.com/library/hh290140.aspx               119027
A-5. msdn.microsoft.com/library/hh524395.aspx                71260
A-6. msdn.microsoft.com/library/ms404677.aspx               199186
A-7. msdn.microsoft.com                                            53266
A-8. msdn.microsoft.com/library/ff730837.aspx               148020

TOTAL bytes returned:  918876

#Group A is complete.
```

<span data-ttu-id="02314-166">Si el usuario hace clic tres veces en el botón **Start**, la aplicación genera una salida similar a las líneas siguientes.</span><span class="sxs-lookup"><span data-stu-id="02314-166">If the user chooses the **Start** button three times, the app produces output that resembles the following lines.</span></span> <span data-ttu-id="02314-167">Las líneas de información que comienzan con una almohadilla (#) siguen el progreso de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="02314-167">The information lines that start with a pound sign (#) trace the progress of the application.</span></span>

```console
#Starting group A.
#Task assigned for group A.

A-1. msdn.microsoft.com/library/hh191443.aspx                87389
A-2. msdn.microsoft.com/library/aa578028.aspx               207089
A-3. msdn.microsoft.com/library/jj155761.aspx                30870
A-4. msdn.microsoft.com/library/hh290140.aspx               119027
A-5. msdn.microsoft.com/library/hh524395.aspx                71259
A-6. msdn.microsoft.com/library/ms404677.aspx               199185

#Starting group B.
#Task assigned for group B.

A-7. msdn.microsoft.com                                            53266

#Starting group C.
#Task assigned for group C.

A-8. msdn.microsoft.com/library/ff730837.aspx               148010

TOTAL bytes returned:  916095

B-1. msdn.microsoft.com/library/hh191443.aspx                87389
B-2. msdn.microsoft.com/library/aa578028.aspx               207089
B-3. msdn.microsoft.com/library/jj155761.aspx                30870
B-4. msdn.microsoft.com/library/hh290140.aspx               119027
B-5. msdn.microsoft.com/library/hh524395.aspx                71260
B-6. msdn.microsoft.com/library/ms404677.aspx               199186

#Group A is complete.

B-7. msdn.microsoft.com                                            53266
B-8. msdn.microsoft.com/library/ff730837.aspx               148010

TOTAL bytes returned:  916097

C-1. msdn.microsoft.com/library/hh191443.aspx                87389
C-2. msdn.microsoft.com/library/aa578028.aspx               207089

#Group B is complete.

C-3. msdn.microsoft.com/library/jj155761.aspx                30870
C-4. msdn.microsoft.com/library/hh290140.aspx               119027
C-5. msdn.microsoft.com/library/hh524395.aspx                72765
C-6. msdn.microsoft.com/library/ms404677.aspx               199186
C-7. msdn.microsoft.com                                            56190
C-8. msdn.microsoft.com/library/ff730837.aspx               148010

TOTAL bytes returned:  920526

#Group C is complete.
```

<span data-ttu-id="02314-168">Los grupos B y C se inician antes de finalizar el grupo A, pero la salida de cada grupo aparece por separado.</span><span class="sxs-lookup"><span data-stu-id="02314-168">Groups B and C start before group A has finished, but the output for the each group appears separately.</span></span> <span data-ttu-id="02314-169">Primero aparece toda la salida del grupo A, seguida de la salida del grupo B y después la del grupo C. La aplicación siempre muestra los grupos en orden y, en cada grupo, muestra la información sobre los sitios web individuales en el orden en que las direcciones URL aparecen en la lista de direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="02314-169">All the output for group A appears first, followed by all the output for group B, and then all the output for group C. The app always displays the groups in order and, for each group, always displays the information about the individual websites in the order that the URLs appear in the list of URLs.</span></span>

<span data-ttu-id="02314-170">Sin embargo, no es posible predecir el orden en que se producen las descargas.</span><span class="sxs-lookup"><span data-stu-id="02314-170">However, you can't predict the order in which the downloads actually happen.</span></span> <span data-ttu-id="02314-171">Después de iniciarse varios grupos, las tareas de descarga que generan están activas.</span><span class="sxs-lookup"><span data-stu-id="02314-171">After multiple groups have been started, the download tasks that they generate are all active.</span></span> <span data-ttu-id="02314-172">No se puede dar por sentado que A-1 se descargará antes que B-1, ni que A-1 se descargará antes que A-2.</span><span class="sxs-lookup"><span data-stu-id="02314-172">You can't assume that A-1 will be downloaded before B-1, and you can't assume that A-1 will be downloaded before A-2.</span></span>

#### <a name="global-definitions"></a><span data-ttu-id="02314-173">Definiciones globales</span><span class="sxs-lookup"><span data-stu-id="02314-173">Global Definitions</span></span>

<span data-ttu-id="02314-174">El código de ejemplo contiene las dos declaraciones globales siguientes que están visibles en todos los métodos.</span><span class="sxs-lookup"><span data-stu-id="02314-174">The sample code contains the following two global declarations that are visible from all methods.</span></span>

```vb
Class MainWindow    ' Class MainPage in Windows Store app.

    ' ***Declare the following variables where all methods can access them.
    Private pendingWork As Task = Nothing
    Private group As Char = ChrW(AscW("A") - 1)
```

<span data-ttu-id="02314-175">La variable de `Task`, `pendingWork`, supervisa el proceso de presentación e impide que un grupo interrumpa la operación de presentación de otro grupo.</span><span class="sxs-lookup"><span data-stu-id="02314-175">The `Task` variable, `pendingWork`, oversees the display process and prevents any group from interrupting another group's display operation.</span></span> <span data-ttu-id="02314-176">La variable de caracteres, `group`, etiqueta la salida de diferentes grupos para comprobar que los resultados aparecen en el orden esperado.</span><span class="sxs-lookup"><span data-stu-id="02314-176">The character variable, `group`, labels the output from different groups to verify that results appear in the expected order.</span></span>

#### <a name="the-click-event-handler"></a><span data-ttu-id="02314-177">El controlador de eventos Click</span><span class="sxs-lookup"><span data-stu-id="02314-177">The Click Event Handler</span></span>

<span data-ttu-id="02314-178">El controlador de eventos, `StartButton_Click`, incrementa la letra del grupo cada vez que el usuario selecciona el botón **Start**.</span><span class="sxs-lookup"><span data-stu-id="02314-178">The event handler, `StartButton_Click`, increments the group letter each time the user chooses the **Start** button.</span></span> <span data-ttu-id="02314-179">A continuación, el controlador llama a `AccessTheWebAsync` para ejecutar la operación de descarga.</span><span class="sxs-lookup"><span data-stu-id="02314-179">Then the handler calls `AccessTheWebAsync` to run the downloading operation.</span></span>

```vb
Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)
    ' ***Verify that each group's results are displayed together, and that
    ' the groups display in order, by marking each group with a letter.
    group = ChrW(AscW(group) + 1)
    ResultsTextBox.Text &= String.Format(vbCrLf & vbCrLf & "#Starting group {0}.", group)

    Try
        ' *** Pass the group value to AccessTheWebAsync.
        Dim finishedGroup As Char = Await AccessTheWebAsync(group)

        ' The following line verifies a successful return from the download and
        ' display procedures.
        ResultsTextBox.Text &= String.Format(vbCrLf & vbCrLf & "#Group {0} is complete." & vbCrLf, finishedGroup)

    Catch ex As Exception
        ResultsTextBox.Text &= vbCrLf & "Downloads failed."

    End Try
End Sub
```

#### <a name="the-accessthewebasync-method"></a><span data-ttu-id="02314-180">El método AccessTheWebAsync</span><span class="sxs-lookup"><span data-stu-id="02314-180">The AccessTheWebAsync Method</span></span>

<span data-ttu-id="02314-181">En este ejemplo se divide `AccessTheWebAsync` en dos métodos.</span><span class="sxs-lookup"><span data-stu-id="02314-181">This example splits `AccessTheWebAsync` into two methods.</span></span> <span data-ttu-id="02314-182">El primer método, `AccessTheWebAsync`, inicia todas las tareas de descarga de un grupo y configura `pendingWork` para controlar el proceso de visualización.</span><span class="sxs-lookup"><span data-stu-id="02314-182">The first method, `AccessTheWebAsync`, starts all the download tasks for a group and sets up `pendingWork` to control the display process.</span></span> <span data-ttu-id="02314-183">El método usa una consulta de Language Integrated Query (consulta LINQ) y <xref:System.Linq.Enumerable.ToArray%2A> para iniciar todas las tareas de descarga al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="02314-183">The method uses a Language Integrated Query (LINQ query) and <xref:System.Linq.Enumerable.ToArray%2A> to start all the download tasks at the same time.</span></span>

<span data-ttu-id="02314-184">A continuación, `AccessTheWebAsync` llama a `FinishOneGroupAsync` para esperar la finalización de todas las descargas y mostrar su duración.</span><span class="sxs-lookup"><span data-stu-id="02314-184">`AccessTheWebAsync` then calls `FinishOneGroupAsync` to await the completion of each download and display its length.</span></span>

<span data-ttu-id="02314-185">`FinishOneGroupAsync` devuelve una tarea que se asigna a `pendingWork` en `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="02314-185">`FinishOneGroupAsync` returns a task that's assigned to `pendingWork` in `AccessTheWebAsync`.</span></span> <span data-ttu-id="02314-186">Ese valor evita que otra operación interrumpa la tarea antes de que finalice.</span><span class="sxs-lookup"><span data-stu-id="02314-186">That value prevents interruption by another operation before the task is complete.</span></span>

```vb
Private Async Function AccessTheWebAsync(grp As Char) As Task(Of Char)

    Dim client = New HttpClient()

    ' Make a list of the web addresses to download.
    Dim urlList As List(Of String) = SetUpURLList()

    ' ***Kick off the downloads. The application of ToArray activates all the download tasks.
    Dim getContentTasks As Task(Of Byte())() =
        urlList.Select(Function(addr) client.GetByteArrayAsync(addr)).ToArray()

    ' ***Call the method that awaits the downloads and displays the results.
    ' Assign the Task that FinishOneGroupAsync returns to the gatekeeper task, pendingWork.
    pendingWork = FinishOneGroupAsync(urlList, getContentTasks, grp)

    ResultsTextBox.Text &=
        String.Format(vbCrLf & "#Task assigned for group {0}. Download tasks are active." & vbCrLf, grp)

    ' ***This task is complete when a group has finished downloading and displaying.
    Await pendingWork

    ' You can do other work here or just return.
    Return grp
End Function
```

#### <a name="the-finishonegroupasync-method"></a><span data-ttu-id="02314-187">El método FinishOneGroupAsync</span><span class="sxs-lookup"><span data-stu-id="02314-187">The FinishOneGroupAsync Method</span></span>

<span data-ttu-id="02314-188">Este método recorre las tareas de descarga de un grupo, espera por cada una de ellas, muestra la longitud del sitio web descargado y agrega la longitud total.</span><span class="sxs-lookup"><span data-stu-id="02314-188">This method cycles through the download tasks in a group, awaiting each one, displaying the length of the downloaded website, and adding the length to the total.</span></span>

<span data-ttu-id="02314-189">La primera instrucción de `FinishOneGroupAsync` usa `pendingWork` para asegurarse de que la entrada al método no interfiere con una operación que ya está en el proceso de visualización o que ya está esperando.</span><span class="sxs-lookup"><span data-stu-id="02314-189">The first statement in `FinishOneGroupAsync` uses `pendingWork` to make sure that entering the method doesn't interfere with an operation that is already in the display process or that's already waiting.</span></span> <span data-ttu-id="02314-190">Si tal operación está en curso, la operación introducida debe esperar su turno.</span><span class="sxs-lookup"><span data-stu-id="02314-190">If such an operation is in progress, the entering operation must wait its turn.</span></span>

```vb
Private Async Function FinishOneGroupAsync(urls As List(Of String), contentTasks As Task(Of Byte())(), grp As Char) As Task

    ' Wait for the previous group to finish displaying results.
    If pendingWork IsNot Nothing Then
        Await pendingWork
    End If

    Dim total = 0

    ' contentTasks is the array of Tasks that was created in AccessTheWebAsync.
    For i As Integer = 0 To contentTasks.Length - 1
        ' Await the download of a particular URL, and then display the URL and
        ' its length.
        Dim content As Byte() = Await contentTasks(i)
        DisplayResults(urls(i), content, i, grp)
        total += content.Length
    Next

    ' Display the total count for all of the websites.
    ResultsTextBox.Text &=
        String.Format(vbCrLf & vbCrLf & "TOTAL bytes returned:  " & total & vbCrLf)
End Function
```

<span data-ttu-id="02314-191">Puede ejecutar este ejemplo pegando los cambios en el código de [Crear la aplicación](#BKMK_BuildingTheApp), o bien puede seguir las instrucciones de [Descargar la aplicación](#BKMK_DownloadingTheApp) para descargar el ejemplo y ejecutar el proyecto de QueueResults.</span><span class="sxs-lookup"><span data-stu-id="02314-191">You can run this example by pasting the changes into the code in [Building the App](#BKMK_BuildingTheApp), or you can follow the instructions in [Downloading the App](#BKMK_DownloadingTheApp) to download the sample, and then run the QueueResults project.</span></span>

#### <a name="points-of-interest"></a><span data-ttu-id="02314-192">Puntos de interés</span><span class="sxs-lookup"><span data-stu-id="02314-192">Points of Interest</span></span>

<span data-ttu-id="02314-193">Las líneas de información que comienzan con un signo de almohadilla (#) en la salida aclaran cómo funciona este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="02314-193">The information lines that start with a pound sign (#) in the output clarify how this example works.</span></span>

<span data-ttu-id="02314-194">La salida muestra los siguientes patrones.</span><span class="sxs-lookup"><span data-stu-id="02314-194">The output shows the following patterns.</span></span>

- <span data-ttu-id="02314-195">Un grupo puede iniciarse mientras un grupo anterior muestra su salida, pero la visualización del grupo anterior no se ve interrumpida.</span><span class="sxs-lookup"><span data-stu-id="02314-195">A group can be started while a previous group is displaying its output, but the display of the previous group's output isn't interrupted.</span></span>

  ```console
  #Starting group A.
  #Task assigned for group A. Download tasks are active.

  A-1. msdn.microsoft.com/library/hh191443.aspx                87389
  A-2. msdn.microsoft.com/library/aa578028.aspx               207089
  A-3. msdn.microsoft.com/library/jj155761.aspx                30870
  A-4. msdn.microsoft.com/library/hh290140.aspx               119037
  A-5. msdn.microsoft.com/library/hh524395.aspx                71260

  #Starting group B.
  #Task assigned for group B. Download tasks are active.

  A-6. msdn.microsoft.com/library/ms404677.aspx               199186
  A-7. msdn.microsoft.com                                            53078
  A-8. msdn.microsoft.com/library/ff730837.aspx               148010

  TOTAL bytes returned:  915919

  B-1. msdn.microsoft.com/library/hh191443.aspx                87388
  B-2. msdn.microsoft.com/library/aa578028.aspx               207089
  B-3. msdn.microsoft.com/library/jj155761.aspx                30870

  #Group A is complete.

  B-4. msdn.microsoft.com/library/hh290140.aspx               119027
  B-5. msdn.microsoft.com/library/hh524395.aspx                71260
  B-6. msdn.microsoft.com/library/ms404677.aspx               199186
  B-7. msdn.microsoft.com                                            53078
  B-8. msdn.microsoft.com/library/ff730837.aspx               148010

  TOTAL bytes returned:  915908
  ```

- <span data-ttu-id="02314-196">La `pendingWork` tarea se encuentra `Nothing` al principio de `FinishOneGroupAsync` solo para el grupo A, que se inició primero.</span><span class="sxs-lookup"><span data-stu-id="02314-196">The `pendingWork` task is `Nothing` at the start of `FinishOneGroupAsync` only for group A, which started first.</span></span> <span data-ttu-id="02314-197">El grupo A todavía no ha completado una expresión await cuando alcanza `FinishOneGroupAsync`.</span><span class="sxs-lookup"><span data-stu-id="02314-197">Group A hasn’t yet completed an await expression when it reaches `FinishOneGroupAsync`.</span></span> <span data-ttu-id="02314-198">Por lo tanto, el control no se ha devuelto a `AccessTheWebAsync`, y la primera asignación a `pendingWork` no se ha producido.</span><span class="sxs-lookup"><span data-stu-id="02314-198">Therefore, control hasn't returned to `AccessTheWebAsync`, and the first assignment to `pendingWork` hasn't occurred.</span></span>

- <span data-ttu-id="02314-199">Las dos líneas siguientes siempre aparecen juntas en la salida.</span><span class="sxs-lookup"><span data-stu-id="02314-199">The following two lines always appear together in the output.</span></span> <span data-ttu-id="02314-200">El código no se interrumpa nunca entre el inicio de la operación de un grupo en de `StartButton_Click` y la asignación de una tarea del grupo a `pendingWork`.</span><span class="sxs-lookup"><span data-stu-id="02314-200">The code is never interrupted between starting a group's operation in `StartButton_Click` and assigning a task for the group to `pendingWork`.</span></span>

  ```console
  #Starting group B.
  #Task assigned for group B. Download tasks are active.
  ```

  <span data-ttu-id="02314-201">Una vez que un grupo introduce `StartButton_Click`, la operación no completa una expresión await hasta que la operación introduce `FinishOneGroupAsync`.</span><span class="sxs-lookup"><span data-stu-id="02314-201">After a group enters `StartButton_Click`, the operation doesn't complete an await expression until the operation enters `FinishOneGroupAsync`.</span></span> <span data-ttu-id="02314-202">Por lo tanto, ninguna otra operación puede lograr el control durante ese segmento de código.</span><span class="sxs-lookup"><span data-stu-id="02314-202">Therefore, no other operation can gain control during that segment of code.</span></span>

## <a name="reviewing-and-running-the-example-app"></a><a name="BKMD_SettingUpTheExample"></a> <span data-ttu-id="02314-203">Revisión y ejecución de la aplicación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="02314-203">Reviewing and Running the Example App</span></span>

<span data-ttu-id="02314-204">Para entender mejor la aplicación de ejemplo, puede descargarla, compilarla usted mismo o revisar el código al final de este tema sin necesidad de implementar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="02314-204">To better understand the example app, you can download it, build it yourself, or review the code at the end of this topic without implementing the app.</span></span>

> [!NOTE]
> <span data-ttu-id="02314-205">Para ejecutar el ejemplo como aplicación de escritorio de Windows Presentation Foundation (WPF), debe tener instalado en el equipo Visual Studio 2012 o posterior, y .NET Framework 4.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="02314-205">To run the example as a Windows Presentation Foundation (WPF) desktop app, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

### <a name="downloading-the-app"></a><a name="BKMK_DownloadingTheApp"></a> <span data-ttu-id="02314-206">Descargar la aplicación</span><span class="sxs-lookup"><span data-stu-id="02314-206">Downloading the App</span></span>

1. <span data-ttu-id="02314-207">Descargue el archivo comprimido de [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06) (Ejemplos asincrónicos: reentrada en aplicaciones de escritorio de .NET).</span><span class="sxs-lookup"><span data-stu-id="02314-207">Download the compressed file from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span>

2. <span data-ttu-id="02314-208">Descomprima el archivo descargado y, a continuación, inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="02314-208">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

3. <span data-ttu-id="02314-209">En la barra de menús, elija **Archivo**, **Abrir**, **Proyecto o solución**.</span><span class="sxs-lookup"><span data-stu-id="02314-209">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>

4. <span data-ttu-id="02314-210">Navegue hasta la carpeta que contiene el código de ejemplo descomprimido y, a continuación, abra el archivo de solución (.sln).</span><span class="sxs-lookup"><span data-stu-id="02314-210">Navigate to the folder that holds the decompressed sample code, and then open the solution (.sln) file.</span></span>

5. <span data-ttu-id="02314-211">En el **Explorador de soluciones**, abra el menú contextual del proyecto que quiere ejecutar y, después, elija **Establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="02314-211">In **Solution Explorer**, open the shortcut menu for the project that you want to run, and then choose **Set as StartUpProject**.</span></span>

6. <span data-ttu-id="02314-212">Elija las teclas CTRL+F5 para compilar y ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="02314-212">Choose the CTRL+F5 keys to build and run the project.</span></span>

### <a name="building-the-app"></a><a name="BKMK_BuildingTheApp"></a> <span data-ttu-id="02314-213">Compilar la aplicación</span><span class="sxs-lookup"><span data-stu-id="02314-213">Building the App</span></span>

<span data-ttu-id="02314-214">La sección siguiente proporciona el código para compilar el ejemplo como una aplicación de WPF.</span><span class="sxs-lookup"><span data-stu-id="02314-214">The following section provides the code to build the example as a WPF app.</span></span>

##### <a name="to-build-a-wpf-app"></a><span data-ttu-id="02314-215">Para compilar una aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="02314-215">To build a WPF app</span></span>

1. <span data-ttu-id="02314-216">Inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="02314-216">Start Visual Studio.</span></span>

2. <span data-ttu-id="02314-217">En la barra de menús, elija **Archivo**, **Nuevo**, **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="02314-217">On the menu bar, choose **File**, **New**, **Project**.</span></span>

     <span data-ttu-id="02314-218">Aparece el cuadro de diálogo **Nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="02314-218">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="02314-219">En el panel **plantillas instaladas** , expanda **Visual Basic** y, a continuación, expanda **Windows**.</span><span class="sxs-lookup"><span data-stu-id="02314-219">In the **Installed Templates** pane, expand **Visual Basic**, and then expand **Windows**.</span></span>

4. <span data-ttu-id="02314-220">En la lista de tipos de proyecto, seleccione **Aplicación WPF**.</span><span class="sxs-lookup"><span data-stu-id="02314-220">In the list of project types, choose **WPF Application**.</span></span>

5. <span data-ttu-id="02314-221">Asigne un nombre al proyecto `WebsiteDownloadWPF`, elija la versión 4.6 de .NET Framework o una posterior y, después, haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="02314-221">Name the project `WebsiteDownloadWPF`, choose .NET Framework version of 4.6 or higher and then click the **OK** button.</span></span>

     <span data-ttu-id="02314-222">El proyecto nuevo aparece en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="02314-222">The new project appears in **Solution Explorer**.</span></span>

6. <span data-ttu-id="02314-223">En el Editor de código de Visual Studio, elija la pestaña **MainWindow.xaml** .</span><span class="sxs-lookup"><span data-stu-id="02314-223">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>

     <span data-ttu-id="02314-224">Si la pestaña no está visible, abra el menú contextual de MainWindow.xaml en el **Explorador de soluciones** y elija **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="02314-224">If the tab isn’t visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **View Code**.</span></span>

7. <span data-ttu-id="02314-225">En la vista **XAML** de MainWindow.xaml, reemplace el código por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="02314-225">In the **XAML** view of MainWindow.xaml, replace the code with the following code.</span></span>

    ```xaml
    <Window x:Class="MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="using:WebsiteDownloadWPF"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        mc:Ignorable="d">

        <Grid Width="517" Height="360">
            <Button x:Name="StartButton" Content="Start" HorizontalAlignment="Left" Margin="-1,0,0,0" VerticalAlignment="Top" Click="StartButton_Click" Height="53" Background="#FFA89B9B" FontSize="36" Width="518"  />
            <TextBox x:Name="ResultsTextBox" HorizontalAlignment="Left" Margin="-1,53,0,-36" TextWrapping="Wrap" VerticalAlignment="Top" Height="343" FontSize="10" ScrollViewer.VerticalScrollBarVisibility="Visible" Width="518" FontFamily="Lucida Console" />
        </Grid>
    </Window>
    ```

     <span data-ttu-id="02314-226">En la vista **Diseño** de MainWindow.xaml aparece una ventana simple que contiene un cuadro de texto y un botón.</span><span class="sxs-lookup"><span data-stu-id="02314-226">A simple window that contains a text box and a button appears in the **Design** view of MainWindow.xaml.</span></span>

8. <span data-ttu-id="02314-227">En el **Explorador de soluciones**, haga clic con el botón derecho en **Referencias** y seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="02314-227">In **Solution Explorer**, right-click on **References** and select **Add Reference**.</span></span>

     <span data-ttu-id="02314-228">Agregue una referencia para <xref:System.Net.Http>, si aún no está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="02314-228">Add a reference for <xref:System.Net.Http>, if it is not selected already.</span></span>

9. <span data-ttu-id="02314-229">En **Explorador de soluciones**, abra el menú contextual de MainWindow. Xaml. VB y, a continuación, elija **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="02314-229">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>

10. <span data-ttu-id="02314-230">En MainWindow. Xaml. VB, reemplace el código por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="02314-230">In MainWindow.xaml.vb , replace the code with the following code.</span></span>

    ```vb
    ' Add the following Imports statements, and add a reference for System.Net.Http.
    Imports System.Net.Http
    Imports System.Threading

    Class MainWindow

        Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)
            System.Net.ServicePointManager.SecurityProtocol = System.Net.ServicePointManager.SecurityProtocol Or System.Net.SecurityProtocolType.Tls12

            ' This line is commented out to make the results clearer in the output.
            'ResultsTextBox.Text = ""

            Try
                Await AccessTheWebAsync()

            Catch ex As Exception
                ResultsTextBox.Text &= vbCrLf & "Downloads failed."

            End Try
        End Sub

        Private Async Function AccessTheWebAsync() As Task

            ' Declare an HttpClient object.
            Dim client = New HttpClient()

            ' Make a list of web addresses.
            Dim urlList As List(Of String) = SetUpURLList()

            Dim total = 0
            Dim position = 0

            For Each url In urlList
                ' GetByteArrayAsync returns a task. At completion, the task
                ' produces a byte array.
                Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)

                position += 1
                DisplayResults(url, urlContents, position)

                ' Update the total.
                total += urlContents.Length
            Next

            ' Display the total count for all of the websites.
            ResultsTextBox.Text &=
                String.Format(vbCrLf & vbCrLf & "TOTAL bytes returned:  " & total & vbCrLf)
        End Function

        Private Function SetUpURLList() As List(Of String)
            Dim urls = New List(Of String) From
            {
                "https://msdn.microsoft.com/library/hh191443.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/jj155761.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/hh524395.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            }
            Return urls
        End Function

        Private Sub DisplayResults(url As String, content As Byte(), pos As Integer)
            ' Display the length of each website. The string format is designed
            ' to be used with a monospaced font, such as Lucida Console or
            ' Global Monospace.

            ' Strip off the "http:'".
            Dim displayURL = url.Replace("https://", "")
            ' Display position in the URL list, the URL, and the number of bytes.
            ResultsTextBox.Text &= String.Format(vbCrLf & "{0}. {1,-58} {2,8}", pos, displayURL, content.Length)
        End Sub
    End Class
    ```

11. <span data-ttu-id="02314-231">Presiones las teclas CTRL+F5 para ejecutar el programa y luego haga clic varias veces en el botón **Start**.</span><span class="sxs-lookup"><span data-stu-id="02314-231">Choose the CTRL+F5 keys to run the program, and then choose the **Start** button several times.</span></span>

12. <span data-ttu-id="02314-232">Realice los cambios de [Deshabilitar el botón de inicio](#BKMK_DisableTheStartButton), [Cancelar y reiniciar la operación](#BKMK_CancelAndRestart) o [Ejecutar varias operaciones y poner en cola el resultado](#BKMK_RunMultipleOperations) para controlar la reentrada.</span><span class="sxs-lookup"><span data-stu-id="02314-232">Make the changes from [Disable the Start Button](#BKMK_DisableTheStartButton), [Cancel and Restart the Operation](#BKMK_CancelAndRestart), or [Run Multiple Operations and Queue the Output](#BKMK_RunMultipleOperations) to handle the reentrancy.</span></span>

## <a name="see-also"></a><span data-ttu-id="02314-233">Vea también</span><span class="sxs-lookup"><span data-stu-id="02314-233">See also</span></span>

- [<span data-ttu-id="02314-234">Tutorial: Acceso a web usando Async y Await (C# y Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02314-234">Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)</span></span>](walkthrough-accessing-the-web-by-using-async-and-await.md)
- [<span data-ttu-id="02314-235">Programación asincrónica con Async y Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02314-235">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](index.md)
