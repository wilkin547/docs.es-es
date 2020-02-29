---
title: Patrones para la programación asincrónica
ms.date: 10/16/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous design patterns, .NET
- .NET Framework, asynchronous design patterns
ms.assetid: 4ece5c0b-f8fe-4114-9862-ac02cfe5a5d7
ms.openlocfilehash: e1efe9c3eb57f317def91e527506c358eb086679
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160058"
---
# <a name="asynchronous-programming-patterns"></a>Patrones para la programación asincrónica

.NET proporciona tres patrones para realizar las operaciones asincrónicas:  

- **Patrón asincrónico basado en tareas (TAP)** , que utiliza un método único para representar el inicio y la finalización de una operación asincrónica. TAP apareció por primera vez en .NET Framework 4. **Es el enfoque recomendado para la programación asincrónica en. NET.** Las palabras clave [2.async](../../csharp/language-reference/keywords/async.md) y [await](../../csharp/language-reference/operators/await.md) en C# y los operadores [Async](../../visual-basic/language-reference/modifiers/async.md) y [Await](../../visual-basic/language-reference/operators/await-operator.md) en Visual Basic agregan compatibilidad de lenguaje para TAP. Para más información, consulte [Patrón asincrónico basado en tareas (TAP)](task-based-asynchronous-pattern-tap.md).  

- El **modelo asincrónico basado en eventos (EAP)** , que es el patrón heredado basado en eventos para proporcionar el comportamiento asincrónico. Requiere un método con el sufijo `Async`, así como uno o más eventos, tipos de delegado de controlador de eventos y tipos derivados de `EventArg`. EAP apareció por primera vez en .NET Framework 2.0. Ya no se recomienda para nuevo desarrollo. Para más información, consulte [Modelo asincrónico basado en eventos (EAP)](event-based-asynchronous-pattern-eap.md).  

- El patrón **Modelo de programación asincrónica (APM)** (también denominado <xref:System.IAsyncResult>), que es el modelo heredado que usa la interfaz <xref:System.IAsyncResult> para ofrecer un comportamiento asincrónico. En este patrón, las operaciones sincrónicas requieren los métodos `Begin` y `End` (por ejemplo, `BeginWrite` y `EndWrite` para implementar una operación de escritura asincrónica). Este patrón ya no se recomienda para nuevo desarrollo. Para más información, consulte [Modelo de programación asincrónica (APM)](asynchronous-programming-model-apm.md).  
  
## <a name="comparison-of-patterns"></a>Comparación de patrones

Para una comparación rápida de cómo los tres patrones modelan las operaciones asincrónicas, considere un método `Read` que lea una determinada cantidad de datos en un búfer proporcionado comenzando en un desplazamiento especificado:  
  
```csharp  
public class MyClass  
{  
    public int Read(byte [] buffer, int offset, int count);  
}  
```  

El equivalente TAP de este método expondría el siguiente método `ReadAsync` único:  
  
```csharp
public class MyClass  
{  
    public Task<int> ReadAsync(byte [] buffer, int offset, int count);  
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
  
El equivalente APM expondría los métodos `BeginRead` y `EndRead`:  
  
```csharp  
public class MyClass  
{  
    public IAsyncResult BeginRead(  
        byte [] buffer, int offset, int count,
        AsyncCallback callback, object state);  
    public int EndRead(IAsyncResult asyncResult);  
}  
```  

## <a name="see-also"></a>Vea también

- [Async en profundidad](../async-in-depth.md)
- [Programación asincrónica en C#](../../csharp/async.md)
- [Programación asincrónica en F#](../../fsharp/tutorials/asynchronous-and-concurrent-programming/async.md)
- [Programación asincrónica con Async y Await (Visual Basic)](../../visual-basic/programming-guide/concepts/async/index.md)
