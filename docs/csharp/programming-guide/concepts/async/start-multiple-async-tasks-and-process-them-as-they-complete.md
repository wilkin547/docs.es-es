---
title: "Iniciar varias tareas asincrónicas y procesarlas a medida que se completan (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
ms.assetid: 25331850-35a7-43b3-ab76-3908e4346b9d
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a5339e1d2d592f3ae2a2b5c0e4e96e2bff2df64c
ms.sourcegitcommit: cec0525b2121c36198379525e69aa5388266db5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2018
---
# <a name="start-multiple-async-tasks-and-process-them-as-they-complete-c"></a>Iniciar varias tareas asincrónicas y procesarlas a medida que se completan (C#)
Si usa <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, puede iniciar varias tareas a la vez y procesarlas una por una a medida que se completen, en lugar de procesarlas en el orden en el que se han iniciado.  
  
 En el siguiente ejemplo se usa una consulta para crear una colección de tareas. Cada tarea descarga el contenido de un sitio web especificado. En cada iteración de un bucle while, una llamada awaited a `WhenAny` devuelve la tarea en la colección de tareas que termine primero su descarga. Esa tarea se quita de la colección y se procesa. El bucle se repite hasta que la colección no contiene más tareas.  
  
> [!NOTE]
>  Para ejecutar los ejemplos, debe tener Visual Studio 2012 o posterior y .NET Framework 4.5 o posterior instalados en el equipo.  
  
## <a name="downloading-the-example"></a>Descargar el ejemplo  
 Puede descargar el proyecto completo de Windows Presentation Foundation (WPF) en [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Ejemplo asincrónico: Ajustar la aplicación [C# y Visual Basic]) y después seguir estos pasos.  
  
1.  Descomprima el archivo descargado y, a continuación, inicie Visual Studio.  
  
2.  En la barra de menús, elija **Archivo**, **Abrir**, **Proyecto o solución**.  
  
3.  En el cuadro de diálogo **Abrir proyecto**, abra la carpeta que contiene el código de ejemplo que descomprimió y, a después, abra el archivo de solución (.sln) para AsyncFineTuningCS.  
  
4.  En el **Explorador de soluciones**, abra el menú contextual del proyecto **ProcessTasksAsTheyFinish** y, después, pulse **Establecer como proyecto de inicio**.  
  
5.  Pulse la tecla F5 para ejecutar el proyecto.  
  
     Pulse las teclas Ctrl+F5 para ejecutar el proyecto sin depurarlo.  
  
6.  Ejecute el proyecto varias veces para comprobar que las longitudes que se han descargado no aparecen siempre en el mismo orden.  
  
 Si no quiere descargar el proyecto, puede revisar el archivo MainWindow.xaml.cs al final de este tema.  
  
## <a name="building-the-example"></a>Compilar el ejemplo  
 Este ejemplo se agrega al código que se ha desarrollado en [Cancelar las tareas asincrónicas restantes cuando se completa una (C#)](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)[Cancelar las tareas asincrónicas restantes cuando se completa una](http://msdn.microsoft.com/library/8e800b58-235a-44b7-a02c-fa4375591d76) y usa la misma interfaz de usuario.  
  
 Para generar el ejemplo personalmente, paso a paso, siga las instrucciones de la sección "Descargar el ejemplo", pero elija **CancelAfterOneTask** como el **Proyecto de inicio**. Agregue los cambios de este tema al método `AccessTheWebAsync` de ese proyecto. Los cambios se marcan con asteriscos.  
  
 El proyecto **CancelAfterOneTask** ya incluye una consulta que, cuando se ejecuta, crea una colección de tareas. Cada llamada a `ProcessURLAsync` en el siguiente código devuelve un objeto <xref:System.Threading.Tasks.Task%601> donde `TResult` es un entero.  
  
```csharp  
IEnumerable<Task<int>> downloadTasksQuery =  
    from url in urlList select ProcessURL(url, client, ct);  
```  
  
 En el archivo MainWindow.xaml.cs del proyecto, realice los siguientes cambios en el método `AccessTheWebAsync`.  
  
-   Ejecute la consulta aplicando <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> en lugar de <xref:System.Linq.Enumerable.ToArray%2A>.  
  
    ```csharp  
    List<Task<int>> downloadTasks = downloadTasksQuery.ToList();  
    ```  
  
-   Agregue un bucle while que realice los pasos siguientes para cada tarea de la colección.  
  
    1.  Espera una llamada a `WhenAny` para identificar la primera tarea en la colección para finalizar su descarga.  
  
        ```csharp  
        Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);  
        ```  
  
    2.  Quita la tarea de la colección.  
  
        ```csharp  
        downloadTasks.Remove(firstFinishedTask);  
        ```  
  
    3.  Espera `firstFinishedTask`, que se devuelve mediante una llamada a `ProcessURLAsync`. La variable `firstFinishedTask` es un <xref:System.Threading.Tasks.Task%601> donde `TReturn` es un entero. La tarea ya está completa, pero la espera para recuperar la longitud del sitio web descargado, como se muestra en el ejemplo siguiente.  
  
        ```csharp  
        int length = await firstFinishedTask;  
        resultsTextBox.Text += String.Format("\r\nLength of the download:  {0}", length);  
        ```  
  
 Debe ejecutar el proyecto varias veces para comprobar que las longitudes que se han descargado no aparecen siempre en el mismo orden.  
  
> [!CAUTION]
>  Puede usar `WhenAny` en un bucle, como se describe en el ejemplo, para solucionar problemas que implican un número reducido de tareas. Sin embargo, otros enfoques son más eficaces si hay que procesar un gran número de tareas. Para más información y ejemplos, vea [Processing Tasks as they complete](https://blogs.msdn.microsoft.com/pfxteam/2012/08/02/processing-tasks-as-they-complete/) (Procesar tareas a medida que se completan).  
  
## <a name="complete-example"></a>Ejemplo completo  
 El código siguiente es el texto completo del archivo MainWindow.xaml.cs para el ejemplo. Los asteriscos marcan los elementos que se agregaron para este ejemplo.  
  
 Observe que debe agregar una referencia para <xref:System.Net.Http>.  
  
 Puede descargar el proyecto de [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Ejemplo asincrónico: Ajustar la aplicación [C# y Visual Basic]).  
  
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
  
// Add a using directive and a reference for System.Net.Http.  
using System.Net.Http;  
  
// Add the following using directive.  
using System.Threading;  
  
namespace ProcessTasksAsTheyFinish  
{  
    public partial class MainWindow : Window  
    {  
        // Declare a System.Threading.CancellationTokenSource.  
        CancellationTokenSource cts;  
  
        public MainWindow()  
        {  
            InitializeComponent();  
        }  
  
        private async void startButton_Click(object sender, RoutedEventArgs e)  
        {  
            resultsTextBox.Clear();  
  
            // Instantiate the CancellationTokenSource.  
            cts = new CancellationTokenSource();  
  
            try  
            {  
                await AccessTheWebAsync(cts.Token);  
                resultsTextBox.Text += "\r\nDownloads complete.";  
            }  
            catch (OperationCanceledException)  
            {  
                resultsTextBox.Text += "\r\nDownloads canceled.\r\n";  
            }  
            catch (Exception)  
            {  
                resultsTextBox.Text += "\r\nDownloads failed.\r\n";  
            }  
  
            cts = null;  
        }  
  
        private void cancelButton_Click(object sender, RoutedEventArgs e)  
        {  
            if (cts != null)  
            {  
                cts.Cancel();  
            }  
        }  
  
        async Task AccessTheWebAsync(CancellationToken ct)  
        {  
            HttpClient client = new HttpClient();  
  
            // Make a list of web addresses.  
            List<string> urlList = SetUpURLList();  
  
            // ***Create a query that, when executed, returns a collection of tasks.  
            IEnumerable<Task<int>> downloadTasksQuery =  
                from url in urlList select ProcessURL(url, client, ct);  
  
            // ***Use ToList to execute the query and start the tasks.   
            List<Task<int>> downloadTasks = downloadTasksQuery.ToList();  
  
            // ***Add a loop to process the tasks one at a time until none remain.  
            while (downloadTasks.Count > 0)  
            {  
                    // Identify the first task that completes.  
                    Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);  
  
                    // ***Remove the selected task from the list so that you don't  
                    // process it more than once.  
                    downloadTasks.Remove(firstFinishedTask);  
  
                    // Await the completed task.  
                    int length = await firstFinishedTask;  
                    resultsTextBox.Text += String.Format("\r\nLength of the download:  {0}", length);  
            }  
        }  
  
        private List<string> SetUpURLList()  
        {  
            List<string> urls = new List<string>   
            {   
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/windows/apps/br211380.aspx",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            };  
            return urls;  
        }  
  
        async Task<int> ProcessURL(string url, HttpClient client, CancellationToken ct)  
        {  
            // GetAsync returns a Task<HttpResponseMessage>.   
            HttpResponseMessage response = await client.GetAsync(url, ct);  
  
            // Retrieve the website contents from the HttpResponseMessage.  
            byte[] urlContents = await response.Content.ReadAsByteArrayAsync();  
  
            return urlContents.Length;  
        }  
    }  
}  
  
// Sample Output:  
  
// Length of the download:  226093  
// Length of the download:  412588  
// Length of the download:  175490  
// Length of the download:  204890  
// Length of the download:  158855  
// Length of the download:  145790  
// Length of the download:  44908  
// Downloads complete.  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.Tasks.Task.WhenAny%2A>  
 [Fine-Tuning Your Async Application (C#)](../../../../csharp/programming-guide/concepts/async/fine-tuning-your-async-application.md) (Ajuste de la aplicación asincrónica [C#])  
 [Programación asincrónica con async y await (C#)](../../../../csharp/programming-guide/concepts/async/index.md)  
 [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Ejemplo asincrónico: ajuste de la aplicación)
