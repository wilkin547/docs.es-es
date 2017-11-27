---
title: Multithreading con el componente BackgroundWorker (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4cd9b2a-f924-470e-a16e-50274709b40e
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bb0734b4bbf3f8bf5b27305754829f1a9f29f42a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-visual-basic"></a>Tutorial: Multithreading con el componente BackgroundWorker (Visual Basic)
Este tutorial muestra cómo crear una aplicación multiproceso de Windows Forms que busque las repeticiones de una palabra en un archivo de texto. Muestra cómo:  
  
-   Definir una clase con un método que puede llamarse mediante el componente <xref:System.ComponentModel.BackgroundWorker>.  
  
-   Controlar eventos que se han generado mediante el componente <xref:System.ComponentModel.BackgroundWorker>.  
  
-   Iniciar un componente <xref:System.ComponentModel.BackgroundWorker> para ejecutar un método.  
  
-   Implementar un botón `Cancel` que detenga el componente <xref:System.ComponentModel.BackgroundWorker>.  
  
### <a name="to-create-the-user-interface"></a>Para crear la interfaz de usuario  
  
1.  Abra un nuevo proyecto de aplicación de Windows Forms de Visual Basic y cree un formulario denominado `Form1`.  
  
2.  Agregue dos botones y cuatro cuadros de texto a `Form1`.  
  
3.  Asigne nombre a los objetos tal y como se muestra en la tabla siguiente.  
  
    |Objeto|Propiedad|Parámetro|  
    |------------|--------------|-------------|  
    |Primer botón|`Name`, `Text`|Iniciar, Iniciar|  
    |Segundo botón|`Name`, `Text`|Cancelar, Cancelar|  
    |Primer cuadro de texto|`Name`, `Text`|SourceFile, ""|  
    |Segundo cuadro de texto|`Name`, `Text`|CompareString, ""|  
    |Tercer cuadro de texto|`Name`, `Text`|WordsCounted, "0"|  
    |Cuarto cuadro de texto|`Name`, `Text`|LinesCounted, "0"|  
  
4.  Agregue una etiqueta junto a cada cuadro de texto. Establezca la propiedad `Text` para cada etiqueta tal y como se muestra en la tabla siguiente.  
  
    |Objeto|Propiedad|Parámetro|  
    |------------|--------------|-------------|  
    |Primera etiqueta|`Text`|Archivo de código fuente|  
    |Segunda etiqueta|`Text`|Cadena de comparación|  
    |Tercer etiqueta|`Text`|Palabras coincidentes|  
    |Cuarta etiqueta|`Text`|Recuento de líneas|  
  
### <a name="to-create-a-backgroundworker-component-and-subscribe-to-its-events"></a>Para crear un componente BackgroundWorker y suscribirse a sus eventos  
  
1.  Agregue un componente <xref:System.ComponentModel.BackgroundWorker> desde la sección **Componentes** del **cuadro de herramientas** al formulario. Aparecerá en la bandeja de componentes del formulario.  
  
2.  Establezca las siguientes propiedades del objeto BackgroundWorker1.  
  
    |Propiedad|Configuración|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|True|  
    |`WorkerSupportsCancellation`|True|  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a>Para definir el método que se ejecutará en un subproceso independiente  
  
1.  En el menú **Proyecto**, elija **Agregar clase** para agregar una clase al proyecto. Se abrirá el cuadro de diálogo **Agregar nuevo elemento**.  
  
2.  Seleccione **Clase** en la ventana de plantillas y escriba `Words.vb` en el campo de nombre.  
  
3.  Haga clic en **Agregar**. Se mostrará la clase `Words`.  
  
4.  Agregue el código siguiente a la clase `Words`:  
  
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
  
### <a name="to-handle-events-from-the-thread"></a>Para controlar eventos del subproceso  
  
-   Agregue los controladores de eventos siguientes al formulario principal:  
  
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
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a>Para iniciar un nuevo subproceso que ejecute el método WordCount y llamarlo  
  
1.  Agregue los procedimientos siguientes al programa:  
  
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
  
2.  Llame al método `StartThread` desde el botón `Start` del formulario:  
  
    ```vb  
    Private Sub Start_Click() Handles Start.Click  
        StartThread()  
    End Sub  
    ```  
  
### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a>Para implementar un botón Cancelar que detenga el subproceso  
  
-   Llame al procedimiento `StopThread` desde el controlador de eventos `Click` para el botón `Cancel`.  
  
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
  
2.  Cuando aparezca el formulario, escriba la ruta de acceso del archivo que quiera probar en el cuadro `sourceFile`. Por ejemplo, supongamos que el archivo de prueba se denomina Test.txt, escriba C:\Test.txt.  
  
3.  En el segundo cuadro de texto, escriba una palabra o frase para que la aplicación la busque en el archivo de texto.  
  
4.  Haga clic en el botón `Start`. El botón `LinesCounted` debe empezar a aumentar inmediatamente. La aplicación mostrará el mensaje "Finished Counting" (Recuento finalizado) cuando haya terminado.  
  
#### <a name="to-test-the-cancel-button"></a>Para probar el botón Cancelar  
  
1.  Pulse F5 para iniciar la aplicación y escriba el nombre de archivo y la palabra de búsqueda tal y como se ha descrito en el procedimiento anterior. Asegúrese de que el archivo que elija es lo bastante grande como para que le dé tiempo a cancelar el procedimiento antes de que finalice.  
  
2.  Haga clic en el botón `Start` para iniciar la aplicación.  
  
3.  Haga clic en el botón `Cancel`. La aplicación debe detener el recuento inmediatamente.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Esta aplicación contiene un control de errores básico. Detecta cadenas de búsqueda en blanco. Puede hacer que el programa sea más sólido mediante el control de otros errores, como, por ejemplo, que se supere el número máximo de palabras o líneas que se pueden contar.  
  
## <a name="see-also"></a>Vea también  
 [Subprocesamiento (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)  
 [Tutorial: Crear un componente sencillo multiproceso con Visual Basic](http://msdn.microsoft.com/library/05693b70-3566-4d91-9f2c-c9bc4ccb3001)  
 [Cómo: Suscribir y cancelar la suscripción a eventos](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)
