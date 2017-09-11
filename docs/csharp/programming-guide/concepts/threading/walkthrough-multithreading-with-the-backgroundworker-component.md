---
title: 'Tutorial: Multithreading con el componente BackgroundWorker (C#)'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: ff670fbf-a0ac-40c1-ab08-9ed53768f880
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 541a1ec788c337eea9965b8a46155e5c6606ea2f
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-c"></a><span data-ttu-id="1e73a-102">Tutorial: Multithreading con el componente BackgroundWorker (C#)</span><span class="sxs-lookup"><span data-stu-id="1e73a-102">Walkthrough: Multithreading with the BackgroundWorker Component (C#)</span></span>
<span data-ttu-id="1e73a-103">Este tutorial muestra cómo crear una aplicación multiproceso de Windows Forms que busque las repeticiones de una palabra en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="1e73a-103">This walkthrough demonstrates how to create a multithreaded Windows Forms application that searches a text file for occurrences of a word.</span></span> <span data-ttu-id="1e73a-104">Muestra cómo:</span><span class="sxs-lookup"><span data-stu-id="1e73a-104">It demonstrates:</span></span>  
  
-   <span data-ttu-id="1e73a-105">Definir una clase con un método que puede llamarse mediante el componente <xref:System.ComponentModel.BackgroundWorker>.</span><span class="sxs-lookup"><span data-stu-id="1e73a-105">Defining a class with a method that can be called by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="1e73a-106">Controlar eventos que se han generado mediante el componente <xref:System.ComponentModel.BackgroundWorker>.</span><span class="sxs-lookup"><span data-stu-id="1e73a-106">Handling events raised by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="1e73a-107">Iniciar un componente <xref:System.ComponentModel.BackgroundWorker> para ejecutar un método.</span><span class="sxs-lookup"><span data-stu-id="1e73a-107">Starting a <xref:System.ComponentModel.BackgroundWorker> component to run a method.</span></span>  
  
-   <span data-ttu-id="1e73a-108">Implementar un botón `Cancel` que detenga el componente <xref:System.ComponentModel.BackgroundWorker>.</span><span class="sxs-lookup"><span data-stu-id="1e73a-108">Implementing a `Cancel` button that stops the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
### <a name="to-create-the-user-interface"></a><span data-ttu-id="1e73a-109">Para crear la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="1e73a-109">To create the user interface</span></span>  
  
1.  <span data-ttu-id="1e73a-110">Abra un nuevo proyecto de aplicación de Windows Forms en C# y cree un formulario denominado `Form1`.</span><span class="sxs-lookup"><span data-stu-id="1e73a-110">Open a new C# Windows Forms Application project, and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="1e73a-111">Agregue dos botones y cuatro cuadros de texto a `Form1`.</span><span class="sxs-lookup"><span data-stu-id="1e73a-111">Add two buttons and four text boxes to `Form1`.</span></span>  
  
3.  <span data-ttu-id="1e73a-112">Asigne nombre a los objetos tal y como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="1e73a-112">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="1e73a-113">Objeto</span><span class="sxs-lookup"><span data-stu-id="1e73a-113">Object</span></span>|<span data-ttu-id="1e73a-114">Propiedad</span><span class="sxs-lookup"><span data-stu-id="1e73a-114">Property</span></span>|<span data-ttu-id="1e73a-115">Parámetro</span><span class="sxs-lookup"><span data-stu-id="1e73a-115">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="1e73a-116">Primer botón</span><span class="sxs-lookup"><span data-stu-id="1e73a-116">First button</span></span>|<span data-ttu-id="1e73a-117">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="1e73a-117">`Name`, `Text`</span></span>|<span data-ttu-id="1e73a-118">Iniciar, Iniciar</span><span class="sxs-lookup"><span data-stu-id="1e73a-118">Start, Start</span></span>|  
    |<span data-ttu-id="1e73a-119">Segundo botón</span><span class="sxs-lookup"><span data-stu-id="1e73a-119">Second button</span></span>|<span data-ttu-id="1e73a-120">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="1e73a-120">`Name`, `Text`</span></span>|<span data-ttu-id="1e73a-121">Cancelar, Cancelar</span><span class="sxs-lookup"><span data-stu-id="1e73a-121">Cancel, Cancel</span></span>|  
    |<span data-ttu-id="1e73a-122">Primer cuadro de texto</span><span class="sxs-lookup"><span data-stu-id="1e73a-122">First text box</span></span>|<span data-ttu-id="1e73a-123">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="1e73a-123">`Name`, `Text`</span></span>|<span data-ttu-id="1e73a-124">SourceFile, ""</span><span class="sxs-lookup"><span data-stu-id="1e73a-124">SourceFile, ""</span></span>|  
    |<span data-ttu-id="1e73a-125">Segundo cuadro de texto</span><span class="sxs-lookup"><span data-stu-id="1e73a-125">Second text box</span></span>|<span data-ttu-id="1e73a-126">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="1e73a-126">`Name`, `Text`</span></span>|<span data-ttu-id="1e73a-127">CompareString, ""</span><span class="sxs-lookup"><span data-stu-id="1e73a-127">CompareString, ""</span></span>|  
    |<span data-ttu-id="1e73a-128">Tercer cuadro de texto</span><span class="sxs-lookup"><span data-stu-id="1e73a-128">Third text box</span></span>|<span data-ttu-id="1e73a-129">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="1e73a-129">`Name`, `Text`</span></span>|<span data-ttu-id="1e73a-130">WordsCounted, "0"</span><span class="sxs-lookup"><span data-stu-id="1e73a-130">WordsCounted, "0"</span></span>|  
    |<span data-ttu-id="1e73a-131">Cuarto cuadro de texto</span><span class="sxs-lookup"><span data-stu-id="1e73a-131">Fourth text box</span></span>|<span data-ttu-id="1e73a-132">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="1e73a-132">`Name`, `Text`</span></span>|<span data-ttu-id="1e73a-133">LinesCounted, "0"</span><span class="sxs-lookup"><span data-stu-id="1e73a-133">LinesCounted, "0"</span></span>|  
  
4.  <span data-ttu-id="1e73a-134">Agregue una etiqueta junto a cada cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="1e73a-134">Add a label next to each text box.</span></span> <span data-ttu-id="1e73a-135">Establezca la propiedad `Text` para cada etiqueta tal y como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="1e73a-135">Set the `Text` property for each label as shown in the following table.</span></span>  
  
    |<span data-ttu-id="1e73a-136">Objeto</span><span class="sxs-lookup"><span data-stu-id="1e73a-136">Object</span></span>|<span data-ttu-id="1e73a-137">Propiedad</span><span class="sxs-lookup"><span data-stu-id="1e73a-137">Property</span></span>|<span data-ttu-id="1e73a-138">Parámetro</span><span class="sxs-lookup"><span data-stu-id="1e73a-138">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="1e73a-139">Primera etiqueta</span><span class="sxs-lookup"><span data-stu-id="1e73a-139">First label</span></span>|`Text`|<span data-ttu-id="1e73a-140">Archivo de código fuente</span><span class="sxs-lookup"><span data-stu-id="1e73a-140">Source File</span></span>|  
    |<span data-ttu-id="1e73a-141">Segunda etiqueta</span><span class="sxs-lookup"><span data-stu-id="1e73a-141">Second label</span></span>|`Text`|<span data-ttu-id="1e73a-142">Cadena de comparación</span><span class="sxs-lookup"><span data-stu-id="1e73a-142">Compare String</span></span>|  
    |<span data-ttu-id="1e73a-143">Tercer etiqueta</span><span class="sxs-lookup"><span data-stu-id="1e73a-143">Third label</span></span>|`Text`|<span data-ttu-id="1e73a-144">Palabras coincidentes</span><span class="sxs-lookup"><span data-stu-id="1e73a-144">Matching Words</span></span>|  
    |<span data-ttu-id="1e73a-145">Cuarta etiqueta</span><span class="sxs-lookup"><span data-stu-id="1e73a-145">Fourth label</span></span>|`Text`|<span data-ttu-id="1e73a-146">Recuento de líneas</span><span class="sxs-lookup"><span data-stu-id="1e73a-146">Lines Counted</span></span>|  
  
### <a name="to-create-a-backgroundworker-component-and-subscribe-to-its-events"></a><span data-ttu-id="1e73a-147">Para crear un componente BackgroundWorker y suscribirse a sus eventos</span><span class="sxs-lookup"><span data-stu-id="1e73a-147">To create a BackgroundWorker component and subscribe to its events</span></span>  
  
1.  <span data-ttu-id="1e73a-148">Agregue un componente <xref:System.ComponentModel.BackgroundWorker> desde la sección **Componentes** del **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="1e73a-148">Add a <xref:System.ComponentModel.BackgroundWorker> component from the **Components** section of the **ToolBox** to the form.</span></span> <span data-ttu-id="1e73a-149">Aparecerá en la bandeja de componentes del formulario.</span><span class="sxs-lookup"><span data-stu-id="1e73a-149">It will appear in the form's component tray.</span></span>  
  
2.  <span data-ttu-id="1e73a-150">Establezca las siguientes propiedades para el objeto backgroundWorker1.</span><span class="sxs-lookup"><span data-stu-id="1e73a-150">Set the following properties for the backgroundWorker1 object.</span></span>  
  
    |<span data-ttu-id="1e73a-151">Propiedad</span><span class="sxs-lookup"><span data-stu-id="1e73a-151">Property</span></span>|<span data-ttu-id="1e73a-152">Configuración</span><span class="sxs-lookup"><span data-stu-id="1e73a-152">Setting</span></span>|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|<span data-ttu-id="1e73a-153">True</span><span class="sxs-lookup"><span data-stu-id="1e73a-153">True</span></span>|  
    |`WorkerSupportsCancellation`|<span data-ttu-id="1e73a-154">True</span><span class="sxs-lookup"><span data-stu-id="1e73a-154">True</span></span>|  
  
3.  <span data-ttu-id="1e73a-155">Suscríbase a los eventos del objeto backgroundWorker1.</span><span class="sxs-lookup"><span data-stu-id="1e73a-155">Subscribe to the events of the backgroundWorker1 object.</span></span> <span data-ttu-id="1e73a-156">En la parte superior de la ventana **Propiedades**, haga clic en el icono **Eventos**.</span><span class="sxs-lookup"><span data-stu-id="1e73a-156">At the top of the **Properties** window, click the **Events** icon.</span></span> <span data-ttu-id="1e73a-157">Haga doble clic en el evento `RunWorkerCompleted` para crear un método del controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="1e73a-157">Double-click the `RunWorkerCompleted` event to create an event handler method.</span></span> <span data-ttu-id="1e73a-158">Haga lo mismo para los eventos `ProgressChanged` y `DoWork`.</span><span class="sxs-lookup"><span data-stu-id="1e73a-158">Do the same for the `ProgressChanged` and `DoWork` events.</span></span>  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a><span data-ttu-id="1e73a-159">Para definir el método que se ejecutará en un subproceso independiente</span><span class="sxs-lookup"><span data-stu-id="1e73a-159">To define the method that will run on a separate thread</span></span>  
  
1.  <span data-ttu-id="1e73a-160">En el menú **Proyecto**, elija **Agregar clase** para agregar una clase al proyecto.</span><span class="sxs-lookup"><span data-stu-id="1e73a-160">From the **Project** menu, choose **Add Class** to add a class to the project.</span></span> <span data-ttu-id="1e73a-161">Se abrirá el cuadro de diálogo **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="1e73a-161">The **Add New Item** dialog box is displayed.</span></span>  
  
2.  <span data-ttu-id="1e73a-162">Seleccione **Clase** en la ventana de plantillas y escriba `Words.cs` en el campo de nombre.</span><span class="sxs-lookup"><span data-stu-id="1e73a-162">Select **Class** from the templates window and enter `Words.cs` in the name field.</span></span>  
  
3.  <span data-ttu-id="1e73a-163">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1e73a-163">Click **Add**.</span></span> <span data-ttu-id="1e73a-164">Se mostrará la clase `Words`.</span><span class="sxs-lookup"><span data-stu-id="1e73a-164">The `Words` class is displayed.</span></span>  
  
4.  <span data-ttu-id="1e73a-165">Agregue el código siguiente a la clase `Words`:</span><span class="sxs-lookup"><span data-stu-id="1e73a-165">Add the following code to the `Words` class:</span></span>  
  
    ```csharp  
    public class Words  
    {  
        // Object to store the current state, for passing to the caller.  
        public class CurrentState  
        {  
            public int LinesCounted;  
            public int WordsMatched;  
        }  
  
        public string SourceFile;  
        public string CompareString;  
        private int WordCount;  
        private int LinesCounted;  
  
        public void CountWords(  
            System.ComponentModel.BackgroundWorker worker,  
            System.ComponentModel.DoWorkEventArgs e)  
        {  
            // Initialize the variables.  
            CurrentState state = new CurrentState();  
            string line = "";  
            int elapsedTime = 20;  
            DateTime lastReportDateTime = DateTime.Now;  
  
            if (CompareString == null ||  
                CompareString == System.String.Empty)  
            {  
                throw new Exception("CompareString not specified.");  
            }  
  
            // Open a new stream.  
            using (System.IO.StreamReader myStream = new System.IO.StreamReader(SourceFile))  
            {  
                // Process lines while there are lines remaining in the file.  
                while (!myStream.EndOfStream)  
                {  
                    if (worker.CancellationPending)  
                    {  
                        e.Cancel = true;  
                        break;  
                    }  
                    else  
                    {  
                        line = myStream.ReadLine();  
                        WordCount += CountInString(line, CompareString);  
                        LinesCounted += 1;  
  
                        // Raise an event so the form can monitor progress.  
                        int compare = DateTime.Compare(  
                            DateTime.Now, lastReportDateTime.AddMilliseconds(elapsedTime));  
                        if (compare > 0)  
                        {  
                            state.LinesCounted = LinesCounted;  
                            state.WordsMatched = WordCount;  
                            worker.ReportProgress(0, state);  
                            lastReportDateTime = DateTime.Now;  
                        }  
                    }  
                    // Uncomment for testing.  
                    //System.Threading.Thread.Sleep(5);  
                }  
  
                // Report the final count values.  
                state.LinesCounted = LinesCounted;  
                state.WordsMatched = WordCount;  
                worker.ReportProgress(0, state);  
            }  
        }  
  
        private int CountInString(  
            string SourceString,  
            string CompareString)  
        {  
            // This function counts the number of times  
            // a word is found in a line.  
            if (SourceString == null)  
            {  
                return 0;  
            }  
  
            string EscapedCompareString =  
                System.Text.RegularExpressions.Regex.Escape(CompareString);  
  
            System.Text.RegularExpressions.Regex regex;  
            regex = new System.Text.RegularExpressions.Regex(   
                // To count all occurrences of the string, even within words, remove  
                // both instances of @"\b" from the following line.  
                @"\b" + EscapedCompareString + @"\b",  
                System.Text.RegularExpressions.RegexOptions.IgnoreCase);  
  
            System.Text.RegularExpressions.MatchCollection matches;  
            matches = regex.Matches(SourceString);  
            return matches.Count;  
        }  
  
    }  
    ```  
  
### <a name="to-handle-events-from-the-thread"></a><span data-ttu-id="1e73a-166">Para controlar eventos del subproceso</span><span class="sxs-lookup"><span data-stu-id="1e73a-166">To handle events from the thread</span></span>  
  
-   <span data-ttu-id="1e73a-167">Agregue los controladores de eventos siguientes al formulario principal:</span><span class="sxs-lookup"><span data-stu-id="1e73a-167">Add the following event handlers to your main form:</span></span>  
  
    ```csharp  
    private void backgroundWorker1_RunWorkerCompleted(object sender, RunWorkerCompletedEventArgs e)  
    {  
    // This event handler is called when the background thread finishes.  
    // This method runs on the main thread.  
    if (e.Error != null)  
        MessageBox.Show("Error: " + e.Error.Message);  
    else if (e.Cancelled)  
        MessageBox.Show("Word counting canceled.");  
    else  
        MessageBox.Show("Finished counting words.");  
    }  
  
    private void backgroundWorker1_ProgressChanged(object sender, ProgressChangedEventArgs e)  
    {  
        // This method runs on the main thread.  
        Words.CurrentState state =  
            (Words.CurrentState)e.UserState;  
        this.LinesCounted.Text = state.LinesCounted.ToString();  
        this.WordsCounted.Text = state.WordsMatched.ToString();  
    }  
    ```  
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a><span data-ttu-id="1e73a-168">Para iniciar un nuevo subproceso que ejecute el método WordCount y llamarlo</span><span class="sxs-lookup"><span data-stu-id="1e73a-168">To start and call a new thread that runs the WordCount method</span></span>  
  
1.  <span data-ttu-id="1e73a-169">Agregue los procedimientos siguientes al programa:</span><span class="sxs-lookup"><span data-stu-id="1e73a-169">Add the following procedures to your program:</span></span>  
  
    ```csharp  
    private void backgroundWorker1_DoWork(object sender, DoWorkEventArgs e)  
    {  
        // This event handler is where the actual work is done.  
        // This method runs on the background thread.  
  
        // Get the BackgroundWorker object that raised this event.  
        System.ComponentModel.BackgroundWorker worker;  
        worker = (System.ComponentModel.BackgroundWorker)sender;  
  
        // Get the Words object and call the main method.  
        Words WC = (Words)e.Argument;  
        WC.CountWords(worker, e);  
    }  
  
    private void StartThread()  
    {  
        // This method runs on the main thread.  
        this.WordsCounted.Text = "0";  
  
        // Initialize the object that the background worker calls.  
        Words WC = new Words();  
        WC.CompareString = this.CompareString.Text;  
        WC.SourceFile = this.SourceFile.Text;  
  
        // Start the asynchronous operation.  
        backgroundWorker1.RunWorkerAsync(WC);  
    }  
    ```  
  
2.  <span data-ttu-id="1e73a-170">Llame al método `StartThread` desde el botón `Start` del formulario:</span><span class="sxs-lookup"><span data-stu-id="1e73a-170">Call the `StartThread` method from the `Start` button on your form:</span></span>  
  
    ```csharp  
    private void Start_Click(object sender, EventArgs e)  
    {  
        StartThread();  
    }  
    ```  
  
    ##### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a><span data-ttu-id="1e73a-171">Para implementar un botón Cancelar que detenga el subproceso</span><span class="sxs-lookup"><span data-stu-id="1e73a-171">To implement a Cancel button that stops the thread</span></span>  
  
    -   <span data-ttu-id="1e73a-172">Llame al procedimiento `StopThread` desde el controlador de eventos `Click` para el botón `Cancel`.</span><span class="sxs-lookup"><span data-stu-id="1e73a-172">Call the `StopThread` procedure from the `Click` event handler for the `Cancel` button.</span></span>  
  
        ```csharp  
        private void Cancel_Click(object sender, EventArgs e)  
        {  
            // Cancel the asynchronous operation.  
            this.backgroundWorker1.CancelAsync();  
        }  
        ```  
  
## <a name="testing"></a><span data-ttu-id="1e73a-173">Pruebas</span><span class="sxs-lookup"><span data-stu-id="1e73a-173">Testing</span></span>  
 <span data-ttu-id="1e73a-174">Ahora puede probar la aplicación para asegurarse de que funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="1e73a-174">You can now test the application to make sure it works correctly.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="1e73a-175">Para probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="1e73a-175">To test the application</span></span>  
  
1.  <span data-ttu-id="1e73a-176">Presione F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1e73a-176">Press F5 to run the application.</span></span>  
  
2.  <span data-ttu-id="1e73a-177">Cuando aparezca el formulario, escriba la ruta de acceso del archivo que quiera probar en el cuadro `sourceFile`.</span><span class="sxs-lookup"><span data-stu-id="1e73a-177">When the form is displayed, enter the file path for the file you want to test in the `sourceFile` box.</span></span> <span data-ttu-id="1e73a-178">Por ejemplo, supongamos que el archivo de prueba se denomina Test.txt, escriba C:\Test.txt.</span><span class="sxs-lookup"><span data-stu-id="1e73a-178">For example, assuming your test file is named Test.txt, enter C:\Test.txt.</span></span>  
  
3.  <span data-ttu-id="1e73a-179">En el segundo cuadro de texto, escriba una palabra o frase para que la aplicación la busque en el archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="1e73a-179">In the second text box, enter a word or phrase for the application to search for in the text file.</span></span>  
  
4.  <span data-ttu-id="1e73a-180">Haga clic en el botón `Start`.</span><span class="sxs-lookup"><span data-stu-id="1e73a-180">Click the `Start` button.</span></span> <span data-ttu-id="1e73a-181">El botón `LinesCounted` debe empezar a aumentar inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="1e73a-181">The `LinesCounted` button should begin incrementing immediately.</span></span> <span data-ttu-id="1e73a-182">La aplicación mostrará el mensaje "Finished Counting" (Recuento finalizado) cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="1e73a-182">The application displays the message "Finished Counting" when it is done.</span></span>  
  
#### <a name="to-test-the-cancel-button"></a><span data-ttu-id="1e73a-183">Para probar el botón Cancelar</span><span class="sxs-lookup"><span data-stu-id="1e73a-183">To test the Cancel button</span></span>  
  
1.  <span data-ttu-id="1e73a-184">Pulse F5 para iniciar la aplicación y escriba el nombre de archivo y la palabra de búsqueda tal y como se ha descrito en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="1e73a-184">Press F5 to start the application, and enter the file name and search word as described in the previous procedure.</span></span> <span data-ttu-id="1e73a-185">Asegúrese de que el archivo que elija es lo bastante grande como para que le dé tiempo a cancelar el procedimiento antes de que finalice.</span><span class="sxs-lookup"><span data-stu-id="1e73a-185">Make sure that the file you choose is large enough to ensure you will have time to cancel the procedure before it is finished.</span></span>  
  
2.  <span data-ttu-id="1e73a-186">Haga clic en el botón `Start` para iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1e73a-186">Click the `Start` button to start the application.</span></span>  
  
3.  <span data-ttu-id="1e73a-187">Haga clic en el botón `Cancel`.</span><span class="sxs-lookup"><span data-stu-id="1e73a-187">Click the `Cancel` button.</span></span> <span data-ttu-id="1e73a-188">La aplicación debe detener el recuento inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="1e73a-188">The application should stop counting immediately.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="1e73a-189">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="1e73a-189">Next Steps</span></span>  
 <span data-ttu-id="1e73a-190">Esta aplicación contiene un control de errores básico.</span><span class="sxs-lookup"><span data-stu-id="1e73a-190">This application contains some basic error handling.</span></span> <span data-ttu-id="1e73a-191">Detecta cadenas de búsqueda en blanco.</span><span class="sxs-lookup"><span data-stu-id="1e73a-191">It detects blank search strings.</span></span> <span data-ttu-id="1e73a-192">Puede hacer que el programa sea más sólido mediante el control de otros errores, como, por ejemplo, que se supere el número máximo de palabras o líneas que se pueden contar.</span><span class="sxs-lookup"><span data-stu-id="1e73a-192">You can make this program more robust by handling other errors, such as exceeding the maximum number of words or lines that can be counted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e73a-193">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e73a-193">See Also</span></span>  
 <span data-ttu-id="1e73a-194">[Threading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md)  (Subprocesos [C#])</span><span class="sxs-lookup"><span data-stu-id="1e73a-194">[Threading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md) </span></span>  
 [<span data-ttu-id="1e73a-195">Cómo: Suscribir y cancelar la suscripción a eventos</span><span class="sxs-lookup"><span data-stu-id="1e73a-195">How to: Subscribe to and Unsubscribe from Events</span></span>](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)

