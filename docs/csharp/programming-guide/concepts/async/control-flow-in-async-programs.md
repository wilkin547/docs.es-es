---
title: Controlar el flujo en los programas asincrónicos (C#)
ms.date: 07/20/2015
ms.assetid: fc92b08b-fe1d-4d07-84ab-5192fafe06bb
ms.openlocfilehash: 99f80a86f14179c5f270064a9f96e35f8611ef13
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "70204444"
---
# <a name="control-flow-in-async-programs-c"></a>Controlar el flujo en los programas asincrónicos (C#)

Puede escribir y mantener los programas asincrónicos más fácilmente usando las palabras clave `async` y `await`. Aun así, los resultados pueden sorprenderle si no sabe cómo funciona el programa. En este tema se hace un seguimiento del flujo de control a través de un programa asincrónico simple en el que se muestra cuándo se mueve el control de un método a otro y qué información se transfiere cada vez.

En general, los métodos que contienen código asincrónico se marcan con el modificador [async (C#)](../../../language-reference/keywords/async.md). En un método que está marcado con un modificador async, puede usar un operador [await (C#)](../../../language-reference/operators/await.md) para especificar dónde se para el método para esperar a que concluya un proceso asincrónico al que se ha llamado. Para obtener más información, vea [Programación asincrónica con async y await (C#)](./index.md).

En el ejemplo siguiente se usan métodos asincrónicos para descargar el contenido de un sitio web especificado como una cadena y mostrar la longitud de la cadena. El ejemplo contiene los dos métodos siguientes:

- `startButton_Click`, que llama a `AccessTheWebAsync` y muestra el resultado.

- `AccessTheWebAsync`, que descarga el contenido de un sitio web como una cadena y devuelve la longitud de esta. `AccessTheWebAsync` usa un método <xref:System.Net.Http.HttpClient> asincrónico, <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>, para descargar el contenido.

Las líneas de visualización numeradas aparecen en puntos estratégicos de todo el programa para ayudarle a entender cómo se ejecuta el programa y explicar lo que ocurre en cada punto marcado. Las líneas de visualización tienen las etiquetas comprendidas entre "UNO" y "SEIS". Las etiquetas representan el orden en el que el programa alcanza estas líneas de código.

En el código siguiente se muestra un esquema del programa.

```csharp
public partial class MainWindow : Window
{
    // . . .
    private async void startButton_Click(object sender, RoutedEventArgs e)
    {
        // ONE
        Task<int> getLengthTask = AccessTheWebAsync();

        // FOUR
        int contentLength = await getLengthTask;

        // SIX
        resultsTextBox.Text +=
            $"\r\nLength of the downloaded string: {contentLength}.\r\n";
    }

    async Task<int> AccessTheWebAsync()
    {
        // TWO
        HttpClient client = new HttpClient();
        Task<string> getStringTask =
            client.GetStringAsync("https://msdn.microsoft.com");

        // THREE
        string urlContents = await getStringTask;

        // FIVE
        return urlContents.Length;
    }
}
```

Cada una de las ubicaciones etiquetadas (del "UNO" al "SEIS") muestra información sobre el estado actual del programa. Se produce el siguiente resultado:

```output
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
> Para ejecutar el ejemplo, debe tener instalado en el equipo Visual Studio 2012 o posterior y .NET Framework 4.5 o posterior.

### <a name="download-the-program"></a>Descargar el programa

Puede descargar la aplicación para este tema en [Ejemplo de Async: Flujo de control en programas asincrónicos](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0). Con los siguientes pasos se abre y se ejecuta el programa.

1. Descomprima el archivo descargado e inicie Visual Studio.

2. En la barra de menús, elija **Archivo** > **Abrir** > **Proyecto/Solución**.

3. Navegue hasta la carpeta que contiene el código de ejemplo descomprimido, abra el archivo de la solución (.sln) y presione la tecla **F5** para compilar y ejecutar el proyecto.

### <a name="create-the-program-yourself"></a>Crear el programa usted mismo

El siguiente proyecto de Windows Presentation Foundation (WPF) contiene el ejemplo de código de este tema.

Para ejecutar el proyecto, realice los pasos siguientes:

1. Inicie Visual Studio.

2. En la barra de menús, elija **Archivo** > **Nuevo** > **Proyecto**.

     Aparece el cuadro de diálogo **Nuevo proyecto** .

3. Elija la categoría **Instalado** > **Visual C#**  > **Escritorio de Windows** y luego elija **Aplicación de WPF** en la lista de plantillas de proyecto.

4. Escriba `AsyncTracer` como el nombre del proyecto y elija el botón **Aceptar**.

     El proyecto nuevo aparece en el **Explorador de soluciones**.

5. En el Editor de código de Visual Studio, elija la pestaña **MainWindow.xaml** .

     Si la pestaña no está visible, abra el menú contextual de MainWindow.xaml en el **Explorador de soluciones** y elija **Ver código**.

6. En la vista **XAML** de MainWindow.xaml, reemplace el código por el código siguiente.

    ```csharp
    <Window
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
            xmlns:d="http://schemas.microsoft.com/expression/blend/2008" xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006" mc:Ignorable="d" x:Class="AsyncTracer.MainWindow"
            Title="Control Flow Trace" Height="350" Width="592">
        <Grid>
            <Button x:Name="startButton" Content="Start
    " HorizontalAlignment="Left" Margin="250,10,0,0" VerticalAlignment="Top" Width="75" Height="24"  Click="startButton_Click" d:LayoutOverrides="GridBox"/>
            <TextBox x:Name="resultsTextBox" HorizontalAlignment="Left" TextWrapping="Wrap" VerticalAlignment="Bottom" Width="576" Height="265" FontFamily="Lucida Console" FontSize="10" VerticalScrollBarVisibility="Visible" Grid.ColumnSpan="3"/>
        </Grid>
    </Window>
    ```

     En la vista **Diseño** de MainWindow.xaml aparece una ventana simple que contiene un cuadro de texto y un botón.

7. Agregue una referencia para <xref:System.Net.Http>.

8. En el **Explorador de soluciones**, abra el menú contextual de MainWindow.xaml.cs y después elija **Ver código**.

9. Reemplace el código del archivo MainWindow.xaml.cs por el código siguiente.

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

    // Add a using directive and a reference for System.Net.Http;
    using System.Net.Http;

    namespace AsyncTracer
    {
        public partial class MainWindow : Window
        {
            public MainWindow()
            {
                InitializeComponent();
            }

            private async void startButton_Click(object sender, RoutedEventArgs e)
            {
                // The display lines in the example lead you through the control shifts.
                resultsTextBox.Text += "ONE:   Entering startButton_Click.\r\n" +
                    "           Calling AccessTheWebAsync.\r\n";

                Task<int> getLengthTask = AccessTheWebAsync();

                resultsTextBox.Text += "\r\nFOUR:  Back in startButton_Click.\r\n" +
                    "           Task getLengthTask is started.\r\n" +
                    "           About to await getLengthTask -- no caller to return to.\r\n";

                int contentLength = await getLengthTask;

                resultsTextBox.Text += "\r\nSIX:   Back in startButton_Click.\r\n" +
                    "           Task getLengthTask is finished.\r\n" +
                    "           Result from AccessTheWebAsync is stored in contentLength.\r\n" +
                    "           About to display contentLength and exit.\r\n";

                resultsTextBox.Text +=
                    $"\r\nLength of the downloaded string: {contentLength}.\r\n";
            }

            async Task<int> AccessTheWebAsync()
            {
                resultsTextBox.Text += "\r\nTWO:   Entering AccessTheWebAsync.";

                // Declare an HttpClient object.
                HttpClient client = new HttpClient();

                resultsTextBox.Text += "\r\n           Calling HttpClient.GetStringAsync.\r\n";

                // GetStringAsync returns a Task<string>.
                Task<string> getStringTask = client.GetStringAsync("https://msdn.microsoft.com");

                resultsTextBox.Text += "\r\nTHREE: Back in AccessTheWebAsync.\r\n" +
                    "           Task getStringTask is started.";

                // AccessTheWebAsync can continue to work until getStringTask is awaited.

                resultsTextBox.Text +=
                    "\r\n           About to await getStringTask and return a Task<int> to startButton_Click.\r\n";

                // Retrieve the website contents when task is complete.
                string urlContents = await getStringTask;

                resultsTextBox.Text += "\r\nFIVE:  Back in AccessTheWebAsync." +
                    "\r\n           Task getStringTask is complete." +
                    "\r\n           Processing the return statement." +
                    "\r\n           Exiting from AccessTheWebAsync.\r\n";

                return urlContents.Length;
            }
        }
    }
    ```

10. Presione la tecla **F5** para ejecutar el programa y elija el botón **Inicio**.

    Aparece el siguiente resultado:

    ```output
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

![Pasos UNO y DOS](./media/asynctrace-onetwo.png "AsyncTrace (pasos UNO y DOS)")

El tipo de valor devuelto de `AccessTheWebAsync` y `client.GetStringAsync` es <xref:System.Threading.Tasks.Task%601>. Para `AccessTheWebAsync`, TResult es un entero. Para `GetStringAsync`, TResult es una cadena. Para obtener más información sobre los tipos de valor devuelto de los métodos asincrónicos, vea [Tipos de valor devueltos asincrónicos (C#)](./async-return-types.md).

Un método asincrónico de devolución de tarea devuelve una instancia de la tarea cuando el control se desplaza al llamador. El control vuelve a su llamador procedente de un método asincrónico cuando se encuentra un operador `await` en el método llamado o cuando este finaliza. Las líneas de visualización que tienen las etiquetas comprendidas entre "TRES" y "SEIS" rastrean esta parte del proceso.

### <a name="step-three"></a>Paso TRES

En `AccessTheWebAsync`, el método asincrónico <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> se llama para descargar el contenido de la página web de destino. El control vuelve a `AccessTheWebAsync` procedente de `client.GetStringAsync` cuando se devuelve `client.GetStringAsync`.

 El método `client.GetStringAsync` devuelve una tarea de la cadena que se asigna a la variable `getStringTask` en `AccessTheWebAsync`. En la siguiente línea del programa de ejemplo se muestra la llamada a `client.GetStringAsync` y la asignación.

```csharp
Task<string> getStringTask = client.GetStringAsync("https://msdn.microsoft.com");
```

 Puede considerar la tarea como una promesa de `client.GetStringAsync` de generar una cadena real. Mientras tanto, si `AccessTheWebAsync` tiene trabajo que no depende de la cadena prometida de `client.GetStringAsync`, dicho trabajo puede continuar mientras `client.GetStringAsync` espera. En el ejemplo, las siguientes líneas de salida, que tienen la etiqueta "TRES", representan la oportunidad de realizar un trabajo independiente

```output
THREE: Back in AccessTheWebAsync.
           Task getStringTask is started.
           About to await getStringTask & return a Task<int> to startButton_Click.
```

 La siguiente instrucción suspende el progreso en `AccessTheWebAsync` cuando se espera a `getStringTask`.

```csharp
string urlContents = await getStringTask;
```

 En la siguiente imagen se muestra el flujo de control procedente de `client.GetStringAsync` a la asignación de `getStringTask` y procedente de la creación de `getStringTask` a la aplicación de un operador await.

 ![Paso TRES](./media/asynctrace-three.png "AsyncTrace (paso TRES)")

 La expresión await suspende `AccessTheWebAsync` hasta que se devuelva `client.GetStringAsync`. Mientras tanto, el control vuelve al llamador de `AccessTheWebAsync`, `startButton_Click`.

> [!NOTE]
> Normalmente se espera la llamada a un método asincrónico de forma inmediata. Por ejemplo, la siguiente asignación podría reemplazar el código anterior que crea y espera `getStringTask`: `string urlContents = await client.GetStringAsync("https://msdn.microsoft.com");`
>
> En este tema, el operador await se aplica más adelante para dar cabida a las líneas de salida que marcan el flujo de control a través del programa.

### <a name="step-four"></a>Paso CUATRO

El tipo de valor devuelto declarado de `AccessTheWebAsync` es `Task<int>`. Por lo tanto, cuando se suspende `AccessTheWebAsync`, devuelve una tarea de entero en `startButton_Click`. Debe entender que la tarea devuelta no es `getStringTask`. La tarea devuelta es una nueva tarea de entero que representa lo que falta por hacer en el método suspendido, `AccessTheWebAsync`. La tarea es una promesa de `AccessTheWebAsync` de generar un entero cuando finalice la tarea.

La siguiente instrucción asigna esta tarea a la variable `getLengthTask`.

```csharp
Task<int> getLengthTask = AccessTheWebAsync();
```

 Como en `AccessTheWebAsync`, `startButton_Click` puede continuar con el trabajo que no depende de los resultados de la tarea asincrónica (`getLengthTask`) hasta que se espere la tarea. Las siguientes líneas de salida representan ese trabajo.

```output
FOUR:  Back in startButton_Click.
           Task getLengthTask is started.
           About to await getLengthTask -- no caller to return to.
```

 El progreso de `startButton_Click` se suspende cuando se espera `getLengthTask`. La siguiente instrucción de asignación suspende `startButton_Click` hasta que concluya `AccessTheWebAsync`.

```csharp
int contentLength = await getLengthTask;
```

 En la siguiente ilustración, las flechas muestran el flujo de control desde la expresión await en `AccessTheWebAsync` hasta la asignación de un valor a `getLengthTask`, seguido del procesamiento normal en `startButton_Click` hasta que se espera a `getLengthTask`.

 ![Paso CUATRO](./media/asynctrace-four.png "AsyncTrace (paso CUATRO)")

### <a name="step-five"></a>Paso CINCO

Cuando `client.GetStringAsync` indica que ha finalizado, el procesamiento de `AccessTheWebAsync` sale de la suspensión y puede continuar una vez superada la instrucción await. En las siguientes líneas de salida se representa la reanudación del procesamiento.

```output
FIVE:  Back in AccessTheWebAsync.
           Task getStringTask is complete.
           Processing the return statement.
           Exiting from AccessTheWebAsync.
```

 El operando de la instrucción de devolución, `urlContents.Length`, se almacena en la tarea que devuelve `AccessTheWebAsync`. La expresión await recupera ese valor de `getLengthTask` en `startButton_Click`.

 En la siguiente imagen se muestra la transferencia de control una vez concluido `client.GetStringAsync` (y `getStringTask`).

 ![Paso CINCO](./media/asynctrace-five.png "AsyncTrace (paso CINCO)")

 `AccessTheWebAsync` se ejecuta hasta el final y el control vuelve a `startButton_Click`, que espera la finalización.

### <a name="step-six"></a>Paso SEIS

Cuando `AccessTheWebAsync` indica que ha finalizado, el procesamiento puede continuar una vez superada la instrucción await en `startButton_Async`. De hecho, el programa no tiene nada más que hacer.

En las siguientes líneas de salida se representa la reanudación del procesamiento en `startButton_Async`:

```output
SIX:   Back in startButton_Click.
           Task getLengthTask is finished.
           Result from AccessTheWebAsync is stored in contentLength.
           About to display contentLength and exit.
```

 La expresión await recupera de `getLengthTask` el valor entero que es el operando de la instrucción de devolución de `AccessTheWebAsync`. La siguiente instrucción asigna ese valor a la variable `contentLength`.

```csharp
int contentLength = await getLengthTask;
```

 En la siguiente imagen se muestra la devolución del control de `AccessTheWebAsync` a `startButton_Click`.

 ![Paso SEIS](./media/asynctrace-six.png "AsyncTrace (paso SEIS)")

## <a name="see-also"></a>Vea también

- [Programación asincrónica con Async y Await (C#)](./index.md)
- [Tipos de valor devueltos asincrónicos (C#)](./async-return-types.md)
- [Tutorial: Acceso a web usando Async y Await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Ejemplo de async: Flujo de control en programas asincrónicos (C# y Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0)
