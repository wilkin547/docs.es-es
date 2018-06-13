---
title: Multithreading con el componente BackgroundWorker (Visual Basic)
ms.date: 07/20/2015
ms.assetid: e4cd9b2a-f924-470e-a16e-50274709b40e
ms.openlocfilehash: 07700aa526866729f1ba1a8d846f22ce333c356d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654296"
---
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-visual-basic"></a><span data-ttu-id="6f771-102">Tutorial: Multithreading con el componente BackgroundWorker (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f771-102">Walkthrough: Multithreading with the BackgroundWorker Component (Visual Basic)</span></span>
<span data-ttu-id="6f771-103">Este tutorial muestra cómo crear una aplicación multiproceso de Windows Forms que busque las repeticiones de una palabra en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="6f771-103">This walkthrough demonstrates how to create a multithreaded Windows Forms application that searches a text file for occurrences of a word.</span></span> <span data-ttu-id="6f771-104">Muestra cómo:</span><span class="sxs-lookup"><span data-stu-id="6f771-104">It demonstrates:</span></span>  
  
-   <span data-ttu-id="6f771-105">Definir una clase con un método que puede llamarse mediante el componente <xref:System.ComponentModel.BackgroundWorker>.</span><span class="sxs-lookup"><span data-stu-id="6f771-105">Defining a class with a method that can be called by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="6f771-106">Controlar eventos que se han generado mediante el componente <xref:System.ComponentModel.BackgroundWorker>.</span><span class="sxs-lookup"><span data-stu-id="6f771-106">Handling events raised by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="6f771-107">Iniciar un componente <xref:System.ComponentModel.BackgroundWorker> para ejecutar un método.</span><span class="sxs-lookup"><span data-stu-id="6f771-107">Starting a <xref:System.ComponentModel.BackgroundWorker> component to run a method.</span></span>  
  
-   <span data-ttu-id="6f771-108">Implementar un botón `Cancel` que detenga el componente <xref:System.ComponentModel.BackgroundWorker>.</span><span class="sxs-lookup"><span data-stu-id="6f771-108">Implementing a `Cancel` button that stops the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
### <a name="to-create-the-user-interface"></a><span data-ttu-id="6f771-109">Para crear la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="6f771-109">To create the user interface</span></span>  
  
1.  <span data-ttu-id="6f771-110">Abra un nuevo proyecto de aplicación de Windows Forms de Visual Basic y cree un formulario denominado `Form1`.</span><span class="sxs-lookup"><span data-stu-id="6f771-110">Open a new Visual Basic Windows Forms Application project, and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="6f771-111">Agregue dos botones y cuatro cuadros de texto a `Form1`.</span><span class="sxs-lookup"><span data-stu-id="6f771-111">Add two buttons and four text boxes to `Form1`.</span></span>  
  
3.  <span data-ttu-id="6f771-112">Asigne nombre a los objetos tal y como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="6f771-112">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="6f771-113">Objeto</span><span class="sxs-lookup"><span data-stu-id="6f771-113">Object</span></span>|<span data-ttu-id="6f771-114">Property</span><span class="sxs-lookup"><span data-stu-id="6f771-114">Property</span></span>|<span data-ttu-id="6f771-115">Parámetro</span><span class="sxs-lookup"><span data-stu-id="6f771-115">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="6f771-116">Primer botón</span><span class="sxs-lookup"><span data-stu-id="6f771-116">First button</span></span>|<span data-ttu-id="6f771-117">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="6f771-117">`Name`, `Text`</span></span>|<span data-ttu-id="6f771-118">Iniciar, Iniciar</span><span class="sxs-lookup"><span data-stu-id="6f771-118">Start, Start</span></span>|  
    |<span data-ttu-id="6f771-119">Segundo botón</span><span class="sxs-lookup"><span data-stu-id="6f771-119">Second button</span></span>|<span data-ttu-id="6f771-120">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="6f771-120">`Name`, `Text`</span></span>|<span data-ttu-id="6f771-121">Cancelar, Cancelar</span><span class="sxs-lookup"><span data-stu-id="6f771-121">Cancel, Cancel</span></span>|  
    |<span data-ttu-id="6f771-122">Primer cuadro de texto</span><span class="sxs-lookup"><span data-stu-id="6f771-122">First text box</span></span>|<span data-ttu-id="6f771-123">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="6f771-123">`Name`, `Text`</span></span>|<span data-ttu-id="6f771-124">SourceFile, ""</span><span class="sxs-lookup"><span data-stu-id="6f771-124">SourceFile, ""</span></span>|  
    |<span data-ttu-id="6f771-125">Segundo cuadro de texto</span><span class="sxs-lookup"><span data-stu-id="6f771-125">Second text box</span></span>|<span data-ttu-id="6f771-126">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="6f771-126">`Name`, `Text`</span></span>|<span data-ttu-id="6f771-127">CompareString, ""</span><span class="sxs-lookup"><span data-stu-id="6f771-127">CompareString, ""</span></span>|  
    |<span data-ttu-id="6f771-128">Tercer cuadro de texto</span><span class="sxs-lookup"><span data-stu-id="6f771-128">Third text box</span></span>|<span data-ttu-id="6f771-129">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="6f771-129">`Name`, `Text`</span></span>|<span data-ttu-id="6f771-130">WordsCounted, "0"</span><span class="sxs-lookup"><span data-stu-id="6f771-130">WordsCounted, "0"</span></span>|  
    |<span data-ttu-id="6f771-131">Cuarto cuadro de texto</span><span class="sxs-lookup"><span data-stu-id="6f771-131">Fourth text box</span></span>|<span data-ttu-id="6f771-132">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="6f771-132">`Name`, `Text`</span></span>|<span data-ttu-id="6f771-133">LinesCounted, "0"</span><span class="sxs-lookup"><span data-stu-id="6f771-133">LinesCounted, "0"</span></span>|  
  
4.  <span data-ttu-id="6f771-134">Agregue una etiqueta junto a cada cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="6f771-134">Add a label next to each text box.</span></span> <span data-ttu-id="6f771-135">Establezca la propiedad `Text` para cada etiqueta tal y como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="6f771-135">Set the `Text` property for each label as shown in the following table.</span></span>  
  
    |<span data-ttu-id="6f771-136">Object</span><span class="sxs-lookup"><span data-stu-id="6f771-136">Object</span></span>|<span data-ttu-id="6f771-137">Property</span><span class="sxs-lookup"><span data-stu-id="6f771-137">Property</span></span>|<span data-ttu-id="6f771-138">Parámetro</span><span class="sxs-lookup"><span data-stu-id="6f771-138">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="6f771-139">Primera etiqueta</span><span class="sxs-lookup"><span data-stu-id="6f771-139">First label</span></span>|`Text`|<span data-ttu-id="6f771-140">Archivo de código fuente</span><span class="sxs-lookup"><span data-stu-id="6f771-140">Source File</span></span>|  
    |<span data-ttu-id="6f771-141">Segunda etiqueta</span><span class="sxs-lookup"><span data-stu-id="6f771-141">Second label</span></span>|`Text`|<span data-ttu-id="6f771-142">Cadena de comparación</span><span class="sxs-lookup"><span data-stu-id="6f771-142">Compare String</span></span>|  
    |<span data-ttu-id="6f771-143">Tercer etiqueta</span><span class="sxs-lookup"><span data-stu-id="6f771-143">Third label</span></span>|`Text`|<span data-ttu-id="6f771-144">Palabras coincidentes</span><span class="sxs-lookup"><span data-stu-id="6f771-144">Matching Words</span></span>|  
    |<span data-ttu-id="6f771-145">Cuarta etiqueta</span><span class="sxs-lookup"><span data-stu-id="6f771-145">Fourth label</span></span>|`Text`|<span data-ttu-id="6f771-146">Recuento de líneas</span><span class="sxs-lookup"><span data-stu-id="6f771-146">Lines Counted</span></span>|  
  
### <a name="to-create-a-backgroundworker-component-and-subscribe-to-its-events"></a><span data-ttu-id="6f771-147">Para crear un componente BackgroundWorker y suscribirse a sus eventos</span><span class="sxs-lookup"><span data-stu-id="6f771-147">To create a BackgroundWorker component and subscribe to its events</span></span>  
  
1.  <span data-ttu-id="6f771-148">Agregue un componente <xref:System.ComponentModel.BackgroundWorker> desde la sección **Componentes** del **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="6f771-148">Add a <xref:System.ComponentModel.BackgroundWorker> component from the **Components** section of the **ToolBox** to the form.</span></span> <span data-ttu-id="6f771-149">Aparecerá en la bandeja de componentes del formulario.</span><span class="sxs-lookup"><span data-stu-id="6f771-149">It will appear in the form's component tray.</span></span>  
  
2.  <span data-ttu-id="6f771-150">Establezca las siguientes propiedades del objeto BackgroundWorker1.</span><span class="sxs-lookup"><span data-stu-id="6f771-150">Set the following properties for the BackgroundWorker1 object.</span></span>  
  
    |<span data-ttu-id="6f771-151">Property</span><span class="sxs-lookup"><span data-stu-id="6f771-151">Property</span></span>|<span data-ttu-id="6f771-152">Configuración</span><span class="sxs-lookup"><span data-stu-id="6f771-152">Setting</span></span>|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|<span data-ttu-id="6f771-153">True</span><span class="sxs-lookup"><span data-stu-id="6f771-153">True</span></span>|  
    |`WorkerSupportsCancellation`|<span data-ttu-id="6f771-154">True</span><span class="sxs-lookup"><span data-stu-id="6f771-154">True</span></span>|  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a><span data-ttu-id="6f771-155">Para definir el método que se ejecutará en un subproceso independiente</span><span class="sxs-lookup"><span data-stu-id="6f771-155">To define the method that will run on a separate thread</span></span>  
  
1.  <span data-ttu-id="6f771-156">En el menú **Proyecto**, elija **Agregar clase** para agregar una clase al proyecto.</span><span class="sxs-lookup"><span data-stu-id="6f771-156">From the **Project** menu, choose **Add Class** to add a class to the project.</span></span> <span data-ttu-id="6f771-157">Se abrirá el cuadro de diálogo **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="6f771-157">The **Add New Item** dialog box is displayed.</span></span>  
  
2.  <span data-ttu-id="6f771-158">Seleccione **Clase** en la ventana de plantillas y escriba `Words.vb` en el campo de nombre.</span><span class="sxs-lookup"><span data-stu-id="6f771-158">Select **Class** from the templates window and enter `Words.vb` in the name field.</span></span>  
  
3.  <span data-ttu-id="6f771-159">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6f771-159">Click **Add**.</span></span> <span data-ttu-id="6f771-160">Se mostrará la clase `Words`.</span><span class="sxs-lookup"><span data-stu-id="6f771-160">The `Words` class is displayed.</span></span>  
  
4.  <span data-ttu-id="6f771-161">Agregue el código siguiente a la clase `Words`:</span><span class="sxs-lookup"><span data-stu-id="6f771-161">Add the following code to the `Words` class:</span></span>  
  
    ```vb  
    Public Class Words  
        ' Object to store the current state, for passing to the caller.  
        Public Class CurrentState  
            Public LinesCounted As Integer  
            Public WordsMatched As Integer  
        End Class  
  
        Public SourceFile As String  
        Public CompareString As String  
        Private WordCount As Integer = 0  
        Private LinesCounted As Integer = 0  
  
        Public Sub CountWords(  
            ByVal worker As System.ComponentModel.BackgroundWorker,  
            ByVal e As System.ComponentModel.DoWorkEventArgs  
        )  
            ' Initialize the variables.  
            Dim state As New CurrentState  
            Dim line = ""  
            Dim elapsedTime = 20  
            Dim lastReportDateTime = Now  
  
            If CompareString Is Nothing OrElse  
               CompareString = System.String.Empty Then  
  
               Throw New Exception("CompareString not specified.")  
            End If  
  
            Using myStream As New System.IO.StreamReader(SourceFile)  
  
                ' Process lines while there are lines remaining in the file.  
                Do While Not myStream.EndOfStream  
                    If worker.CancellationPending Then  
                        e.Cancel = True  
                        Exit Do  
                    Else  
                        line = myStream.ReadLine  
                        WordCount += CountInString(line, CompareString)  
                        LinesCounted += 1  
  
                        ' Raise an event so the form can monitor progress.  
                        If Now > lastReportDateTime.AddMilliseconds(elapsedTime) Then  
                            state.LinesCounted = LinesCounted  
                            state.WordsMatched = WordCount  
                            worker.ReportProgress(0, state)  
                            lastReportDateTime = Now  
                        End If  
  
                        ' Uncomment for testing.  
                        'System.Threading.Thread.Sleep(5)  
                    End If  
                Loop  
  
                ' Report the final count values.  
                state.LinesCounted = LinesCounted  
                state.WordsMatched = WordCount  
                worker.ReportProgress(0, state)  
            End Using  
        End Sub  
  
        Private Function CountInString(  
            ByVal SourceString As String,  
            ByVal CompareString As String  
        ) As Integer  
            ' This function counts the number of times  
            ' a word is found in a line.  
            If SourceString Is Nothing Then  
                Return 0  
            End If  
  
            Dim EscapedCompareString =  
                System.Text.RegularExpressions.Regex.Escape(CompareString)  
  
            ' To count all occurrences of the string, even within words, remove  
            ' both instances of "\b".  
            Dim regex As New System.Text.RegularExpressions.Regex(  
                "\b" + EscapedCompareString + "\b",  
                System.Text.RegularExpressions.RegexOptions.IgnoreCase)  
  
            Dim matches As System.Text.RegularExpressions.MatchCollection  
            matches = regex.Matches(SourceString)  
            Return matches.Count  
        End Function  
    End Class  
    ```  
  
### <a name="to-handle-events-from-the-thread"></a><span data-ttu-id="6f771-162">Para controlar eventos del subproceso</span><span class="sxs-lookup"><span data-stu-id="6f771-162">To handle events from the thread</span></span>  
  
-   <span data-ttu-id="6f771-163">Agregue los controladores de eventos siguientes al formulario principal:</span><span class="sxs-lookup"><span data-stu-id="6f771-163">Add the following event handlers to your main form:</span></span>  
  
    ```vb  
    Private Sub BackgroundWorker1_RunWorkerCompleted(   
        ByVal sender As Object,   
        ByVal e As System.ComponentModel.RunWorkerCompletedEventArgs  
      ) Handles BackgroundWorker1.RunWorkerCompleted  
  
        ' This event handler is called when the background thread finishes.  
        ' This method runs on the main thread.  
        If e.Error IsNot Nothing Then  
            MessageBox.Show("Error: " & e.Error.Message)  
        ElseIf e.Cancelled Then  
            MessageBox.Show("Word counting canceled.")  
        Else  
            MessageBox.Show("Finished counting words.")  
        End If  
    End Sub  
  
    Private Sub BackgroundWorker1_ProgressChanged(   
        ByVal sender As Object,   
        ByVal e As System.ComponentModel.ProgressChangedEventArgs  
      ) Handles BackgroundWorker1.ProgressChanged  
  
        ' This method runs on the main thread.  
        Dim state As Words.CurrentState =   
            CType(e.UserState, Words.CurrentState)  
        Me.LinesCounted.Text = state.LinesCounted.ToString  
        Me.WordsCounted.Text = state.WordsMatched.ToString  
    End Sub  
    ```  
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a><span data-ttu-id="6f771-164">Para iniciar un nuevo subproceso que ejecute el método WordCount y llamarlo</span><span class="sxs-lookup"><span data-stu-id="6f771-164">To start and call a new thread that runs the WordCount method</span></span>  
  
1.  <span data-ttu-id="6f771-165">Agregue los procedimientos siguientes al programa:</span><span class="sxs-lookup"><span data-stu-id="6f771-165">Add the following procedures to your program:</span></span>  
  
    ```vb  
    Private Sub BackgroundWorker1_DoWork(   
        ByVal sender As Object,   
        ByVal e As System.ComponentModel.DoWorkEventArgs  
      ) Handles BackgroundWorker1.DoWork  
  
        ' This event handler is where the actual work is done.  
        ' This method runs on the background thread.  
  
        ' Get the BackgroundWorker object that raised this event.  
        Dim worker As System.ComponentModel.BackgroundWorker  
        worker = CType(sender, System.ComponentModel.BackgroundWorker)  
  
        ' Get the Words object and call the main method.  
        Dim WC As Words = CType(e.Argument, Words)  
        WC.CountWords(worker, e)  
    End Sub  
  
    Sub StartThread()  
        ' This method runs on the main thread.  
        Me.WordsCounted.Text = "0"  
  
        ' Initialize the object that the background worker calls.  
        Dim WC As New Words  
        WC.CompareString = Me.CompareString.Text  
        WC.SourceFile = Me.SourceFile.Text  
  
        ' Start the asynchronous operation.  
        BackgroundWorker1.RunWorkerAsync(WC)  
    End Sub  
    ```  
  
2.  <span data-ttu-id="6f771-166">Llame al método `StartThread` desde el botón `Start` del formulario:</span><span class="sxs-lookup"><span data-stu-id="6f771-166">Call the `StartThread` method from the `Start` button on your form:</span></span>  
  
    ```vb  
    Private Sub Start_Click() Handles Start.Click  
        StartThread()  
    End Sub  
    ```  
  
### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a><span data-ttu-id="6f771-167">Para implementar un botón Cancelar que detenga el subproceso</span><span class="sxs-lookup"><span data-stu-id="6f771-167">To implement a Cancel button that stops the thread</span></span>  
  
-   <span data-ttu-id="6f771-168">Llame al procedimiento `StopThread` desde el controlador de eventos `Click` para el botón `Cancel`.</span><span class="sxs-lookup"><span data-stu-id="6f771-168">Call the `StopThread` procedure from the `Click` event handler for the `Cancel` button.</span></span>  
  
    ```vb  
    Private Sub Cancel_Click() Handles Cancel.Click  
        ' Cancel the asynchronous operation.  
        Me.BackgroundWorker1.CancelAsync()  
    End Sub  
    ```  
  
## <a name="testing"></a><span data-ttu-id="6f771-169">Pruebas</span><span class="sxs-lookup"><span data-stu-id="6f771-169">Testing</span></span>  
 <span data-ttu-id="6f771-170">Ahora puede probar la aplicación para asegurarse de que funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="6f771-170">You can now test the application to make sure it works correctly.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="6f771-171">Para probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="6f771-171">To test the application</span></span>  
  
1.  <span data-ttu-id="6f771-172">Presione F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6f771-172">Press F5 to run the application.</span></span>  
  
2.  <span data-ttu-id="6f771-173">Cuando aparezca el formulario, escriba la ruta de acceso del archivo que quiera probar en el cuadro `sourceFile`.</span><span class="sxs-lookup"><span data-stu-id="6f771-173">When the form is displayed, enter the file path for the file you want to test in the `sourceFile` box.</span></span> <span data-ttu-id="6f771-174">Por ejemplo, supongamos que el archivo de prueba se denomina Test.txt, escriba C:\Test.txt.</span><span class="sxs-lookup"><span data-stu-id="6f771-174">For example, assuming your test file is named Test.txt, enter C:\Test.txt.</span></span>  
  
3.  <span data-ttu-id="6f771-175">En el segundo cuadro de texto, escriba una palabra o frase para que la aplicación la busque en el archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="6f771-175">In the second text box, enter a word or phrase for the application to search for in the text file.</span></span>  
  
4.  <span data-ttu-id="6f771-176">Haga clic en el botón `Start`.</span><span class="sxs-lookup"><span data-stu-id="6f771-176">Click the `Start` button.</span></span> <span data-ttu-id="6f771-177">El botón `LinesCounted` debe empezar a aumentar inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="6f771-177">The `LinesCounted` button should begin incrementing immediately.</span></span> <span data-ttu-id="6f771-178">La aplicación mostrará el mensaje "Finished Counting" (Recuento finalizado) cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="6f771-178">The application displays the message "Finished Counting" when it is done.</span></span>  
  
#### <a name="to-test-the-cancel-button"></a><span data-ttu-id="6f771-179">Para probar el botón Cancelar</span><span class="sxs-lookup"><span data-stu-id="6f771-179">To test the Cancel button</span></span>  
  
1.  <span data-ttu-id="6f771-180">Pulse F5 para iniciar la aplicación y escriba el nombre de archivo y la palabra de búsqueda tal y como se ha descrito en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="6f771-180">Press F5 to start the application, and enter the file name and search word as described in the previous procedure.</span></span> <span data-ttu-id="6f771-181">Asegúrese de que el archivo que elija es lo bastante grande como para que le dé tiempo a cancelar el procedimiento antes de que finalice.</span><span class="sxs-lookup"><span data-stu-id="6f771-181">Make sure that the file you choose is large enough to ensure you will have time to cancel the procedure before it is finished.</span></span>  
  
2.  <span data-ttu-id="6f771-182">Haga clic en el botón `Start` para iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6f771-182">Click the `Start` button to start the application.</span></span>  
  
3.  <span data-ttu-id="6f771-183">Haga clic en el botón `Cancel`.</span><span class="sxs-lookup"><span data-stu-id="6f771-183">Click the `Cancel` button.</span></span> <span data-ttu-id="6f771-184">La aplicación debe detener el recuento inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="6f771-184">The application should stop counting immediately.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6f771-185">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="6f771-185">Next Steps</span></span>  
 <span data-ttu-id="6f771-186">Esta aplicación contiene un control de errores básico.</span><span class="sxs-lookup"><span data-stu-id="6f771-186">This application contains some basic error handling.</span></span> <span data-ttu-id="6f771-187">Detecta cadenas de búsqueda en blanco.</span><span class="sxs-lookup"><span data-stu-id="6f771-187">It detects blank search strings.</span></span> <span data-ttu-id="6f771-188">Puede hacer que el programa sea más sólido mediante el control de otros errores, como, por ejemplo, que se supere el número máximo de palabras o líneas que se pueden contar.</span><span class="sxs-lookup"><span data-stu-id="6f771-188">You can make this program more robust by handling other errors, such as exceeding the maximum number of words or lines that can be counted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f771-189">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f771-189">See Also</span></span>  
 [<span data-ttu-id="6f771-190">Subprocesamiento (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f771-190">Threading (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/index.md)  
 [<span data-ttu-id="6f771-191">Tutorial: Crear un componente sencillo multiproceso con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6f771-191">Walkthrough: Authoring a Simple Multithreaded Component with Visual Basic</span></span>](http://msdn.microsoft.com/library/05693b70-3566-4d91-9f2c-c9bc4ccb3001)  
 [<span data-ttu-id="6f771-192">Cómo: Suscribir y cancelar la suscripción a eventos</span><span class="sxs-lookup"><span data-stu-id="6f771-192">How to: Subscribe to and Unsubscribe from Events</span></span>](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)
