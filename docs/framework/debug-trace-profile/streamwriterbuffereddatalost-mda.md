---
title: MDA de streamWriterBufferedDataLost
ms.date: 03/30/2017
helpviewer_keywords:
- StreamWriter class, data buffering problems
- managed debugging assistants (MDAs), StreamWriter data buffering
- buffers, StreamWriter problems
- MDAs (managed debugging assistants), StreamWriter data buffering
- StreamWriter buffered data lost
- data buffering problems
- streamWriterBufferedDataLost MDA
ms.assetid: 6e5c07be-bc5b-437a-8398-8779e23126ab
ms.openlocfilehash: 18b2a5a95756ed125d26b2846c0b1ddc320463ea
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181736"
---
# <a name="streamwriterbuffereddatalost-mda"></a>MDA de streamWriterBufferedDataLost
El Asistente para la depuración administrada (MDA) `streamWriterBufferedDataLost` se activa cuando se escribe un <xref:System.IO.StreamWriter>, pero después no se llama al método <xref:System.IO.StreamWriter.Flush%2A> o <xref:System.IO.StreamWriter.Close%2A> antes de que se destruya la instancia del <xref:System.IO.StreamWriter>. Cuando este MDA está habilitado, el tiempo de ejecución determina si los datos almacenados en búfer todavía existen en <xref:System.IO.StreamWriter>. Si existen datos almacenados en búfer, se activa el MDA. Llamar a los métodos <xref:System.GC.Collect%2A> y <xref:System.GC.WaitForPendingFinalizers%2A> puede forzar la ejecución de los finalizadores. En caso contrario, los finalizadores se ejecutarán en momentos aparentemente arbitrarios y posiblemente no lo hagan en la salida del proceso. La ejecución explícita de los finalizadores con este MDA habilitado ayudará a reproducir este tipo de problema de forma más confiable.  
  
## <a name="symptoms"></a>Síntomas  
 <xref:System.IO.StreamWriter> no escribe los últimos 1-4 KB de datos en un archivo.  
  
## <a name="cause"></a>Causa  
 <xref:System.IO.StreamWriter> almacena en búfer los datos internamente, lo que requiere que se llame al método <xref:System.IO.StreamWriter.Close%2A> o <xref:System.IO.StreamWriter.Flush%2A> para escribir los datos almacenados en búfer en el almacén de datos subyacente. Si no se llama a <xref:System.IO.StreamWriter.Close%2A> o <xref:System.IO.StreamWriter.Flush%2A> adecuadamente, es posible que los datos almacenados en búfer en la instancia de <xref:System.IO.StreamWriter> no se escriban de la forma esperada.  
  
 El siguiente es un ejemplo de código mal escrito que este MDA debería detectar.  
  
```csharp  
// Poorly written code.  
void Write()
{  
    StreamWriter sw = new StreamWriter("file.txt");  
    sw.WriteLine("Data");  
    // Problem: forgot to close the StreamWriter.  
}  
```  
  
 El código anterior activará este MDA de una manera más confiable si se desencadena una recolección de elementos no utilizados y después se suspende hasta que hayan terminado los finalizadores. Para realizar un seguimiento de este tipo de problema, puede agregar el código siguiente al final del método anterior en una compilación de depuración. Esto ayudará a activar el MDA de forma confiable, pero por supuesto no soluciona la causa del problema.  
  
```csharp
GC.Collect();  
GC.WaitForPendingFinalizers();  
```  
  
## <a name="resolution"></a>Solución  
 Asegúrese de que se llama a <xref:System.IO.StreamWriter.Close%2A> o <xref:System.IO.StreamWriter.Flush%2A> en <xref:System.IO.StreamWriter> antes de cerrar una aplicación o cualquier bloque de código que tenga una instancia de <xref:System.IO.StreamWriter>. Uno de los mejores mecanismos para conseguirlo es crear la instancia con un bloque `using` de C# (`Using` en Visual Basic), que se asegurará de que se invoca el método <xref:System.IO.StreamWriter.Dispose%2A> para el escritor y, como resultado, la instancia se cerrará correctamente.  
  
```csharp
using(StreamWriter sw = new StreamWriter("file.txt"))
{  
    sw.WriteLine("Data");  
}  
```  
  
 En el código siguiente se muestra la misma solución, usando `try/finally` en lugar de `using`.  
  
```csharp
StreamWriter sw;  
try
{  
    sw = new StreamWriter("file.txt"));  
    sw.WriteLine("Data");  
}  
finally
{  
    if (sw != null)  
        sw.Close();  
}  
```  
  
 Si ninguna de estas soluciones se pueden usar (por ejemplo, si un <xref:System.IO.StreamWriter> se almacena en una variable estática y no se puede ejecutar fácilmente código al final de su duración), llamar a <xref:System.IO.StreamWriter.Flush%2A> en <xref:System.IO.StreamWriter> después de su último uso o establecer la propiedad <xref:System.IO.StreamWriter.AutoFlush%2A> en `true` antes de su primer uso debería evitar este problema.  
  
```csharp
private static StreamWriter log;  
// static class constructor.  
static WriteToFile()
{  
    StreamWriter sw = new StreamWriter("log.txt");  
    sw.AutoFlush = true;  
  
    // Publish the StreamWriter for other threads.  
    log = sw;  
}  
```  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  
 Este MDA no tiene ningún efecto en el tiempo de ejecución.  
  
## <a name="output"></a>Output  
 Un mensaje que indica que se produjo esta infracción.  
  
## <a name="configuration"></a>Configuración  
  
```xml  
<mdaConfig>  
  <assistants>  
    <streamWriterBufferedDataLost />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.IO.StreamWriter>
- [Diagnóstico de errores con asistentes para la depuración administrada](diagnosing-errors-with-managed-debugging-assistants.md)
