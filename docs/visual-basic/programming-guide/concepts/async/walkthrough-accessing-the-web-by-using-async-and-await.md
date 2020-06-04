---
title: 'Tutorial: Acceso a web mediante async y await'
ms.date: 07/20/2015
ms.assetid: 84fd047f-fab8-4d89-8ced-104fb7310a91
ms.openlocfilehash: 41ededd4d4335b78b8d7a33e8fe387c7d632cbee
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400750"
---
# <a name="walkthrough-accessing-the-web-by-using-async-and-await-visual-basic"></a><span data-ttu-id="0f410-102">Tutorial: Acceso a web usando Async y Await (C# y Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f410-102">Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)</span></span>

<span data-ttu-id="0f410-103">Puede escribir programas asincrónicos de manera más fácil e intuitiva usando las características async/await.</span><span class="sxs-lookup"><span data-stu-id="0f410-103">You can write asynchronous programs more easily and intuitively by using async/await features.</span></span> <span data-ttu-id="0f410-104">Puede escribir código asincrónico parecido al código sincrónico y dejar que el compilador gestione las difíciles funciones de devolución de llamada y continuaciones que normalmente implica el código asincrónico.</span><span class="sxs-lookup"><span data-stu-id="0f410-104">You can write asynchronous code that looks like synchronous code and let the compiler handle the difficult callback functions and continuations that asynchronous code usually entails.</span></span>

<span data-ttu-id="0f410-105">Para obtener más información sobre la característica Async, consulte [programación asincrónica con Async y Await (Visual Basic)](index.md).</span><span class="sxs-lookup"><span data-stu-id="0f410-105">For more information about the Async feature, see [Asynchronous Programming with Async and Await (Visual Basic)](index.md).</span></span>

<span data-ttu-id="0f410-106">Este tutorial comienza con una aplicación sincrónica de Windows Presentation Foundation (WPF) que suma el número de bytes de una lista de sitios web.</span><span class="sxs-lookup"><span data-stu-id="0f410-106">This walkthrough starts with a synchronous Windows Presentation Foundation (WPF) application that sums the number of bytes in a list of websites.</span></span> <span data-ttu-id="0f410-107">A continuación, el tutorial convierte la aplicación en una solución asincrónica mediante el uso de las características nuevas.</span><span class="sxs-lookup"><span data-stu-id="0f410-107">The walkthrough then converts the application to an asynchronous solution by using the new features.</span></span>

<span data-ttu-id="0f410-108">Si no quiere compilar las aplicaciones por su cuenta, puede descargar "Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)" (Muestra de Async: obtener acceso al tutorial web [C# y Visual Basic]) de [Muestras de código para desarrollador](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span><span class="sxs-lookup"><span data-stu-id="0f410-108">If you don't want to build the applications yourself, you can download "Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)" from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span></span>

<span data-ttu-id="0f410-109">En este tutorial, se realizarán las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="0f410-109">In this walkthrough, you complete the following tasks:</span></span>

> [!div class="checklist"]
>
> - [<span data-ttu-id="0f410-110">Crear una aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="0f410-110">Create a WPF application</span></span>](#create-a-wpf-application)
> - [<span data-ttu-id="0f410-111">Diseñar una ventana MainWindow simple de WPF</span><span class="sxs-lookup"><span data-stu-id="0f410-111">Design a simple WPF MainWindow</span></span>](#design-a-simple-wpf-mainwindow)
> - [<span data-ttu-id="0f410-112">Agregar una referencia</span><span class="sxs-lookup"><span data-stu-id="0f410-112">Add a reference</span></span>](#add-a-reference)
> - [<span data-ttu-id="0f410-113">Agregar instrucciones Imports necesarias</span><span class="sxs-lookup"><span data-stu-id="0f410-113">Add necessary Imports statements</span></span>](#add-necessary-imports-statements)
> - [<span data-ttu-id="0f410-114">Crear una aplicación sincrónica</span><span class="sxs-lookup"><span data-stu-id="0f410-114">Create a synchronous application</span></span>](#create-a-synchronous-application)
> - [<span data-ttu-id="0f410-115">Probar la solución sincrónica</span><span class="sxs-lookup"><span data-stu-id="0f410-115">Test the synchronous solution</span></span>](#test-the-synchronous-solution)
> - [<span data-ttu-id="0f410-116">Convertir GetURLContents en un método asincrónico</span><span class="sxs-lookup"><span data-stu-id="0f410-116">Convert GetURLContents to an asynchronous method</span></span>](#convert-geturlcontents-to-an-asynchronous-method)
> - [<span data-ttu-id="0f410-117">Convertir SumPageSizes en un método asincrónico</span><span class="sxs-lookup"><span data-stu-id="0f410-117">Convert SumPageSizes to an asynchronous method</span></span>](#convert-sumpagesizes-to-an-asynchronous-method)
> - [<span data-ttu-id="0f410-118">Convertir startButton_Click en un método asincrónico</span><span class="sxs-lookup"><span data-stu-id="0f410-118">Convert startButton_Click to an asynchronous method</span></span>](#convert-startbutton_click-to-an-asynchronous-method)
> - [<span data-ttu-id="0f410-119">Probar la solución asincrónica</span><span class="sxs-lookup"><span data-stu-id="0f410-119">Test the asynchronous solution</span></span>](#test-the-asynchronous-solution)
> - [<span data-ttu-id="0f410-120">Reemplazar el método GetURLContentsAsync por un método .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0f410-120">Replace the GetURLContentsAsync method with a .NET Framework method</span></span>](#replace-the-geturlcontentsasync-method-with-a-net-framework-method)

<span data-ttu-id="0f410-121">Vea la sección [ejemplo](#example) para ver el ejemplo asincrónico completo.</span><span class="sxs-lookup"><span data-stu-id="0f410-121">See the [Example](#example) section for the complete asynchronous example.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0f410-122">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0f410-122">Prerequisites</span></span>

<span data-ttu-id="0f410-123">Debe tener Visual Studio 2012 o posterior instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="0f410-123">Visual Studio 2012 or later must be installed on your computer.</span></span> <span data-ttu-id="0f410-124">Para obtener más información, vea la página de [descargas](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0f410-124">For more information, see the Visual Studio [Downloads](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) page.</span></span>

## <a name="create-a-wpf-application"></a><span data-ttu-id="0f410-125">Crear una aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="0f410-125">Create a WPF application</span></span>

1. <span data-ttu-id="0f410-126">Inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0f410-126">Start Visual Studio.</span></span>

2. <span data-ttu-id="0f410-127">En la barra de menús, elija **Archivo**, **Nuevo**, **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="0f410-127">On the menu bar, choose **File**, **New**, **Project**.</span></span>

    <span data-ttu-id="0f410-128">Aparece el cuadro de diálogo **Nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="0f410-128">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="0f410-129">En el panel **plantillas instaladas** , elija Visual Basic y, a continuación, elija **aplicación WPF** en la lista de tipos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="0f410-129">In the **Installed Templates** pane, choose Visual Basic, and then choose **WPF Application** from the list of project types.</span></span>

4. <span data-ttu-id="0f410-130">En el cuadro de texto **Nombre**, escriba `AsyncExampleWPF` y elija el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0f410-130">In the **Name** text box, enter `AsyncExampleWPF`, and then choose the **OK** button.</span></span>

    <span data-ttu-id="0f410-131">El proyecto nuevo aparece en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="0f410-131">The new project appears in **Solution Explorer**.</span></span>

## <a name="design-a-simple-wpf-mainwindow"></a><span data-ttu-id="0f410-132">Diseñar una ventana MainWindow simple de WPF</span><span class="sxs-lookup"><span data-stu-id="0f410-132">Design a simple WPF MainWindow</span></span>

1. <span data-ttu-id="0f410-133">En el Editor de código de Visual Studio, elija la pestaña **MainWindow.xaml** .</span><span class="sxs-lookup"><span data-stu-id="0f410-133">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>

2. <span data-ttu-id="0f410-134">Si la ventana **Cuadro de herramientas** no está visible, abra el menú **Vista** y elija **Cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="0f410-134">If the **Toolbox** window isn’t visible, open the **View** menu, and then choose **Toolbox**.</span></span>

3. <span data-ttu-id="0f410-135">Agregue un control **Botón** y un control **TextBox** a la ventana **MainWindow**.</span><span class="sxs-lookup"><span data-stu-id="0f410-135">Add a **Button** control and a **TextBox** control to the **MainWindow** window.</span></span>

4. <span data-ttu-id="0f410-136">Resalte el control **TextBox** y, en la ventana **Propiedades**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="0f410-136">Highlight the **TextBox** control and, in the **Properties** window, set the following values:</span></span>

    - <span data-ttu-id="0f410-137">Establezca la propiedad **Nombre** en `resultsTextBox`.</span><span class="sxs-lookup"><span data-stu-id="0f410-137">Set the **Name** property to `resultsTextBox`.</span></span>

    - <span data-ttu-id="0f410-138">Establezca la propiedad **Alto** en 250.</span><span class="sxs-lookup"><span data-stu-id="0f410-138">Set the **Height** property to 250.</span></span>

    - <span data-ttu-id="0f410-139">Establezca la propiedad **Ancho** en 500.</span><span class="sxs-lookup"><span data-stu-id="0f410-139">Set the **Width** property to 500.</span></span>

    - <span data-ttu-id="0f410-140">En la pestaña **Texto**, especifique una fuente monoespaciada, como Lucida Console o Global Monospace.</span><span class="sxs-lookup"><span data-stu-id="0f410-140">On the **Text** tab, specify a monospaced font, such as Lucida Console or Global Monospace.</span></span>

5. <span data-ttu-id="0f410-141">Resalte el control **Botón** y, en la ventana **Propiedades**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="0f410-141">Highlight the **Button** control and, in the **Properties** window, set the following values:</span></span>

    - <span data-ttu-id="0f410-142">Establezca la propiedad **Nombre** en `startButton`.</span><span class="sxs-lookup"><span data-stu-id="0f410-142">Set the **Name** property to `startButton`.</span></span>

    - <span data-ttu-id="0f410-143">Cambie el valor de la propiedad **Contenido** de **Botón** a **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="0f410-143">Change the value of the **Content** property from **Button** to **Start**.</span></span>

6. <span data-ttu-id="0f410-144">Coloque el cuadro de texto y el botón de manera que ambos aparezcan en la ventana **MainWindow**.</span><span class="sxs-lookup"><span data-stu-id="0f410-144">Position the text box and the button so that both appear in the **MainWindow** window.</span></span>

    <span data-ttu-id="0f410-145">Para obtener más información sobre el Diseñador XAML de WPF, consulte [Crear una IU con el Diseñador XAML](/visualstudio/xaml-tools/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="0f410-145">For more information about the WPF XAML Designer, see [Creating a UI by using XAML Designer](/visualstudio/xaml-tools/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span></span>

## <a name="add-a-reference"></a><span data-ttu-id="0f410-146">Agregar una referencia</span><span class="sxs-lookup"><span data-stu-id="0f410-146">Add a reference</span></span>

1. <span data-ttu-id="0f410-147">En el **Explorador de soluciones**, resalte el nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0f410-147">In **Solution Explorer**, highlight your project's name.</span></span>

2. <span data-ttu-id="0f410-148">En la barra de menús, elija **Proyecto**, **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="0f410-148">On the menu bar, choose **Project**, **Add Reference**.</span></span>

    <span data-ttu-id="0f410-149">Aparecerá el cuadro de diálogo **Administrador de referencias**.</span><span class="sxs-lookup"><span data-stu-id="0f410-149">The **Reference Manager** dialog box appears.</span></span>

3. <span data-ttu-id="0f410-150">En la parte superior del cuadro de diálogo, compruebe que el proyecto tiene como destino .NET Framework 4.5 o superior.</span><span class="sxs-lookup"><span data-stu-id="0f410-150">At the top of the dialog box, verify that your project is targeting the .NET Framework 4.5 or higher.</span></span>

4. <span data-ttu-id="0f410-151">En el área **Ensamblados**, elija **Framework** si no está ya seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0f410-151">In the **Assemblies** area, choose **Framework** if it isn’t already chosen.</span></span>

5. <span data-ttu-id="0f410-152">En la lista de nombres, seleccione la casilla **System.Net.Http**.</span><span class="sxs-lookup"><span data-stu-id="0f410-152">In the list of names, select the **System.Net.Http** check box.</span></span>

6. <span data-ttu-id="0f410-153">Elija el botón **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="0f410-153">Choose the **OK** button to close the dialog box.</span></span>

## <a name="add-necessary-imports-statements"></a><span data-ttu-id="0f410-154">Agregar instrucciones Imports necesarias</span><span class="sxs-lookup"><span data-stu-id="0f410-154">Add necessary Imports statements</span></span>

1. <span data-ttu-id="0f410-155">En **Explorador de soluciones**, abra el menú contextual de MainWindow. Xaml. VB y, a continuación, elija **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="0f410-155">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>

2. <span data-ttu-id="0f410-156">Agregue las siguientes `Imports` instrucciones en la parte superior del archivo de código si aún no están presentes.</span><span class="sxs-lookup"><span data-stu-id="0f410-156">Add the following `Imports` statements at the top of the code file if they’re not already present.</span></span>

    ```vb
    Imports System.Net.Http
    Imports System.Net
    Imports System.IO
    ```

## <a name="create-a-synchronous-application"></a><span data-ttu-id="0f410-157">Crear una aplicación sincrónica</span><span class="sxs-lookup"><span data-stu-id="0f410-157">Create a synchronous application</span></span>

1. <span data-ttu-id="0f410-158">En la ventana de diseño, MainWindow. XAML, haga doble clic en el botón **Inicio** para crear el `startButton_Click` controlador de eventos en MainWindow. Xaml. VB.</span><span class="sxs-lookup"><span data-stu-id="0f410-158">In the design window, MainWindow.xaml, double-click the **Start** button to create the `startButton_Click` event handler in MainWindow.xaml.vb.</span></span>

2. <span data-ttu-id="0f410-159">En MainWindow. Xaml. VB, copie el código siguiente en el cuerpo de `startButton_Click` :</span><span class="sxs-lookup"><span data-stu-id="0f410-159">In MainWindow.xaml.vb, copy the following code into the body of `startButton_Click`:</span></span>

    ```vb
    resultsTextBox.Clear()
    SumPageSizes()
    resultsTextBox.Text &= vbCrLf & "Control returned to startButton_Click."
    ```

    <span data-ttu-id="0f410-160">El código llama al método que controla la aplicación, `SumPageSizes`, y muestra un mensaje cuando el control vuelve a `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="0f410-160">The code calls the method that drives the application, `SumPageSizes`, and displays a message when control returns to `startButton_Click`.</span></span>

3. <span data-ttu-id="0f410-161">El código de la solución sincrónica contiene los cuatro métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0f410-161">The code for the synchronous solution contains the following four methods:</span></span>

    - <span data-ttu-id="0f410-162">`SumPageSizes`, que obtiene una lista de direcciones URL de páginas web de `SetUpURLList` y, a continuación, llama a `GetURLContents` y `DisplayResults` para que procesen cada dirección URL.</span><span class="sxs-lookup"><span data-stu-id="0f410-162">`SumPageSizes`, which gets a list of webpage URLs from `SetUpURLList` and then calls `GetURLContents` and `DisplayResults` to process each URL.</span></span>

    - <span data-ttu-id="0f410-163">`SetUpURLList`, que crea y devuelve una lista de direcciones web.</span><span class="sxs-lookup"><span data-stu-id="0f410-163">`SetUpURLList`, which makes and returns a list of web addresses.</span></span>

    - <span data-ttu-id="0f410-164">`GetURLContents`, que descarga el contenido de cada sitio web y devuelve el contenido como una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="0f410-164">`GetURLContents`, which downloads the contents of each website and returns the contents as a byte array.</span></span>

    - <span data-ttu-id="0f410-165">`DisplayResults`, que muestra el número de bytes de la matriz de bytes de cada dirección URL.</span><span class="sxs-lookup"><span data-stu-id="0f410-165">`DisplayResults`, which displays  the number of bytes in the byte array for each URL.</span></span>

    <span data-ttu-id="0f410-166">Copie los cuatro métodos siguientes y péguelos en el `startButton_Click` controlador de eventos en MainWindow. Xaml. VB:</span><span class="sxs-lookup"><span data-stu-id="0f410-166">Copy the following four methods, and then paste them under the `startButton_Click` event handler in MainWindow.xaml.vb:</span></span>

    ```vb
    Private Sub SumPageSizes()

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        Dim total = 0
        For Each url In urlList
            ' GetURLContents returns the contents of url as a byte array.
            Dim urlContents As Byte() = GetURLContents(url)

            DisplayResults(url, urlContents)

            ' Update the total.
            total += urlContents.Length
        Next

        ' Display the total count for all of the web addresses.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf & "Total bytes returned:  {0}" & vbCrLf, total)
    End Sub

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
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
            }
        Return urls
    End Function

    Private Function GetURLContents(url As String) As Byte()

        ' The downloaded resource ends up in the variable named content.
        Dim content = New MemoryStream()

        ' Initialize an HttpWebRequest for the current URL.
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)

        ' Send the request to the Internet resource and wait for
        ' the response.
        ' Note: you can't use HttpWebRequest.GetResponse in a Windows Store app.
        Using response As WebResponse = webReq.GetResponse()
            ' Get the data stream that is associated with the specified URL.
            Using responseStream As Stream = response.GetResponseStream()
                ' Read the bytes in responseStream and copy them to content.
                responseStream.CopyTo(content)
            End Using
        End Using

        ' Return the result as a byte array.
        Return content.ToArray()
    End Function

    Private Sub DisplayResults(url As String, content As Byte())

        ' Display the length of each website. The string format
        ' is designed to be used with a monospaced font, such as
        ' Lucida Console or Global Monospace.
        Dim bytes = content.Length
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub
    ```

## <a name="test-the-synchronous-solution"></a><span data-ttu-id="0f410-167">Probar la solución sincrónica</span><span class="sxs-lookup"><span data-stu-id="0f410-167">Test the synchronous solution</span></span>

1. <span data-ttu-id="0f410-168">Presione la tecla F5 para ejecutar el programa y elija el botón **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="0f410-168">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>

    <span data-ttu-id="0f410-169">Debería aparecer un resultado similar a la lista siguiente:</span><span class="sxs-lookup"><span data-stu-id="0f410-169">Output that resembles the following list should appear:</span></span>

    ```console
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

    <span data-ttu-id="0f410-170">Tenga en cuenta que los recuentos tardan unos segundos en mostrarse.</span><span class="sxs-lookup"><span data-stu-id="0f410-170">Notice that it takes a few seconds to display the counts.</span></span> <span data-ttu-id="0f410-171">Durante ese tiempo, el subproceso de interfaz de usuario se bloquea mientras espera a que se descarguen los recursos solicitados.</span><span class="sxs-lookup"><span data-stu-id="0f410-171">During that time, the UI thread is blocked while it waits for requested resources to download.</span></span> <span data-ttu-id="0f410-172">Como resultado, no se puede mover, maximizar, minimizar o ni siquiera cerrar la ventana de la pantalla después de elegir el botón **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="0f410-172">As a result, you can't move, maximize, minimize, or even close the display window after you choose the  **Start** button.</span></span> <span data-ttu-id="0f410-173">Estos intentos producirán un error hasta que empiecen a aparecer los recuentos de bytes.</span><span class="sxs-lookup"><span data-stu-id="0f410-173">These efforts fail until the byte counts start to appear.</span></span> <span data-ttu-id="0f410-174">Si un sitio web no responde, no se le indicará cuál es el sitio que produjo el error.</span><span class="sxs-lookup"><span data-stu-id="0f410-174">If a website isn’t responding, you have no indication of which site failed.</span></span> <span data-ttu-id="0f410-175">Incluso resulta difícil dejar de esperar y cerrar el programa.</span><span class="sxs-lookup"><span data-stu-id="0f410-175">It is difficult even to stop waiting and close the program.</span></span>

## <a name="convert-geturlcontents-to-an-asynchronous-method"></a><span data-ttu-id="0f410-176">Convertir GetURLContents en un método asincrónico</span><span class="sxs-lookup"><span data-stu-id="0f410-176">Convert GetURLContents to an asynchronous method</span></span>

1. <span data-ttu-id="0f410-177">Para convertir la solución sincrónica en una solución asincrónica, el mejor lugar para comenzar es `GetURLContents` porque las llamadas al <xref:System.Net.HttpWebRequest.GetResponse%2A?displayProperty=nameWithType> método y al <xref:System.IO.Stream.CopyTo%2A?displayProperty=nameWithType> método son el lugar en el que la aplicación tiene acceso a la Web.</span><span class="sxs-lookup"><span data-stu-id="0f410-177">To convert the synchronous solution to an asynchronous solution, the best place to start is in `GetURLContents` because the calls to the <xref:System.Net.HttpWebRequest.GetResponse%2A?displayProperty=nameWithType> method and to the <xref:System.IO.Stream.CopyTo%2A?displayProperty=nameWithType> method are where the application accesses the web.</span></span> <span data-ttu-id="0f410-178">.NET Framework facilita la conversión proporcionando versiones asincrónicas de ambos métodos.</span><span class="sxs-lookup"><span data-stu-id="0f410-178">The .NET Framework makes the conversion easy by supplying asynchronous versions of both methods.</span></span>

    <span data-ttu-id="0f410-179">Para obtener más información sobre los modelos que se usan en `GetURLContents`, vea <xref:System.Net.WebRequest>.</span><span class="sxs-lookup"><span data-stu-id="0f410-179">For more information about the methods that are used in `GetURLContents`, see <xref:System.Net.WebRequest>.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0f410-180">A medida que siga los pasos de este tutorial, aparecerán varios errores del compilador.</span><span class="sxs-lookup"><span data-stu-id="0f410-180">As you follow the steps in this walkthrough, several compiler errors appear.</span></span> <span data-ttu-id="0f410-181">Puede hacer caso omiso y continuar con el tutorial.</span><span class="sxs-lookup"><span data-stu-id="0f410-181">You can ignore them and continue with the walkthrough.</span></span>

    <span data-ttu-id="0f410-182">Cambie el método al que se llama en la tercera línea de `GetURLContents` de `GetResponse` al método <xref:System.Net.WebRequest.GetResponseAsync%2A> asincrónico basado en tareas.</span><span class="sxs-lookup"><span data-stu-id="0f410-182">Change the method that's called in the third line of `GetURLContents` from `GetResponse` to the asynchronous, task-based <xref:System.Net.WebRequest.GetResponseAsync%2A> method.</span></span>

    ```vb
    Using response As WebResponse = webReq.GetResponseAsync()
    ```

2. <span data-ttu-id="0f410-183">`GetResponseAsync` devuelve <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="0f410-183">`GetResponseAsync` returns a <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="0f410-184">En este caso, la *variable de devolución de tarea*, `TResult` , tiene el tipo <xref:System.Net.WebResponse> .</span><span class="sxs-lookup"><span data-stu-id="0f410-184">In this case, the *task return variable*, `TResult`, has type <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="0f410-185">La tarea es una promesa para generar un objeto `WebResponse` real después de que se descarguen los datos solicitados y la tarea se ejecute hasta completarse.</span><span class="sxs-lookup"><span data-stu-id="0f410-185">The task is a promise to produce an actual `WebResponse` object after the requested data has been downloaded and the task has run to completion.</span></span>

    <span data-ttu-id="0f410-186">Para recuperar el `WebResponse` valor de la tarea, aplique un operador [Await](../../../language-reference/operators/await-operator.md) a la llamada a `GetResponseAsync` , como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="0f410-186">To retrieve the `WebResponse` value from the task, apply an [Await](../../../language-reference/operators/await-operator.md) operator to the call to `GetResponseAsync`, as the following code shows.</span></span>

    ```vb
    Using response As WebResponse = Await webReq.GetResponseAsync()
    ```

    <span data-ttu-id="0f410-187">El operador `Await` suspende la ejecución del método actual, `GetURLContents`, hasta que se complete la tarea esperada.</span><span class="sxs-lookup"><span data-stu-id="0f410-187">The `Await` operator suspends the execution of the current method, `GetURLContents`, until the awaited task is complete.</span></span> <span data-ttu-id="0f410-188">Mientras tanto, el control devuelve al llamador del método actual.</span><span class="sxs-lookup"><span data-stu-id="0f410-188">In the meantime, control returns to the caller of the current method.</span></span> <span data-ttu-id="0f410-189">En este ejemplo, el método actual es `GetURLContents` y el llamador es `SumPageSizes`.</span><span class="sxs-lookup"><span data-stu-id="0f410-189">In this example, the current method is `GetURLContents`, and the caller is `SumPageSizes`.</span></span> <span data-ttu-id="0f410-190">Cuando la tarea finaliza, el objeto `WebResponse` prometido se genera como valor de la tarea esperada y se asigna a la variable `response`.</span><span class="sxs-lookup"><span data-stu-id="0f410-190">When the task is finished, the promised `WebResponse` object is produced as the value of the awaited task and assigned to the variable `response`.</span></span>

    <span data-ttu-id="0f410-191">La instrucción anterior se puede dividir en las dos instrucciones siguientes para aclarar lo que sucede.</span><span class="sxs-lookup"><span data-stu-id="0f410-191">The previous statement can be separated into the following two statements to clarify what happens.</span></span>

    ```vb
    Dim responseTask As Task(Of WebResponse) = webReq.GetResponseAsync()
    Using response As WebResponse = Await responseTask
    ```

    <span data-ttu-id="0f410-192">La llamada a `webReq.GetResponseAsync` devuelve `Task(Of WebResponse)` o `Task<WebResponse>`.</span><span class="sxs-lookup"><span data-stu-id="0f410-192">The call to `webReq.GetResponseAsync` returns a `Task(Of WebResponse)` or `Task<WebResponse>`.</span></span> <span data-ttu-id="0f410-193">A continuación, `Await` se aplica un operador a la tarea para recuperar el `WebResponse` valor.</span><span class="sxs-lookup"><span data-stu-id="0f410-193">Then an `Await` operator is applied to the task to retrieve the `WebResponse` value.</span></span>

    <span data-ttu-id="0f410-194">Si el método asincrónico debe realizar un trabajo que no depende de la finalización de la tarea, el método puede continuar con ese trabajo entre estas dos instrucciones, después de la llamada al método asincrónico y antes de que se aplique el operador await.</span><span class="sxs-lookup"><span data-stu-id="0f410-194">If your async method has work to do that doesn’t depend on the completion of the task, the method can continue with that work between these two statements, after the call to the async method and before the await operator is applied.</span></span> <span data-ttu-id="0f410-195">Para obtener ejemplos, vea [Cómo: hacer varias solicitudes web en paralelo mediante Async y Await (Visual Basic)](how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) y [Cómo: ampliar el tutorial de Async mediante Task. WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span><span class="sxs-lookup"><span data-stu-id="0f410-195">For examples, see [How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)](how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) and [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>

3. <span data-ttu-id="0f410-196">Dado que ha agregado el operador `Await` en el paso anterior, se produce un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="0f410-196">Because you added the `Await` operator in the previous step, a compiler error occurs.</span></span> <span data-ttu-id="0f410-197">El operador solo se puede usar en métodos marcados con el modificador [Async](../../../language-reference/modifiers/async.md) .</span><span class="sxs-lookup"><span data-stu-id="0f410-197">The operator can be used only in methods that are marked with the [Async](../../../language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="0f410-198">Omita el error mientras repita los pasos de conversión para reemplazar la llamada a `CopyTo` con una llamada a `CopyToAsync`.</span><span class="sxs-lookup"><span data-stu-id="0f410-198">Ignore the error while you repeat the conversion steps to replace the call to `CopyTo` with a call to `CopyToAsync`.</span></span>

    - <span data-ttu-id="0f410-199">Cambie el nombre del método al que se llama a <xref:System.IO.Stream.CopyToAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="0f410-199">Change the name of the method that’s called to <xref:System.IO.Stream.CopyToAsync%2A>.</span></span>

    - <span data-ttu-id="0f410-200">El método `CopyTo` o `CopyToAsync` copia bytes a su argumento, `content`, y no devuelve un valor significativo.</span><span class="sxs-lookup"><span data-stu-id="0f410-200">The `CopyTo` or `CopyToAsync` method copies bytes to its argument, `content`, and doesn’t return a meaningful value.</span></span> <span data-ttu-id="0f410-201">En la versión sincrónica, la llamada a `CopyTo` es una sencilla instrucción que no devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="0f410-201">In the synchronous version, the call to `CopyTo` is a simple statement that doesn't return a value.</span></span> <span data-ttu-id="0f410-202">La versión asincrónica, `CopyToAsync`, devuelve una <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="0f410-202">The asynchronous version, `CopyToAsync`, returns a <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="0f410-203">La tarea funciona como "Task(void)" y permite que se espere al método.</span><span class="sxs-lookup"><span data-stu-id="0f410-203">The task functions like "Task(void)" and enables the method to be awaited.</span></span> <span data-ttu-id="0f410-204">Aplique `Await` o `await` a la llamada a `CopyToAsync`, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="0f410-204">Apply `Await` or `await` to the call to `CopyToAsync`, as the following code shows.</span></span>

        ```vb
        Await responseStream.CopyToAsync(content)
        ```

         <span data-ttu-id="0f410-205">La instrucción anterior abrevia las dos líneas de código siguientes.</span><span class="sxs-lookup"><span data-stu-id="0f410-205">The previous statement abbreviates the following two lines of code.</span></span>

        ```vb
        ' CopyToAsync returns a Task, not a Task<T>.
        Dim copyTask As Task = responseStream.CopyToAsync(content)

        ' When copyTask is completed, content contains a copy of
        ' responseStream.
        Await copyTask
        ```

4. <span data-ttu-id="0f410-206">Lo único que queda por hacer en `GetURLContents` es ajustar la firma del método.</span><span class="sxs-lookup"><span data-stu-id="0f410-206">All that remains to be done in `GetURLContents` is to adjust the method signature.</span></span> <span data-ttu-id="0f410-207">Puede usar el `Await` operador solo en métodos marcados con el modificador [Async](../../../language-reference/modifiers/async.md) .</span><span class="sxs-lookup"><span data-stu-id="0f410-207">You can use the `Await` operator only in methods that are marked with the [Async](../../../language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="0f410-208">Agregue el modificador para marcar el método como *método asincrónico*, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="0f410-208">Add the modifier to mark the method as an *async method*, as the following code shows.</span></span>

    ```vb
    Private Async Function GetURLContents(url As String) As Byte()
    ```

5. <span data-ttu-id="0f410-209">El tipo de valor devuelto de un método asincrónico solo puede ser <xref:System.Threading.Tasks.Task> , <xref:System.Threading.Tasks.Task%601> .</span><span class="sxs-lookup"><span data-stu-id="0f410-209">The return type of an async method can only be <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="0f410-210">En Visual Basic, el método debe ser `Function`, que devuelve `Task` o `Task(Of T)`, o el método debe ser `Sub`.</span><span class="sxs-lookup"><span data-stu-id="0f410-210">In Visual Basic, the method must be a `Function` that returns a `Task` or a `Task(Of T)`, or the method must be a `Sub`.</span></span> <span data-ttu-id="0f410-211">Normalmente, un `Sub` método solo se usa en un controlador de eventos Async, donde `Sub` es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="0f410-211">Typically, a `Sub` method  is used only in an async event handler, where `Sub` is required.</span></span> <span data-ttu-id="0f410-212">En otros casos, se usa `Task(T)` si el método completado tiene una instrucción [Return](../../../language-reference/statements/return-statement.md) que devuelve un valor de tipo T, y se usa `Task` si el método completado no devuelve un valor significativo.</span><span class="sxs-lookup"><span data-stu-id="0f410-212">In other cases, you use `Task(T)` if the completed method has a [Return](../../../language-reference/statements/return-statement.md) statement that returns a value of type T, and you use `Task` if the completed method doesn’t return a meaningful value.</span></span>

    <span data-ttu-id="0f410-213">Para obtener más información, vea [tipos de valor devueltos Async (Visual Basic)](async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="0f410-213">For more information, see [Async Return Types (Visual Basic)](async-return-types.md).</span></span>

    <span data-ttu-id="0f410-214">El método `GetURLContents` tiene una instrucción return, y la instrucción devuelve una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="0f410-214">Method `GetURLContents` has a return statement, and the statement returns a byte array.</span></span> <span data-ttu-id="0f410-215">Por lo tanto, el tipo de valor devuelto de la versión de async es Task(T), donde T es una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="0f410-215">Therefore, the return type of the async version is Task(T), where T is a byte array.</span></span> <span data-ttu-id="0f410-216">Realice los cambios siguientes en la firma del método:</span><span class="sxs-lookup"><span data-stu-id="0f410-216">Make the following changes in the method signature:</span></span>

    - <span data-ttu-id="0f410-217">Cambie el tipo de valor devuelto a `Task(Of Byte())`.</span><span class="sxs-lookup"><span data-stu-id="0f410-217">Change the return type to `Task(Of Byte())`.</span></span>

    - <span data-ttu-id="0f410-218">Por convención, los métodos asincrónicos tienen nombres que terminan en "Async", por lo que debe cambiar el nombre del método a `GetURLContentsAsync`.</span><span class="sxs-lookup"><span data-stu-id="0f410-218">By convention, asynchronous methods have names that end in "Async," so rename the method `GetURLContentsAsync`.</span></span>

    <span data-ttu-id="0f410-219">En el código siguiente se muestran estos cambios.</span><span class="sxs-lookup"><span data-stu-id="0f410-219">The following code shows these changes.</span></span>

    ```vb
    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())
    ```

    <span data-ttu-id="0f410-220">Con estos pocos cambios, se completa la conversión de `GetURLContents` en un método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="0f410-220">With those few changes, the conversion of `GetURLContents` to an asynchronous method is complete.</span></span>

## <a name="convert-sumpagesizes-to-an-asynchronous-method"></a><span data-ttu-id="0f410-221">Convertir SumPageSizes en un método asincrónico</span><span class="sxs-lookup"><span data-stu-id="0f410-221">Convert SumPageSizes to an asynchronous method</span></span>

1. <span data-ttu-id="0f410-222">Repita los pasos del procedimiento anterior para `SumPageSizes`.</span><span class="sxs-lookup"><span data-stu-id="0f410-222">Repeat the steps from the previous procedure for `SumPageSizes`.</span></span> <span data-ttu-id="0f410-223">Primero, cambie la llamada a `GetURLContents` a una llamada asincrónica.</span><span class="sxs-lookup"><span data-stu-id="0f410-223">First, change the call to `GetURLContents` to an asynchronous call.</span></span>

    - <span data-ttu-id="0f410-224">Cambie el nombre del método al que se llama de `GetURLContents` a `GetURLContentsAsync`, si aún no lo ha hecho.</span><span class="sxs-lookup"><span data-stu-id="0f410-224">Change the name of the method that’s called from `GetURLContents` to `GetURLContentsAsync`, if you haven't already done so.</span></span>

    - <span data-ttu-id="0f410-225">Aplique `Await` a la tarea que devuelve `GetURLContentsAsync` para obtener el valor de la matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="0f410-225">Apply `Await` to the task that `GetURLContentsAsync` returns to obtain the byte array value.</span></span>

    <span data-ttu-id="0f410-226">En el código siguiente se muestran estos cambios.</span><span class="sxs-lookup"><span data-stu-id="0f410-226">The following code shows these changes.</span></span>

    ```vb
    Dim urlContents As Byte() = Await GetURLContentsAsync(url)
    ```

    <span data-ttu-id="0f410-227">La asignación anterior abrevia las dos líneas de código siguientes.</span><span class="sxs-lookup"><span data-stu-id="0f410-227">The previous assignment abbreviates the following two lines of code.</span></span>

    ```vb
    ' GetURLContentsAsync returns a task. At completion, the task
    ' produces a byte array.
    Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)
    Dim urlContents As Byte() = Await getContentsTask
    ```

2. <span data-ttu-id="0f410-228">Realice los cambios siguientes en la firma del método:</span><span class="sxs-lookup"><span data-stu-id="0f410-228">Make the following changes in the method's signature:</span></span>

    - <span data-ttu-id="0f410-229">Marque el método con el modificador `Async`.</span><span class="sxs-lookup"><span data-stu-id="0f410-229">Mark the method with the `Async` modifier.</span></span>

    - <span data-ttu-id="0f410-230">Agregue "Async" al nombre del método.</span><span class="sxs-lookup"><span data-stu-id="0f410-230">Add "Async" to the method name.</span></span>

    - <span data-ttu-id="0f410-231">No hay ninguna variable de devolución de tarea, T, esta vez porque `SumPageSizesAsync` no devuelve un valor para t. (el método no tiene ninguna `Return` instrucción). Sin embargo, el método debe devolver un `Task` para que sea Await.</span><span class="sxs-lookup"><span data-stu-id="0f410-231">There is no task return variable, T, this time because `SumPageSizesAsync` doesn’t return a value for T. (The method has no `Return` statement.) However, the method must return a `Task` to be awaitable.</span></span> <span data-ttu-id="0f410-232">Por lo tanto, cambie el tipo de método de `Sub` a `Function` .</span><span class="sxs-lookup"><span data-stu-id="0f410-232">Therefore, change the method type from `Sub` to `Function`.</span></span> <span data-ttu-id="0f410-233">El tipo de valor devuelto de la función es `Task`.</span><span class="sxs-lookup"><span data-stu-id="0f410-233">The return type of the function is `Task`.</span></span>

    <span data-ttu-id="0f410-234">En el código siguiente se muestran estos cambios.</span><span class="sxs-lookup"><span data-stu-id="0f410-234">The following code shows these changes.</span></span>

    ```vb
    Private Async Function SumPageSizesAsync() As Task
    ```

    <span data-ttu-id="0f410-235">Se completa así la conversión de `SumPageSizes` a `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="0f410-235">The conversion of `SumPageSizes` to `SumPageSizesAsync` is complete.</span></span>

## <a name="convert-startbutton_click-to-an-asynchronous-method"></a><span data-ttu-id="0f410-236">Convertir startButton_Click en un método asincrónico</span><span class="sxs-lookup"><span data-stu-id="0f410-236">Convert startButton_Click to an asynchronous method</span></span>

1. <span data-ttu-id="0f410-237">En el controlador de eventos, cambie el nombre del método llamado de `SumPageSizes` a `SumPageSizesAsync`, si aún no lo ha hecho.</span><span class="sxs-lookup"><span data-stu-id="0f410-237">In the event handler, change the name of the called method from `SumPageSizes` to `SumPageSizesAsync`, if you haven’t already done so.</span></span>

2. <span data-ttu-id="0f410-238">Dado que `SumPageSizesAsync` es un método asincrónico, cambie el código en el controlador de eventos para esperar el resultado.</span><span class="sxs-lookup"><span data-stu-id="0f410-238">Because `SumPageSizesAsync` is an async method, change the code in the event handler to await the result.</span></span>

    <span data-ttu-id="0f410-239">La llamada a `SumPageSizesAsync` refleja la llamada a `CopyToAsync` en `GetURLContentsAsync`.</span><span class="sxs-lookup"><span data-stu-id="0f410-239">The call to `SumPageSizesAsync` mirrors the call to `CopyToAsync` in `GetURLContentsAsync`.</span></span> <span data-ttu-id="0f410-240">La llamada devuelve `Task`, no `Task(T)`.</span><span class="sxs-lookup"><span data-stu-id="0f410-240">The call returns a `Task`, not a `Task(T)`.</span></span>

    <span data-ttu-id="0f410-241">Al igual que en los procedimientos anteriores, puede convertir la llamada usando una o dos instrucciones.</span><span class="sxs-lookup"><span data-stu-id="0f410-241">As in previous procedures, you can convert the call by using one statement or two statements.</span></span> <span data-ttu-id="0f410-242">En el código siguiente se muestran estos cambios.</span><span class="sxs-lookup"><span data-stu-id="0f410-242">The following code shows these changes.</span></span>

    ```vb
    ' One-step async call.
    Await SumPageSizesAsync()

    ' Two-step async call.
    Dim sumTask As Task = SumPageSizesAsync()
    Await sumTask
    ```

3. <span data-ttu-id="0f410-243">Para evitar volver a entrar accidentalmente en la operación, agregue la instrucción siguiente encima de `startButton_Click` para deshabilitar el botón **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="0f410-243">To prevent accidentally reentering the operation, add the following statement at the top of `startButton_Click` to disable the **Start** button.</span></span>

    ```vb
    ' Disable the button until the operation is complete.
    startButton.IsEnabled = False
    ```

    <span data-ttu-id="0f410-244">Puede volver a habilitar el botón al final del controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="0f410-244">You can reenable the button at the end of the event handler.</span></span>

    ```vb
    ' Reenable the button in case you want to run the operation again.
    startButton.IsEnabled = True
    ```

    <span data-ttu-id="0f410-245">Para obtener más información sobre la reentrada, consulte [control de la reentrada en aplicaciones asincrónicas (Visual Basic)](handling-reentrancy-in-async-apps.md).</span><span class="sxs-lookup"><span data-stu-id="0f410-245">For more information about reentrancy, see [Handling Reentrancy in Async Apps (Visual Basic)](handling-reentrancy-in-async-apps.md).</span></span>

4. <span data-ttu-id="0f410-246">Finalmente, agregue el modificador `Async` a la declaración de modo que el controlador de eventos pueda esperar `SumPagSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="0f410-246">Finally, add the `Async` modifier to the declaration so that the event handler can await `SumPagSizesAsync`.</span></span>

    ```vb
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click
    ```

    <span data-ttu-id="0f410-247">Normalmente, no se cambian los nombres de los controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="0f410-247">Typically, the names of event handlers aren’t changed.</span></span> <span data-ttu-id="0f410-248">El tipo de valor devuelto no se cambia a `Task` porque los controladores de eventos deben ser `Sub` procedimientos en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="0f410-248">The return type isn’t changed to `Task` because event handlers must be `Sub` procedures in Visual Basic.</span></span>

    <span data-ttu-id="0f410-249">Así se completa la conversión del proyecto de procesamiento sincrónico a asincrónico.</span><span class="sxs-lookup"><span data-stu-id="0f410-249">The conversion of the project from synchronous to asynchronous processing is complete.</span></span>

## <a name="test-the-asynchronous-solution"></a><span data-ttu-id="0f410-250">Probar la solución asincrónica</span><span class="sxs-lookup"><span data-stu-id="0f410-250">Test the asynchronous solution</span></span>

1. <span data-ttu-id="0f410-251">Presione la tecla F5 para ejecutar el programa y elija el botón **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="0f410-251">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>

2. <span data-ttu-id="0f410-252">Deberían aparecer resultados similares a los de la solución sincrónica.</span><span class="sxs-lookup"><span data-stu-id="0f410-252">Output that resembles the output of the synchronous solution should appear.</span></span> <span data-ttu-id="0f410-253">No obstante, debe tener en cuenta las siguientes diferencias.</span><span class="sxs-lookup"><span data-stu-id="0f410-253">However, notice the following differences.</span></span>

    - <span data-ttu-id="0f410-254">No todos los resultados se producen al mismo tiempo cuando se completa el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="0f410-254">The results don’t all occur at the same time, after the processing is complete.</span></span> <span data-ttu-id="0f410-255">Por ejemplo, ambos programas contienen una línea en `startButton_Click` que borra el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="0f410-255">For example, both programs contain a line in `startButton_Click` that clears the text box.</span></span> <span data-ttu-id="0f410-256">La intención es borrar el cuadro de texto entre ejecuciones si elige el botón **Inicio** por segunda vez, después de que haya aparecido un conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="0f410-256">The intent is to clear the text box between runs if you choose the **Start** button for a second time, after one set of results has appeared.</span></span> <span data-ttu-id="0f410-257">En la versión sincrónica, el cuadro de texto se borra antes de que aparezcan los recuentos por segunda vez, cuando se completen las descargas y el subproceso de interfaz de usuario esté libre para llevar a cabo otro trabajo.</span><span class="sxs-lookup"><span data-stu-id="0f410-257">In the synchronous version, the text box is cleared just before the counts appear for the second time, when the downloads are completed and the UI thread is free to do other work.</span></span> <span data-ttu-id="0f410-258">En la versión asincrónica, el cuadro de texto se borra inmediatamente después de que se elija el botón **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="0f410-258">In the asynchronous version, the text box clears immediately after you choose the **Start** button.</span></span>

    - <span data-ttu-id="0f410-259">Lo más importante es que el subproceso de interfaz de usuario no se bloquea durante las descargas.</span><span class="sxs-lookup"><span data-stu-id="0f410-259">Most importantly, the UI thread isn’t blocked during the downloads.</span></span> <span data-ttu-id="0f410-260">Puede mover o cambiar el tamaño de la ventana mientras se descargan, se cuentan y se muestran los recursos web.</span><span class="sxs-lookup"><span data-stu-id="0f410-260">You can move or resize the window while the web resources are being downloaded, counted, and displayed.</span></span> <span data-ttu-id="0f410-261">Si uno de los sitios web es lento o no responde, puede cancelar la operación eligiendo el botón **Cerrar** (la X en el campo de color rojo en la esquina superior derecha).</span><span class="sxs-lookup"><span data-stu-id="0f410-261">If one of the websites is slow or not responding, you can cancel the operation by choosing the **Close** button (the x in the red field in the upper-right corner).</span></span>

## <a name="replace-the-geturlcontentsasync-method-with-a-net-framework-method"></a><span data-ttu-id="0f410-262">Reemplazar el método GetURLContentsAsync por un método .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0f410-262">Replace the GetURLContentsAsync method with a .NET Framework method</span></span>

1. <span data-ttu-id="0f410-263">El .NET Framework proporciona muchos métodos asincrónicos que puede usar.</span><span class="sxs-lookup"><span data-stu-id="0f410-263">The .NET Framework provides many async methods that you can use.</span></span> <span data-ttu-id="0f410-264">Uno de ellos, el <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29?displayProperty=nameWithType> método, hace exactamente lo que necesita para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="0f410-264">One of them, the <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29?displayProperty=nameWithType> method, does just what you need for this walkthrough.</span></span> <span data-ttu-id="0f410-265">Se puede usar en lugar del método `GetURLContentsAsync` que creó en un procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="0f410-265">You can use it instead of the `GetURLContentsAsync` method that you created in an earlier procedure.</span></span>

    <span data-ttu-id="0f410-266">El primer paso es crear un <xref:System.Net.Http.HttpClient> objeto en el `SumPageSizesAsync` método.</span><span class="sxs-lookup"><span data-stu-id="0f410-266">The first step is to create an <xref:System.Net.Http.HttpClient> object in the `SumPageSizesAsync` method.</span></span> <span data-ttu-id="0f410-267">Agregue la siguiente declaración al principio del método.</span><span class="sxs-lookup"><span data-stu-id="0f410-267">Add the following declaration at the start of the method.</span></span>

    ```vb
    ' Declare an HttpClient object and increase the buffer size. The
    ' default buffer size is 65,536.
    Dim client As HttpClient =
        New HttpClient() With {.MaxResponseContentBufferSize = 1000000}
    ```

2. <span data-ttu-id="0f410-268">En `SumPageSizesAsync,` reemplace la llamada a su método `GetURLContentsAsync` con una llamada al método `HttpClient`.</span><span class="sxs-lookup"><span data-stu-id="0f410-268">In `SumPageSizesAsync,` replace the call to your `GetURLContentsAsync` method with a call to the `HttpClient` method.</span></span>

    ```vb
    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)
    ```

3. <span data-ttu-id="0f410-269">Quite o marque como comentario el método `GetURLContentsAsync` que escribió.</span><span class="sxs-lookup"><span data-stu-id="0f410-269">Remove or comment out the `GetURLContentsAsync` method that you wrote.</span></span>

4. <span data-ttu-id="0f410-270">Presione la tecla F5 para ejecutar el programa y elija el botón **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="0f410-270">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>

    <span data-ttu-id="0f410-271">El comportamiento de esta versión del proyecto debería coincidir con el comportamiento que se describe en el procedimiento "Para probar la solución asincrónica", pero con incluso menos trabajo por su parte.</span><span class="sxs-lookup"><span data-stu-id="0f410-271">The behavior of this version of the project should match the behavior that the "To test the asynchronous solution" procedure describes but with even less effort from you.</span></span>

## <a name="example"></a><span data-ttu-id="0f410-272">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0f410-272">Example</span></span>

<span data-ttu-id="0f410-273">El siguiente es el ejemplo completo de la solución asincrónica convertida que usa el método asincrónico `GetURLContentsAsync` .</span><span class="sxs-lookup"><span data-stu-id="0f410-273">The following is the full example of the converted asynchronous solution that uses the asynchronous `GetURLContentsAsync` method.</span></span> <span data-ttu-id="0f410-274">Observe que es muy parecida a la solución sincrónica original.</span><span class="sxs-lookup"><span data-stu-id="0f410-274">Notice that it strongly resembles the original, synchronous solution.</span></span>

```vb
' Add the following Imports statements, and add a reference for System.Net.Http.
Imports System.Net.Http
Imports System.Net
Imports System.IO

Class MainWindow

    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click

        ' Disable the button until the operation is complete.
        startButton.IsEnabled = False

        resultsTextBox.Clear()

        '' One-step async call.
        Await SumPageSizesAsync()

        ' Two-step async call.
        'Dim sumTask As Task = SumPageSizesAsync()
        'Await sumTask

        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."

        ' Reenable the button in case you want to run the operation again.
        startButton.IsEnabled = True
    End Sub

    Private Async Function SumPageSizesAsync() As Task

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        Dim total = 0
        For Each url In urlList
            Dim urlContents As Byte() = Await GetURLContentsAsync(url)

            ' The previous line abbreviates the following two assignment statements.

            '//<snippet21>
            ' GetURLContentsAsync returns a task. At completion, the task
            ' produces a byte array.
            'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)
            'Dim urlContents As Byte() = Await getContentsTask

            DisplayResults(url, urlContents)

            ' Update the total.
            total += urlContents.Length
        Next

        ' Display the total count for all of the websites.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
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
            }
        Return urls
    End Function

    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())

        ' The downloaded resource ends up in the variable named content.
        Dim content = New MemoryStream()

        ' Initialize an HttpWebRequest for the current URL.
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)

        ' Send the request to the Internet resource and wait for
        ' the response.
        Using response As WebResponse = Await webReq.GetResponseAsync()

            ' The previous statement abbreviates the following two statements.

            'Dim responseTask As Task(Of WebResponse) = webReq.GetResponseAsync()
            'Using response As WebResponse = Await responseTask

            ' Get the data stream that is associated with the specified URL.
            Using responseStream As Stream = response.GetResponseStream()
                ' Read the bytes in responseStream and copy them to content.
                Await responseStream.CopyToAsync(content)

                ' The previous statement abbreviates the following two statements.

                ' CopyToAsync returns a Task, not a Task<T>.
                'Dim copyTask As Task = responseStream.CopyToAsync(content)

                ' When copyTask is completed, content contains a copy of
                ' responseStream.
                'Await copyTask
            End Using
        End Using

        ' Return the result as a byte array.
        Return content.ToArray()
    End Function

    Private Sub DisplayResults(url As String, content As Byte())

        ' Display the length of each website. The string format
        ' is designed to be used with a monospaced font, such as
        ' Lucida Console or Global Monospace.
        Dim bytes = content.Length
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub

End Class
```

<span data-ttu-id="0f410-275">El código siguiente contiene el ejemplo completo de la solución que usa el método `HttpClient`, `GetByteArrayAsync`.</span><span class="sxs-lookup"><span data-stu-id="0f410-275">The following code contains the full example of the solution that uses the `HttpClient` method, `GetByteArrayAsync`.</span></span>

```vb
' Add the following Imports statements, and add a reference for System.Net.Http.
Imports System.Net.Http
Imports System.Net
Imports System.IO

Class MainWindow

    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click

        resultsTextBox.Clear()

        ' Disable the button until the operation is complete.
        startButton.IsEnabled = False

        ' One-step async call.
        Await SumPageSizesAsync()

        ' Two-step async call.
        'Dim sumTask As Task = SumPageSizesAsync()
        'Await sumTask

        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."

        ' Reenable the button in case you want to run the operation again.
        startButton.IsEnabled = True
    End Sub

    Private Async Function SumPageSizesAsync() As Task

        ' Declare an HttpClient object and increase the buffer size. The
        ' default buffer size is 65,536.
        Dim client As HttpClient =
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        Dim total = 0
        For Each url In urlList
            ' GetByteArrayAsync returns a task. At completion, the task
            ' produces a byte array.
            Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)

            ' The following two lines can replace the previous assignment statement.
            'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)
            'Dim urlContents As Byte() = Await getContentsTask

            DisplayResults(url, urlContents)

            ' Update the total.
            total += urlContents.Length
        Next

        ' Display the total count for all of the websites.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
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
            }
        Return urls
    End Function

    Private Sub DisplayResults(url As String, content As Byte())

        ' Display the length of each website. The string format
        ' is designed to be used with a monospaced font, such as
        ' Lucida Console or Global Monospace.
        Dim bytes = content.Length
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub

End Class
```

## <a name="see-also"></a><span data-ttu-id="0f410-276">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0f410-276">See also</span></span>

- <span data-ttu-id="0f410-277">[Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) (Muestra de Async: obtener acceso al tutorial web [C# y Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="0f410-277">[Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f)</span></span>
- [<span data-ttu-id="0f410-278">Await (operador)</span><span class="sxs-lookup"><span data-stu-id="0f410-278">Await Operator</span></span>](../../../language-reference/operators/await-operator.md)
- [<span data-ttu-id="0f410-279">Asincrónica</span><span class="sxs-lookup"><span data-stu-id="0f410-279">Async</span></span>](../../../language-reference/modifiers/async.md)
- [<span data-ttu-id="0f410-280">Programación asincrónica con Async y Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f410-280">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](index.md)
- <span data-ttu-id="0f410-281">[Async Return Types (Visual Basic)](async-return-types.md) (Tipos de valor devuelto de Async [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="0f410-281">[Async Return Types (Visual Basic)](async-return-types.md)</span></span>
- <span data-ttu-id="0f410-282">[Task-based Asynchronous Programming (TAP) (Programación asincrónica basada en tareas [TAP])](https://www.microsoft.com/download/details.aspx?id=19957)</span><span class="sxs-lookup"><span data-stu-id="0f410-282">[Task-based Asynchronous Programming (TAP)](https://www.microsoft.com/download/details.aspx?id=19957)</span></span>
- <span data-ttu-id="0f410-283">[How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md) (Ampliación del tutorial de Async mediante Task.WhenAll [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="0f410-283">[How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md)</span></span>
- <span data-ttu-id="0f410-284">[How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)](how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) (Realización de solicitudes web en paralelo mediante Async y Await [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="0f410-284">[How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)](how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)</span></span>
