---
title: 'Tutorial: Multithreading con el componente BackgroundWorker (C#) | Microsoft Docs'
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1a27591c62e55295b3cf2b9716776b25d984865a
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-c"></a>Tutorial: Multithreading con el componente BackgroundWorker (C#)
Este tutorial muestra cómo crear una aplicación multiproceso de Windows Forms que busque las repeticiones de una palabra en un archivo de texto. Muestra cómo:  
  
-   Definir una clase con un método que el componente <xref:System.ComponentModel.BackgroundWorker> pueda llamar.  
  
-   Controlar eventos provocados por el componente <xref:System.ComponentModel.BackgroundWorker>.  
  
-   Iniciar un componente <xref:System.ComponentModel.BackgroundWorker> para ejecutar un método.  
  
-   Implementar un botón `Cancel` que detenga el componente <xref:System.ComponentModel.BackgroundWorker>.  
  
### <a name="to-create-the-user-interface"></a>Para crear la interfaz de usuario  
  
1.  Abra un nuevo proyecto de aplicación de Windows Forms en C# y cree un formulario denominado `Form1`.  
  
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
  
1.  Agregue un componente <xref:System.ComponentModel.BackgroundWorker> de la sección **Componentes** del **Cuadro de herramientas** al formulario. Aparecerá en la bandeja de componentes del formulario.  
  
2.  Establezca las siguientes propiedades para el objeto backgroundWorker1.  
  
    |Propiedad|Configuración|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|True|  
    |`WorkerSupportsCancellation`|True|  
  
3.  Suscríbase a los eventos del objeto backgroundWorker1. En la parte superior de la ventana **Propiedades**, haga clic en el icono **Eventos**. Haga doble clic en el evento `RunWorkerCompleted` para crear un método del controlador de eventos. Haga lo mismo para los eventos `ProgressChanged` y `DoWork`.  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a>Para definir el método que se ejecutará en un subproceso independiente  
  
1.  En el menú **Proyecto**, elija **Agregar clase** para agregar una clase al proyecto. Se abrirá el cuadro de diálogo **Agregar nuevo elemento**.  
  
2.  Seleccione **Clase** en la ventana de plantillas y escriba `Words.cs` en el campo de nombre.  
  
3.  Haga clic en **Agregar**. Se mostrará la clase `Words`.  
  
4.  Agregue el código siguiente a la clase `Words`:  
  
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
  
### <a name="to-handle-events-from-the-thread"></a>Para controlar eventos del subproceso  
  
-   Agregue los controladores de eventos siguientes al formulario principal:  
  
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
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a>Para iniciar un nuevo subproceso que ejecute el método WordCount y llamarlo  
  
1.  Agregue los procedimientos siguientes al programa:  
  
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
  
2.  Llame al método `StartThread` desde el botón `Start` del formulario:  
  
    ```csharp  
    private void Start_Click(object sender, EventArgs e)  
    {  
        StartThread();  
    }  
    ```  
  
    ##### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a>Para implementar un botón Cancelar que detenga el subproceso  
  
    -   Llame al procedimiento `StopThread` desde el controlador de eventos `Click` para el botón `Cancel`.  
  
        ```csharp  
        private void Cancel_Click(object sender, EventArgs e)  
        {  
            // Cancel the asynchronous operation.  
            this.backgroundWorker1.CancelAsync();  
        }  
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
 [Threading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md)  (Subprocesos [C#])  
 [Cómo: Suscribir y cancelar la suscripción a eventos](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)
