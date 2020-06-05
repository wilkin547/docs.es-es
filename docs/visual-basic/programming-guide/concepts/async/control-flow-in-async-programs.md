---
title: Flujo de control en programas Async
ms.date: 07/20/2015
ms.assetid: b0443af7-c586-4cb0-b476-742ae4098a96
ms.openlocfilehash: 0c479b9dd2a691b1b353fac54ee3320a895b1c7f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396667"
---
# <a name="control-flow-in-async-programs-visual-basic"></a>Control Flow in Async Programs (Visual Basic) (Flujo de control en programas asincrónicos [Visual Basic])

Puede escribir y mantener los programas asincrónicos más fácilmente usando las palabras clave `Async` y `Await`. Aun así, los resultados pueden sorprenderle si no sabe cómo funciona el programa. En este tema se hace un seguimiento del flujo de control a través de un programa asincrónico simple en el que se muestra cuándo se mueve el control de un método a otro y qué información se transfiere cada vez.

> [!NOTE]
> Las palabras clave `Async` y `Await` se incluyeron en Visual Studio 2012.

En general, los métodos que contienen código asincrónico se marcan con el modificador [Async](../../../language-reference/modifiers/async.md) . En un método que está marcado con un modificador Async, puede usar un operador [Await (Visual Basic)](../../../language-reference/operators/await-operator.md) para especificar dónde se detiene el método para esperar a que se complete el proceso asincrónico al que se ha llamado. Para obtener más información, vea [programación asincrónica con Async y Await (Visual Basic)](index.md).

En el ejemplo siguiente se usan métodos asincrónicos para descargar el contenido de un sitio web especificado como una cadena y mostrar la longitud de la cadena. El ejemplo contiene los dos métodos siguientes:

- `startButton_Click`, que llama a `AccessTheWebAsync` y muestra el resultado.

- `AccessTheWebAsync`, que descarga el contenido de un sitio web como una cadena y devuelve la longitud de esta. `AccessTheWebAsync` usa un método <xref:System.Net.Http.HttpClient> asincrónico, <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>, para descargar el contenido.

Las líneas de visualización numeradas aparecen en puntos estratégicos de todo el programa para ayudarle a entender cómo se ejecuta el programa y explicar lo que ocurre en cada punto marcado. Las líneas de visualización tienen las etiquetas comprendidas entre "UNO" y "SEIS". Las etiquetas representan el orden en el que el programa alcanza estas líneas de código.

En el código siguiente se muestra un esquema del programa.

```vb
Class MainWindow

    Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs) Handles StartButton.Click

        ' ONE
        Dim getLengthTask As Task(Of Integer) = AccessTheWebAsync()

        ' FOUR
        Dim contentLength As Integer = Await getLengthTask

        ' SIX
        ResultsTextBox.Text &=
            vbCrLf & $"Length of the downloaded string: {contentLength}." & vbCrLf

    End Sub

    Async Function AccessTheWebAsync() As Task(Of Integer)

        ' TWO
        Dim client As HttpClient = New HttpClient()
        Dim getStringTask As Task(Of String) =
            client.GetStringAsync("https://msdn.microsoft.com")

        ' THREE
        Dim urlContents As String = Await getStringTask

        ' FIVE
        Return urlContents.Length
    End Function

End Class
```

Cada una de las ubicaciones etiquetadas (del "UNO" al "SEIS") muestra información sobre el estado actual del programa. Se produce el siguiente resultado:

```console
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

Puede descargar el código que se usa en este tema desde MSDN o crearlo usted mismo.

> [!NOTE]
> Para ejecutar el ejemplo, debe tener Visual Studio 2012 o posterior y el .NET Framework 4,5 o posterior instalado en el equipo.

### <a name="download-the-program"></a>Descargar el programa

Puede descargar la aplicación de este tema en [Ejemplo de Async: Controlar el flujo en los programas asincrónicos](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0). Con los siguientes pasos se abre y se ejecuta el programa.

1. Descomprima el archivo descargado e inicie Visual Studio.

2. En la barra de menús, elija **Archivo**, **Abrir**, **Proyecto o solución**.

3. Navegue hasta la carpeta que contiene el código de ejemplo descomprimido, abra el archivo de la solución (.sln) y elija la tecla F5 para compilar y ejecutar el proyecto.

### <a name="build-the-program-yourself"></a>Compilar el programa usted mismo

El siguiente proyecto de Windows Presentation Foundation (WPF) contiene el ejemplo de código de este tema.

Para ejecutar el proyecto, realice los pasos siguientes:

1. Inicie Visual Studio.

2. En la barra de menús, elija **Archivo**, **Nuevo**, **Proyecto**.

    Aparece el cuadro de diálogo **Nuevo proyecto** .

3. En el panel **plantillas instaladas** , elija **Visual Basic**y, a continuación, elija **aplicación WPF** en la lista de tipos de proyecto.

4. Escriba `AsyncTracer` como el nombre del proyecto y elija el botón **Aceptar**.

    El proyecto nuevo aparece en el **Explorador de soluciones**.

5. En el Editor de código de Visual Studio, elija la pestaña **MainWindow.xaml** .

    Si la pestaña no está visible, abra el menú contextual de MainWindow.xaml en el **Explorador de soluciones** y elija **Ver código**.

6. En la vista **XAML** de MainWindow.xaml, reemplace el código por el código siguiente.

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

    En la vista **Diseño** de MainWindow.xaml aparece una ventana simple que contiene un cuadro de texto y un botón.

7. Agregue una referencia para <xref:System.Net.Http>.

8. En **Explorador de soluciones**, abra el menú contextual de MainWindow. Xaml. VB y, a continuación, elija **Ver código**.

9. En MainWindow. Xaml. VB, reemplace el código por el código siguiente.

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
            Dim getStringTask As Task(Of String) = client.GetStringAsync("https://msdn.microsoft.com")

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

10. Presione la tecla F5 para ejecutar el programa y elija el botón **Inicio**.

    Debería aparecer el siguiente resultado:

    ```console
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

## <a name="trace-the-program"></a>Hacer un seguimiento del programa

### <a name="steps-one-and-two"></a>Pasos UNO y DOS

Las dos primeras líneas siguen la ruta de acceso a medida que `startButton_Click` llama a `AccessTheWebAsync` y `AccessTheWebAsync` llama al método <xref:System.Net.Http.HttpClient> asincrónico <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>. En la siguiente imagen se describen las llamadas de método a método.

![Pasos UNO y DOS](../../../../csharp/programming-guide/concepts/async/media/asynctrace-onetwo.png "AsyncTrace-ONETWO")

El tipo de valor devuelto de `AccessTheWebAsync` y `client.GetStringAsync` es <xref:System.Threading.Tasks.Task%601>. Para `AccessTheWebAsync`, TResult es un entero. Para `GetStringAsync`, TResult es una cadena. Para obtener más información sobre los tipos de valor devueltos de métodos asincrónicos, vea [tipos de valor devuelto asincrónico (Visual Basic)](async-return-types.md).

Un método asincrónico de devolución de tarea devuelve una instancia de la tarea cuando el control se desplaza al llamador. El control vuelve a su llamador procedente de un método asincrónico cuando se encuentra un operador `Await` en el método llamado o cuando este finaliza. Las líneas de visualización que tienen las etiquetas comprendidas entre "TRES" y "SEIS" rastrean esta parte del proceso.

### <a name="step-three"></a>Paso TRES

En `AccessTheWebAsync`, el método asincrónico <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> se llama para descargar el contenido de la página web de destino. El control vuelve a `AccessTheWebAsync` procedente de `client.GetStringAsync` cuando se devuelve `client.GetStringAsync`.

El método `client.GetStringAsync` devuelve una tarea de la cadena que se asigna a la variable `getStringTask` en `AccessTheWebAsync`. En la siguiente línea del programa de ejemplo se muestra la llamada a `client.GetStringAsync` y la asignación.

```vb
Dim getStringTask As Task(Of String) = client.GetStringAsync("https://msdn.microsoft.com")
```

Puede considerar la tarea como una promesa de `client.GetStringAsync` de generar una cadena real. Mientras tanto, si `AccessTheWebAsync` tiene trabajo que no depende de la cadena prometida de `client.GetStringAsync`, dicho trabajo puede continuar mientras `client.GetStringAsync` espera. En el ejemplo, las siguientes líneas de salida, que tienen la etiqueta "TRES", representan la oportunidad de realizar un trabajo independiente

```console
THREE: Back in AccessTheWebAsync.
           Task getStringTask is started.
           About to await getStringTask & return a Task<int> to startButton_Click.
```

 La siguiente instrucción suspende el progreso en `AccessTheWebAsync` cuando se espera a `getStringTask`.

```vb
Dim urlContents As String = Await getStringTask
```

En la imagen siguiente se muestra el flujo de control desde `client.GetStringAsync` hasta la asignación hasta la `getStringTask` creación de `getStringTask` a la aplicación de un operador Await.

![Paso tres](../../../../csharp/programming-guide/concepts/async/media/asynctrace-three.png "AsyncTrace-tres")

La expresión await suspende `AccessTheWebAsync` hasta que se devuelva `client.GetStringAsync`. Mientras tanto, el control vuelve al llamador de `AccessTheWebAsync`, `startButton_Click`.

> [!NOTE]
> Normalmente se espera la llamada a un método asincrónico de forma inmediata. Por ejemplo, la siguiente asignación podría reemplazar el código anterior que crea y espera `getStringTask`: `Dim urlContents As String = Await client.GetStringAsync("https://msdn.microsoft.com")`
>
> En este tema, el operador await se aplica más adelante para dar cabida a las líneas de salida que marcan el flujo de control a través del programa.

### <a name="step-four"></a>Paso CUATRO

El tipo de valor devuelto declarado de `AccessTheWebAsync` es `Task(Of Integer)`. Por lo tanto, cuando se suspende `AccessTheWebAsync`, devuelve una tarea de entero en `startButton_Click`. Debe entender que la tarea devuelta no es `getStringTask`. La tarea devuelta es una nueva tarea de entero que representa lo que falta por hacer en el método suspendido, `AccessTheWebAsync`. La tarea es una promesa de `AccessTheWebAsync` de generar un entero cuando finalice la tarea.

La siguiente instrucción asigna esta tarea a la variable `getLengthTask`.

```vb
Dim getLengthTask As Task(Of Integer) = AccessTheWebAsync()
```

Como en `AccessTheWebAsync`, `startButton_Click` puede continuar con el trabajo que no depende de los resultados de la tarea asincrónica (`getLengthTask`) hasta que se espere la tarea. Las siguientes líneas de salida representan ese trabajo:

```console
FOUR:  Back in startButton_Click.
           Task getLengthTask is started.
           About to await getLengthTask -- no caller to return to.
```

El progreso de `startButton_Click` se suspende cuando se espera `getLengthTask`. La siguiente instrucción de asignación suspende `startButton_Click` hasta que concluya `AccessTheWebAsync`.

```vb
Dim contentLength As Integer = Await getLengthTask
```

En la siguiente ilustración, las flechas muestran el flujo de control desde la expresión await en `AccessTheWebAsync` hasta la asignación de un valor a `getLengthTask`, seguido del procesamiento normal en `startButton_Click` hasta que se espera a `getLengthTask`.

![Paso cuatro](../../../../csharp/programming-guide/concepts/async/media/asynctrace-four.png "AsyncTrace-cuatro")

### <a name="step-five"></a>Paso CINCO

Cuando `client.GetStringAsync` indica que ha finalizado, el procesamiento de `AccessTheWebAsync` sale de la suspensión y puede continuar una vez superada la instrucción await. Las siguientes líneas de salida representan la reanudación del procesamiento:

```console
FIVE:  Back in AccessTheWebAsync.
           Task getStringTask is complete.
           Processing the return statement.
           Exiting from AccessTheWebAsync.
```

El operando de la instrucción de devolución, `urlContents.Length`, se almacena en la tarea que devuelve `AccessTheWebAsync`. La expresión await recupera ese valor de `getLengthTask` en `startButton_Click`.

En la siguiente imagen se muestra la transferencia de control una vez concluido `client.GetStringAsync` (y `getStringTask`).

![Paso CINCO](../../../../csharp/programming-guide/concepts/async/media/asynctrace-five.png "AsyncTrace-cinco")

`AccessTheWebAsync` se ejecuta hasta el final y el control vuelve a `startButton_Click`, que espera la finalización.

### <a name="step-six"></a>Paso SEIS

Cuando `AccessTheWebAsync` indica que ha finalizado, el procesamiento puede continuar una vez superada la instrucción await en `startButton_Async`. De hecho, el programa no tiene nada más que hacer.

En las siguientes líneas de salida se representa la reanudación del procesamiento en `startButton_Async`:

```console
SIX:   Back in startButton_Click.
           Task getLengthTask is finished.
           Result from AccessTheWebAsync is stored in contentLength.
           About to display contentLength and exit.
```

La expresión await recupera de `getLengthTask` el valor entero que es el operando de la instrucción de devolución de `AccessTheWebAsync`. La siguiente instrucción asigna ese valor a la variable `contentLength`.

```vb
Dim contentLength As Integer = Await getLengthTask
```

En la siguiente imagen se muestra la devolución del control de `AccessTheWebAsync` a `startButton_Click`.

![Paso SEIS](../../../../csharp/programming-guide/concepts/async/media/asynctrace-six.png "AsyncTrace-seis")

## <a name="see-also"></a>Consulte también

- [Programación asincrónica con Async y Await (Visual Basic)](index.md)
- [Async Return Types (Visual Basic)](async-return-types.md) (Tipos de valor devuelto de Async [Visual Basic])
- [Tutorial: Acceso a web usando Async y Await (C# y Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Ejemplo de Async: Controlar el flujo en los programas asincrónicos (C# y Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0)
