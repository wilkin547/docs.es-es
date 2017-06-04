---
title: "Trace Listeners | Microsoft Docs"
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
  - "Listener object types"
  - "listeners"
  - "Trace class, listeners"
  - "trace listeners, about trace listeners"
  - "Listeners collection"
  - "trace listeners"
  - "tracing [.NET Framework], trace listeners"
  - "logs, trace listeners"
ms.assetid: 444b0d33-67ea-4c36-9e94-79c50f839025
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# Trace Listeners
Al usar **Rastrear**, **Depurar** y <xref:System.Diagnostics.TraceSource>, debe disponer de un mecanismo para recopilar y grabar los mensajes que se envíen.  Los *agentes de escucha* reciben los mensajes de seguimiento.  Un agente de escucha se encarga de recopilar, almacenar y enrutar los mensajes de seguimiento.  Los agentes de escucha dirigen los resultados del seguimiento a un destino apropiado, como un registro, una ventana o un archivo de texto.  
  
 Los agentes de escucha están disponibles para las clases **Depurar**, **Rastrear** y <xref:System.Diagnostics.TraceSource>, cada una de las cuales puede enviar sus resultados a una variedad de objetos de escucha.  A continuación se indican los agentes de escucha predefinidos más usados:  
  
-   Un <xref:System.Diagnostics.TextWriterTraceListener> redirige los resultados a una instancia de la clase <xref:System.IO.TextWriter> o a cualquier cosa que sea una clase <xref:System.IO.Stream>.  También puede escribir en la consola o en un archivo, ya que ambos son clases <xref:System.IO.Stream>.  
  
-   Un <xref:System.Diagnostics.EventLogTraceListener> redirige los resultados a un registro de eventos.  
  
-   Un <xref:System.Diagnostics.DefaultTraceListener> emite mensajes **Escribir** y **WriteLine** a **OutputDebugString** y al método **Debugger.Log**.  En Visual Studio, esto hace que los mensajes de depuración aparezcan en la ventana Resultados.  También se envían mensajes **Error** y **Aserción** a la API de Windows **OutputDebugString** y al método **Debugger.Log** y también hacen que se muestre un cuadro de mensaje  Este comportamiento es el comportamiento predeterminado de los mensajes **Depurar** y **Rastrear**, porque **DefaultTraceListener** se incluye automáticamente en cada colección de `Listeners` y es el único agente de escucha que se incluye automáticamente.  
  
-   Un <xref:System.Diagnostics.ConsoleTraceListener> dirige los resultados del seguimiento o de la depuración a los resultados estándar o al flujo de error estándar.  
  
-   Un <xref:System.Diagnostics.DelimitedListTraceListener> dirige los resultados del seguimiento o de la depuración a un escritor de texto, como un escritor de secuencias, o a una secuencia, como una secuencia de archivo. El resultado del seguimiento está en un formato de texto delimitado que utiliza el delimitador especificado por la propiedad <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A>.  
  
-   Un <xref:System.Diagnostics.XmlWriterTraceListener> dirige los resultados del seguimiento o de la depuración como datos codificados en XML a un <xref:System.IO.TextWriter> o a un <xref:System.IO.Stream>, como un <xref:System.IO.FileStream>.  
  
 Si desea que algún agente de escucha además del <xref:System.Diagnostics.DefaultTraceListener> reciba los resultados de **Depurar**, **Rastrear** y <xref:System.Diagnostics.TraceSource>, debe agregarlo a la colección de `Listeners`.  Para obtener más información, consulte [How to: Create and Initialize Trace Listeners](../../../docs/framework/debug-trace-profile/how-to-create-and-initialize-trace-listeners.md) y [How to: Use TraceSource and Filters with Trace Listeners](../../../docs/framework/debug-trace-profile/how-to-use-tracesource-and-filters-with-trace-listeners.md).  Todos los agentes de escucha de la colección **Agentes de escucha** reciben los mismos mensajes de los métodos de resultados de seguimiento.  Por ejemplo, supongamos que configura dos agentes de escucha: un **TextWriterTraceListener** y un **EventLogTraceListener**.  Cada agente de escucha recibe el mismo mensaje.  El **TextWriterTraceListener** dirigiría sus resultados a una secuencia y el **EventLogTraceListener** dirigiría los suyos a un registro de eventos.  
  
 En el siguiente ejemplo se muestra cómo enviar resultados a la colección  **Agentes de escucha**.  
  
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
  
 La depuración y el seguimiento comparten la misma colección de **Agentes de escucha**, por lo que si se agrega un objeto de escucha a una colección de **Debug.Listeners** en su aplicación, se agrega también a la colección de **Trace.Listeners**.  
  
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
  
## Agentes de escucha definidos por el desarrollador  
 Puede definir sus propios agentes de escucha heredándolos de la clase base **TraceListener** y reemplazando los métodos de dicha clase por métodos personalizados que usted tenga.  Para obtener más información sobre cómo crear agentes de escucha definidos por el desarrollador, consulte <xref:System.Diagnostics.TraceListener> en la documentación de .NET Framework.  
  
## Vea también  
 <xref:System.Diagnostics.TextWriterTraceListener>   
 <xref:System.Diagnostics.EventLogTraceListener>   
 <xref:System.Diagnostics.DefaultTraceListener>   
 <xref:System.Diagnostics.TraceListener>   
 [Tracing and Instrumenting Applications](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)   
 [Trace Switches](../../../docs/framework/debug-trace-profile/trace-switches.md)