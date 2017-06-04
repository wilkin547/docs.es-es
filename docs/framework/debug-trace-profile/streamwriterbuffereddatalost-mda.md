---
title: "streamWriterBufferedDataLost MDA | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "StreamWriter class, data buffering problems"
  - "managed debugging assistants (MDAs), StreamWriter data buffering"
  - "buffers, StreamWriter problems"
  - "MDAs (managed debugging assistants), StreamWriter data buffering"
  - "StreamWriter buffered data lost"
  - "data buffering problems"
  - "streamWriterBufferedDataLost MDA"
ms.assetid: 6e5c07be-bc5b-437a-8398-8779e23126ab
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# streamWriterBufferedDataLost MDA
El asistente para la depuración administrada \(MDA\) `streamWriterBufferedDataLost` se activa cuando se escribe en <xref:System.IO.StreamWriter>, pero no se llama subsecuentemente al método <xref:System.IO.StreamWriter.Flush%2A> o <xref:System.IO.StreamWriter.Close%2A> antes de destruir la instancia de <xref:System.IO.StreamWriter>.  Cuando este MDA está habilitado, el motor en tiempo de ejecución determina si todavía existen datos almacenados en búfer dentro del escritor <xref:System.IO.StreamWriter>.  Si existen datos almacenados en búfer, se activa el MDA.  Llamar a los métodos <xref:System.GC.Collect%2A> y <xref:System.GC.WaitForPendingFinalizers%2A> puede obligar a que se ejecuten los finalizadores.  De lo contrario, los finalizadores ejecutarán en momentos aparentemente arbitrarios y posiblemente no se ejecuten al salir del proceso.  Ejecutar explícitamente los finalizadores con este MDA habilitado ayudará a reproducir este tipo de problema con más confiabilidad.  
  
## Síntomas  
 Un <xref:System.IO.StreamWriter> no escribe los últimos 1–4 KB de datos en un archivo.  
  
## Motivo  
 El escritor <xref:System.IO.StreamWriter> almacena internamente los datos en el búfer, lo que requiere que se llame al método <xref:System.IO.StreamWriter.Close%2A> o <xref:System.IO.StreamWriter.Flush%2A> para escribir los datos almacenados en búfer en el almacén de datos subyacente.  Si no se llama adecuadamente a <xref:System.IO.StreamWriter.Close%2A> o a <xref:System.IO.StreamWriter.Flush%2A>, los datos almacenados en búfer en la instancia de <xref:System.IO.StreamWriter> podrían no escribirse de la manera esperada.  
  
 Lo siguiente es un ejemplo de código deficientemente escrito que debería detectar este MDA.  
  
```  
// Poorly written code.  
void Write()   
{  
    StreamWriter sw = new StreamWriter("file.txt");  
    sw.WriteLine("Data");  
    // Problem: forgot to close the StreamWriter.  
}  
```  
  
 El código anterior activará este MDA con más seguridad si se desencadena una recolección de elementos no utilizados y, a continuación, quedará en suspenso hasta que hayan terminado los finalizadores.  Para encontrar este tipo de problema, puede agregar el código siguiente al final del método anterior en una versión de depuración.  Esto ayudará a activar el MDA con seguridad, pero desde luego no corrige la causa del problema.  
  
```  
GC.Collect();  
GC.WaitForPendingFinalizers();  
```  
  
## Resolución  
 Asegúrese de llamar a <xref:System.IO.StreamWriter.Close%2A> o a <xref:System.IO.StreamWriter.Flush%2A> en el <xref:System.IO.StreamWriter> antes de cerrar una aplicación o cualquier bloque de código que tenga una instancia de un escritor <xref:System.IO.StreamWriter>.  Uno de los mejores mecanismos de conseguir este objetivo consiste en crear la instancia con un bloque `using` de C\# \(`Using` en Visual Basic\), que garantizará que se llamará al método <xref:System.IO.StreamWriter.Dispose%2A> del escritor, de manera que la instancia se cerrará correctamente.  
  
```  
using(StreamWriter sw = new StreamWriter("file.txt"))   
{  
    sw.WriteLine("Data");  
}  
```  
  
 El código siguiente muestra la misma solución, utilizando `try/finally` en lugar de `using`.  
  
```  
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
  
 Si no se puede usar ninguna de estas soluciones \(por ejemplo, si se almacena <xref:System.IO.StreamWriter> en una variable estática y no es fácil ejecutar código al final de su período de duración\), este problema podría evitarse llamando a <xref:System.IO.StreamWriter.Flush%2A> de <xref:System.IO.StreamWriter> después de su última utilización o establecer la propiedad <xref:System.IO.StreamWriter.AutoFlush%2A> en `true` antes de usarlo por primera vez.  
  
```  
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
  
## Efecto en el Runtime  
 Este MDA no tiene ningún efecto en tiempo de ejecución.  
  
## Resultados  
 Un mensaje que indica que se produjo esta infracción.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <streamWriterBufferedDataLost />  
  </assistants>  
</mdaConfig>  
```  
  
## Vea también  
 <xref:System.IO.StreamWriter>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)