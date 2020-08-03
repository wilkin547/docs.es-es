---
title: 'Tutorial: Acceso a web usando Async y Await (C#)'
description: En este tutorial se convierte una aplicación sincrónica en una solución asincrónica de C# que usa las características async y await.
ms.date: 07/20/2015
ms.assetid: c95d8d71-5a98-4bf0-aaf4-45fed2ebbacd
ms.openlocfilehash: d643793bfcdeaaeff56dd252c510d197a45442f9
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925116"
---
# <a name="walkthrough-accessing-the-web-by-using-async-and-await-c"></a><span data-ttu-id="48090-103">Tutorial: Acceso a web usando Async y Await (C#)</span><span class="sxs-lookup"><span data-stu-id="48090-103">Walkthrough: Accessing the Web by Using async and await (C#)</span></span>

<span data-ttu-id="48090-104">Puede escribir programas asincrónicos de manera más fácil e intuitiva usando las características async/await.</span><span class="sxs-lookup"><span data-stu-id="48090-104">You can write asynchronous programs more easily and intuitively by using async/await features.</span></span> <span data-ttu-id="48090-105">Puede escribir código asincrónico parecido al código sincrónico y dejar que el compilador gestione las difíciles funciones de devolución de llamada y continuaciones que normalmente implica el código asincrónico.</span><span class="sxs-lookup"><span data-stu-id="48090-105">You can write asynchronous code that looks like synchronous code and let the compiler handle the difficult callback functions and continuations that asynchronous code usually entails.</span></span>

<span data-ttu-id="48090-106">Para obtener más información sobre la característica Async, consulte [Programación asincrónica con async y await (C#)](./index.md).</span><span class="sxs-lookup"><span data-stu-id="48090-106">For more information about the Async feature, see [Asynchronous Programming with async and await (C#)](./index.md).</span></span>

<span data-ttu-id="48090-107">Este tutorial comienza con una aplicación sincrónica de Windows Presentation Foundation (WPF) que suma el número de bytes de una lista de sitios web.</span><span class="sxs-lookup"><span data-stu-id="48090-107">This walkthrough starts with a synchronous Windows Presentation Foundation (WPF) application that sums the number of bytes in a list of websites.</span></span> <span data-ttu-id="48090-108">A continuación, el tutorial convierte la aplicación en una solución asincrónica mediante el uso de las características nuevas.</span><span class="sxs-lookup"><span data-stu-id="48090-108">The walkthrough then converts the application to an asynchronous solution by using the new features.</span></span>

<span data-ttu-id="48090-109">Si no quiere compilar usted mismo las aplicaciones, puede descargar [Ejemplo de Async: obtener acceso al tutorial web (C# y Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span><span class="sxs-lookup"><span data-stu-id="48090-109">If you don't want to build the applications yourself, you can download [Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span></span>

> [!NOTE]
> <span data-ttu-id="48090-110">Para ejecutar los ejemplos, debe tener Visual Studio 2012 o posterior, y .NET Framework 4.5 o posterior, instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="48090-110">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

## <a name="create-a-wpf-application"></a><span data-ttu-id="48090-111">Crear una aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="48090-111">Create a WPF application</span></span>

1. <span data-ttu-id="48090-112">Inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="48090-112">Start Visual Studio.</span></span>

2. <span data-ttu-id="48090-113">En la barra de menús, elija **Archivo** > **Nuevo** > **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="48090-113">On the menu bar, choose **File** > **New** > **Project**.</span></span>

     <span data-ttu-id="48090-114">Aparece el cuadro de diálogo **Nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="48090-114">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="48090-115">En el panel **Plantillas instaladas**, elija Visual C# y después elija **Aplicación WPF** en la lista de tipos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="48090-115">In the **Installed Templates** pane, choose Visual C#, and then choose **WPF Application** from the list of project types.</span></span>

4. <span data-ttu-id="48090-116">En el cuadro de texto **Nombre**, escriba `AsyncExampleWPF` y elija el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="48090-116">In the **Name** text box, enter `AsyncExampleWPF`, and then choose the **OK** button.</span></span>

     <span data-ttu-id="48090-117">El proyecto nuevo aparece en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="48090-117">The new project appears in **Solution Explorer**.</span></span>

## <a name="design-a-simple-wpf-mainwindow"></a><span data-ttu-id="48090-118">Diseñar una ventana MainWindow simple de WPF</span><span class="sxs-lookup"><span data-stu-id="48090-118">Design a simple WPF MainWindow</span></span>

1. <span data-ttu-id="48090-119">En el Editor de código de Visual Studio, elija la pestaña **MainWindow.xaml** .</span><span class="sxs-lookup"><span data-stu-id="48090-119">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>

2. <span data-ttu-id="48090-120">Si la ventana **Cuadro de herramientas** no se está mostrando, abra el menú **Vista** y elija **Cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="48090-120">If the **Toolbox** window isn't visible, open the **View** menu, and then choose **Toolbox**.</span></span>

3. <span data-ttu-id="48090-121">Agregue un control **Botón** y un control **TextBox** a la ventana **MainWindow**.</span><span class="sxs-lookup"><span data-stu-id="48090-121">Add a **Button** control and a **TextBox** control to the **MainWindow** window.</span></span>

4. <span data-ttu-id="48090-122">Resalte el control **TextBox** y, en la ventana **Propiedades**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="48090-122">Highlight the **TextBox** control and, in the **Properties** window, set the following values:</span></span>

    - <span data-ttu-id="48090-123">Establezca la propiedad **Nombre** en `resultsTextBox`.</span><span class="sxs-lookup"><span data-stu-id="48090-123">Set the **Name** property to `resultsTextBox`.</span></span>

    - <span data-ttu-id="48090-124">Establezca la propiedad **Alto** en 250.</span><span class="sxs-lookup"><span data-stu-id="48090-124">Set the **Height** property to 250.</span></span>

    - <span data-ttu-id="48090-125">Establezca la propiedad **Ancho** en 500.</span><span class="sxs-lookup"><span data-stu-id="48090-125">Set the **Width** property to 500.</span></span>

    - <span data-ttu-id="48090-126">En la pestaña **Texto**, especifique una fuente monoespaciada, como Lucida Console o Global Monospace.</span><span class="sxs-lookup"><span data-stu-id="48090-126">On the **Text** tab, specify a monospaced font, such as Lucida Console or Global Monospace.</span></span>

5. <span data-ttu-id="48090-127">Resalte el control **Botón** y, en la ventana **Propiedades**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="48090-127">Highlight the **Button** control and, in the **Properties** window, set the following values:</span></span>

    - <span data-ttu-id="48090-128">Establezca la propiedad **Nombre** en `startButton`.</span><span class="sxs-lookup"><span data-stu-id="48090-128">Set the **Name** property to `startButton`.</span></span>

    - <span data-ttu-id="48090-129">Cambie el valor de la propiedad **Contenido** de **Botón** a **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="48090-129">Change the value of the **Content** property from **Button** to **Start**.</span></span>

6. <span data-ttu-id="48090-130">Coloque el cuadro de texto y el botón de manera que ambos aparezcan en la ventana **MainWindow**.</span><span class="sxs-lookup"><span data-stu-id="48090-130">Position the text box and the button so that both appear in the **MainWindow** window.</span></span>

     <span data-ttu-id="48090-131">Para obtener más información sobre el Diseñador XAML de WPF, consulte [Crear una IU con el Diseñador XAML](/visualstudio/xaml-tools/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="48090-131">For more information about the WPF XAML Designer, see [Creating a UI by using XAML Designer](/visualstudio/xaml-tools/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span></span>

## <a name="add-a-reference"></a><span data-ttu-id="48090-132">Agregar una referencia</span><span class="sxs-lookup"><span data-stu-id="48090-132">Add a reference</span></span>

1. <span data-ttu-id="48090-133">En el **Explorador de soluciones**, resalte el nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="48090-133">In **Solution Explorer**, highlight your project's name.</span></span>

2. <span data-ttu-id="48090-134">En la barra de menús, elija **Proyecto** > **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="48090-134">On the menu bar, choose **Project** > **Add Reference**.</span></span>

     <span data-ttu-id="48090-135">Aparecerá el cuadro de diálogo **Administrador de referencias**.</span><span class="sxs-lookup"><span data-stu-id="48090-135">The **Reference Manager** dialog box appears.</span></span>

3. <span data-ttu-id="48090-136">En la parte superior del cuadro de diálogo, compruebe que el proyecto tiene como destino .NET Framework 4.5 o superior.</span><span class="sxs-lookup"><span data-stu-id="48090-136">At the top of the dialog box, verify that your project is targeting the .NET Framework 4.5 or higher.</span></span>

4. <span data-ttu-id="48090-137">En la categoría **Ensamblados**, elija **Framework** si no está ya seleccionado.</span><span class="sxs-lookup"><span data-stu-id="48090-137">In the **Assemblies** category, choose **Framework** if it isn't already chosen.</span></span>

5. <span data-ttu-id="48090-138">En la lista de nombres, seleccione la casilla **System.Net.Http**.</span><span class="sxs-lookup"><span data-stu-id="48090-138">In the list of names, select the **System.Net.Http** check box.</span></span>

6. <span data-ttu-id="48090-139">Elija el botón **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="48090-139">Choose the **OK** button to close the dialog box.</span></span>

## <a name="add-necessary-using-directives"></a><span data-ttu-id="48090-140">Agregar las directivas using necesarias</span><span class="sxs-lookup"><span data-stu-id="48090-140">Add necessary using directives</span></span>

1. <span data-ttu-id="48090-141">En el **Explorador de soluciones**, abra el menú contextual de MainWindow.xaml.cs y después elija **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="48090-141">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.cs, and then choose **View Code**.</span></span>

2. <span data-ttu-id="48090-142">Agregue las siguientes directivas `using` en la parte superior del archivo de código si no están ya presentes.</span><span class="sxs-lookup"><span data-stu-id="48090-142">Add the following `using` directives at the top of the code file if they're not already present.</span></span>

    ```csharp
    using System.Net.Http;
    using System.Net;
    using System.IO;
    ```

## <a name="create-a-synchronous-app"></a><span data-ttu-id="48090-143">Crear una aplicación sincrónica</span><span class="sxs-lookup"><span data-stu-id="48090-143">Create a synchronous app</span></span>

1. <span data-ttu-id="48090-144">En la ventana de diseño, MainWindow.xaml, haga doble clic en el botón **Inicio** para crear el controlador de eventos `startButton_Click` en MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="48090-144">In the design window, MainWindow.xaml, double-click the **Start** button to create the `startButton_Click` event handler in MainWindow.xaml.cs.</span></span>

2. <span data-ttu-id="48090-145">En MainWindow.xaml.cs, copie el código siguiente en el cuerpo de `startButton_Click`:</span><span class="sxs-lookup"><span data-stu-id="48090-145">In MainWindow.xaml.cs, copy the following code into the body of `startButton_Click`:</span></span>

    ```csharp
    resultsTextBox.Clear();
    SumPageSizes();
    resultsTextBox.Text += "\r\nControl returned to startButton_Click.";
    ```

    <span data-ttu-id="48090-146">El código llama al método que controla la aplicación, `SumPageSizes`, y muestra un mensaje cuando el control vuelve a `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="48090-146">The code calls the method that drives the application, `SumPageSizes`, and displays a message when control returns to `startButton_Click`.</span></span>

3. <span data-ttu-id="48090-147">El código de la solución sincrónica contiene los cuatro métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="48090-147">The code for the synchronous solution contains the following four methods:</span></span>

    - <span data-ttu-id="48090-148">`SumPageSizes`, que obtiene una lista de direcciones URL de páginas web de `SetUpURLList` y, a continuación, llama a `GetURLContents` y `DisplayResults` para que procesen cada dirección URL.</span><span class="sxs-lookup"><span data-stu-id="48090-148">`SumPageSizes`, which gets a list of webpage URLs from `SetUpURLList` and then calls `GetURLContents` and `DisplayResults` to process each URL.</span></span>

    - <span data-ttu-id="48090-149">`SetUpURLList`, que crea y devuelve una lista de direcciones web.</span><span class="sxs-lookup"><span data-stu-id="48090-149">`SetUpURLList`, which makes and returns a list of web addresses.</span></span>

    - <span data-ttu-id="48090-150">`GetURLContents`, que descarga el contenido de cada sitio web y devuelve el contenido como una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="48090-150">`GetURLContents`, which downloads the contents of each website and returns the contents as a byte array.</span></span>

    - <span data-ttu-id="48090-151">`DisplayResults`, que muestra el número de bytes de la matriz de bytes de cada dirección URL.</span><span class="sxs-lookup"><span data-stu-id="48090-151">`DisplayResults`, which displays  the number of bytes in the byte array for each URL.</span></span>

    <span data-ttu-id="48090-152">Copie los cuatro métodos siguientes y péguelos bajo el controlador de eventos `startButton_Click` en MainWindow.xaml.cs:</span><span class="sxs-lookup"><span data-stu-id="48090-152">Copy the following four methods, and then paste them under the `startButton_Click` event handler in MainWindow.xaml.cs:</span></span>

    ```csharp
    private void SumPageSizes()
    {
        // Make a list of web addresses.
        List<string> urlList = SetUpURLList();

        var total = 0;
        foreach (var url in urlList)
        {
            // GetURLContents returns the contents of url as a byte array.
            byte[] urlContents = GetURLContents(url);

            DisplayResults(url, urlContents);

            // Update the total.
            total += urlContents.Length;
        }

        // Display the total count for all of the web addresses.
        resultsTextBox.Text += $"\r\n\r\nTotal bytes returned:  {total}\r\n";
    }

    private List<string> SetUpURLList()
    {
        var urls = new List<string>
        {
            "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
            "https://msdn.microsoft.com",
            "https://msdn.microsoft.com/library/hh290136.aspx",
            "https://msdn.microsoft.com/library/ee256749.aspx",
            "https://msdn.microsoft.com/library/hh290138.aspx",
            "https://msdn.microsoft.com/library/hh290140.aspx",
            "https://msdn.microsoft.com/library/dd470362.aspx",
            "https://msdn.microsoft.com/library/aa578028.aspx",
            "https://msdn.microsoft.com/library/ms404677.aspx",
            "https://msdn.microsoft.com/library/ff730837.aspx"
        };
        return urls;
    }

    private byte[] GetURLContents(string url)
    {
        // The downloaded resource ends up in the variable named content.
        var content = new MemoryStream();

        // Initialize an HttpWebRequest for the current URL.
        var webReq = (HttpWebRequest)WebRequest.Create(url);

        // Send the request to the Internet resource and wait for
        // the response.
        // Note: you can't use HttpWebRequest.GetResponse in a Windows Store app.
        using (WebResponse response = webReq.GetResponse())
        {
            // Get the data stream that is associated with the specified URL.
            using (Stream responseStream = response.GetResponseStream())
            {
                // Read the bytes in responseStream and copy them to content.
                responseStream.CopyTo(content);
            }
        }

        // Return the result as a byte array.
        return content.ToArray();
    }

    private void DisplayResults(string url, byte[] content)
    {
        // Display the length of each website. The string format
        // is designed to be used with a monospaced font, such as
        // Lucida Console or Global Monospace.
        var bytes = content.Length;
        // Strip off the "https://".
        var displayURL = url.Replace("https://", "");
        resultsTextBox.Text += $"\n{displayURL,-58} {bytes,8}";
    }
    ```

## <a name="test-the-synchronous-solution"></a><span data-ttu-id="48090-153">Probar la solución sincrónica</span><span class="sxs-lookup"><span data-stu-id="48090-153">Test the synchronous solution</span></span>

<span data-ttu-id="48090-154">Presione la tecla **F5** para ejecutar el programa y elija el botón **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="48090-154">Choose the **F5** key to run the program, and then choose the **Start** button.</span></span>

<span data-ttu-id="48090-155">Debería aparecer un resultado similar a la lista siguiente:</span><span class="sxs-lookup"><span data-stu-id="48090-155">Output that resembles the following list should appear:</span></span>

```text
msdn.microsoft.com/library/windows/apps/br211380.aspx        383832
msdn.microsoft.com                                            33964
msdn.microsoft.com/library/hh290136.aspx               225793
msdn.microsoft.com/library/ee256749.aspx               143577
msdn.microsoft.com/library/hh290138.aspx               237372
msdn.microsoft.com/library/hh290140.aspx               128279
msdn.microsoft.com/library/dd470362.aspx               157649
msdn.microsoft.com/library/aa578028.aspx               204457
msdn.microsoft.com/library/ms404677.aspx               176405
msdn.microsoft.com/library/ff730837.aspx               143474

Total bytes returned:  1834802

Control returned to startButton_Click.
```

<span data-ttu-id="48090-156">Tenga en cuenta que los recuentos tardan unos segundos en mostrarse.</span><span class="sxs-lookup"><span data-stu-id="48090-156">Notice that it takes a few seconds to display the counts.</span></span> <span data-ttu-id="48090-157">Durante ese tiempo, el subproceso de interfaz de usuario se bloquea mientras espera a que se descarguen los recursos solicitados.</span><span class="sxs-lookup"><span data-stu-id="48090-157">During that time, the UI thread is blocked while it waits for requested resources to download.</span></span> <span data-ttu-id="48090-158">Como resultado, no se puede mover, maximizar, minimizar o ni siquiera cerrar la ventana de la pantalla después de elegir el botón **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="48090-158">As a result, you can't move, maximize, minimize, or even close the display window after you choose the  **Start** button.</span></span> <span data-ttu-id="48090-159">Estos intentos producirán un error hasta que empiecen a aparecer los recuentos de bytes.</span><span class="sxs-lookup"><span data-stu-id="48090-159">These efforts fail until the byte counts start to appear.</span></span> <span data-ttu-id="48090-160">Si un sitio web no responde, no se le indicará cuál es el sitio que produjo el error.</span><span class="sxs-lookup"><span data-stu-id="48090-160">If a website isn't responding, you have no indication of which site failed.</span></span> <span data-ttu-id="48090-161">Incluso resulta difícil dejar de esperar y cerrar el programa.</span><span class="sxs-lookup"><span data-stu-id="48090-161">It is difficult even to stop waiting and close the program.</span></span>

## <a name="convert-geturlcontents-to-an-asynchronous-method"></a><span data-ttu-id="48090-162">Convertir GetURLContents en un método asincrónico</span><span class="sxs-lookup"><span data-stu-id="48090-162">Convert GetURLContents to an asynchronous method</span></span>

1. <span data-ttu-id="48090-163">Para convertir la solución sincrónica a una solución asincrónica, lo mejor es comenzar en `GetURLContents`, ya que las llamadas al método <xref:System.Net.HttpWebRequest><xref:System.Net.HttpWebRequest.GetResponse%2A> y al método <xref:System.IO.Stream><xref:System.IO.Stream.CopyTo%2A> son el lugar desde donde la aplicación accede a la web.</span><span class="sxs-lookup"><span data-stu-id="48090-163">To convert the synchronous solution to an asynchronous solution, the best place to start is in `GetURLContents` because the calls to the <xref:System.Net.HttpWebRequest> method <xref:System.Net.HttpWebRequest.GetResponse%2A> and to the <xref:System.IO.Stream> method <xref:System.IO.Stream.CopyTo%2A> are where the application accesses the web.</span></span> <span data-ttu-id="48090-164">.NET Framework facilita la conversión proporcionando versiones asincrónicas de ambos métodos.</span><span class="sxs-lookup"><span data-stu-id="48090-164">.NET Framework makes the conversion easy by supplying asynchronous versions of both methods.</span></span>

     <span data-ttu-id="48090-165">Para obtener más información sobre los modelos que se usan en `GetURLContents`, vea <xref:System.Net.WebRequest>.</span><span class="sxs-lookup"><span data-stu-id="48090-165">For more information about the methods that are used in `GetURLContents`, see <xref:System.Net.WebRequest>.</span></span>

    > [!NOTE]
    > <span data-ttu-id="48090-166">A medida que siga los pasos de este tutorial, aparecerán varios errores del compilador.</span><span class="sxs-lookup"><span data-stu-id="48090-166">As you follow the steps in this walkthrough, several compiler errors appear.</span></span> <span data-ttu-id="48090-167">Puede hacer caso omiso y continuar con el tutorial.</span><span class="sxs-lookup"><span data-stu-id="48090-167">You can ignore them and continue with the walkthrough.</span></span>

     <span data-ttu-id="48090-168">Cambie el método al que se llama en la tercera línea de `GetURLContents` de `GetResponse` al método <xref:System.Net.WebRequest.GetResponseAsync%2A> asincrónico basado en tareas.</span><span class="sxs-lookup"><span data-stu-id="48090-168">Change the method that's called in the third line of `GetURLContents` from `GetResponse` to the asynchronous, task-based <xref:System.Net.WebRequest.GetResponseAsync%2A> method.</span></span>

    ```csharp
    using (WebResponse response = webReq.GetResponseAsync())
    ```

2. <span data-ttu-id="48090-169">`GetResponseAsync` devuelve <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="48090-169">`GetResponseAsync` returns a <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="48090-170">En este caso, la *variable de devolución de tarea*, `TResult`, tiene un tipo <xref:System.Net.WebResponse>.</span><span class="sxs-lookup"><span data-stu-id="48090-170">In this case, the *task return variable*, `TResult`, has type <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="48090-171">La tarea es una promesa para generar un objeto `WebResponse` real después de que se descarguen los datos solicitados y la tarea se ejecute hasta completarse.</span><span class="sxs-lookup"><span data-stu-id="48090-171">The task is a promise to produce an actual `WebResponse` object after the requested data has been downloaded and the task has run to completion.</span></span>

     <span data-ttu-id="48090-172">Para recuperar el valor `WebResponse` de la tarea, aplique un operador [await](../../../language-reference/operators/await.md) a la llamada a `GetResponseAsync`, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="48090-172">To retrieve the `WebResponse` value from the task, apply an [await](../../../language-reference/operators/await.md) operator to the call to `GetResponseAsync`, as the following code shows.</span></span>

    ```csharp
    using (WebResponse response = await webReq.GetResponseAsync())
    ```

     <span data-ttu-id="48090-173">El operador `await` suspende la ejecución del método actual, `GetURLContents`, hasta que se complete la tarea esperada.</span><span class="sxs-lookup"><span data-stu-id="48090-173">The `await` operator suspends the execution of the current method, `GetURLContents`, until the awaited task is complete.</span></span> <span data-ttu-id="48090-174">Mientras tanto, el control devuelve al llamador del método actual.</span><span class="sxs-lookup"><span data-stu-id="48090-174">In the meantime, control returns to the caller of the current method.</span></span> <span data-ttu-id="48090-175">En este ejemplo, el método actual es `GetURLContents` y el llamador es `SumPageSizes`.</span><span class="sxs-lookup"><span data-stu-id="48090-175">In this example, the current method is `GetURLContents`, and the caller is `SumPageSizes`.</span></span> <span data-ttu-id="48090-176">Cuando la tarea finaliza, el objeto `WebResponse` prometido se genera como valor de la tarea esperada y se asigna a la variable `response`.</span><span class="sxs-lookup"><span data-stu-id="48090-176">When the task is finished, the promised `WebResponse` object is produced as the value of the awaited task and assigned to the variable `response`.</span></span>

     <span data-ttu-id="48090-177">La instrucción anterior se puede dividir en las dos instrucciones siguientes para aclarar lo que sucede.</span><span class="sxs-lookup"><span data-stu-id="48090-177">The previous statement can be separated into the following two statements to clarify what happens.</span></span>

    ```csharp
    //Task<WebResponse> responseTask = webReq.GetResponseAsync();
    //using (WebResponse response = await responseTask)
    ```

     <span data-ttu-id="48090-178">La llamada a `webReq.GetResponseAsync` devuelve `Task(Of WebResponse)` o `Task<WebResponse>`.</span><span class="sxs-lookup"><span data-stu-id="48090-178">The call to `webReq.GetResponseAsync` returns a `Task(Of WebResponse)` or `Task<WebResponse>`.</span></span> <span data-ttu-id="48090-179">A continuación, se aplica un operador await a la tarea para recuperar el valor `WebResponse`.</span><span class="sxs-lookup"><span data-stu-id="48090-179">Then an await operator is applied to the task to retrieve the `WebResponse` value.</span></span>

     <span data-ttu-id="48090-180">Si el método asincrónico debe realizar un trabajo que no depende de la finalización de la tarea, el método puede continuar con ese trabajo entre estas dos instrucciones, después de la llamada al método asincrónico y antes de que se aplique el operador `await`.</span><span class="sxs-lookup"><span data-stu-id="48090-180">If your async method has work to do that doesn't depend on the completion of the task, the method can continue with that work between these two statements, after the call to the async method and before the `await` operator is applied.</span></span> <span data-ttu-id="48090-181">Para obtener ejemplos, vea [Procedimiento para realizar varias solicitudes web en paralelo con async y await (C#)](./how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) y [Procedimiento para ampliar el tutorial de async usando Task.WhenAll (C#)](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span><span class="sxs-lookup"><span data-stu-id="48090-181">For examples, see [How to make multiple web requests in parallel by using async and await (C#)](./how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) and [How to extend the async walkthrough by using Task.WhenAll (C#)](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>

3. <span data-ttu-id="48090-182">Dado que ha agregado el operador `await` en el paso anterior, se produce un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="48090-182">Because you added the `await` operator in the previous step, a compiler error occurs.</span></span> <span data-ttu-id="48090-183">El operador puede usarse únicamente en los métodos marcados con el modificador [async](../../../language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="48090-183">The operator can be used only in methods that are marked with the [async](../../../language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="48090-184">Omita el error mientras repita los pasos de conversión para reemplazar la llamada a `CopyTo` con una llamada a `CopyToAsync`.</span><span class="sxs-lookup"><span data-stu-id="48090-184">Ignore the error while you repeat the conversion steps to replace the call to `CopyTo` with a call to `CopyToAsync`.</span></span>

    - <span data-ttu-id="48090-185">Cambie el nombre del método al que se llama a <xref:System.IO.Stream.CopyToAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="48090-185">Change the name of the method that's called to <xref:System.IO.Stream.CopyToAsync%2A>.</span></span>

    - <span data-ttu-id="48090-186">El método `CopyTo` o `CopyToAsync` copia bytes a su argumento, `content`, y no devuelve un valor significativo.</span><span class="sxs-lookup"><span data-stu-id="48090-186">The `CopyTo` or `CopyToAsync` method copies bytes to its argument, `content`, and doesn't return a meaningful value.</span></span> <span data-ttu-id="48090-187">En la versión sincrónica, la llamada a `CopyTo` es una sencilla instrucción que no devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="48090-187">In the synchronous version, the call to `CopyTo` is a simple statement that doesn't return a value.</span></span> <span data-ttu-id="48090-188">La versión asincrónica, `CopyToAsync`, devuelve una <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="48090-188">The asynchronous version, `CopyToAsync`, returns a <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="48090-189">La tarea funciona como "Task(void)" y permite que se espere al método.</span><span class="sxs-lookup"><span data-stu-id="48090-189">The task functions like "Task(void)" and enables the method to be awaited.</span></span> <span data-ttu-id="48090-190">Aplique `Await` o `await` a la llamada a `CopyToAsync`, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="48090-190">Apply `Await` or `await` to the call to `CopyToAsync`, as the following code shows.</span></span>

        ```csharp
        await responseStream.CopyToAsync(content);
        ```

         <span data-ttu-id="48090-191">La instrucción anterior abrevia las dos líneas de código siguientes.</span><span class="sxs-lookup"><span data-stu-id="48090-191">The previous statement abbreviates the following two lines of code.</span></span>

        ```csharp
        // CopyToAsync returns a Task, not a Task<T>.
        //Task copyTask = responseStream.CopyToAsync(content);

        // When copyTask is completed, content contains a copy of
        // responseStream.
        //await copyTask;
        ```

4. <span data-ttu-id="48090-192">Lo único que queda por hacer en `GetURLContents` es ajustar la firma del método.</span><span class="sxs-lookup"><span data-stu-id="48090-192">All that remains to be done in `GetURLContents` is to adjust the method signature.</span></span> <span data-ttu-id="48090-193">Puede usar el operador `await` únicamente en los métodos marcados con el modificador [async](../../../language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="48090-193">You can use the `await` operator only in methods that are marked with the [async](../../../language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="48090-194">Agregue el modificador para marcar el método como *método asincrónico*, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="48090-194">Add the modifier to mark the method as an *async method*, as the following code shows.</span></span>

    ```csharp
    private async byte[] GetURLContents(string url)
    ```

5. <span data-ttu-id="48090-195">El tipo de valor devuelto de un método asincrónico solo puede ser <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601> o `void` en C#.</span><span class="sxs-lookup"><span data-stu-id="48090-195">The return type of an async method can only be <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, or `void` in C#.</span></span> <span data-ttu-id="48090-196">Normalmente, el tipo de valor devuelto `void` se usa solo en un controlador de eventos asincrónico, en el que se requiere `void`.</span><span class="sxs-lookup"><span data-stu-id="48090-196">Typically, a return type of `void` is used only in an async event handler, where `void` is required.</span></span> <span data-ttu-id="48090-197">En otros casos, se usa `Task(T)` si el método completado tiene una instrucción [return](../../../language-reference/keywords/return.md) que devuelve un valor de tipo T, y se usa `Task` si el método completado no devuelve un valor significativo.</span><span class="sxs-lookup"><span data-stu-id="48090-197">In other cases, you use `Task(T)` if the completed method has a [return](../../../language-reference/keywords/return.md) statement that returns a value of type T, and you use `Task` if the completed method doesn't return a meaningful value.</span></span> <span data-ttu-id="48090-198">Puede considerar que el tipo de valor devuelto `Task` significa "Task(void)".</span><span class="sxs-lookup"><span data-stu-id="48090-198">You can think of the `Task` return type as meaning "Task(void)."</span></span>

     <span data-ttu-id="48090-199">Para obtener más información, consulte [Tipos de valor devueltos asincrónicos (C#)](./async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="48090-199">For more information, see [Async Return Types (C#)](./async-return-types.md).</span></span>

     <span data-ttu-id="48090-200">El método `GetURLContents` tiene una instrucción return, y la instrucción devuelve una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="48090-200">Method `GetURLContents` has a return statement, and the statement returns a byte array.</span></span> <span data-ttu-id="48090-201">Por lo tanto, el tipo de valor devuelto de la versión de async es Task(T), donde T es una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="48090-201">Therefore, the return type of the async version is Task(T), where T is a byte array.</span></span> <span data-ttu-id="48090-202">Realice los cambios siguientes en la firma del método:</span><span class="sxs-lookup"><span data-stu-id="48090-202">Make the following changes in the method signature:</span></span>

    - <span data-ttu-id="48090-203">Cambie el tipo de valor devuelto a `Task<byte[]>`.</span><span class="sxs-lookup"><span data-stu-id="48090-203">Change the return type to `Task<byte[]>`.</span></span>

    - <span data-ttu-id="48090-204">Por convención, los métodos asincrónicos tienen nombres que terminan en "Async", por lo que debe cambiar el nombre del método a `GetURLContentsAsync`.</span><span class="sxs-lookup"><span data-stu-id="48090-204">By convention, asynchronous methods have names that end in "Async," so rename the method `GetURLContentsAsync`.</span></span>

     <span data-ttu-id="48090-205">En el código siguiente se muestran estos cambios.</span><span class="sxs-lookup"><span data-stu-id="48090-205">The following code shows these changes.</span></span>

    ```csharp
    private async Task<byte[]> GetURLContentsAsync(string url)
    ```

     <span data-ttu-id="48090-206">Con estos pocos cambios, se completa la conversión de `GetURLContents` en un método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="48090-206">With those few changes, the conversion of `GetURLContents` to an asynchronous method is complete.</span></span>

## <a name="convert-sumpagesizes-to-an-asynchronous-method"></a><span data-ttu-id="48090-207">Convertir SumPageSizes en un método asincrónico</span><span class="sxs-lookup"><span data-stu-id="48090-207">Convert SumPageSizes to an asynchronous method</span></span>

1. <span data-ttu-id="48090-208">Repita los pasos del procedimiento anterior para `SumPageSizes`.</span><span class="sxs-lookup"><span data-stu-id="48090-208">Repeat the steps from the previous procedure for `SumPageSizes`.</span></span> <span data-ttu-id="48090-209">Primero, cambie la llamada a `GetURLContents` a una llamada asincrónica.</span><span class="sxs-lookup"><span data-stu-id="48090-209">First, change the call to `GetURLContents` to an asynchronous call.</span></span>

    - <span data-ttu-id="48090-210">Cambie el nombre del método al que se llama de `GetURLContents` a `GetURLContentsAsync`, si aún no lo ha hecho.</span><span class="sxs-lookup"><span data-stu-id="48090-210">Change the name of the method that's called from `GetURLContents` to `GetURLContentsAsync`, if you haven't already done so.</span></span>

    - <span data-ttu-id="48090-211">Aplique `await` a la tarea que devuelve `GetURLContentsAsync` para obtener el valor de la matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="48090-211">Apply `await` to the task that `GetURLContentsAsync` returns to obtain the byte array value.</span></span>

     <span data-ttu-id="48090-212">En el código siguiente se muestran estos cambios.</span><span class="sxs-lookup"><span data-stu-id="48090-212">The following code shows these changes.</span></span>

    ```csharp
    byte[] urlContents = await GetURLContentsAsync(url);
    ```

     <span data-ttu-id="48090-213">La asignación anterior abrevia las dos líneas de código siguientes.</span><span class="sxs-lookup"><span data-stu-id="48090-213">The previous assignment abbreviates the following two lines of code.</span></span>

    ```csharp
    // GetURLContentsAsync returns a Task<T>. At completion, the task
    // produces a byte array.
    //Task<byte[]> getContentsTask = GetURLContentsAsync(url);
    //byte[] urlContents = await getContentsTask;
    ```

2. <span data-ttu-id="48090-214">Realice los cambios siguientes en la firma del método:</span><span class="sxs-lookup"><span data-stu-id="48090-214">Make the following changes in the method's signature:</span></span>

    - <span data-ttu-id="48090-215">Marque el método con el modificador `async`.</span><span class="sxs-lookup"><span data-stu-id="48090-215">Mark the method with the `async` modifier.</span></span>

    - <span data-ttu-id="48090-216">Agregue "Async" al nombre del método.</span><span class="sxs-lookup"><span data-stu-id="48090-216">Add "Async" to the method name.</span></span>

    - <span data-ttu-id="48090-217">Esta vez no hay ninguna variable de devolución de tarea, T, porque `SumPageSizesAsync` no devuelve un valor para T. (El método no tiene ninguna instrucción `return`). Sin embargo, el método debe devolver `Task` para admitir await.</span><span class="sxs-lookup"><span data-stu-id="48090-217">There is no task return variable, T, this time because `SumPageSizesAsync` doesn't return a value for T. (The method has no `return` statement.) However, the method must return a `Task` to be awaitable.</span></span> <span data-ttu-id="48090-218">Por tanto, cambie el tipo de valor devuelto del método de `void` a `Task`.</span><span class="sxs-lookup"><span data-stu-id="48090-218">Therefore, change the return type of the method from `void` to `Task`.</span></span>

    <span data-ttu-id="48090-219">En el código siguiente se muestran estos cambios.</span><span class="sxs-lookup"><span data-stu-id="48090-219">The following code shows these changes.</span></span>

    ```csharp
    private async Task SumPageSizesAsync()
    ```

     <span data-ttu-id="48090-220">Se completa así la conversión de `SumPageSizes` a `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="48090-220">The conversion of `SumPageSizes` to `SumPageSizesAsync` is complete.</span></span>

## <a name="convert-startbutton_click-to-an-asynchronous-method"></a><span data-ttu-id="48090-221">Convertir startButton_Click en un método asincrónico</span><span class="sxs-lookup"><span data-stu-id="48090-221">Convert startButton_Click to an asynchronous method</span></span>

1. <span data-ttu-id="48090-222">En el controlador de eventos, cambie el nombre del método llamado de `SumPageSizes` a `SumPageSizesAsync`, si aún no lo ha hecho.</span><span class="sxs-lookup"><span data-stu-id="48090-222">In the event handler, change the name of the called method from `SumPageSizes` to `SumPageSizesAsync`, if you haven't already done so.</span></span>

2. <span data-ttu-id="48090-223">Dado que `SumPageSizesAsync` es un método asincrónico, cambie el código en el controlador de eventos para esperar el resultado.</span><span class="sxs-lookup"><span data-stu-id="48090-223">Because `SumPageSizesAsync` is an async method, change the code in the event handler to await the result.</span></span>

     <span data-ttu-id="48090-224">La llamada a `SumPageSizesAsync` refleja la llamada a `CopyToAsync` en `GetURLContentsAsync`.</span><span class="sxs-lookup"><span data-stu-id="48090-224">The call to `SumPageSizesAsync` mirrors the call to `CopyToAsync` in `GetURLContentsAsync`.</span></span> <span data-ttu-id="48090-225">La llamada devuelve `Task`, no `Task(T)`.</span><span class="sxs-lookup"><span data-stu-id="48090-225">The call returns a `Task`, not a `Task(T)`.</span></span>

     <span data-ttu-id="48090-226">Al igual que en los procedimientos anteriores, puede convertir la llamada usando una o dos instrucciones.</span><span class="sxs-lookup"><span data-stu-id="48090-226">As in previous procedures, you can convert the call by using one statement or two statements.</span></span> <span data-ttu-id="48090-227">En el código siguiente se muestran estos cambios.</span><span class="sxs-lookup"><span data-stu-id="48090-227">The following code shows these changes.</span></span>

    ```csharp
    // One-step async call.
    await SumPageSizesAsync();

    // Two-step async call.
    //Task sumTask = SumPageSizesAsync();
    //await sumTask;
    ```

3. <span data-ttu-id="48090-228">Para evitar volver a entrar accidentalmente en la operación, agregue la instrucción siguiente encima de `startButton_Click` para deshabilitar el botón **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="48090-228">To prevent accidentally reentering the operation, add the following statement at the top of `startButton_Click` to disable the **Start** button.</span></span>

    ```csharp
    // Disable the button until the operation is complete.
    startButton.IsEnabled = false;
    ```

     <span data-ttu-id="48090-229">Puede volver a habilitar el botón al final del controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="48090-229">You can reenable the button at the end of the event handler.</span></span>

    ```csharp
    // Reenable the button in case you want to run the operation again.
    startButton.IsEnabled = true;
    ```

     <span data-ttu-id="48090-230">Para obtener más información sobre la reentrada, consulte [Handling Reentrancy in Async Apps (C#)](./handling-reentrancy-in-async-apps.md) (Controlar la reentrada en aplicaciones asincrónicas [C#]).</span><span class="sxs-lookup"><span data-stu-id="48090-230">For more information about reentrancy, see [Handling Reentrancy in Async Apps (C#)](./handling-reentrancy-in-async-apps.md).</span></span>

4. <span data-ttu-id="48090-231">Finalmente, agregue el modificador `async` a la declaración de modo que el controlador de eventos pueda esperar `SumPagSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="48090-231">Finally, add the `async` modifier to the declaration so that the event handler can await `SumPagSizesAsync`.</span></span>

    ```csharp
    private async void startButton_Click(object sender, RoutedEventArgs e)
    ```

     <span data-ttu-id="48090-232">Normalmente, no se cambian los nombres de los controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="48090-232">Typically, the names of event handlers aren't changed.</span></span> <span data-ttu-id="48090-233">El tipo de valor devuelto no se cambia a `Task` porque los controladores de eventos deben devolver `void`.</span><span class="sxs-lookup"><span data-stu-id="48090-233">The return type isn't changed to `Task` because event handlers must return `void`.</span></span>

     <span data-ttu-id="48090-234">Así se completa la conversión del proyecto de procesamiento sincrónico a asincrónico.</span><span class="sxs-lookup"><span data-stu-id="48090-234">The conversion of the project from synchronous to asynchronous processing is complete.</span></span>

## <a name="test-the-asynchronous-solution"></a><span data-ttu-id="48090-235">Probar la solución asincrónica</span><span class="sxs-lookup"><span data-stu-id="48090-235">Test the asynchronous solution</span></span>

1. <span data-ttu-id="48090-236">Presione la tecla **F5** para ejecutar el programa y elija el botón **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="48090-236">Choose the **F5** key to run the program, and then choose the **Start** button.</span></span>

2. <span data-ttu-id="48090-237">Deberían aparecer resultados similares a los de la solución sincrónica.</span><span class="sxs-lookup"><span data-stu-id="48090-237">Output that resembles the output of the synchronous solution should appear.</span></span> <span data-ttu-id="48090-238">No obstante, debe tener en cuenta las siguientes diferencias.</span><span class="sxs-lookup"><span data-stu-id="48090-238">However, notice the following differences.</span></span>

    - <span data-ttu-id="48090-239">No todos los resultados se producen al mismo tiempo cuando se completa el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="48090-239">The results don't all occur at the same time, after the processing is complete.</span></span> <span data-ttu-id="48090-240">Por ejemplo, ambos programas contienen una línea en `startButton_Click` que borra el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="48090-240">For example, both programs contain a line in `startButton_Click` that clears the text box.</span></span> <span data-ttu-id="48090-241">La intención es borrar el cuadro de texto entre ejecuciones si elige el botón **Inicio** por segunda vez, después de que haya aparecido un conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="48090-241">The intent is to clear the text box between runs if you choose the **Start** button for a second time, after one set of results has appeared.</span></span> <span data-ttu-id="48090-242">En la versión sincrónica, el cuadro de texto se borra antes de que aparezcan los recuentos por segunda vez, cuando se completen las descargas y el subproceso de interfaz de usuario esté libre para llevar a cabo otro trabajo.</span><span class="sxs-lookup"><span data-stu-id="48090-242">In the synchronous version, the text box is cleared just before the counts appear for the second time, when the downloads are completed and the UI thread is free to do other work.</span></span> <span data-ttu-id="48090-243">En la versión asincrónica, el cuadro de texto se borra inmediatamente después de que se elija el botón **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="48090-243">In the asynchronous version, the text box clears immediately after you choose the **Start** button.</span></span>

    - <span data-ttu-id="48090-244">Lo más importante es que el subproceso de interfaz de usuario no se bloquea durante las descargas.</span><span class="sxs-lookup"><span data-stu-id="48090-244">Most importantly, the UI thread isn't blocked during the downloads.</span></span> <span data-ttu-id="48090-245">Puede mover o cambiar el tamaño de la ventana mientras se descargan, se cuentan y se muestran los recursos web.</span><span class="sxs-lookup"><span data-stu-id="48090-245">You can move or resize the window while the web resources are being downloaded, counted, and displayed.</span></span> <span data-ttu-id="48090-246">Si uno de los sitios web es lento o no responde, puede cancelar la operación eligiendo el botón **Cerrar** (la X en el campo de color rojo en la esquina superior derecha).</span><span class="sxs-lookup"><span data-stu-id="48090-246">If one of the websites is slow or not responding, you can cancel the operation by choosing the **Close** button (the x in the red field in the upper-right corner).</span></span>

## <a name="replace-method-geturlcontentsasync-with-a-net-method"></a><span data-ttu-id="48090-247">Reemplazar el método GetURLContentsAsync con un método de .NET</span><span class="sxs-lookup"><span data-stu-id="48090-247">Replace method GetURLContentsAsync with a .NET method</span></span>

1. <span data-ttu-id="48090-248">.NET Framework 4.5 y las versiones posteriores proporcionan muchos métodos asincrónicos que puede usar.</span><span class="sxs-lookup"><span data-stu-id="48090-248">.NET Framework 4.5 and later versions provide many async methods that you can use.</span></span> <span data-ttu-id="48090-249">Uno de ellos, el método <xref:System.Net.Http.HttpClient><xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29>, hace justo lo que necesita para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="48090-249">One of them, the <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29>, does just what you need for this walkthrough.</span></span> <span data-ttu-id="48090-250">Se puede usar en lugar del método `GetURLContentsAsync` que creó en un procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="48090-250">You can use it instead of the `GetURLContentsAsync` method that you created in an earlier procedure.</span></span>

     <span data-ttu-id="48090-251">El primer paso es crear un objeto `HttpClient` en el método `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="48090-251">The first step is to create an `HttpClient` object in method `SumPageSizesAsync`.</span></span> <span data-ttu-id="48090-252">Agregue la siguiente declaración al principio del método.</span><span class="sxs-lookup"><span data-stu-id="48090-252">Add the following declaration at the start of the method.</span></span>

    ```csharp
    // Declare an HttpClient object and increase the buffer size. The
    // default buffer size is 65,536.
    HttpClient client =
        new HttpClient() { MaxResponseContentBufferSize = 1000000 };
    ```

2. <span data-ttu-id="48090-253">En `SumPageSizesAsync,` reemplace la llamada a su método `GetURLContentsAsync` con una llamada al método `HttpClient`.</span><span class="sxs-lookup"><span data-stu-id="48090-253">In `SumPageSizesAsync,` replace the call to your `GetURLContentsAsync` method with a call to the `HttpClient` method.</span></span>

    ```csharp
    byte[] urlContents = await client.GetByteArrayAsync(url);
    ```

3. <span data-ttu-id="48090-254">Quite o marque como comentario el método `GetURLContentsAsync` que escribió.</span><span class="sxs-lookup"><span data-stu-id="48090-254">Remove or comment out the `GetURLContentsAsync` method that you wrote.</span></span>

4. <span data-ttu-id="48090-255">Presione la tecla **F5** para ejecutar el programa y elija el botón **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="48090-255">Choose the **F5** key to run the program, and then choose the **Start** button.</span></span>

     <span data-ttu-id="48090-256">El comportamiento de esta versión del proyecto debería coincidir con el comportamiento que se describe en el procedimiento "Para probar la solución asincrónica", pero con incluso menos trabajo por su parte.</span><span class="sxs-lookup"><span data-stu-id="48090-256">The behavior of this version of the project should match the behavior that the "To test the asynchronous solution" procedure describes but with even less effort from you.</span></span>

## <a name="example-code"></a><span data-ttu-id="48090-257">código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="48090-257">Example code</span></span>

<span data-ttu-id="48090-258">El código siguiente contiene el ejemplo completo de la conversión de una solución sincrónica a una asincrónica usando el método `GetURLContentsAsync` asincrónico que escribió.</span><span class="sxs-lookup"><span data-stu-id="48090-258">The following code contains the full example of the conversion from a synchronous to an asynchronous solution by using the asynchronous `GetURLContentsAsync` method that you wrote.</span></span> <span data-ttu-id="48090-259">Observe que es muy parecida a la solución sincrónica original.</span><span class="sxs-lookup"><span data-stu-id="48090-259">Notice that it strongly resembles the original, synchronous solution.</span></span>

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
using System.IO;
using System.Net;

namespace AsyncExampleWPF
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            // Disable the button until the operation is complete.
            startButton.IsEnabled = false;

            resultsTextBox.Clear();

            // One-step async call.
            await SumPageSizesAsync();

            // Two-step async call.
            //Task sumTask = SumPageSizesAsync();
            //await sumTask;

            resultsTextBox.Text += "\r\nControl returned to startButton_Click.\r\n";

            // Reenable the button in case you want to run the operation again.
            startButton.IsEnabled = true;
        }

        private async Task SumPageSizesAsync()
        {
            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            var total = 0;

            foreach (var url in urlList)
            {
                byte[] urlContents = await GetURLContentsAsync(url);

                // The previous line abbreviates the following two assignment statements.

                // GetURLContentsAsync returns a Task<T>. At completion, the task
                // produces a byte array.
                //Task<byte[]> getContentsTask = GetURLContentsAsync(url);
                //byte[] urlContents = await getContentsTask;

                DisplayResults(url, urlContents);

                // Update the total.
                total += urlContents.Length;
            }
            // Display the total count for all of the websites.
            resultsTextBox.Text +=
                $"\r\n\r\nTotal bytes returned:  {total}\r\n";
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }

        private async Task<byte[]> GetURLContentsAsync(string url)
        {
            // The downloaded resource ends up in the variable named content.
            var content = new MemoryStream();

            // Initialize an HttpWebRequest for the current URL.
            var webReq = (HttpWebRequest)WebRequest.Create(url);

            // Send the request to the Internet resource and wait for
            // the response.
            using (WebResponse response = await webReq.GetResponseAsync())

            // The previous statement abbreviates the following two statements.

            //Task<WebResponse> responseTask = webReq.GetResponseAsync();
            //using (WebResponse response = await responseTask)
            {
                // Get the data stream that is associated with the specified url.
                using (Stream responseStream = response.GetResponseStream())
                {
                    // Read the bytes in responseStream and copy them to content.
                    await responseStream.CopyToAsync(content);

                    // The previous statement abbreviates the following two statements.

                    // CopyToAsync returns a Task, not a Task<T>.
                    //Task copyTask = responseStream.CopyToAsync(content);

                    // When copyTask is completed, content contains a copy of
                    // responseStream.
                    //await copyTask;
                }
            }
            // Return the result as a byte array.
            return content.ToArray();
        }

        private void DisplayResults(string url, byte[] content)
        {
            // Display the length of each website. The string format
            // is designed to be used with a monospaced font, such as
            // Lucida Console or Global Monospace.
            var bytes = content.Length;
            // Strip off the "https://".
            var displayURL = url.Replace("https://", "");
            resultsTextBox.Text += $"\n{displayURL,-58} {bytes,8}";
        }
    }
}
```

<span data-ttu-id="48090-260">El código siguiente contiene el ejemplo completo de la solución que usa el método `HttpClient`, `GetByteArrayAsync`.</span><span class="sxs-lookup"><span data-stu-id="48090-260">The following code contains the full example of the solution that uses the `HttpClient` method, `GetByteArrayAsync`.</span></span>

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
using System.IO;
using System.Net;

namespace AsyncExampleWPF
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            resultsTextBox.Clear();

            // Disable the button until the operation is complete.
            startButton.IsEnabled = false;

            // One-step async call.
            await SumPageSizesAsync();

            //// Two-step async call.
            //Task sumTask = SumPageSizesAsync();
            //await sumTask;

            resultsTextBox.Text += "\r\nControl returned to startButton_Click.\r\n";

            // Reenable the button in case you want to run the operation again.
            startButton.IsEnabled = true;
        }

        private async Task SumPageSizesAsync()
        {
            // Declare an HttpClient object and increase the buffer size. The
            // default buffer size is 65,536.
            HttpClient client =
                new HttpClient() { MaxResponseContentBufferSize = 1000000 };

            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            var total = 0;

            foreach (var url in urlList)
            {
                // GetByteArrayAsync returns a task. At completion, the task
                // produces a byte array.
                byte[] urlContents = await client.GetByteArrayAsync(url);

                // The following two lines can replace the previous assignment statement.
                //Task<byte[]> getContentsTask = client.GetByteArrayAsync(url);
                //byte[] urlContents = await getContentsTask;

                DisplayResults(url, urlContents);

                // Update the total.
                total += urlContents.Length;
            }

            // Display the total count for all of the websites.
            resultsTextBox.Text +=
                $"\r\n\r\nTotal bytes returned:  {total}\r\n";
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }

        private void DisplayResults(string url, byte[] content)
        {
            // Display the length of each website. The string format
            // is designed to be used with a monospaced font, such as
            // Lucida Console or Global Monospace.
            var bytes = content.Length;
            // Strip off the "https://".
            var displayURL = url.Replace("https://", "");
            resultsTextBox.Text += $"\n{displayURL,-58} {bytes,8}";
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="48090-261">Vea también</span><span class="sxs-lookup"><span data-stu-id="48090-261">See also</span></span>

- <span data-ttu-id="48090-262">[Ejemplo de async: Acceso al tutorial web (C# y Visual Basic)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/hh300224(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="48090-262">[Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/hh300224(v=vs.110))</span></span>
- [<span data-ttu-id="48090-263">async</span><span class="sxs-lookup"><span data-stu-id="48090-263">async</span></span>](../../../language-reference/keywords/async.md)
- [<span data-ttu-id="48090-264">await</span><span class="sxs-lookup"><span data-stu-id="48090-264">await</span></span>](../../../language-reference/operators/await.md)
- [<span data-ttu-id="48090-265">Programación asincrónica con Async y Await (C#)</span><span class="sxs-lookup"><span data-stu-id="48090-265">Asynchronous Programming with async and await (C#)</span></span>](./index.md)
- [<span data-ttu-id="48090-266">Tipos de valor devueltos asincrónicos (C#)</span><span class="sxs-lookup"><span data-stu-id="48090-266">Async Return Types (C#)</span></span>](./async-return-types.md)
- <span data-ttu-id="48090-267">[Task-based Asynchronous Programming (TAP)](https://www.microsoft.com/download/details.aspx?id=19957) (Programación asincrónica basada en tareas [TAP])</span><span class="sxs-lookup"><span data-stu-id="48090-267">[Task-based Asynchronous Programming (TAP)](https://www.microsoft.com/download/details.aspx?id=19957)</span></span>
- [<span data-ttu-id="48090-268">Procedimiento para ampliar el tutorial de async usando Task.WhenAll (C#)</span><span class="sxs-lookup"><span data-stu-id="48090-268">How to extend the async walkthrough by using Task.WhenAll (C#)</span></span>](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md)
- [<span data-ttu-id="48090-269">Procedimiento para realizar varias solicitudes web en paralelo con async y await (C#)</span><span class="sxs-lookup"><span data-stu-id="48090-269">How to make multiple web requests in parallel by using async and await (C#)</span></span>](./how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)
