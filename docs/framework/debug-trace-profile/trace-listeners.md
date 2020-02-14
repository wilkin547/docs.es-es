---
title: Agentes de escucha de seguimiento
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Listener object types
- listeners
- Trace class, listeners
- trace listeners, about trace listeners
- Listeners collection
- trace listeners
- tracing [.NET Framework], trace listeners
- logs, trace listeners
ms.assetid: 444b0d33-67ea-4c36-9e94-79c50f839025
ms.openlocfilehash: a51c046a296fbb62d21c7784cf7c1e78b700f3e9
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216143"
---
# <a name="trace-listeners"></a>Agentes de escucha de seguimiento
Al usar **Trace**, **Debug** y <xref:System.Diagnostics.TraceSource>, debe disponer de un mecanismo para recopilar y grabar los mensajes que se envíen. Los *agentes de escucha* reciben los mensajes de seguimiento. El propósito de un agente de escucha es recopilar, almacenar y transferir mensajes de seguimiento. Los agentes de escucha dirigen el resultado del seguimiento a un destino adecuado, como un registro, una ventana o un archivo de texto.  
  
 Los agentes de escucha están disponibles para las clases **Debug**, **Trace** y <xref:System.Diagnostics.TraceSource>, cada una de las cuales puede enviar sus resultados a una variedad de objetos de escucha. A continuación se indican los agentes de escucha predefinidos más usados:  
  
- Un <xref:System.Diagnostics.TextWriterTraceListener> redirige los resultados a una instancia de la clase <xref:System.IO.TextWriter> o a cualquier cosa que sea una clase <xref:System.IO.Stream>. También puede escribir en la consola o en un archivo, ya que ambos son clases <xref:System.IO.Stream>.  
  
- Un <xref:System.Diagnostics.EventLogTraceListener> redirige los resultados a un registro de eventos.  
  
- Un <xref:System.Diagnostics.DefaultTraceListener> emite mensajes **Write** y **WriteLine** a **OutputDebugString** y al método **Debugger.Log**. En Visual Studio, esto hace que los mensajes de depuración aparezcan en la ventana Resultados. También se envían mensajes **Fail** y **Assert** a la API de Windows **OutputDebugString** y al método **Debugger.Log**, y también hacen que se muestre un cuadro de mensaje. Este comportamiento es el predeterminado de los mensajes **Debug** y **Trace**, porque **DefaultTraceListener** se incluye automáticamente en cada colección de `Listeners` y es el único agente de escucha que se incluye automáticamente.  
  
- Un <xref:System.Diagnostics.ConsoleTraceListener> dirige los resultados del seguimiento o de la depuración a los resultados estándar o al flujo de error estándar.  
  
- Un <xref:System.Diagnostics.DelimitedListTraceListener> dirige los resultados del seguimiento o de la depuración a un escritor de texto, como un escritor de secuencias, o a una secuencia, como una secuencia de archivo. La salida del seguimiento se encuentra en un formato de texto delimitado que usa el delimitador especificado por la propiedad <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A>.  
  
- Un <xref:System.Diagnostics.XmlWriterTraceListener> dirige los resultados del seguimiento o de la depuración como datos codificados en XML a un <xref:System.IO.TextWriter> o a un <xref:System.IO.Stream>, como un <xref:System.IO.FileStream>.  
  
 Si quiere que algún agente de escucha además del <xref:System.Diagnostics.DefaultTraceListener> reciba los resultados de **Debug**, **Trace** y <xref:System.Diagnostics.TraceSource>, debe agregarlo a la colección de `Listeners`. Para más información, vea [Cómo: Crear e inicializar agentes de escucha de seguimiento](how-to-create-and-initialize-trace-listeners.md) y [Cómo: Utilizar TraceSource y filtros con agentes de escucha de seguimiento](how-to-use-tracesource-and-filters-with-trace-listeners.md). Todos los agentes de escucha de la colección **Listeners** reciben los mismos mensajes de los métodos de resultados de seguimiento. Por ejemplo, supongamos que configura dos agentes de escucha: **TextWriterTraceListener** y **EventLogTraceListener**. Cada agente de escucha recibe el mismo mensaje. **TextWriterTraceListener** dirigiría sus resultados a una secuencia y **EventLogTraceListener** dirigiría los suyos a un registro de eventos.  
  
 En el siguiente ejemplo se muestra cómo enviar resultados a la colección **Listeners**.  
  
```vb  
' Use this example when debugging.  
Debug.WriteLine("Error in Widget 42")  
' Use this example when tracing.  
Trace.WriteLine("Error in Widget 42")  
```  
  
```csharp  
// Use this example when debugging.  
System.Diagnostics.Debug.WriteLine("Error in Widget 42");  
// Use this example when tracing.  
System.Diagnostics.Trace.WriteLine("Error in Widget 42");  
```  
  
 La depuración y el seguimiento comparten la misma colección **Listeners**, por lo que si se agrega un objeto de escucha a una colección de **Debug.Listeners** en la aplicación, se agrega también a la colección **Trace.Listeners**.  
  
 En el siguiente ejemplo se indica cómo utilizar un agente de escucha para enviar información de seguimiento a una consola:  
  
```vb  
Trace.Listeners.Clear()  
Trace.Listeners.Add(New TextWriterTraceListener(Console.Out))  
```  
  
```csharp  
System.Diagnostics.Trace.Listeners.Clear();  
System.Diagnostics.Trace.Listeners.Add(  
   new System.Diagnostics.TextWriterTraceListener(Console.Out));  
```  
  
## <a name="developer-defined-listeners"></a>Agentes de escucha definidos por el desarrollador  
 Puede definir sus propios agentes de escucha heredándolos de la clase base **TraceListener** y reemplazando los métodos de esa clase por métodos personalizados. Para obtener más información sobre cómo crear agentes de escucha definidos por el desarrollador, consulte <xref:System.Diagnostics.TraceListener> en la documentación de .NET Framework.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TraceListener>
- [Traza e instrumentación de aplicaciones](tracing-and-instrumenting-applications.md)
- [Modificadores de seguimiento](trace-switches.md)
