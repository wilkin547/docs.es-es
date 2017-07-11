---
title: "Aplicación de consola | Microsoft Docs"
description: "Este tutorial le enseña varias características de .NET Core y el lenguaje C#."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 883cd93d-50ce-4144-b7c9-2df28d9c11a0
ms.translationtype: Human Translation
ms.sourcegitcommit: 4437ce5d344cf06d30e31911def6287999fc6ffc
ms.openlocfilehash: 7e8cc0ed7093a90a51d1b0c50123adb73ca968aa
ms.contentlocale: es-es
ms.lasthandoff: 06/12/2017

---

<a id="console-application" class="xliff"></a>

# Aplicación de consola

<a id="introduction" class="xliff"></a>

## Introducción
Este tutorial le enseña varias características de .NET Core y el lenguaje C#. Aprenderá lo siguiente:
*   Los aspectos básicos de la interfaz de línea de comandos (CLI) de .NET Core
*   La estructura de una aplicación de consola en C#
*   E/S de consola
*   Los aspectos básicos de las API de E/S de archivo en .NET Core
*   Los aspectos básicos del modelo de programación asincrónica de tareas en .NET Core

Creará una aplicación que lea un archivo de texto y refleje el contenido de ese archivo de texto en la consola. El ritmo de la salida a la consola se ajustará para que coincida con la lectura en voz alta. Para aumentar o reducir el ritmo, presione las teclas "<" o ">".

Hay muchas características en este tutorial. Vamos a compilarlas una a una. 
<a id="prerequisites" class="xliff"></a>

## Requisitos previos
Deberá configurar la máquina para ejecutar .NET Core. Puede encontrar las instrucciones de instalación en la página de [.NET Core](https://www.microsoft.com/net/core). Puede ejecutar esta aplicación en Windows, Linux, Mac OS o en un contenedor de Docker. Deberá instalar su editor de código favorito. 
<a id="create-the-application" class="xliff"></a>

## Crear la aplicación
El primer paso es crear una nueva aplicación. Abra un símbolo del sistema y cree un nuevo directorio para la aplicación. Conviértalo en el directorio actual. Escriba el comando `dotnet new console` en el símbolo del sistema. Esta acción crea los archivos de inicio para una aplicación básica "Hola mundo".

Antes de comenzar a realizar modificaciones, vamos a recorrer los pasos para ejecutar la aplicación Hola a todos sencilla. Después de crear la aplicación, escriba `dotnet restore` en el símbolo del sistema. Este comando ejecuta el proceso de restauración de paquetes de NuGet. NuGet es un administrador de paquetes .NET. Este comando permite descargar cualquiera de las dependencias que faltan para el proyecto. Como se trata de un nuevo proyecto, ninguna de las dependencias está en su lugar, así que con la primera ejecución se descargará .NET Core Framework. Después de este paso inicial, solo deberá ejecutar `dotnet restore` al agregar nuevos paquetes dependientes, o actualizar las versiones de cualquiera de sus dependencias. Este proceso también crea el archivo de bloqueo de proyecto (project.lock.json) en el directorio del proyecto. Este archivo ayuda a administrar las dependencias del proyecto. Contiene la ubicación local de todas las dependencias del proyecto. No es necesario colocar el archivo en el control de código fuente; se generará al ejecutar `dotnet restore`. 

Después de restaurar los paquetes, ejecutará `dotnet build`. Esta acción ejecuta el motor de compilación y crea el ejecutable de aplicación. Por último, ejecute `dotnet run` para ejecutar la aplicación.  

El código de la aplicación sencilla Hola a todos está todo en Program.cs. Abra ese archivo con el editor de texto de su elección. Nos disponemos a realizar nuestros primeros cambios.
En la parte superior del archivo, verá una instrucción using:

```csharp
using System;
```

Esta instrucción indica al compilador que cualquier tipo del espacio de nombres `System` está en el ámbito. Al igual que otros lenguajes orientados a objetos que pueda haber usado, C# utiliza espacios de nombres para organizar los tipos. Este programa de Hola a todos no es diferente. Puede ver que el programa está incluido en el espacio de nombres `ConsoleApplication`. No es un nombre muy descriptivo, así que cámbielo por `TeleprompterConsole`:

```csharp
namespace TeleprompterConsole
```

<a id="reading-and-echoing-the-file" class="xliff"></a>

## Lectura y reflejo del archivo
La primera característica que se va a agregar es la capacidad de leer un archivo de texto y visualizar todo ese texto en la consola. En primer lugar, vamos a agregar un archivo de texto. Copie el archivo [sampleQuotes.txt](https://raw.githubusercontent.com/dotnet/docs/master/samples/csharp/getting-started/console-teleprompter/sampleQuotes.txt) del repositorio de GitHub de este [ejemplo](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/console-teleprompter) en su directorio del proyecto. Servirá como script para la aplicación. Si quiere obtener información sobre cómo descargar la aplicación de ejemplo de este tema, vea las instrucciones del tema [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

Luego, agregue el siguiente método a la clase Program (justo debajo del método `Main`):

```csharp
static IEnumerable<string> ReadFrom(string file)
{
    string line;
    using (var reader = File.OpenText(file))
    {
        while ((line = reader.ReadLine()) != null)
        {
            yield return line;
        }
    }
}
```

Este método usa tipos de dos nuevos espacios de nombres. Para compilar esto, deberá agregar las dos líneas siguientes a la parte superior del archivo:

```csharp
using System.Collections.Generic;
using System.IO;
```

La interfaz `IEnumerable<T>` se define en el espacio de nombres `System.Collections.Generic`. La clase @System.IO.File se define en el espacio de nombres `System.IO`.

Este método es un tipo especial de método de C# llamado*método de enumerador*. Los métodos de enumerador devuelven secuencias que se evalúan de forma diferida. Eso significa que cada elemento de la secuencia se genera como lo solicita el código que consume la secuencia. Los métodos de enumerador son métodos que contienen una o varias instrucciones `yield return`. El objeto que devuelve el método `ReadFrom` contiene el código para generar cada elemento en la secuencia. En este ejemplo, que implica la lectura de la siguiente línea de texto del archivo de origen y la devolución de esa cadena, cada vez que el código de llamada solicita el siguiente elemento de la secuencia, el código lee la siguiente línea de texto del archivo y la devuelve. Cuando el archivo se ha leído completamente, la secuencia indica que no hay más elementos.

Hay otros dos elementos de la sintaxis de C# con los que podría no estar familiarizado. La instrucción `using` de este método administra la limpieza de recursos. La variable que se inicializa en la instrucción `using` (`reader`, en este ejemplo) debe implementar la interfaz `IDisposable`. La interfaz @System.IDisposable define un único método, `Dispose`, que se debe llamar cuando sea necesario liberar el recurso. El compilador genera esa llamada cuando la ejecución llega a la llave de cierre de la instrucción `using`. El código generado por el compilador garantiza que el recurso se libera incluso si se produce una excepción desde el código en el bloqueo definido mediante la instrucción using.

La variable `reader` se define mediante la palabra clave `var`. `var` define una *variable local con tipo implícito*. Esto significa que el tipo de la variable viene determinado por el tipo de tiempo de compilación del objeto asignado a la variable. Aquí, ese es el valor devuelto por @System.IO.File.OpenText, que es un objeto @System.IO.StreamReader.
 
Ahora, vamos a rellenar el código para leer el archivo en el método `Main`: 

```csharp
var lines = ReadFrom("sampleQuotes.txt");
foreach (var line in lines)
{
    Console.WriteLine(line); 
}
```

Ejecute el programa (mediante `dotnet run` y podrá ver cada línea impresa en la consola).  

<a id="adding-delays-and-formatting-output" class="xliff"></a>

## Adición de retrasos y formato de salida
Lo que tiene se va a mostrar lejos, demasiado rápido para leerlo en voz alta. Ahora debe agregar los retrasos en la salida. Cuando empiece, estará creando parte del código principal que permite el procesamiento asincrónico. Sin embargo, a estos primeros pasos le seguirán algunos antipatrones. Los antipatrones se señalan en los comentarios cuando se agrega el código y el código se actualizará en los pasos posteriores.

Hay dos pasos hasta esta sección. Primero, actualizará el método Iterator para devolver palabras sueltas en lugar de líneas enteras. Para ello, son necesarias estas modificaciones. Reemplace la instrucción `yield return line;` por el código siguiente:

```csharp
var words = line.Split(' ');
foreach (var word in words)
{
    yield return word + " ";
}
yield return Environment.NewLine;
```

A continuación, debe modificar el modo en que se consumen las líneas del archivo y agregar un retraso después de escribir cada palabra. Reemplace la instrucción `Console.WriteLine(line)` del método `Main` por el bloqueo siguiente:

```csharp
Console.Write(line);
if (!string.IsNullOrWhiteSpace(line))
{
    var pause = Task.Delay(200);
    // Synchronously waiting on a task is an
    // anti-pattern. This will get fixed in later
    // steps.
    pause.Wait();
}
```

La clase `Task` está en el espacio de nombres `System.Threading.Tasks`, así que debe agregar esa instrucción `using` en la parte superior del archivo:

```csharp
using System.Threading.Tasks;
```

Ejecute el ejemplo y compruebe la salida. Ahora, se imprime cada palabra suelta, seguido de un retraso de 200 ms. Sin embargo, la salida mostrada indica algunos problemas porque el archivo de texto de origen tiene varias líneas con más de 80 caracteres sin un salto de línea. Este texto puede ser difícil de leer al desplazarse por él. Esto es fácil de corregir. Simplemente realizará el seguimiento de la longitud de cada línea y generará una nueva línea cada vez que la longitud de la línea alcance un determinado umbral. Declare una variable local después de la declaración de `words` que contiene la longitud de línea:

```csharp
var lineLength = 0;
```
 
A continuación, agregue el código siguiente después de la instrucción `yield return word + " ";` (antes de la llave de cierre):

```csharp
lineLength += word.Length + 1;
if (lineLength > 70)
{
    yield return Environment.NewLine;
    lineLength = 0;
}
```
 
Ejecute el ejemplo y podrá leer en alto a su ritmo preconfigurado.

<a id="async-tasks" class="xliff"></a>

## Tareas asincrónicas
En este paso final, agregará el código para escribir la salida de manera asincrónica en una tarea, mientras se ejecuta también otra tarea para leer la entrada del usuario si quiere aumentar o reducir la velocidad de la pantalla de texto. Incluye unos cuantos pasos y, al final, tendrá todas las actualizaciones que necesita.
El primer paso es crear un método de devolución @System.Threading.Tasks.Task asincrónico que represente el código que ha creado hasta el momento para leer y visualizar el archivo.

Agregue este método a su clase `Program` (se toma del cuerpo del método `Main`):

```csharp
private static async Task ShowTeleprompter()
{
    var words = ReadFrom("sampleQuotes.txt");
    foreach (var line in words)
    {
        Console.Write(line);
        if (!string.IsNullOrWhiteSpace(line))
        {
            await Task.Delay(200);
        }
    }
}
```

Advertirá dos cambios. Primero, en el cuerpo del método, en lugar de llamar a @System.Threading.Tasks.Task.Wait para esperar a que finalice una tarea de manera sincrónica, esta versión usa la palabra clave `await`. Para ello, debe agregar el modificador `async` a la signatura del método. Este método devuelve un objeto `Task`. Observe que no hay ninguna instrucción Return que devuelva un objeto `Task`. En su lugar, ese objeto `Task` se crea mediante el código que genera el compilador cuando usa el operador `await`. Puede imaginar que este método devuelve cuando alcanza un valor de `await`. El valor devuelto de `Task` indica que el trabajo no ha finalizado.
El método se reanuda cuando se completa la tarea en espera. Cuando se ha ejecutado hasta su finalización, el valor de `Task` devuelto indica que se ha completado.
El código de llamada puede supervisar ese valor de `Task` devuelto para determinar cuándo se ha completado.

Puede llamar a este nuevo método en su método `Main`:

```csharp
ShowTeleprompter().Wait();
```

Aquí, en `Main`, el código espera de manera sincrónica. Siempre que sea posible, debe usar el operador `await` en lugar de esperar sincrónicamente. Sin embargo, en el método `Main` de una aplicación de consola, no puede usar el operador `await`. Si así fuera, la aplicación se cerraría antes de que todas las tareas se hubieran completado.

A continuación, debe escribir el segundo método asincrónico para leer de la consola y controlar las teclas "<" y ">". Este es el método que agrega para esa tarea:

```csharp
private static async Task GetInput()
{
    var delay = 200;
    Action work = () =>
    {
        do {
            var key = Console.ReadKey(true);
            if (key.KeyChar == '>')
            {
                delay -= 10;
            }
            else if (key.KeyChar == '<')
            {
                delay += 10;
            }
        } while (true);
    };
    await Task.Run(work);
}
```

Se crea una expresión lambda que representa un delegado de @System.Action que lee una clave de la consola y modifica una variable local que representa el retraso cuando el usuario presiona las teclas "<" o ">". Este método usa @System.Console.ReadKey para bloquear y esperar a que el usuario presione una tecla.

Para finalizar esta característica, debe crear un nuevo método de devolución `async Task` que inicie estas dos tareas (`GetInput` y `ShowTeleprompter`) y también administre los datos compartidos entre ellas.
 
Es hora de crear una clase que controle los datos compartidos entre estas dos tareas. Esta clase contiene dos propiedades públicas: el retraso y una marca para indicar que el archivo se ha leído completamente:

```csharp
namespace TeleprompterConsole
{
    internal class TelePrompterConfig
    {
        private object lockHandle = new object();
        public int DelayInMilliseconds { get; private set; } = 200;

        public void UpdateDelay(int increment) // negative to speed up
        {
            var newDelay = Min(DelayInMilliseconds + increment, 1000);
            newDelay = Max(newDelay, 20);
            lock (lockHandle)
            {
                DelayInMilliseconds = newDelay;
            }
        }
    }
}
```

Coloque esa clase en un archivo nuevo e inclúyala en el espacio de nombres `TeleprompterConsole`, como se ha mostrado anteriormente. También deberá agregar una instrucción `using static` para que pueda hacer referencia al método `Min` y `Max` sin la clase envolvente o los nombres de espacio de nombres. Una instrucción `using static` importa los métodos de una clase, mientras que las instrucciones `using` usadas hasta el momento han importado todas las clases de un espacio de nombres.

```csharp
using static System.Math;
```

La otra característica del lenguaje que es nueva es la instrucción `lock`. Esta instrucción garantiza que solo un subproceso pueda estar en ese código en un momento dado. Si un subproceso está en la sección bloqueada, otros subprocesos deben esperar a que el primer subproceso salga de esa sección. La instrucción `lock` usa un objeto que protege la sección de bloqueo. Esta clase sigue un giro estándar para bloquear un objeto privado en la clase.

A continuación, debe actualizar los métodos `ShowTeleprompter` y `GetInput` para usar el nuevo objeto `config`. Escriba un método final `async` de devolución de `Task` para iniciar ambas tareas y salir cuando la primera tarea finalice:

```csharp
private static async Task RunTeleprompter()
{
    var config = new TelePrompterConfig();
    var displayTask = ShowTeleprompter(config);

    var speedTask = GetInput(config);
    await Task.WhenAny(displayTask, speedTask);
}
```

El método nuevo aquí es la llamada a @System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[]). Dicha llamada crea un valor de `Task` que finaliza en cuanto alguna de las tareas de su lista de argumentos se completa.

A continuación, debe actualizar los métodos `ShowTeleprompter` y `GetInput` para usar el objeto `config` para el retraso:

```csharp
private static async Task ShowTeleprompter(TelePrompterConfig config)
{
    var words = ReadFrom("sampleQuotes.txt");
    foreach (var line in words)
    {
        Console.Write(line);
        if (!string.IsNullOrWhiteSpace(line))
        {
            await Task.Delay(config.DelayInMilliseconds);
        }
    }
    config.SetDone();
}

private static async Task GetInput(TelePrompterConfig config)
{

    Action work = () =>
    {
        do {
            var key = Console.ReadKey(true);
            if (key.KeyChar == '>')
                config.UpdateDelay(-10);
            else if (key.KeyChar == '<')
                config.UpdateDelay(10);
        } while (!config.Done);
    };
    await Task.Run(work);
}
```

Esta nueva versión de `ShowTeleprompter` llama a un nuevo método de la clase `TeleprompterConfig`. Ahora, debe actualizar `Main` para llamar a `RunTeleprompter` en lugar de a `ShowTeleprompter`:

```csharp
RunTeleprompter().Wait();
```

Para terminar, debe agregar el método `SetDone` y la propiedad `Done` a la clase `TelePrompterConfig`:

```csharp
public bool Done => done;

private bool done;

public void SetDone()
{
    done = true;    
}
```

<a id="conclusion" class="xliff"></a>

## Conclusión
En este tutorial se han mostrado varias características en torno al lenguaje C# y las bibliotecas .NET Core, relacionadas con el trabajo en aplicaciones de consola.
Puede partir de este conocimiento para explorar más sobre el lenguaje y las clases aquí presentadas. Ha visto los conceptos básicos de E/S de archivo y consola, el uso con bloqueo y sin bloqueo del modelo de programación asincrónica basado en tareas, un paseo por el lenguaje C# y cómo los programas en C# están organizados. También ha conocido la interfaz de línea de comandos y las herramientas de .NET Core.
 

