---
title: "Asynchronous Programming Patterns | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "asynchronous design patterns, .NET Framework"
  - ".NET Framework, asynchronous design patterns"
ms.assetid: 4ece5c0b-f8fe-4114-9862-ac02cfe5a5d7
caps.latest.revision: 5
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 5
---
# Asynchronous Programming Patterns
.NET Framework proporciona tres patrones para realizar las operaciones asincrónicas:  
  
-   El patrón de programación asincrónica \(APM\) \(también llamado patrón <xref:System.IAsyncResult>\), en el que las operaciones asincrónicas requieren los métodos `Begin` y `End` \(por ejemplo, `BeginWrite` y `EndWrite` para las operaciones asincrónicas de escritura\).  Este patrón ya no se recomienda para nuevo desarrollo.  Para obtener más información, vea [Asynchronous Programming Model \(APM\)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md).  
  
-   El patrón asincrónico basado en eventos \(EAP\), que requiere un método que tiene el sufijo `Async` y también uno o más eventos, tipos de delegado de controlador de eventos y tipos derivados de `EventArg`.  EAP apareció por primera vez en .NET Framework 2.0.  Ya no se recomienda para nuevo desarrollo.  Para obtener más información, vea [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).  
  
-   El patrón asincrónico basado en tareas \(TAP\), que utiliza un método único para representar el inicio y la finalización de una operación asincrónica.  TAP se introdujo en .NET Framework 4 y es el método recomendado para programación asincrónica en .NET Framework.  Las palabras clave [async](../Topic/async%20\(C%23%20Reference\).md) y [await](../Topic/await%20\(C%23%20Reference\).md) en C\# y los operadores [Async](../Topic/Async%20\(Visual%20Basic\).md) y [Await](../Topic/Await%20Operator%20\(Visual%20Basic\).md) en Visual Basic agregan compatibilidad de lenguaje para TAP.  Para obtener más información, vea [Task\-based Asynchronous Pattern \(TAP\)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).  
  
## Comparación de patrones  
 Para una comparación rápida de cómo los tres patrones modelan las operaciones asincrónicas, considere un método `Read` que lea una determinada cantidad de datos en un búfer proporcionado comenzando en un desplazamiento especificado:  
  
```csharp  
public class MyClass  
{  
    public int Read(byte [] buffer, int offset, int count);  
}  
```  
  
 El equivalente de APM para este método expondría los métodos `BeginRead` y `EndRead`:  
  
```csharp  
public class MyClass  
{  
    public IAsyncResult BeginRead(  
        byte [] buffer, int offset, int count,   
        AsyncCallback callback, object state);  
    public int EndRead(IAsyncResult asyncResult);  
}  
```  
  
 El equivalente EAP expondría el siguiente conjunto de tipos y miembros:  
  
```csharp  
public class MyClass  
{  
    public void ReadAsync(byte [] buffer, int offset, int count);  
    public event ReadCompletedEventHandler ReadCompleted;  
}  
```  
  
 El equivalente TAP expondría el siguiente método `ReadAsync` único:  
  
```csharp  
public class MyClass  
{  
    public Task<int> ReadAsync(byte [] buffer, int offset, int count);  
}  
```  
  
 Para obtener información completa sobre TAP, APM y EAP, consulte los vínculos de la sección siguiente.  
  
## Temas relacionados  
  
|Título|Descripción|  
|------------|-----------------|  
|[Asynchronous Programming Model \(APM\)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md)|Describe el patrón heredado que utiliza la interfaz <xref:System.IAsyncResult> para proporcionar un comportamiento asincrónico.  Este patrón ya no se recomienda para nuevo desarrollo.|  
|[Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)|Describe el patrón heredado basado en eventos para proporcionar el comportamiento asincrónico.  Este patrón ya no se recomienda para nuevo desarrollo.|  
|[Task\-based Asynchronous Pattern \(TAP\)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)|Describe el nuevo patrón asincrónico basado en el espacio de nombres <xref:System.Threading.Tasks>.  Este patrón es el método recomendado para la programación asincrónica en .NET Framework 4 y versiones posteriores.|