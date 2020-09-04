---
title: Acceso asincrónico a archivos (C#)
description: Aprenda a usar la característica async para acceder a archivos en C#. Puede llamar a métodos asincrónicos sin usar devoluciones de llamada ni dividir el código en métodos.
ms.date: 08/19/2020
ms.assetid: bb018fea-5313-4c80-ab3f-7c24b2145bd9
ms.openlocfilehash: 9a8db6004e8fff2cb39f0c350b403b56ea619e54
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812047"
---
# <a name="asynchronous-file-access-c"></a>Acceso asincrónico a archivos (C#)

Puede usar la característica async para acceder a archivos. Con la característica async, se puede llamar a métodos asincrónicos sin usar devoluciones de llamada ni dividir el código en varios métodos o expresiones lambda. Para convertir código sincrónico en asincrónico, basta con llamar a un método asincrónico y no a un método sincrónico y agregar algunas palabras clave al código.

Podrían considerarse los siguientes motivos para agregar asincronía a las llamadas de acceso a archivos:

> [!div class="checklist"]
>
> - La asincronía hace que las aplicaciones de interfaz de usuario tengan mayor capacidad de respuesta porque el subproceso de interfaz de usuario que inicia la operación puede realizar otro trabajo. Si el subproceso de interfaz de usuario debe ejecutar código que tarda mucho tiempo (por ejemplo, más de 50 milisegundos), puede inmovilizar la interfaz de usuario hasta que la E/S se complete y el subproceso de interfaz de usuario pueda volver a procesar la entrada de teclado y de mouse y otros eventos.
> - La asincronía mejora la escalabilidad de ASP.NET y otras aplicaciones basadas en servidor reduciendo la necesidad de subproceso. Si la aplicación usa un subproceso dedicado por respuesta y se procesa un millar de solicitudes simultáneamente, se necesitan mil subprocesos. Las operaciones asincrónicas no suelen necesitar un subproceso durante la espera. Usan el subproceso existente de finalización de E/S brevemente al final.
> - Puede que la latencia de una operación de acceso a archivos sea muy baja en las condiciones actuales, pero puede aumentar mucho en el futuro. Por ejemplo, se puede mover un archivo a un servidor que está a escala mundial.
> - La sobrecarga resultante de usar la característica Async es pequeña.
> - Las tareas asincrónicas se pueden ejecutar fácilmente en paralelo.

## <a name="use-appropriate-classes"></a>Uso de las clases adecuadas

Los ejemplos sencillos de este tema muestran cómo usar los métodos <xref:System.IO.File.WriteAllTextAsync%2A?displayProperty=nameWithType> y <xref:System.IO.File.ReadAllTextAsync%2A?displayProperty=nameWithType>. Para tener control finito sobre las operaciones de E/S de archivos, use la clase <xref:System.IO.FileStream>, que tiene una opción que hace que la E/S asincrónica se produzca en el nivel del sistema operativo. Si usa esta opción, puede evitar bloquear un subproceso del grupo de subprocesos en muchos casos. Para habilitar esta opción, especifique el argumento `useAsync=true` o `options=FileOptions.Asynchronous` en la llamada al constructor.

No puede usar esta opción con <xref:System.IO.StreamReader> y <xref:System.IO.StreamWriter> si los abre directamente al especificar una ruta de acceso de archivo. En cambio, puede usar esta opción si les proporciona un <xref:System.IO.Stream> que ha abierto la clase <xref:System.IO.FileStream>. Las llamadas asincrónicas son más rápidas en aplicaciones de interfaz de usuario aunque un subproceso del grupo de subprocesos se bloquee, porque el subproceso de interfaz de usuario no se bloquea durante la espera.

## <a name="write-text"></a>Escritura de texto

En los siguientes ejemplos se escribe texto en un archivo. En cada instrucción await, el método finaliza inmediatamente. Cuando se complete la E/S de archivo, el método se reanuda en la instrucción que sigue a la instrucción await. El modificador async se encuentra en la definición de métodos que usan la instrucción await.

### <a name="simple-example"></a>Ejemplo sencillo

:::code language="csharp" source="snippets/file-access/Program.cs" id="SimpleWrite":::

### <a name="finite-control-example"></a>Ejemplo de control finito

:::code language="csharp" source="snippets/file-access/Program.cs" id="WriteText":::

El ejemplo original incluye la instrucción `await sourceStream.WriteAsync(encodedText, 0, encodedText.Length);`, que es una contracción de las dos instrucciones siguientes:

```csharp
Task theTask = sourceStream.WriteAsync(encodedText, 0, encodedText.Length);
await theTask;
```

La primera instrucción devuelve una tarea e inicia el procesamiento de archivos. La segunda instrucción con await finaliza el método inmediatamente y devuelve otra tarea. Después, cuando se complete el procesamiento de archivos, la ejecución vuelve a la instrucción que sigue a la instrucción await.

## <a name="read-text"></a>Lectura de texto

En los ejemplos siguientes se lee texto de un archivo.

### <a name="simple-example"></a>Ejemplo sencillo

:::code language="csharp" source="snippets/file-access/Program.cs" id="SimpleRead":::

### <a name="finite-control-example"></a>Ejemplo de control finito

El texto se almacena en búfer y, en este caso, se coloca en un <xref:System.Text.StringBuilder>. A diferencia del ejemplo anterior, la evaluación de la instrucción await genera un valor. El método <xref:System.IO.Stream.ReadAsync%2A> devuelve <xref:System.Threading.Tasks.Task>\<<xref:System.Int32>>, por lo que la evaluación de await genera un valor `Int32` (`numRead`) una vez completada la operación. Para obtener más información, consulte [Tipos de valor devueltos asincrónicos (C#)](async-return-types.md).

:::code language="csharp" source="snippets/file-access/Program.cs" id="ReadText":::

## <a name="parallel-asynchronous-io"></a>E/S asincrónica en paralelo

En los siguientes ejemplos se muestra el procesamiento paralelo escribiendo 10 archivos de texto.

### <a name="simple-example"></a>Ejemplo sencillo

:::code language="csharp" source="snippets/file-access/Program.cs" id="SimpleParallelWrite":::

### <a name="finite-control-example"></a>Ejemplo de control finito

Para cada archivo, el método <xref:System.IO.Stream.WriteAsync%2A> devuelve una tarea que luego se agrega a una lista de tareas. La instrucción `await Task.WhenAll(tasks);` finaliza el método y se reanuda en el método cuando el procesamiento de archivos se completa para todas las tareas.

Tras completar las tareas, el ejemplo cierra todas las instancias de <xref:System.IO.FileStream> de un bloque `finally`. Si en lugar de ello, cada `FileStream` se ha creado en una instrucción `using`, la `FileStream` se podría desechar antes de completarse la tarea.

Cualquier aumento del rendimiento se debe casi por completo al procesamiento en paralelo y no al procesamiento asincrónico. Las ventajas de la asincronía radican en que no inmoviliza varios subprocesos ni el subproceso de interfaz de usuario.

:::code language="csharp" source="snippets/file-access/Program.cs" id="ParallelWriteText":::

Al usar los métodos <xref:System.IO.Stream.WriteAsync%2A> y <xref:System.IO.Stream.ReadAsync%2A>, puede especificar un <xref:System.Threading.CancellationToken>, que puede usar para cancelar la operación en mitad de la secuencia. Para más información, consulte [Cancelación de subprocesos administrados](../../../../standard/threading/cancellation-in-managed-threads.md).

## <a name="see-also"></a>Vea también

- [Programación asincrónica con async y await (C#)](index.md)
- [Tipos de valor devueltos asincrónicos (C#)](async-return-types.md)
