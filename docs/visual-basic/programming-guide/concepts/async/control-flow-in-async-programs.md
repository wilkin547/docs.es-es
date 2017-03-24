---
title: Controlar el flujo en programas Async (Visual Basic) | Documentos de Microsoft
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
ms.assetid: b0443af7-c586-4cb0-b476-742ae4098a96
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
ms.openlocfilehash: 15e02fbc023db9ae2f3ee9f40598faa7c9c027a0
ms.lasthandoff: 03/13/2017

---
# <a name="control-flow-in-async-programs-visual-basic"></a>Flujo de control en programas Async (Visual Basic)
Puede escribir y mantener más fácilmente programas asincrónicas utilizando la `Async` y `Await` palabras clave. Sin embargo, los resultados pueden sorprenderle si no comprende cómo funciona su programa. Seguimientos de este tema del flujo de control a través de un programa asincrónico simple para mostrar cuando el control se mueve de un método a otra y qué información se transfiere cada vez.  
  
> [!NOTE]
>  Las palabras clave `Async` y `Await` se incluyeron en Visual Studio 2012.  
  
 En general, marcar los métodos que contienen código asincrónico con la [Async](../../../../visual-basic/language-reference/modifiers/async.md) modificador. En un método que está marcado con un modificador async, puede usar un [Await (Visual Basic)](../../../../visual-basic/language-reference/operators/await-operator.md) (operador) para especificar que el método pausa para esperar un proceso denominado asincrónico completar. Para obtener más información, consulte [la programación asincrónica con Async y Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).  
  
 En el ejemplo siguiente se utiliza métodos asincrónicos para descargar el contenido de un sitio Web especificado como una cadena y mostrar la longitud de la cadena. El ejemplo contiene los dos métodos siguientes.  
  
-   `startButton_Click`, que llama `AccessTheWebAsync` y muestra el resultado.  
  
-   `AccessTheWebAsync`, que descarga el contenido de un sitio Web como una cadena y devuelve la longitud de la cadena. `AccessTheWebAsync`usa asincrónico <xref:System.Net.Http.HttpClient>método, <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>, para descargar el contenido.</xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> </xref:System.Net.Http.HttpClient>  
  
 Numeran mostrar líneas aparecen en puntos estratégicos en todo el programa para ayudarle a entender cómo se ejecuta el programa y explican lo que ocurre en cada punto marcado. Las líneas de la pantalla se etiquetan "Uno"a "seis." Las etiquetas representan el orden en el que el programa llegue a estas líneas de código.  
  
 El código siguiente muestra un esquema del programa.  
  
```vb  
Class MainWindow  
  
    Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs) Handles StartButton.Click  
  
        ' ONE  
        Dim getLengthTask As Task(Of Integer) = AccessTheWebAsync()  
  
        ' FOUR  
        Dim contentLength As Integer = Await getLengthTask  
  
        ' SIX  
        ResultsTextBox.Text &=  
            String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
  
    End Sub  
  
    Async Function AccessTheWebAsync() As Task(Of Integer)  
  
        ' TWO  
        Dim client As HttpClient = New HttpClient()   
        Dim getStringTask As Task(Of String) =   
            client.GetStringAsync("http://msdn.microsoft.com")  
  
        ' THREE  
        Dim urlContents As String = Await getStringTask  
  
        ' FIVE  
        Return urlContents.Length  
    End Function  
  
End Class  
  
```  
  
 Cada una de las ubicaciones con la etiqueta "Uno"a "seis," muestra información sobre el estado actual del programa. Se produce el siguiente resultado.  
  
```  
  
ONE:   Entering startButton_Click.  
           Calling AccessTheWebAsync.  
  
TWO:   Entering AccessTheWebAsync.  
           Calling HttpClient.GetStringAsync.  
  
THREE: Back in AccessTheWebAsync.  
           Task getStringTask is started.  
           About to await getStringTask & return a Task<int> to startButton_Click.  
  
FOUR:  Back in startButton_Click.  
           Task getLengthTask is started.  
           About to await getLengthTask -- no caller to return to.  
  
FIVE:  Back in AccessTheWebAsync.  
           Task getStringTask is complete.  
           Processing the return statement.  
           Exiting from AccessTheWebAsync.  
  
SIX:   Back in startButton_Click.  
           Task getLengthTask is finished.  
           Result from AccessTheWebAsync is stored in contentLength.  
           About to display contentLength and exit.  
  
Length of the downloaded string: 33946.  
```  
  
## <a name="set-up-the-program"></a>Configurar el programa  
 Puede descargar el código que utiliza en este tema de MSDN o crearla usted mismo.  
  
> [!NOTE]
>  Para ejecutar el ejemplo, debe tener Visual Studio 2012 o posterior y .NET Framework 4.5 o posterior, instalado en el equipo.  
  
### <a name="download-the-program"></a>Descargue el programa  
 Puede descargar la aplicación de este tema de [ejemplo Async: flujo de Control en programas Async](http://go.microsoft.com/fwlink/?LinkId=255285). Los siguientes pasos se abra y ejecuten el programa.  
  
1.  Descomprima el archivo descargado y, a continuación, inicie Visual Studio.  
  
2.  En la barra de menús, elija **Archivo**, **Abrir**, **Proyecto o solución**.  
  
3.  Navegue hasta la carpeta que contiene el código de ejemplo sin comprimir, abra el archivo de solución (.sln) y, a continuación, elija la tecla F5 para compilar y ejecutar el proyecto.  
  
### <a name="build-the-program-yourself"></a>Compilar el programa usted mismo  
 El siguiente proyecto de Windows Presentation Foundation (WPF) contiene el ejemplo de código de este tema.  
  
 Para ejecutar el proyecto, realice los pasos siguientes:  
  
1.  Inicie Visual Studio.  
  
2.  En la barra de menús, elija **Archivo**, **Nuevo**, **Proyecto**.  
  
     Aparece el cuadro de diálogo **Nuevo proyecto** .  
  
3.  En el **plantillas instaladas** panel, elija **Visual Basic**y, a continuación, elija **aplicación WPF** de la lista de tipos de proyecto.  
  
4.  Escriba `AsyncTracer` como el nombre del proyecto y, a continuación, elija la **Aceptar** botón.  
  
     El proyecto nuevo aparece en **el Explorador de soluciones**.  
  
5.  En el Editor de código de Visual Studio, elija la pestaña **MainWindow.xaml** .  
  
     Si la ficha no está visible, abra el menú contextual de MainWindow.xaml en **el Explorador de soluciones**y, a continuación, elija **ver código**.  
  
6.  En el **XAML** ver de MainWindow.xaml, reemplace el código por el código siguiente.  
  
    ```vb  
    <Window  
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008" xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006" mc:Ignorable="d" x:Class="MainWindow"  
        Title="Control Flow Trace" Height="350" Width="525">  
        <Grid>  
            <Button x:Name="StartButton" Content="Start" HorizontalAlignment="Left" Margin="221,10,0,0" VerticalAlignment="Top" Width="75"/>  
            <TextBox x:Name="ResultsTextBox" HorizontalAlignment="Left" TextWrapping="Wrap" VerticalAlignment="Bottom" Width="510" Height="265" FontFamily="Lucida Console" FontSize="10" VerticalScrollBarVisibility="Visible" d:LayoutOverrides="HorizontalMargin"/>  
  
        </Grid>  
    </Window>  
  
    ```  
  
     Aparece una ventana simple que contiene un cuadro de texto y un botón en la **diseño** vista de MainWindow.xaml.  
  
7.  Agregue una referencia de <xref:System.Net.Http>.</xref:System.Net.Http>  
  
8.  En **el Explorador de soluciones**, abra el menú contextual para MainWindow.xaml.vb y, a continuación, elija **ver código**.  
  
9. En MainWindow.xaml.vb, reemplace el código con el código siguiente.  
  
    ```vb  
    ' Add an Imports statement and a reference for System.Net.Http.  
    Imports System.Net.Http  
  
    Class MainWindow  
  
        Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs) Handles StartButton.Click  
  
            ' The display lines in the example lead you through the control shifts.  
            ResultsTextBox.Text &= "ONE:   Entering StartButton_Click." & vbCrLf &  
                "           Calling AccessTheWebAsync." & vbCrLf  
  
            Dim getLengthTask As Task(Of Integer) = AccessTheWebAsync()  
  
            ResultsTextBox.Text &= vbCrLf & "FOUR:  Back in StartButton_Click." & vbCrLf &  
                "           Task getLengthTask is started." & vbCrLf &  
                "           About to await getLengthTask -- no caller to return to." & vbCrLf  
  
            Dim contentLength As Integer = Await getLengthTask  
  
            ResultsTextBox.Text &= vbCrLf & "SIX:   Back in StartButton_Click." & vbCrLf &  
                "           Task getLengthTask is finished." & vbCrLf &  
                "           Result from AccessTheWebAsync is stored in contentLength." & vbCrLf &  
                "           About to display contentLength and exit." & vbCrLf  
  
            ResultsTextBox.Text &=  
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
        End Sub  
  
        Async Function AccessTheWebAsync() As Task(Of Integer)  
  
            ResultsTextBox.Text &= vbCrLf & "TWO:   Entering AccessTheWebAsync."  
  
            ' Declare an HttpClient object.  
            Dim client As HttpClient = New HttpClient()  
  
            ResultsTextBox.Text &= vbCrLf & "           Calling HttpClient.GetStringAsync." & vbCrLf  
  
            ' GetStringAsync returns a Task(Of String).   
            Dim getStringTask As Task(Of String) = client.GetStringAsync("http://msdn.microsoft.com")  
  
            ResultsTextBox.Text &= vbCrLf & "THREE: Back in AccessTheWebAsync." & vbCrLf &  
                "           Task getStringTask is started."  
  
            ' AccessTheWebAsync can continue to work until getStringTask is awaited.  
  
            ResultsTextBox.Text &=  
                vbCrLf & "           About to await getStringTask & return a Task(Of Integer) to StartButton_Click." & vbCrLf  
  
            ' Retrieve the website contents when task is complete.  
            Dim urlContents As String = Await getStringTask  
  
            ResultsTextBox.Text &= vbCrLf & "FIVE:  Back in AccessTheWebAsync." &  
                vbCrLf & "           Task getStringTask is complete." &  
                vbCrLf & "           Processing the return statement." &  
                vbCrLf & "           Exiting from AccessTheWebAsync." & vbCrLf  
  
            Return urlContents.Length  
        End Function  
  
    End Class  
    ```  
  
10. Presione la tecla F5 para ejecutar el programa y elija el botón **Inicio** .  
  
     Debe aparecer los siguientes resultados.  
  
    ```  
    ONE:   Entering startButton_Click.  
               Calling AccessTheWebAsync.  
  
    TWO:   Entering AccessTheWebAsync.  
               Calling HttpClient.GetStringAsync.  
  
    THREE: Back in AccessTheWebAsync.  
               Task getStringTask is started.  
               About to await getStringTask & return a Task<int> to startButton_Click.  
  
    FOUR:  Back in startButton_Click.  
               Task getLengthTask is started.  
               About to await getLengthTask -- no caller to return to.  
  
    FIVE:  Back in AccessTheWebAsync.  
               Task getStringTask is complete.  
               Processing the return statement.  
               Exiting from AccessTheWebAsync.  
  
    SIX:   Back in startButton_Click.  
               Task getLengthTask is finished.  
               Result from AccessTheWebAsync is stored in contentLength.  
               About to display contentLength and exit.  
  
    Length of the downloaded string: 33946.  
    ```  
  
## <a name="trace-the-program"></a>El programa de seguimiento  
  
### <a name="steps-one-and-two"></a>Pasos UNO y DOS  
 Las dos primeros mostrar las líneas rastrear la ruta de acceso como `startButton_Click` llamadas `AccessTheWebAsync`, y `AccessTheWebAsync` llama al <xref:System.Net.Http.HttpClient>método <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>.</xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> </xref:System.Net.Http.HttpClient> de asincrónica La imagen siguiente describe las llamadas de método a método.  
  
 ![Pasos uno y dos](../../../../csharp/programming-guide/concepts/async/media/asynctrace-onetwo.png "AsyncTrace ONETWO")  
  
 El tipo de valor devuelto de ambos `AccessTheWebAsync` y `client.GetStringAsync` es <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> Para `AccessTheWebAsync`, TResult es un entero. Para `GetStringAsync`, TResult es una cadena. Para obtener más información sobre los tipos de valor devuelto de método asincrónico, vea [Async devolver tipos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
 Un método asincrónico de devolución de tarea devuelve una instancia de la tarea cuando se desplaza el control al llamador. Devuelve el control de un método asincrónico a su llamador cuando un `Await` operador se encuentra en el método llamado o cuando finaliza el método llamado. Mostrar líneas que tienen la etiqueta "Tres"a "seis" esta parte del proceso de seguimiento.  
  
### <a name="step-three"></a>Paso TRES  
 En `AccessTheWebAsync`, el método asincrónico <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>se llama para descargar el contenido de la página Web de destino.</xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> Devuelve el control de `client.GetStringAsync` a `AccessTheWebAsync` cuando `client.GetStringAsync` devuelve.  
  
 El `client.GetStringAsync` método devuelve una tarea de la cadena que se asigna a la `getStringTask` variable `AccessTheWebAsync`. La siguiente línea en el programa de ejemplo muestra la llamada a `client.GetStringAsync` y la asignación.  
  
<CodeContentPlaceHolder>5</CodeContentPlaceHolder>  
 Puede pensar de la tarea como un compromiso por `client.GetStringAsync` para generar una cadena real finalmente. Mientras tanto, si `AccessTheWebAsync` tiene trabajo que no dependa de la cadena de Promise `client.GetStringAsync`, que puede continuar el trabajo mientras `client.GetStringAsync` espera. En el ejemplo, las siguientes líneas de salida, que se denomina "Tres", representan la oportunidad de realizar un trabajo independiente  
  
<CodeContentPlaceHolder>6</CodeContentPlaceHolder>  
 La siguiente instrucción suspende el progreso en `AccessTheWebAsync` cuando `getStringTask` esperado.  
  
<CodeContentPlaceHolder>7</CodeContentPlaceHolder>  
 La siguiente imagen muestra el flujo de control de `client.GetStringAsync` para la asignación a `getStringTask` y desde la creación de `getStringTask` a la aplicación de un operador Await.  
  
 ![Paso tres](../../../../csharp/programming-guide/concepts/async/media/asynctrace-three.png "AsyncTrace tres")  
  
 La expresión await suspende `AccessTheWebAsync` hasta que `client.GetStringAsync` devuelve. Mientras tanto, el control vuelve al llamador del `AccessTheWebAsync`, `startButton_Click`.  
  
> [!NOTE]
>  Normalmente, espera la llamada a un método asincrónico inmediatamente. Por ejemplo, la siguiente asignación podría reemplazar el código anterior que crea y, a continuación, espera `getStringTask`:`Dim urlContents As String = Await client.GetStringAsync("http://msdn.microsoft.com")`  
>   
>  En este tema, el operador await se aplica más adelante para dar cabida a las líneas de salida que marcan el flujo de control a través del programa.  
  
### <a name="step-four"></a>Paso CUATRO  
 El declarado tipo de valor devuelto de `AccessTheWebAsync` es `Task(Of Integer)`. Por lo tanto, cuando `AccessTheWebAsync` está suspendido, devuelve una tarea de entero en `startButton_Click`. Debe entender que la tarea devuelta no es `getStringTask`. La tarea devuelta es una nueva tarea de entero que representa lo que falta por hacer en el método suspendido, `AccessTheWebAsync`. La tarea es una promesa de `AccessTheWebAsync` para producir un entero cuando se completa la tarea.  
  
 La instrucción siguiente asigna esta tarea a la `getLengthTask` variable.  
  
<CodeContentPlaceHolder>8</CodeContentPlaceHolder>  
 Como en `AccessTheWebAsync`, `startButton_Click` puede continuar con el trabajo que no dependa de los resultados de la tarea asincrónica (`getLengthTask`) hasta que la tarea se espera. Las siguientes líneas de salida representan ese trabajo.  
  
<CodeContentPlaceHolder>9</CodeContentPlaceHolder>  
 Progreso de `startButton_Click` se suspende cuando `getLengthTask` esperado. Suspende la siguiente instrucción de asignación `startButton_Click` hasta `AccessTheWebAsync` completada.  
  
<CodeContentPlaceHolder>10</CodeContentPlaceHolder>  
 En la siguiente ilustración, las flechas muestran el flujo de control de la expresión await en `AccessTheWebAsync` a la asignación de un valor a `getLengthTask`, seguido por el procesamiento normal en `startButton_Click` hasta `getLengthTask` esperado.  
  
 ![Paso cuatro](../../../../csharp/programming-guide/concepts/async/media/asynctrace-four.png "AsyncTrace cuatro")  
  
### <a name="step-five"></a>Paso CINCO  
 Cuando `client.GetStringAsync` indica que ha finalizado, el procesamiento en `AccessTheWebAsync` se libera de la suspensión y puede continuar más allá de la instrucción await. Las siguientes líneas de salida representan la reanudación del procesamiento.  
  
<CodeContentPlaceHolder>11</CodeContentPlaceHolder>  
 El operando de la instrucción return, `urlContents.Length`, se almacena en la tarea que `AccessTheWebAsync` devuelve. La expresión await recupera ese valor de `getLengthTask` en `startButton_Click`.  
  
 La siguiente imagen muestra la transferencia de control después de `client.GetStringAsync` (y `getStringTask`) están completos.  
  
 ![Paso cinco](../../../../csharp/programming-guide/concepts/async/media/asynctrace-five.png "AsyncTrace cinco")  
  
 `AccessTheWebAsync`se ejecuta hasta el final y el control se devuelve a `startButton_Click`, que está esperando la finalización.  
  
### <a name="step-six"></a>Paso SEIS  
 Cuando `AccessTheWebAsync` señala que haya finalizado, el procesamiento puede continuar más allá de la instrucción await en `startButton_Async`. De hecho, el programa no tiene nada más que hacer.  
  
 Las siguientes líneas de salida representan la reanudación del procesamiento en `startButton_Async`:  
  
<CodeContentPlaceHolder>12</CodeContentPlaceHolder>  
 La expresión await recupera de `getLengthTask` el valor entero que es el operando de la instrucción return en `AccessTheWebAsync`. La instrucción siguiente asigna ese valor a la `contentLength` variable.  
  
<CodeContentPlaceHolder>13</CodeContentPlaceHolder>  
 La siguiente imagen muestra la devolución del control de `AccessTheWebAsync` a `startButton_Click`.  
  
 ![Paso seis](../../../../csharp/programming-guide/concepts/async/media/asynctrace-six.png "AsyncTrace seis")  
  
## <a name="see-also"></a>Vea también  
 [Programación asincrónica con Async y Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)   
 [Tipos de valor devueltos de Async (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md)   
 [Tutorial: Acceso a la Web usando Async y Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)   
 [Ejemplo ASYNC: Flujo de Control en programas asincrónicos (C# y Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=255285)
