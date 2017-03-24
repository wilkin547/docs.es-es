---
title: Acceso a la Web con Async y Await (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- VB
ms.assetid: 84fd047f-fab8-4d89-8ced-104fb7310a91
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
ms.openlocfilehash: 643fff648336c664961ad7956308acbaea262f61
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-accessing-the-web-by-using-async-and-await-visual-basic"></a>Tutorial: Acceso a web usando Async y Await (C# y Visual Basic)
Puede escribir programas asincrónicas más fácil e intuitiva mediante las características que se introdujeron en [!INCLUDE[vs_dev11_long](../../../../csharp/includes/vs_dev11_long_md.md)]. Puede escribir código asincrónico parecido al código sincrónico y dejar que el compilador gestione las difíciles funciones de devolución de llamada y continuaciones que normalmente implica el código asincrónico.  
  
 Para obtener más información acerca de la característica Async, consulte [la programación asincrónica con Async y Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).  
  
 Este tutorial comienza con una aplicación sincrónica de Windows Presentation Foundation (WPF) que suma el número de bytes de una lista de sitios web. A continuación, el tutorial convierte la aplicación en una solución asincrónica mediante el uso de las características nuevas.  
  
 Si no desea crear las aplicaciones usted mismo, puede descargar "ejemplo Async: obtener acceso a un tutorial de Web (C# y Visual Basic)" de [ejemplos de código para desarrolladores](http://go.microsoft.com/fwlink/?LinkId=255191).  
  
 En este tutorial, se realizarán las siguientes tareas:  
  
-   [Para crear una aplicación de WPF](#CreateWPFApp)  
  
-   [Para diseñar un MainWindow simple de WPF](#MainWindow)  
  
-   [Para agregar una referencia](#AddRef)  
  
-   [Para agregar las instrucciones Imports necesarias](#ImportsState)  
  
-   [Para crear una aplicación sincrónica](#synchronous)  
  
-   [Para probar la solución sincrónica](#testSynch)  
  
-   [Para convertir GetURLContents a un método asincrónico](#GetURLContents)  
  
-   [Para convertir SumPageSizes a un método asincrónico](#SumPageSizes)  
  
-   [Para convertir startButton_Click a un método asincrónico](#startButton)  
  
-   [Para probar la solución asincrónica](#testAsynch)  
  
-   [Para reemplazar el método GetURLContentsAsync con un método de .NET Framework](#GetURLContentsAsync)  
  
-   [Ejemplo](#BKMK_CompleteCodeExamples)  
  
## <a name="prerequisites"></a>Requisitos previos  
 Visual Studio 2012 o posterior debe estar instalado en el equipo. Para obtener más información, consulte el [sitio Web de Microsoft](http://go.microsoft.com/fwlink/?LinkId=235233).  
  
###  <a name="CreateWPFApp"></a>Para crear una aplicación de WPF  
  
1.  Inicie Visual Studio.  
  
2.  En la barra de menús, elija **Archivo**, **Nuevo**, **Proyecto**.  
  
     Aparece el cuadro de diálogo **Nuevo proyecto** .  
  
3.  En el **plantillas instaladas** panel, elija Visual Basic y, a continuación, elija **aplicación WPF** de la lista de tipos de proyecto.  
  
4.  En el **nombre** texto, escriba `AsyncExampleWPF`y, a continuación, elija la **Aceptar** botón.  
  
     El proyecto nuevo aparece en **el Explorador de soluciones**.  
  
##  <a name="BKMK_DesignWPFMainWin"></a>   
###  <a name="MainWindow"></a>Para diseñar un MainWindow simple de WPF  
  
1.  En el Editor de código de Visual Studio, elija la pestaña **MainWindow.xaml** .  
  
2.  Si el **cuadro de herramientas** ventana no está visible, abra el **vista** menú y, a continuación, elija **cuadro de herramientas**.  
  
3.  Agregar un **botón** control y un **cuadro de texto** el control a la **MainWindow** ventana.  
  
4.  Resalte la **cuadro de texto** control y, en la **propiedades** ventana, establezca los siguientes valores:  
  
    -   Establecer el **nombre** propiedad `resultsTextBox`.  
  
    -   Establecer el **alto** propiedad a 250.  
  
    -   Establecer el **ancho** propiedad a 500.  
  
    -   En el **texto** , especifique una fuente monoespaciada, como Lucida Console o Monospace Global.  
  
5.  Resalte la **botón** control y, en la **propiedades** ventana, establezca los siguientes valores:  
  
    -   Establecer el **nombre** propiedad `startButton`.  
  
    -   Cambie el valor de la **contenido** propiedad de **botón** a **iniciar**.  
  
6.  Coloque el cuadro de texto y el botón para que ambos aparezcan en el **MainWindow** ventana.  
  
     Para obtener más información acerca del Diseñador de XAML de WPF, vea [crear una interfaz de usuario mediante el Diseñador XAML](https://docs.microsoft.com/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio).  
  
##  <a name="BKMK_AddReference"></a>   
###  <a name="AddRef"></a>Para agregar una referencia  
  
1.  En **el Explorador de soluciones**, resalte el nombre del proyecto.  
  
2.  En la barra de menús, elija **proyecto**, **Agregar referencia**.  
  
     El **Administrador de referencias** aparece el cuadro de diálogo.  
  
3.  En la parte superior del cuadro de diálogo, compruebe que el proyecto tiene como destino .NET Framework 4.5 o posterior.  
  
4.  En el **ensamblados** área, elija **Framework** si no está ya seleccionada.  
  
5.  En la lista de nombres, seleccione el **System.Net.Http** casilla de verificación.  
  
6.  Elija la **Aceptar** botón para cerrar el cuadro de diálogo.  
  
##  <a name="BKMK_AddStatesandDirs"></a>   
###  <a name="ImportsState"></a>Para agregar las instrucciones Imports necesarias  
  
1.  En **el Explorador de soluciones**, abra el menú contextual para MainWindow.xaml.vb y, a continuación, elija **ver código**.  
  
2.  Agregue las siguientes `Imports` en la parte superior del archivo de código si no están ya presentes.  
  
    ```vb  
    Imports System.Net.Http  
    Imports System.Net  
    Imports System.IO  
    ```  
  
##  <a name="BKMK_CreatSynchApp"></a>   
###  <a name="synchronous"></a>Para crear una aplicación sincrónica  
  
1.  En la ventana de diseño, MainWindow.xaml, haga doble clic en el **iniciar** botón para crear el `startButton_Click` MainWindow.xaml.vb de controlador de eventos.  
  
2.  En MainWindow.xaml.vb, copie el código siguiente en el cuerpo de `startButton_Click`:  
  
    ```vb  
    resultsTextBox.Clear()  
    SumPageSizes()  
    resultsTextBox.Text &= vbCrLf & "Control returned to startButton_Click."  
    ```  
  
     El código llama al método que controla la aplicación, `SumPageSizes`, y muestra un mensaje cuando el control vuelve a `startButton_Click`.  
  
3.  El código de la solución sincrónica contiene los cuatro métodos siguientes:  
  
    -   `SumPageSizes`, que obtiene una lista de direcciones URL de páginas web de `SetUpURLList` y, a continuación, llama a `GetURLContents` y `DisplayResults` para que procesen cada dirección URL.  
  
    -   `SetUpURLList`, que crea y devuelve una lista de direcciones web.  
  
    -   `GetURLContents`, que descarga el contenido de cada sitio web y devuelve el contenido como una matriz de bytes.  
  
    -   `DisplayResults`, que muestra el número de bytes de la matriz de bytes de cada dirección URL.  
  
     Copie los cuatro métodos siguientes y, a continuación, pegarlos en el `startButton_Click` MainWindow.xaml.vb de controlador de eventos:  
  
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
                "http://msdn.microsoft.com/library/windows/apps/br211380.aspx",  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/ee256749.aspx",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
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
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
    ```  
  
##  <a name="BKMK_TestSynchSol"></a>   
###  <a name="testSynch"></a>Para probar la solución sincrónica  
  
1.  Presione la tecla F5 para ejecutar el programa y elija el botón **Inicio** .  
  
     Debería aparecer un resultado similar a la lista siguiente.  
  
    ```  
  
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
  
     Tenga en cuenta que los recuentos tardan unos segundos en mostrarse. Durante ese tiempo, el subproceso de interfaz de usuario se bloquea mientras espera a que se descarguen los recursos solicitados. Como resultado, no se puede mover, maximizar, minimizar o incluso cerrar la ventana después de elegir la **iniciar** botón. Estos intentos producirán un error hasta que empiecen a aparecer los recuentos de bytes. Si un sitio web no responde, no se le indicará cuál es el sitio que produjo el error. Incluso resulta difícil dejar de esperar y cerrar el programa.  
  
##  <a name="BKMK_ConvertGtBtArr"></a>   
###  <a name="GetURLContents"></a>Para convertir GetURLContents a un método asincrónico  
  
1.  Para convertir la solución sincrónica en una solución asincrónica, el mejor lugar para comenzar es en `GetURLContents` porque las llamadas a la <xref:System.Net.HttpWebRequest>método <xref:System.Net.HttpWebRequest.GetResponse%2A>y a la <xref:System.IO.Stream>método <xref:System.IO.Stream.CopyTo%2A>son donde la aplicación obtiene acceso a la web.</xref:System.IO.Stream.CopyTo%2A> </xref:System.IO.Stream> </xref:System.Net.HttpWebRequest.GetResponse%2A> </xref:System.Net.HttpWebRequest> .NET Framework facilita la conversión proporcionando versiones asincrónicas de ambos métodos.  
  
     Para obtener más información acerca de los métodos que se utilizan en `GetURLContents`, consulte <xref:System.Net.WebRequest>.</xref:System.Net.WebRequest>  
  
    > [!NOTE]
    >  A medida que siga los pasos de este tutorial, aparecerán varios errores del compilador. Puede hacer caso omiso y continuar con el tutorial.  
  
     Cambiar el método que se llama en la tercera línea de `GetURLContents` de `GetResponse` asincrónica, basada en tareas <xref:System.Net.WebRequest.GetResponseAsync%2A>método.</xref:System.Net.WebRequest.GetResponseAsync%2A>  
  
    ```vb  
    Using response As WebResponse = webReq.GetResponseAsync()  
    ```  
  
2.  `GetResponseAsync`Devuelve un valor de <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> En este caso, el *variable de retorno de tarea*, `TResult`, tiene un tipo <xref:System.Net.WebResponse>.</xref:System.Net.WebResponse> La tarea es una promesa para generar un objeto `WebResponse` real después de que se descarguen los datos solicitados y la tarea se ejecute hasta completarse.  
  
     Para recuperar la `WebResponse` valor de la tarea, aplicar un [Await](../../../../visual-basic/language-reference/operators/await-operator.md) operador a la llamada a `GetResponseAsync`, como se muestra en el código siguiente.  
  
<CodeContentPlaceHolder>5</CodeContentPlaceHolder>  
     El `Await` operador suspende la ejecución del método actual, `GetURLContents`, hasta que se complete la tarea esperada. Mientras tanto, el control devuelve al llamador del método actual. En este ejemplo, el método actual es `GetURLContents` y el llamador es `SumPageSizes`. Cuando la tarea finaliza, el objeto `WebResponse` prometido se genera como valor de la tarea esperada y se asigna a la variable `response`.  
  
     The previous statement can be separated into the following two statements to clarify what happens.  
  
<CodeContentPlaceHolder>6</CodeContentPlaceHolder>  
     La llamada a `webReq.GetResponseAsync` devuelve `Task(Of WebResponse)` o `Task<WebResponse>`. Un `Await` operador se aplica a la tarea para recuperar el `WebResponse` valor.  
  
     If your async method has work to do that doesn’t depend on the completion of the task, the method can continue with that work between these two statements, after the call to the async method and before the await operator is applied. For examples, see [How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) and [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).  
  
3.  Dado que agregó el `Await` operador en el paso anterior, que se produce un error del compilador. El operador puede utilizarse únicamente en los métodos que se marcan con el [Async](../../../../visual-basic/language-reference/modifiers/async.md) modificador. Omita el error mientras repita los pasos de conversión para reemplazar la llamada a `CopyTo` con una llamada a `CopyToAsync`.  
  
    -   Cambiar el nombre del método que se llama a <xref:System.IO.Stream.CopyToAsync%2A>.</xref:System.IO.Stream.CopyToAsync%2A>  
  
    -   El método `CopyTo` o `CopyToAsync` copia bytes a su argumento, `content`, y no devuelve un valor significativo. En la versión sincrónica, la llamada a `CopyTo` es una sencilla instrucción que no devuelve un valor. La versión asincrónica, `CopyToAsync`, devuelve un <xref:System.Threading.Tasks.Task>.</xref:System.Threading.Tasks.Task> La tarea funciona como "Task(void)" y permite que se espere al método. Aplique `Await` o `await` a la llamada a `CopyToAsync`, como se muestra en el código siguiente.  
  
<CodeContentPlaceHolder>7</CodeContentPlaceHolder>  
         La instrucción anterior abrevia las dos líneas de código siguientes.  
  
<CodeContentPlaceHolder>8</CodeContentPlaceHolder>  
4.  Lo único que queda por hacer en `GetURLContents` es ajustar la firma del método. Puede usar el `Await` operador sólo en métodos marcados con el [Async](../../../../visual-basic/language-reference/modifiers/async.md) modificador. Agregue el modificador para marcar el método como un *método asincrónico*, como se muestra en el código siguiente.  
  
<CodeContentPlaceHolder>9</CodeContentPlaceHolder>  
5.  Sólo puede ser el tipo de valor devuelto de un método asincrónico <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task> En Visual Basic, el método debe ser `Function`, que devuelve `Task` o `Task(Of T)`, o el método debe ser `Sub`. Normalmente, un `Sub` método sólo se utiliza en un controlador de eventos asincrónicos, donde `Sub` es necesaria. En otros casos, se utiliza `Task(T)` si tiene el método completado un [devolver](../../../../visual-basic/language-reference/statements/return-statement.md) instrucción que devuelve un valor de tipo T, y usar `Task` si el método completado no devuelve un valor significativo.  
  
     Para obtener más información, consulte [Async devolver tipos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
     El método `GetURLContents` tiene una instrucción return, y la instrucción devuelve una matriz de bytes. Por lo tanto, el tipo de valor devuelto de la versión de async es Task(T), donde T es una matriz de bytes. Realice los cambios siguientes en la firma del método:  
  
    -   Cambiar el tipo de valor devuelto para `Task(Of Byte())`.  
  
    -   Por convención, los métodos asincrónicos tienen nombres que terminan en "Async", por lo que debe cambiar el nombre del método a `GetURLContentsAsync`.  
  
     En el código siguiente se muestran estos cambios.  
  
    ```vb  
    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())  
    ```  
  
     Con estos pocos cambios, se completa la conversión de `GetURLContents` en un método asincrónico.  
  
##  <a name="BKMK_ConvertSumPagSzs"></a>   
###  <a name="SumPageSizes"></a>Para convertir SumPageSizes a un método asincrónico  
  
1.  Repita los pasos del procedimiento anterior para `SumPageSizes`. Primero, cambie la llamada a `GetURLContents` a una llamada asincrónica.  
  
    -   Cambie el nombre del método al que se llama de `GetURLContents` a `GetURLContentsAsync`, si aún no lo ha hecho.  
  
    -   Aplicar `Await` a la tarea que `GetURLContentsAsync` devuelve el byte de obtener el valor de matriz.  
  
     En el código siguiente se muestran estos cambios.  
  
    ```vb  
    Dim urlContents As Byte() = Await GetURLContentsAsync(url)  
    ```  
  
     La asignación anterior abrevia las dos líneas de código siguientes.  
  
    ```vb  
    ' GetURLContentsAsync returns a task. At completion, the task   
    ' produces a byte array.   
    'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)   
    'Dim urlContents As Byte() = Await getContentsTask  
  
    ```  
  
2.  Realice los cambios siguientes en la firma del método:  
  
    -   Marque el método con el `Async` modificador.  
  
    -   Agregue "Async" al nombre del método.  
  
    -   Esta vez no hay ninguna variable de devolución de tarea, T, porque `SumPageSizesAsync` no devuelve un valor para T. (El método no tiene ningún `Return` instrucción.) Sin embargo, el método debe devolver `Task` para admitir await. Por lo tanto, cambie el tipo de método de `Sub` a `Function`. El tipo de valor devuelto de la función es `Task`.  
  
     En el código siguiente se muestran estos cambios.  
  
    ```vb  
    Private Async Function SumPageSizesAsync() As Task  
    ```  
  
     Se completa así la conversión de `SumPageSizes` a `SumPageSizesAsync`.  
  
##  <a name="BKMK_Cnvrtbttn1"></a>   
###  <a name="startButton"></a>Para convertir startButton_Click a un método asincrónico  
  
1.  En el controlador de eventos, cambie el nombre del método llamado de `SumPageSizes` a `SumPageSizesAsync`, si aún no lo ha hecho.  
  
2.  Dado que `SumPageSizesAsync` es un método asincrónico, cambie el código en el controlador de eventos para esperar el resultado.  
  
     La llamada a `SumPageSizesAsync` refleja la llamada a `CopyToAsync` en `GetURLContentsAsync`. La llamada devuelve `Task`, no `Task(T)`.  
  
     Al igual que en los procedimientos anteriores, puede convertir la llamada usando una o dos instrucciones. En el código siguiente se muestran estos cambios.  
  
    ```vb  
    '' One-step async call.  
    Await SumPageSizesAsync()  
  
    ' Two-step async call.  
    'Dim sumTask As Task = SumPageSizesAsync()  
    'Await sumTask  
    ```  
  
3.  Para evitar que accidentalmente volver a escribir la operación, agregue la siguiente instrucción al principio del `startButton_Click` para deshabilitar la **iniciar** botón.  
  
    ```vb  
    ' Disable the button until the operation is complete.  
    startButton.IsEnabled = False  
    ```  
  
     Puede volver a habilitar el botón al final del controlador de eventos.  
  
    ```vb  
    ' Reenable the button in case you want to run the operation again.  
    startButton.IsEnabled = True  
    ```  
  
     Para obtener más información acerca de reentrada, consulte [control reentrada en aplicaciones asincrónicas (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md).  
  
4.  Finalmente, agregue el `Async` modificador a la declaración de modo que puede esperar el controlador de eventos `SumPagSizesAsync`.  
  
    ```vb  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
    ```  
  
     Normalmente, no se cambian los nombres de los controladores de eventos. El tipo de valor devuelto no se cambia a `Task` porque los controladores de eventos deben ser `Sub` procedimientos en Visual Basic.  
  
     Así se completa la conversión del proyecto de procesamiento sincrónico a asincrónico.  
  
##  <a name="BKMK_testAsynchSolution"></a>   
###  <a name="testAsynch"></a>Para probar la solución asincrónica  
  
1.  Presione la tecla F5 para ejecutar el programa y elija el botón **Inicio** .  
  
2.  Deberían aparecer resultados similares a los de la solución sincrónica. No obstante, debe tener en cuenta las siguientes diferencias.  
  
    -   No todos los resultados se producen al mismo tiempo cuando se completa el procesamiento. Por ejemplo, ambos programas contienen una línea en `startButton_Click` que borra el cuadro de texto. La intención es borrar el cuadro de texto entre ejecuciones si elige la **iniciar** botón por segunda vez, después de que ha aparecido un conjunto de resultados. En la versión sincrónica, el cuadro de texto se borra antes de que aparezcan los recuentos por segunda vez, cuando se completen las descargas y el subproceso de interfaz de usuario esté libre para llevar a cabo otro trabajo. En la versión asincrónica, se borra el cuadro de texto inmediatamente después de elegir la **iniciar** botón.  
  
    -   Lo más importante es que el subproceso de interfaz de usuario no se bloquea durante las descargas. Puede mover o cambiar el tamaño de la ventana mientras se descargan, se cuentan y se muestran los recursos web. Si uno de los sitios Web es lento o no responde, puede cancelar la operación eligiendo el **cerrar** botón (la x en el campo de color rojo en la esquina superior derecha).  
  
##  <a name="BKMK_ReplaceGetByteArrayAsync"></a>   
###  <a name="GetURLContentsAsync"></a>Para reemplazar el método GetURLContentsAsync con un método de .NET Framework  
  
1.  .NET Framework 4.5 pone a su disposición muchos métodos asincrónicos. Uno de ellos, el <xref:System.Net.Http.HttpClient>método <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29>, necesita sólo para este tutorial.</xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29> </xref:System.Net.Http.HttpClient> Se puede usar en lugar del método `GetURLContentsAsync` que creó en un procedimiento anterior.  
  
     El primer paso es crear un objeto `HttpClient` en el método `SumPageSizesAsync`. Agregue la siguiente declaración al principio del método.  
  
    ```vb  
    ' Declare an HttpClient object and increase the buffer size. The  
    ' default buffer size is 65,536.  
    Dim client As HttpClient =  
        New HttpClient() With {.MaxResponseContentBufferSize = 1000000}  
    ```  
  
2.  En `SumPageSizesAsync,` reemplace la llamada a su método `GetURLContentsAsync` con una llamada al método `HttpClient`.  
  
    ```vb  
    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)  
    ```  
  
3.  Quite o marque como comentario el método `GetURLContentsAsync` que escribió.  
  
4.  Presione la tecla F5 para ejecutar el programa y elija el botón **Inicio** .  
  
     El comportamiento de esta versión del proyecto debería coincidir con el comportamiento que se describe en el procedimiento "Para probar la solución asincrónica", pero con incluso menos trabajo por su parte.  
  
##  <a name="BKMK_CompleteCodeExamples"></a>Ejemplo  
 El código siguiente contiene el ejemplo completo de la conversión de una solución sincrónica a una asincrónica usando el método `GetURLContentsAsync` asincrónico que escribió. Observe que es muy parecida a la solución sincrónica original.  
  
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
                "http://msdn.microsoft.com/library/windows/apps/br211380.aspx",  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/ee256749.aspx",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
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
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
  
End Class  
```  
  
 El código siguiente contiene el ejemplo completo de la solución que usa el método `HttpClient`, `GetByteArrayAsync`.  
  
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
  
        '' Two-step async call.  
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
                "http://msdn.microsoft.com/library/windows/apps/br211380.aspx",  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/ee256749.aspx",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
    End Function  
  
    Private Sub DisplayResults(url As String, content As Byte())  
  
        ' Display the length of each website. The string format   
        ' is designed to be used with a monospaced font, such as  
        ' Lucida Console or Global Monospace.  
        Dim bytes = content.Length  
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
  
End Class  
```  
  
## <a name="see-also"></a>Vea también  
 [Ejemplo ASYNC: Obtener acceso a un tutorial de Web (C# y Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=255191)   
 [Await (operador)](../../../../visual-basic/language-reference/operators/await-operator.md)   
 [Async](../../../../visual-basic/language-reference/modifiers/async.md)   
 [Programación asincrónica con Async y Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)   
 [Tipos de valor devueltos de Async (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md)   
 [Programación asincrónica basada en tareas (TAP)](http://go.microsoft.com/fwlink/?LinkId=204847)   
 [Cómo: ampliar el tutorial de Async usando Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)   
 [Cómo: hacer varias solicitudes Web en paralelo utilizando Async y Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)
