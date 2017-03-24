---
title: Multithreading con el componente BackgroundWorker (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: e4cd9b2a-f924-470e-a16e-50274709b40e
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3686eb230349876f6cfffd2ad94ed1f547779ab1
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-visual-basic"></a>Tutorial: Multithreading con el componente BackgroundWorker (Visual Basic)
Este tutorial muestra cómo crear una aplicación de formularios Windows Forms multiproceso que busque las apariciones de una palabra en una archivo de texto. Muestra:  
  
-   Definir una clase con un método que se puede llamar mediante el <xref:System.ComponentModel.BackgroundWorker>componente.</xref:System.ComponentModel.BackgroundWorker>  
  
-   Controlar eventos provocados por la <xref:System.ComponentModel.BackgroundWorker>componente.</xref:System.ComponentModel.BackgroundWorker>  
  
-   A partir de un <xref:System.ComponentModel.BackgroundWorker>un método de ejecución del componente.</xref:System.ComponentModel.BackgroundWorker>  
  
-   Implementar un `Cancel` botón que detiene el <xref:System.ComponentModel.BackgroundWorker>componente.</xref:System.ComponentModel.BackgroundWorker>  
  
### <a name="to-create-the-user-interface"></a>Para crear la interfaz de usuario  
  
1.  Abra un nuevo proyecto de aplicación de Windows Forms de Visual Basic y cree un formulario denominado `Form1`.  
  
2.  Agregue dos botones y cuatro cuadros de texto para `Form1`.  
  
3.  Nombre de los objetos como se muestra en la tabla siguiente.  
  
    |Objeto|Propiedad|Parámetro|  
    |------------|--------------|-------------|  
    |Primer botón|`Name`, `Text`|Inicio, inicio|  
    |Segundo botón|`Name`, `Text`|Cancelar, Cancelar|  
    |Primer cuadro de texto|`Name`, `Text`|SourceFile, ""|  
    |Segundo cuadro de texto|`Name`, `Text`|CompareString, ""|  
    |Tercer cuadro de texto|`Name`, `Text`|WordsCounted, "0"|  
    |Cuarto cuadro de texto|`Name`, `Text`|LinesCounted, "0"|  
  
4.  Agregue una etiqueta al lado de cada cuadro de texto. Establecer el `Text` propiedad para cada etiqueta, como se muestra en la tabla siguiente.  
  
    |Objeto|Propiedad|Parámetro|  
    |------------|--------------|-------------|  
    |Primera etiqueta|`Text`|Archivo de código fuente|  
    |Segunda etiqueta|`Text`|Comparar cadenas|  
    |Tercera etiqueta|`Text`|Coincidencia de palabras|  
    |Cuarta etiqueta|`Text`|Recuento de líneas|  
  
### <a name="to-create-a-backgroundworker-component-and-subscribe-to-its-events"></a>Para crear un componente BackgroundWorker y suscribirse a sus eventos  
  
1.  Agregar un <xref:System.ComponentModel.BackgroundWorker>componente desde la **componentes** sección de la **herramientas** al formulario.</xref:System.ComponentModel.BackgroundWorker> Aparecerá en la Bandeja de componentes del formulario.  
  
2.  Establezca las siguientes propiedades del objeto BackgroundWorker1.  
  
    |Propiedad|Configuración|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|True|  
    |`WorkerSupportsCancellation`|True|  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a>Para definir el método que se ejecutará en un subproceso independiente  
  
1.  Desde el **proyecto** menú, elija **Agregar clase** para agregar una clase al proyecto. El **Agregar nuevo elemento** se muestra el cuadro de diálogo.  
  
2.  Seleccione **clase** desde la ventana de plantillas y escriba `Words.vb` en el campo nombre.  
  
3.  Haga clic en **Agregar**. El `Words` se muestra la clase.  
  
4.  Agregue el código siguiente a la clase `Words` :  
  
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
  
### <a name="to-handle-events-from-the-thread"></a>Controlar eventos desde el subproceso  
  
-   Agregue los siguientes controladores de eventos a su formulario principal:  
  
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
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a>Para iniciar y llamar a un nuevo subproceso que ejecuta el método WordCount  
  
1.  Agregue los siguientes procedimientos en el programa:  
  
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
  
2.  Llame a la `StartThread` método desde el `Start` botón en el formulario:  
  
    ```vb  
    Private Sub Start_Click() Handles Start.Click  
        StartThread()  
    End Sub  
    ```  
  
### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a>Para implementar un botón Cancel que detiene el subproceso  
  
-   Llame a la `StopThread` procedimiento desde el `Click` controlador de eventos para el `Cancel` botón.  
  
    ```vb  
    Private Sub Cancel_Click() Handles Cancel.Click  
        ' Cancel the asynchronous operation.  
        Me.BackgroundWorker1.CancelAsync()  
    End Sub  
    ```  
  
## <a name="testing"></a>Pruebas  
 Ahora puede probar la aplicación para asegurarse de que funciona correctamente.  
  
#### <a name="to-test-the-application"></a>Para probar la aplicación  
  
1.  Presione F5 para ejecutar la aplicación.  
  
2.  Cuando se muestre el formulario, escriba la ruta de acceso de archivo para el archivo que desea probar en la `sourceFile` cuadro. Por ejemplo, suponiendo que el archivo de prueba denominado Test.txt, escriba C:\Test.txt.  
  
3.  En el segundo cuadro de texto, escriba una palabra o frase para la aplicación buscar en el archivo de texto.  
  
4.  Haga clic en el botón `Start`. El `LinesCounted` botón empezará a incrementar inmediatamente. La aplicación muestra el mensaje "Finished Counting" cuando termine.  
  
#### <a name="to-test-the-cancel-button"></a>Para probar el botón Cancelar  
  
1.  Presione F5 para iniciar la aplicación y escriba la palabra de búsqueda y de nombre de archivo como se describe en el procedimiento anterior. Asegúrese de que el archivo que elige es lo suficientemente grande como para asegurarse de que tendrá tiempo para cancelar el procedimiento antes de que finalice.  
  
2.  Haga clic en el `Start` botón para iniciar la aplicación.  
  
3.  Haga clic en el botón `Cancel`. La aplicación parará de contar inmediatamente.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Esta aplicación contiene un control de errores básico. Detecta las cadenas de búsqueda en blanco. Puede hacer que este programa más sólido por otros errores, por ejemplo, si se supera el número máximo de palabras o líneas que se pueden contar.  
  
## <a name="see-also"></a>Vea también  
 [Subprocesamiento (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)   
 [Tutorial: Crear un componente sencillo multiproceso con Visual Basic](http://msdn.microsoft.com/library/05693b70-3566-4d91-9f2c-c9bc4ccb3001)   
 [Cómo: Suscribir y cancelar la suscripción a eventos](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)
