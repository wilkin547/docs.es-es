---
title: Controlar la reentrada en aplicaciones asincrónicas (C#)
description: Aprenda a controlar la reentrada en aplicaciones asincrónicas de C#, que hace referencia a volver a escribir una operación asincrónica antes de que finalice con posibles resultados inesperados.
ms.date: 07/20/2015
ms.assetid: 47c5075e-c448-45ce-9155-ed4e7e98c677
ms.openlocfilehash: fdd440d167b95268a5ae6de0e57a32f0fad66b7c
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925246"
---
# <a name="handling-reentrancy-in-async-apps-c"></a><span data-ttu-id="2c0b2-103">Controlar la reentrada en aplicaciones asincrónicas (C#)</span><span class="sxs-lookup"><span data-stu-id="2c0b2-103">Handling Reentrancy in Async Apps (C#)</span></span>

<span data-ttu-id="2c0b2-104">Cuando se incluye código asincrónico en una aplicación, hay que tener en cuenta (y posiblemente evitar) la reentrada, que significa volver a especificar una operación asincrónica antes de que finalice.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-104">When you include asynchronous code in your app, you should consider and possibly prevent reentrancy, which refers to reentering an asynchronous operation before it has completed.</span></span> <span data-ttu-id="2c0b2-105">Si no se identifican ni controlan las posibilidades de reentrada, pueden producirse resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-105">If you don't identify and handle possibilities for reentrancy, it can cause unexpected results.</span></span>

<span data-ttu-id="2c0b2-106">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="2c0b2-106">**In this topic**</span></span>

- [<span data-ttu-id="2c0b2-107">Reconocer la reentrada</span><span class="sxs-lookup"><span data-stu-id="2c0b2-107">Recognizing Reentrancy</span></span>](#BKMK_RecognizingReentrancy)

- [<span data-ttu-id="2c0b2-108">Controlar la reentrada</span><span class="sxs-lookup"><span data-stu-id="2c0b2-108">Handling Reentrancy</span></span>](#BKMK_HandlingReentrancy)

  - [<span data-ttu-id="2c0b2-109">Deshabilitar el botón de inicio</span><span class="sxs-lookup"><span data-stu-id="2c0b2-109">Disable the Start Button</span></span>](#BKMK_DisableTheStartButton)

  - [<span data-ttu-id="2c0b2-110">Cancelar y reiniciar la operación</span><span class="sxs-lookup"><span data-stu-id="2c0b2-110">Cancel and Restart the Operation</span></span>](#BKMK_CancelAndRestart)

  - [<span data-ttu-id="2c0b2-111">Ejecutar varias operaciones y poner en cola la salida</span><span class="sxs-lookup"><span data-stu-id="2c0b2-111">Run Multiple Operations and Queue the Output</span></span>](#BKMK_RunMultipleOperations)

- [<span data-ttu-id="2c0b2-112">Revisión y ejecución de la aplicación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="2c0b2-112">Reviewing and Running the Example App</span></span>](#BKMD_SettingUpTheExample)

> [!NOTE]
> <span data-ttu-id="2c0b2-113">Para ejecutar el ejemplo, debe tener instalado en el equipo Visual Studio 2012 o posterior y .NET Framework 4.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-113">To run the example, you must have Visual Studio 2012 or newer and .NET Framework 4.5 or newer installed on your computer.</span></span>

> [!NOTE]
> <span data-ttu-id="2c0b2-114">La versión 1.2 de Seguridad de la capa de transporte (TLS) es ahora la versión mínima que se usará en el desarrollo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-114">Transport Layer Security (TLS) version 1.2 is now the minimum version to use in your app development.</span></span> <span data-ttu-id="2c0b2-115">Si la aplicación tiene como destino una versión de .NET Framework anterior a la 4.7, consulte el artículo siguiente para obtener [Prácticas recomendadas de Seguridad de la capa de transporte (TLS) con .NET Framework](../../../../framework/network-programming/tls.md).</span><span class="sxs-lookup"><span data-stu-id="2c0b2-115">If your app targets a .NET Framework version earlier than 4.7, refer to the following article for [Transport Layer Security (TLS) best practices with .NET Framework](../../../../framework/network-programming/tls.md).</span></span>

## <a name="recognizing-reentrancy"></a><a name="BKMK_RecognizingReentrancy"></a> <span data-ttu-id="2c0b2-116">Reconocer la reentrada</span><span class="sxs-lookup"><span data-stu-id="2c0b2-116">Recognizing Reentrancy</span></span>

<span data-ttu-id="2c0b2-117">En el ejemplo de este tema, los usuarios hacen clic en un botón **Start** (Iniciar) para iniciar una aplicación asincrónica que descarga una serie de sitios web y calcula el número total de bytes que se descargan.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-117">In the example in this topic, users choose a **Start** button to initiate an asynchronous app that downloads a series of websites and calculates the total number of bytes that are downloaded.</span></span> <span data-ttu-id="2c0b2-118">Una versión sincrónica del ejemplo respondería de la misma forma independientemente de cuántas veces un usuario elija el botón porque, tras la primera vez, el subproceso de UI omite esos eventos hasta que finaliza la ejecución de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-118">A synchronous version of the example would respond the same way regardless of how many times a user chooses the button because, after the first time, the UI thread ignores those events until the app finishes running.</span></span> <span data-ttu-id="2c0b2-119">Sin embargo, en una aplicación asincrónica, el subproceso de UI continúa respondiendo y podría volver a introducir la operación asincrónica antes de que finalice.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-119">In an asynchronous app, however, the UI thread continues to respond, and you might reenter the asynchronous operation before it has completed.</span></span>

<span data-ttu-id="2c0b2-120">En el ejemplo siguiente se muestra la salida esperada si el usuario hace clic en el botón **Start** una sola vez.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-120">The following example shows the expected output if the user chooses the **Start** button only once.</span></span> <span data-ttu-id="2c0b2-121">Aparece una lista de los sitios web descargados con el tamaño, en bytes, de cada sitio.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-121">A list of the downloaded websites appears with the size, in bytes, of each site.</span></span> <span data-ttu-id="2c0b2-122">El número total de bytes aparece al final.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-122">The total number of bytes appears at the end.</span></span>

```output
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

<span data-ttu-id="2c0b2-123">Sin embargo, si el usuario elige el botón más de una vez, el controlador de eventos se invoca repetidamente y el proceso de descarga se vuelve a introducir cada vez.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-123">However, if the user chooses the button more than once, the event handler is invoked repeatedly, and the download process is reentered each time.</span></span> <span data-ttu-id="2c0b2-124">Como resultado, se ejecutan varias operaciones asincrónicas al mismo tiempo, la salida intercala los resultados y el número total de bytes es confuso.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-124">As a result, several asynchronous operations are running at the same time, the output interleaves the results, and the total number of bytes is confusing.</span></span>

```output
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

<span data-ttu-id="2c0b2-125">Al final de este tema puede revisar el código que genera este resultado.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-125">You can review the code that produces this output by scrolling to the end of this topic.</span></span> <span data-ttu-id="2c0b2-126">Si quiere experimentar con el código, descargue la solución en el equipo local y ejecute el proyecto WebsiteDownload o use el código que aparece al final de este tema para crear su propio proyecto.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-126">You can experiment with the code by downloading the solution to your local computer and then running the WebsiteDownload project or by using the code at the end of this topic to create your own project.</span></span> <span data-ttu-id="2c0b2-127">Para más información e instrucciones, vea [Revisión y ejecución de la aplicación de ejemplo](#BKMD_SettingUpTheExample).</span><span class="sxs-lookup"><span data-stu-id="2c0b2-127">For more information and instructions, see [Reviewing and Running the Example App](#BKMD_SettingUpTheExample).</span></span>

## <a name="handling-reentrancy"></a><a name="BKMK_HandlingReentrancy"></a> <span data-ttu-id="2c0b2-128">Controlar la reentrada</span><span class="sxs-lookup"><span data-stu-id="2c0b2-128">Handling Reentrancy</span></span>

<span data-ttu-id="2c0b2-129">La reentrada se puede controlar de varias maneras en función de lo que se desee de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-129">You can handle reentrancy in a variety of ways, depending on what you want your app to do.</span></span> <span data-ttu-id="2c0b2-130">Este tema presenta los siguientes ejemplos:</span><span class="sxs-lookup"><span data-stu-id="2c0b2-130">This topic presents the following examples:</span></span>

- [<span data-ttu-id="2c0b2-131">Deshabilitar el botón de inicio</span><span class="sxs-lookup"><span data-stu-id="2c0b2-131">Disable the Start Button</span></span>](#BKMK_DisableTheStartButton)

  <span data-ttu-id="2c0b2-132">Deshabilite el botón **Start** (Iniciar) mientras se ejecuta la operación de modo que el usuario no pueda interrumpirla.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-132">Disable the **Start** button while the operation is running so that the user can't interrupt it.</span></span>

- [<span data-ttu-id="2c0b2-133">Cancelar y reiniciar la operación</span><span class="sxs-lookup"><span data-stu-id="2c0b2-133">Cancel and Restart the Operation</span></span>](#BKMK_CancelAndRestart)

  <span data-ttu-id="2c0b2-134">Cancele cualquier operación que se esté ejecutando cuando el usuario haga clic de nuevo en el botón **Start** y, después, deje que continúe la última operación solicitada.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-134">Cancel any operation that is still running when the user chooses the **Start** button again, and then let the most recently requested operation continue.</span></span>

- [<span data-ttu-id="2c0b2-135">Ejecutar varias operaciones y poner en cola la salida</span><span class="sxs-lookup"><span data-stu-id="2c0b2-135">Run Multiple Operations and Queue the Output</span></span>](#BKMK_RunMultipleOperations)

  <span data-ttu-id="2c0b2-136">Permita que todas las operaciones solicitadas se ejecuten de forma asincrónica, pero coordine la presentación de salida para que los resultados de cada operación aparecen juntos y en orden.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-136">Allow all requested operations to run asynchronously, but coordinate the display of output so that the results from each operation appear together and in order.</span></span>

### <a name="disable-the-start-button"></a><a name="BKMK_DisableTheStartButton"></a> <span data-ttu-id="2c0b2-137">Deshabilitar el botón de inicio</span><span class="sxs-lookup"><span data-stu-id="2c0b2-137">Disable the Start Button</span></span>

<span data-ttu-id="2c0b2-138">Puede bloquear el botón **Start** mientras se ejecuta una operación si lo deshabilita en la parte superior del controlador de eventos `StartButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-138">You can block the **Start** button while an operation is running by disabling the button at the top of the `StartButton_Click` event handler.</span></span> <span data-ttu-id="2c0b2-139">A continuación, cuando finalice la operación, puede habilitar de nuevo el botón desde un bloque `finally` de modo que los usuarios puedan volver a ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-139">You can then reenable the button from within a  `finally` block when the operation finishes so that users can run the app again.</span></span>

<span data-ttu-id="2c0b2-140">Para configurar este escenario, haga los cambios siguientes en el código básico que se proporciona en [Revisión y ejecución de la aplicación de ejemplo](#BKMD_SettingUpTheExample).</span><span class="sxs-lookup"><span data-stu-id="2c0b2-140">To set up this scenario, make the following changes to the basic code that is provided in [Reviewing and Running the Example App](#BKMD_SettingUpTheExample).</span></span> <span data-ttu-id="2c0b2-141">También puede descargar la aplicación finalizada de [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06) (Ejemplos asincrónicos: reentrada en aplicaciones de escritorio de .NET).</span><span class="sxs-lookup"><span data-stu-id="2c0b2-141">You can also download the finished app from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span> <span data-ttu-id="2c0b2-142">El nombre del proyecto es DisableStartButton.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-142">The name of the project is DisableStartButton.</span></span>

```csharp
private async void StartButton_Click(object sender, RoutedEventArgs e)
{
    // This line is commented out to make the results clearer in the output.
    //ResultsTextBox.Text = "";

    // ***Disable the Start button until the downloads are complete.
    StartButton.IsEnabled = false;

    try
    {
        await AccessTheWebAsync();
    }
    catch (Exception)
    {
        ResultsTextBox.Text += "\r\nDownloads failed.";
    }
    // ***Enable the Start button in case you want to run the program again.
    finally
    {
        StartButton.IsEnabled = true;
    }
}
```

<span data-ttu-id="2c0b2-143">Como resultado de los cambios, el botón no responde mientras `AccessTheWebAsync` está descargando los sitios web, por lo que no se puede volver a introducir el proceso.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-143">As a result of the changes, the button doesn't respond while `AccessTheWebAsync` is downloading the websites, so the process can't be reentered.</span></span>

### <a name="cancel-and-restart-the-operation"></a><a name="BKMK_CancelAndRestart"></a> <span data-ttu-id="2c0b2-144">Cancelar y reiniciar la operación</span><span class="sxs-lookup"><span data-stu-id="2c0b2-144">Cancel and Restart the Operation</span></span>

<span data-ttu-id="2c0b2-145">En lugar de deshabilitar el botón **Start**, puede mantenerlo activo y, si el usuario vuelve a seleccionarlo, cancelar la operación que ya se está ejecutando y permitir que la última operación iniciada continúe.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-145">Instead of disabling the **Start** button, you can keep the button active but, if the user chooses that button again, cancel the operation that's already running and let the most recently started operation continue.</span></span>

<span data-ttu-id="2c0b2-146">Para más información sobre la cancelación, vea [Fine-Tuning Your Async Application (C#)](./fine-tuning-your-async-application.md) (Ajustar la aplicación asincrónica [C#]).</span><span class="sxs-lookup"><span data-stu-id="2c0b2-146">For more information about cancellation, see [Fine-Tuning Your Async Application (C#)](./fine-tuning-your-async-application.md).</span></span>

<span data-ttu-id="2c0b2-147">Para configurar este escenario, haga los cambios siguientes en el código básico que se proporciona en [Revisión y ejecución de la aplicación de ejemplo](#BKMD_SettingUpTheExample).</span><span class="sxs-lookup"><span data-stu-id="2c0b2-147">To set up this scenario, make the following changes to the basic code that is provided in [Reviewing and Running the Example App](#BKMD_SettingUpTheExample).</span></span> <span data-ttu-id="2c0b2-148">También puede descargar la aplicación finalizada de [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06) (Ejemplos asincrónicos: reentrada en aplicaciones de escritorio de .NET).</span><span class="sxs-lookup"><span data-stu-id="2c0b2-148">You can also download the finished app from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span> <span data-ttu-id="2c0b2-149">El nombre del proyecto es CancelAndRestart.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-149">The name of the project is CancelAndRestart.</span></span>

1. <span data-ttu-id="2c0b2-150">Declare una variable de <xref:System.Threading.CancellationTokenSource>, `cts`, que esté en el ámbito de todos los métodos.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-150">Declare a <xref:System.Threading.CancellationTokenSource> variable, `cts`, that's in scope for all methods.</span></span>

    ```csharp
    public partial class MainWindow : Window   // Or class MainPage
    {
        // *** Declare a System.Threading.CancellationTokenSource.
        CancellationTokenSource cts;
    ```

2. <span data-ttu-id="2c0b2-151">En `StartButton_Click`, determine si una operación ya está en curso.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-151">In `StartButton_Click`, determine whether an operation is already underway.</span></span> <span data-ttu-id="2c0b2-152">Si el valor de `cts` es NULL, ya no hay ninguna operación activa.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-152">If the value of `cts` is null, no operation is already active.</span></span> <span data-ttu-id="2c0b2-153">Si el valor no es null, se cancela la operación que se esté ejecutando.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-153">If the value isn't null, the operation that is already running is canceled.</span></span>

    ```csharp
    // *** If a download process is already underway, cancel it.
    if (cts != null)
    {
        cts.Cancel();
    }
    ```

3. <span data-ttu-id="2c0b2-154">Establezca `cts` en un valor diferente que represente el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-154">Set `cts` to a different value that represents the current process.</span></span>

    ```csharp
    // *** Now set cts to a new value that you can use to cancel the current process
    // if the button is chosen again.
    CancellationTokenSource newCTS = new CancellationTokenSource();
    cts = newCTS;
    ```

4. <span data-ttu-id="2c0b2-155">Al final de `StartButton_Click`, el proceso actual está completo, así que vuelva a establecer el valor de `cts` en null.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-155">At the end of `StartButton_Click`, the current process is complete, so set the value of `cts` back to null.</span></span>

    ```csharp
    // *** When the process is complete, signal that another process can begin.
    if (cts == newCTS)
        cts = null;
    ```

<span data-ttu-id="2c0b2-156">El código siguiente muestra todos los cambios en `StartButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-156">The following code shows all the changes in `StartButton_Click`.</span></span> <span data-ttu-id="2c0b2-157">Las adiciones se marcan con asteriscos.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-157">The additions are marked with asterisks.</span></span>

```csharp
private async void StartButton_Click(object sender, RoutedEventArgs e)
{
    // This line is commented out to make the results clearer in the output.
    //ResultsTextBox.Clear();

    // *** If a download process is already underway, cancel it.
    if (cts != null)
    {
        cts.Cancel();
    }

    // *** Now set cts to cancel the current process if the button is chosen again.
    CancellationTokenSource newCTS = new CancellationTokenSource();
    cts = newCTS;

    try
    {
        // ***Send cts.Token to carry the message if there is a cancellation request.
        await AccessTheWebAsync(cts.Token);

    }
    // *** Catch cancellations separately.
    catch (OperationCanceledException)
    {
        ResultsTextBox.Text += "\r\nDownloads canceled.\r\n";
    }
    catch (Exception)
    {
        ResultsTextBox.Text += "\r\nDownloads failed.\r\n";
    }
    // *** When the process is complete, signal that another process can proceed.
    if (cts == newCTS)
        cts = null;
}
```

<span data-ttu-id="2c0b2-158">En `AccessTheWebAsync`, realice los siguientes cambios.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-158">In `AccessTheWebAsync`, make the following changes.</span></span>

- <span data-ttu-id="2c0b2-159">Agregue un parámetro para aceptar el token de cancelación de `StartButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-159">Add a parameter to accept the cancellation token from `StartButton_Click`.</span></span>

- <span data-ttu-id="2c0b2-160">Use el método <xref:System.Net.Http.HttpClient.GetAsync%2A> para descargar los sitios web porque `GetAsync` acepta un argumento <xref:System.Threading.CancellationToken>.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-160">Use the <xref:System.Net.Http.HttpClient.GetAsync%2A> method to download the websites because `GetAsync` accepts a <xref:System.Threading.CancellationToken> argument.</span></span>

- <span data-ttu-id="2c0b2-161">Antes de llamar a `DisplayResults` para mostrar los resultados de los sitios web descargados, revise `ct` para comprobar que no se ha cancelado la operación actual.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-161">Before calling `DisplayResults` to display the results for each downloaded website, check `ct` to verify that the current operation hasn't been canceled.</span></span>

<span data-ttu-id="2c0b2-162">El código siguiente muestra estos cambios marcados con asteriscos.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-162">The following code shows these changes, which are marked with asterisks.</span></span>

```csharp
// *** Provide a parameter for the CancellationToken from StartButton_Click.
async Task AccessTheWebAsync(CancellationToken ct)
{
    // Declare an HttpClient object.
    HttpClient client = new HttpClient();

    // Make a list of web addresses.
    List<string> urlList = SetUpURLList();

    var total = 0;
    var position = 0;

    foreach (var url in urlList)
    {
        // *** Use the HttpClient.GetAsync method because it accepts a
        // cancellation token.
        HttpResponseMessage response = await client.GetAsync(url, ct);

        // *** Retrieve the website contents from the HttpResponseMessage.
        byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

        // *** Check for cancellations before displaying information about the
        // latest site.
        ct.ThrowIfCancellationRequested();

        DisplayResults(url, urlContents, ++position);

        // Update the total.
        total += urlContents.Length;
    }

    // Display the total count for all of the websites.
    ResultsTextBox.Text +=
        $"\r\n\r\nTOTAL bytes returned:  {total}\r\n";
}
```

<span data-ttu-id="2c0b2-163">Si hace clic varias veces en el botón **Start** mientras se ejecuta esta aplicación, debería producir resultados similares a la salida siguiente.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-163">If you choose the **Start** button several times while this app is running, it should produce results that resemble the following output.</span></span>

```output
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

<span data-ttu-id="2c0b2-164">Para eliminar las listas parciales, quite el comentario de la primera línea de código en `StartButton_Click` para borrar el cuadro de texto cada vez que el usuario reinicie la operación.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-164">To eliminate the partial lists, uncomment the first line of code in `StartButton_Click` to clear the text box each time the user restarts the operation.</span></span>

### <a name="run-multiple-operations-and-queue-the-output"></a><a name="BKMK_RunMultipleOperations"></a> <span data-ttu-id="2c0b2-165">Ejecutar varias operaciones y poner en cola el resultado</span><span class="sxs-lookup"><span data-stu-id="2c0b2-165">Run Multiple Operations and Queue the Output</span></span>

<span data-ttu-id="2c0b2-166">Este tercer ejemplo es el más complicado porque la aplicación inicia otra operación asincrónica cada vez que el usuario selecciona el botón **Start** y todas las operaciones se ejecutan hasta completarse.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-166">This third example is the most complicated in that the app starts another asynchronous operation each time that the user chooses the **Start** button, and all the operations run to completion.</span></span> <span data-ttu-id="2c0b2-167">Todas las operaciones solicitadas descargan los sitios web de la lista de forma asincrónica, pero la salida de las operaciones se presenta de manera secuencial.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-167">All the requested operations download websites from the list asynchronously, but the output from the operations is presented sequentially.</span></span> <span data-ttu-id="2c0b2-168">Es decir, la actividad de descarga real se intercala, según se muestra en la salida de [Reconocer la reentrada](#BKMK_RecognizingReentrancy), pero la lista de resultados de cada grupo se presenta por separado.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-168">That is, the actual downloading activity is interleaved, as the output in [Recognizing Reentrancy](#BKMK_RecognizingReentrancy) shows, but the list of results for each group is presented separately.</span></span>

<span data-ttu-id="2c0b2-169">Las operaciones comparten una <xref:System.Threading.Tasks.Task> global, `pendingWork`, que actúa de equipo selector para el proceso de visualización.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-169">The operations share a global <xref:System.Threading.Tasks.Task>, `pendingWork`, which serves as a gatekeeper for the display process.</span></span>

<span data-ttu-id="2c0b2-170">Para configurar este escenario, haga los cambios siguientes en el código básico que se proporciona en [Revisión y ejecución de la aplicación de ejemplo](#BKMD_SettingUpTheExample).</span><span class="sxs-lookup"><span data-stu-id="2c0b2-170">To set up this scenario, make the following changes to the basic code that is provided in [Reviewing and Running the Example App](#BKMD_SettingUpTheExample).</span></span> <span data-ttu-id="2c0b2-171">También puede descargar la aplicación finalizada de [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06) (Ejemplos asincrónicos: reentrada en aplicaciones de escritorio de .NET).</span><span class="sxs-lookup"><span data-stu-id="2c0b2-171">You can also download the finished app from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span> <span data-ttu-id="2c0b2-172">El nombre del proyecto es QueueResults.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-172">The name of the project is QueueResults.</span></span>

<span data-ttu-id="2c0b2-173">En la salida siguiente se muestra el resultado cuando el usuario selecciona el botón **Start** una sola vez.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-173">The following output shows the result if the user chooses the **Start** button only once.</span></span> <span data-ttu-id="2c0b2-174">La etiqueta de letra A indica que el resultado se corresponde a la primera vez que se selecciona el botón **Start**.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-174">The letter label, A, indicates that the result is from the first time the **Start** button is chosen.</span></span> <span data-ttu-id="2c0b2-175">Los números muestran el orden de las direcciones URL en la lista de destinos de descarga.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-175">The numbers show the order of the URLs in the list of download targets.</span></span>

```output
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

<span data-ttu-id="2c0b2-176">Si el usuario hace clic tres veces en el botón **Start**, la aplicación genera una salida similar a las líneas siguientes.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-176">If the user chooses the **Start** button three times, the app produces output that resembles the following lines.</span></span> <span data-ttu-id="2c0b2-177">Las líneas de información que comienzan con una almohadilla (#) siguen el progreso de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-177">The information lines that start with a pound sign (#) trace the progress of the application.</span></span>

```output
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

<span data-ttu-id="2c0b2-178">Los grupos B y C se inician antes de finalizar el grupo A, pero la salida de cada grupo aparece por separado.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-178">Groups B and C start before group A has finished, but the output for the each group appears separately.</span></span> <span data-ttu-id="2c0b2-179">Primero aparece toda la salida del grupo A, seguida de la salida del grupo B y después la del grupo C. La aplicación siempre muestra los grupos en orden y, en cada grupo, muestra la información sobre los sitios web individuales en el orden en que las direcciones URL aparecen en la lista de direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-179">All the output for group A appears first, followed by all the output for group B, and then all the output for group C. The app always displays the groups in order and, for each group, always displays the information about the individual websites in the order that the URLs appear in the list of URLs.</span></span>

<span data-ttu-id="2c0b2-180">Sin embargo, no es posible predecir el orden en que se producen las descargas.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-180">However, you can't predict the order in which the downloads actually happen.</span></span> <span data-ttu-id="2c0b2-181">Después de iniciarse varios grupos, las tareas de descarga que generan están activas.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-181">After multiple groups have been started, the download tasks that they generate are all active.</span></span> <span data-ttu-id="2c0b2-182">No se puede dar por sentado que A-1 se descargará antes que B-1, ni que A-1 se descargará antes que A-2.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-182">You can't assume that A-1 will be downloaded before B-1, and you can't assume that A-1 will be downloaded before A-2.</span></span>

#### <a name="global-definitions"></a><span data-ttu-id="2c0b2-183">Definiciones globales</span><span class="sxs-lookup"><span data-stu-id="2c0b2-183">Global Definitions</span></span>

<span data-ttu-id="2c0b2-184">El código de ejemplo contiene las dos declaraciones globales siguientes que están visibles en todos los métodos.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-184">The sample code contains the following two global declarations that are visible from all methods.</span></span>

```csharp
public partial class MainWindow : Window  // Class MainPage in Windows Store app.
{
    // ***Declare the following variables where all methods can access them.
    private Task pendingWork = null;
    private char group = (char)('A' - 1);
```

<span data-ttu-id="2c0b2-185">La variable de `Task`, `pendingWork`, supervisa el proceso de presentación e impide que un grupo interrumpa la operación de presentación de otro grupo.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-185">The `Task` variable, `pendingWork`, oversees the display process and prevents any group from interrupting another group's display operation.</span></span> <span data-ttu-id="2c0b2-186">La variable de caracteres, `group`, etiqueta la salida de diferentes grupos para comprobar que los resultados aparecen en el orden esperado.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-186">The character variable, `group`, labels the output from different groups to verify that results appear in the expected order.</span></span>

#### <a name="the-click-event-handler"></a><span data-ttu-id="2c0b2-187">El controlador de eventos Click</span><span class="sxs-lookup"><span data-stu-id="2c0b2-187">The Click Event Handler</span></span>

<span data-ttu-id="2c0b2-188">El controlador de eventos, `StartButton_Click`, incrementa la letra del grupo cada vez que el usuario selecciona el botón **Start**.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-188">The event handler, `StartButton_Click`, increments the group letter each time the user chooses the **Start** button.</span></span> <span data-ttu-id="2c0b2-189">A continuación, el controlador llama a `AccessTheWebAsync` para ejecutar la operación de descarga.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-189">Then the handler calls `AccessTheWebAsync` to run the downloading operation.</span></span>

```csharp
private async void StartButton_Click(object sender, RoutedEventArgs e)
{
    // ***Verify that each group's results are displayed together, and that
    // the groups display in order, by marking each group with a letter.
    group = (char)(group + 1);
    ResultsTextBox.Text += $"\r\n\r\n#Starting group {group}.";

    try
    {
        // *** Pass the group value to AccessTheWebAsync.
        char finishedGroup = await AccessTheWebAsync(group);

        // The following line verifies a successful return from the download and
        // display procedures.
        ResultsTextBox.Text += $"\r\n\r\n#Group {finishedGroup} is complete.\r\n";
    }
    catch (Exception)
    {
        ResultsTextBox.Text += "\r\nDownloads failed.";
    }
}
```

#### <a name="the-accessthewebasync-method"></a><span data-ttu-id="2c0b2-190">El método AccessTheWebAsync</span><span class="sxs-lookup"><span data-stu-id="2c0b2-190">The AccessTheWebAsync Method</span></span>

<span data-ttu-id="2c0b2-191">En este ejemplo se divide `AccessTheWebAsync` en dos métodos.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-191">This example splits `AccessTheWebAsync` into two methods.</span></span> <span data-ttu-id="2c0b2-192">El primer método, `AccessTheWebAsync`, inicia todas las tareas de descarga de un grupo y configura `pendingWork` para controlar el proceso de visualización.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-192">The first method, `AccessTheWebAsync`, starts all the download tasks for a group and sets up `pendingWork` to control the display process.</span></span> <span data-ttu-id="2c0b2-193">El método usa una consulta de Language Integrated Query (consulta LINQ) y <xref:System.Linq.Enumerable.ToArray%2A> para iniciar todas las tareas de descarga al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-193">The method uses a Language Integrated Query (LINQ query) and <xref:System.Linq.Enumerable.ToArray%2A> to start all the download tasks at the same time.</span></span>

<span data-ttu-id="2c0b2-194">A continuación, `AccessTheWebAsync` llama a `FinishOneGroupAsync` para esperar la finalización de todas las descargas y mostrar su duración.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-194">`AccessTheWebAsync` then calls `FinishOneGroupAsync` to await the completion of each download and display its length.</span></span>

<span data-ttu-id="2c0b2-195">`FinishOneGroupAsync` devuelve una tarea que se asigna a `pendingWork` en `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-195">`FinishOneGroupAsync` returns a task that's assigned to `pendingWork` in `AccessTheWebAsync`.</span></span> <span data-ttu-id="2c0b2-196">Ese valor evita que otra operación interrumpa la tarea antes de que finalice.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-196">That value prevents interruption by another operation before the task is complete.</span></span>

```csharp
private async Task<char> AccessTheWebAsync(char grp)
{
    HttpClient client = new HttpClient();

    // Make a list of the web addresses to download.
    List<string> urlList = SetUpURLList();

    // ***Kick off the downloads. The application of ToArray activates all the download tasks.
    Task<byte[]>[] getContentTasks = urlList.Select(url => client.GetByteArrayAsync(url)).ToArray();

    // ***Call the method that awaits the downloads and displays the results.
    // Assign the Task that FinishOneGroupAsync returns to the gatekeeper task, pendingWork.
    pendingWork = FinishOneGroupAsync(urlList, getContentTasks, grp);

    ResultsTextBox.Text += $"\r\n#Task assigned for group {grp}. Download tasks are active.\r\n";

    // ***This task is complete when a group has finished downloading and displaying.
    await pendingWork;

    // You can do other work here or just return.
    return grp;
}
```

#### <a name="the-finishonegroupasync-method"></a><span data-ttu-id="2c0b2-197">El método FinishOneGroupAsync</span><span class="sxs-lookup"><span data-stu-id="2c0b2-197">The FinishOneGroupAsync Method</span></span>

<span data-ttu-id="2c0b2-198">Este método recorre las tareas de descarga de un grupo, espera por cada una de ellas, muestra la longitud del sitio web descargado y agrega la longitud total.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-198">This method cycles through the download tasks in a group, awaiting each one, displaying the length of the downloaded website, and adding the length to the total.</span></span>

<span data-ttu-id="2c0b2-199">La primera instrucción de `FinishOneGroupAsync` usa `pendingWork` para asegurarse de que la entrada al método no interfiere con una operación que ya está en el proceso de visualización o que ya está esperando.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-199">The first statement in `FinishOneGroupAsync` uses `pendingWork` to make sure that entering the method doesn't interfere with an operation that is already in the display process or that's already waiting.</span></span> <span data-ttu-id="2c0b2-200">Si tal operación está en curso, la operación introducida debe esperar su turno.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-200">If such an operation is in progress, the entering operation must wait its turn.</span></span>

```csharp
private async Task FinishOneGroupAsync(List<string> urls, Task<byte[]>[] contentTasks, char grp)
{
    // ***Wait for the previous group to finish displaying results.
    if (pendingWork != null) await pendingWork;

    int total = 0;

    // contentTasks is the array of Tasks that was created in AccessTheWebAsync.
    for (int i = 0; i < contentTasks.Length; i++)
    {
        // Await the download of a particular URL, and then display the URL and
        // its length.
        byte[] content = await contentTasks[i];
        DisplayResults(urls[i], content, i, grp);
        total += content.Length;
    }

    // Display the total count for all of the websites.
    ResultsTextBox.Text +=
        $"\r\n\r\nTOTAL bytes returned:  {total}\r\n";
}
```

#### <a name="points-of-interest"></a><span data-ttu-id="2c0b2-201">Puntos de interés</span><span class="sxs-lookup"><span data-stu-id="2c0b2-201">Points of Interest</span></span>

<span data-ttu-id="2c0b2-202">Las líneas de información que comienzan con un signo de almohadilla (#) en la salida aclaran cómo funciona este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-202">The information lines that start with a pound sign (#) in the output clarify how this example works.</span></span>

<span data-ttu-id="2c0b2-203">La salida muestra los siguientes patrones.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-203">The output shows the following patterns.</span></span>

- <span data-ttu-id="2c0b2-204">Un grupo puede iniciarse mientras un grupo anterior muestra su salida, pero la visualización del grupo anterior no se ve interrumpida.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-204">A group can be started while a previous group is displaying its output, but the display of the previous group's output isn't interrupted.</span></span>

    ```output
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

- <span data-ttu-id="2c0b2-205">La tarea `pendingWork` es NULL al inicio de `FinishOneGroupAsync` solo para el grupo A, que fue el primero en empezar.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-205">The `pendingWork` task is null  at the start of `FinishOneGroupAsync` only for group A, which started first.</span></span> <span data-ttu-id="2c0b2-206">El grupo A todavía no ha completado una expresión await cuando alcanza `FinishOneGroupAsync`.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-206">Group A hasn't yet completed an await expression when it reaches `FinishOneGroupAsync`.</span></span> <span data-ttu-id="2c0b2-207">Por lo tanto, el control no se ha devuelto a `AccessTheWebAsync`, y la primera asignación a `pendingWork` no se ha producido.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-207">Therefore, control hasn't returned to `AccessTheWebAsync`, and the first assignment to `pendingWork` hasn't occurred.</span></span>

- <span data-ttu-id="2c0b2-208">Las dos líneas siguientes siempre aparecen juntas en la salida.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-208">The following two lines always appear together in the output.</span></span> <span data-ttu-id="2c0b2-209">El código no se interrumpa nunca entre el inicio de la operación de un grupo en de `StartButton_Click` y la asignación de una tarea del grupo a `pendingWork`.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-209">The code is never interrupted between starting a group's operation in `StartButton_Click` and assigning a task for the group to `pendingWork`.</span></span>

    ```output
    #Starting group B.
    #Task assigned for group B. Download tasks are active.
    ```

    <span data-ttu-id="2c0b2-210">Una vez que un grupo introduce `StartButton_Click`, la operación no completa una expresión await hasta que la operación introduce `FinishOneGroupAsync`.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-210">After a group enters `StartButton_Click`, the operation doesn't complete an await expression until the operation enters `FinishOneGroupAsync`.</span></span> <span data-ttu-id="2c0b2-211">Por lo tanto, ninguna otra operación puede lograr el control durante ese segmento de código.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-211">Therefore, no other operation can gain control during that segment of code.</span></span>

## <a name="reviewing-and-running-the-example-app"></a><a name="BKMD_SettingUpTheExample"></a> <span data-ttu-id="2c0b2-212">Revisión y ejecución de la aplicación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="2c0b2-212">Reviewing and Running the Example App</span></span>

<span data-ttu-id="2c0b2-213">Para entender mejor la aplicación de ejemplo, puede descargarla, compilarla usted mismo o revisar el código al final de este tema sin necesidad de implementar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-213">To better understand the example app, you can download it, build it yourself, or review the code at the end of this topic without implementing the app.</span></span>

> [!NOTE]
> <span data-ttu-id="2c0b2-214">Para ejecutar el ejemplo como aplicación de escritorio de Windows Presentation Foundation (WPF), debe tener instalado en el equipo Visual Studio 2012 o posterior, y .NET Framework 4.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-214">To run the example as a Windows Presentation Foundation (WPF) desktop app, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

### <a name="downloading-the-app"></a><a name="BKMK_DownloadingTheApp"></a> <span data-ttu-id="2c0b2-215">Descargar la aplicación</span><span class="sxs-lookup"><span data-stu-id="2c0b2-215">Downloading the App</span></span>

1. <span data-ttu-id="2c0b2-216">Descargue el archivo comprimido de [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06) (Ejemplos asincrónicos: reentrada en aplicaciones de escritorio de .NET).</span><span class="sxs-lookup"><span data-stu-id="2c0b2-216">Download the compressed file from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span>

2. <span data-ttu-id="2c0b2-217">Descomprima el archivo descargado y, a continuación, inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-217">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

3. <span data-ttu-id="2c0b2-218">En la barra de menús, elija **Archivo**, **Abrir**, **Proyecto o solución**.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-218">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>

4. <span data-ttu-id="2c0b2-219">Navegue hasta la carpeta que contiene el código de ejemplo descomprimido y, a continuación, abra el archivo de solución (.sln).</span><span class="sxs-lookup"><span data-stu-id="2c0b2-219">Navigate to the folder that holds the decompressed sample code, and then open the solution (.sln) file.</span></span>

5. <span data-ttu-id="2c0b2-220">En el **Explorador de soluciones**, abra el menú contextual del proyecto que quiere ejecutar y, después, elija **Establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-220">In **Solution Explorer**, open the shortcut menu for the project that you want to run, and then choose **Set as StartUpProject**.</span></span>

6. <span data-ttu-id="2c0b2-221">Elija las teclas CTRL+F5 para compilar y ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-221">Choose the CTRL+F5 keys to build and run the project.</span></span>

### <a name="building-the-app"></a><a name="BKMK_BuildingTheApp"></a> <span data-ttu-id="2c0b2-222">Compilar la aplicación</span><span class="sxs-lookup"><span data-stu-id="2c0b2-222">Building the App</span></span>

<span data-ttu-id="2c0b2-223">La sección siguiente proporciona el código para compilar el ejemplo como una aplicación de WPF.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-223">The following section provides the code to build the example as a WPF app.</span></span>

##### <a name="to-build-a-wpf-app"></a><span data-ttu-id="2c0b2-224">Para compilar una aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="2c0b2-224">To build a WPF app</span></span>

1. <span data-ttu-id="2c0b2-225">Inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-225">Start Visual Studio.</span></span>

2. <span data-ttu-id="2c0b2-226">En la barra de menús, elija **Archivo**, **Nuevo**, **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-226">On the menu bar, choose **File**, **New**, **Project**.</span></span>

     <span data-ttu-id="2c0b2-227">Aparece el cuadro de diálogo **Nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="2c0b2-227">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="2c0b2-228">En el panel **Plantillas instaladas**, expanda **Visual C#** y después **Windows**.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-228">In the **Installed Templates** pane, expand **Visual C#**, and then expand **Windows**.</span></span>

4. <span data-ttu-id="2c0b2-229">En la lista de tipos de proyecto, seleccione **Aplicación WPF**.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-229">In the list of project types, choose **WPF Application**.</span></span>

5. <span data-ttu-id="2c0b2-230">Asigne un nombre al proyecto `WebsiteDownloadWPF`, elija la versión 4.6 de .NET Framework o una posterior y, después, haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-230">Name the project `WebsiteDownloadWPF`, choose .NET Framework version of 4.6 or higher, and then click the **OK** button.</span></span>

     <span data-ttu-id="2c0b2-231">El proyecto nuevo aparece en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-231">The new project appears in **Solution Explorer**.</span></span>

6. <span data-ttu-id="2c0b2-232">En el Editor de código de Visual Studio, elija la pestaña **MainWindow.xaml** .</span><span class="sxs-lookup"><span data-stu-id="2c0b2-232">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>

     <span data-ttu-id="2c0b2-233">Si la pestaña no está visible, abra el menú contextual de MainWindow.xaml en el **Explorador de soluciones**y elija **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-233">If the tab isn't visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **View Code**.</span></span>

7. <span data-ttu-id="2c0b2-234">En la vista **XAML** de MainWindow.xaml, reemplace el código por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-234">In the **XAML** view of MainWindow.xaml, replace the code with the following code.</span></span>

    ```csharp
    <Window x:Class="WebsiteDownloadWPF.MainWindow"
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

     <span data-ttu-id="2c0b2-235">En la vista **Diseño** de MainWindow.xaml aparece una ventana simple que contiene un cuadro de texto y un botón.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-235">A simple window that contains a text box and a button appears in the **Design** view of MainWindow.xaml.</span></span>

8. <span data-ttu-id="2c0b2-236">En el **Explorador de soluciones**, haga clic con el botón derecho en **Referencias** y seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-236">In **Solution Explorer**, right-click on **References** and select **Add Reference**.</span></span>

     <span data-ttu-id="2c0b2-237">Agregue una referencia para <xref:System.Net.Http>, si aún no está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-237">Add a reference for <xref:System.Net.Http>, if it is not selected already.</span></span>

9. <span data-ttu-id="2c0b2-238">En el **Explorador de soluciones**, abra el menú contextual de MainWindow.xaml.cs y después elija **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-238">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.cs, and then choose **View Code**.</span></span>

10. <span data-ttu-id="2c0b2-239">Reemplace el código del archivo MainWindow.xaml.cs por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-239">In MainWindow.xaml.cs, replace the code with the following code.</span></span>

    ```csharp
    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Text;
    using System.Threading.Tasks;
    using System.Windows;
    using System.Windows.Controls;
    using System.Windows.Data;
    using System.Windows.Documents;
    using System.Windows.Input;
    using System.Windows.Media;
    using System.Windows.Media.Imaging;
    using System.Windows.Navigation;
    using System.Windows.Shapes;

    // Add the following using directives, and add a reference for System.Net.Http.
    using System.Net.Http;
    using System.Threading;

    namespace WebsiteDownloadWPF
    {
        public partial class MainWindow : Window
        {
            public MainWindow()
            {
                System.Net.ServicePointManager.SecurityProtocol |= System.Net.SecurityProtocolType.Tls12;
                InitializeComponent();
            }

            private async void StartButton_Click(object sender, RoutedEventArgs e)
            {
                // This line is commented out to make the results clearer in the output.
                //ResultsTextBox.Text = "";

                try
                {
                    await AccessTheWebAsync();
                }
                catch (Exception)
                {
                    ResultsTextBox.Text += "\r\nDownloads failed.";
                }
            }

            private async Task AccessTheWebAsync()
            {
                // Declare an HttpClient object.
                HttpClient client = new HttpClient();

                // Make a list of web addresses.
                List<string> urlList = SetUpURLList();

                var total = 0;
                var position = 0;

                foreach (var url in urlList)
                {
                    // GetByteArrayAsync returns a task. At completion, the task
                    // produces a byte array.
                    byte[] urlContents = await client.GetByteArrayAsync(url);

                    DisplayResults(url, urlContents, ++position);

                    // Update the total.
                    total += urlContents.Length;
                }

                // Display the total count for all of the websites.
                ResultsTextBox.Text +=
                    $"\r\n\r\nTOTAL bytes returned:  {total}\r\n";
            }

            private List<string> SetUpURLList()
            {
                List<string> urls = new List<string>
                {
                    "https://msdn.microsoft.com/library/hh191443.aspx",
                    "https://msdn.microsoft.com/library/aa578028.aspx",
                    "https://msdn.microsoft.com/library/jj155761.aspx",
                    "https://msdn.microsoft.com/library/hh290140.aspx",
                    "https://msdn.microsoft.com/library/hh524395.aspx",
                    "https://msdn.microsoft.com/library/ms404677.aspx",
                    "https://msdn.microsoft.com",
                    "https://msdn.microsoft.com/library/ff730837.aspx"
                };
                return urls;
            }

            private void DisplayResults(string url, byte[] content, int pos)
            {
                // Display the length of each website. The string format is designed
                // to be used with a monospaced font, such as Lucida Console or
                // Global Monospace.

                // Strip off the "https://".
                var displayURL = url.Replace("https://", "");
                // Display position in the URL list, the URL, and the number of bytes.
                ResultsTextBox.Text += $"\n{pos}. {displayURL,-58} {content.Length,8}";
            }
        }
    }
    ```

11. <span data-ttu-id="2c0b2-240">Presiones las teclas CTRL+F5 para ejecutar el programa y luego haga clic varias veces en el botón **Start**.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-240">Choose the CTRL+F5 keys to run the program, and then choose the **Start** button several times.</span></span>

12. <span data-ttu-id="2c0b2-241">Realice los cambios de [Deshabilitar el botón de inicio](#BKMK_DisableTheStartButton), [Cancelar y reiniciar la operación](#BKMK_CancelAndRestart) o [Ejecutar varias operaciones y poner en cola el resultado](#BKMK_RunMultipleOperations) para controlar la reentrada.</span><span class="sxs-lookup"><span data-stu-id="2c0b2-241">Make the changes from [Disable the Start Button](#BKMK_DisableTheStartButton), [Cancel and Restart the Operation](#BKMK_CancelAndRestart), or [Run Multiple Operations and Queue the Output](#BKMK_RunMultipleOperations) to handle the reentrancy.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c0b2-242">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c0b2-242">See also</span></span>

- [<span data-ttu-id="2c0b2-243">Tutorial: Acceso a web usando Async y Await (C#)</span><span class="sxs-lookup"><span data-stu-id="2c0b2-243">Walkthrough: Accessing the Web by Using async and await (C#)</span></span>](./walkthrough-accessing-the-web-by-using-async-and-await.md)
- [<span data-ttu-id="2c0b2-244">Programación asincrónica con Async y Await (C#)</span><span class="sxs-lookup"><span data-stu-id="2c0b2-244">Asynchronous Programming with async and await (C#)</span></span>](./index.md)
