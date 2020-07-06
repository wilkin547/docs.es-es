---
title: 'try-catch: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- try
- try_CSharpKeyword
- catch
- catch_CSharpKeyword
helpviewer_keywords:
- catch keyword [C#]
- try-catch statement [C#]
ms.assetid: cb5503c7-bfa1-4610-8fc2-ddcd2e84c438
ms.openlocfilehash: 4715a27a94ac86c5e4955c0e8be95c6ee4a28507
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619707"
---
# <a name="try-catch-c-reference"></a>try-catch (Referencia de C#)

La instrucción try-catch consta de un bloque `try` seguido de una o más cláusulas `catch` que especifican controladores para diferentes excepciones.

Cuando se produce una excepción, Common Language Runtime (CLR) busca la instrucción `catch` que controla esta excepción. Si el método que se ejecuta actualmente no contiene un bloque `catch`, CLR busca el método que llamó el método actual, y así sucesivamente hasta la pila de llamadas. Si no existe ningún bloque `catch`, CLR muestra al usuario un mensaje de excepción no controlada y detiene la ejecución del programa.

El bloque `try` contiene el código protegido que puede producir la excepción. El bloque se ejecuta hasta que se produce una excepción o hasta que se completa correctamente. Por ejemplo, el intento siguiente de convertir un objeto `null` produce la excepción <xref:System.NullReferenceException>:

```csharp
object o2 = null;
try
{
    int i2 = (int)o2;   // Error
}
```

Aunque la cláusula `catch` puede utilizarse sin argumentos para detectar cualquier tipo de excepción, no se recomienda este uso. En general, solo debe convertir las excepciones que sabe cómo recuperar. Por lo tanto, debe especificar siempre un argumento de objeto derivado de <xref:System.Exception?displayProperty=nameWithType> Por ejemplo:

```csharp
catch (InvalidCastException e)
{
}
```

Es posible utilizar más de una cláusula `catch` específica en la misma instrucción try-catch. En este caso, el orden de las cláusulas  `catch` es importante, puesto que las cláusulas `catch` se examinan por orden. Detectar las excepciones más específicas antes que las menos específicas. El compilador genera un error si ordena los bloques de detección para que un bloque posterior nunca pueda alcanzarse.

La utilización de los argumentos `catch` es una manera de filtrar las excepciones que desea controlar.  También se puede usar una expresión de filtro que examine aún más la excepción para decidir si controlarla.  Si la expresión de filtro devuelve false, prosigue la búsqueda de un controlador.

```csharp
catch (ArgumentException e) when (e.ParamName == "…")
{
}
```

Los filtros de excepción son preferibles para detectar y volver a producir (se explica a continuación) porque los filtros dejan la pila intacta.  Si un controlador posterior vuelca la pila, puede ver la procedencia original de la excepción, más que solo la ubicación en la que se volvió a producir.  Un uso común de las expresiones de filtro de excepciones es el registro.  Puede crear una función de filtro que siempre devuelva false y que también resulte en un registro, o bien puede registrar excepciones a medida que se produzcan sin tener que controlarlas y volver a generarlas.

Se puede usar una instrucción [throw](throw.md) en un bloque `catch` para volver a iniciar la excepción detectada por la instrucción `catch`. En el ejemplo siguiente se extrae información de origen de una excepción <xref:System.IO.IOException> y, a continuación, se produce la excepción al método principal.

```csharp
catch (FileNotFoundException e)
{
    // FileNotFoundExceptions are handled here.
}
catch (IOException e)
{
    // Extract some information from this exception, and then
    // throw it to the parent method.
    if (e.Source != null)
        Console.WriteLine("IOException source: {0}", e.Source);
    throw;
}
```

Puede capturar una excepción y producir una excepción diferente. Al hacerlo, especifique la excepción que detectó como excepción interna, tal como se muestra en el ejemplo siguiente.

```csharp
catch (InvalidCastException e)
{
    // Perform some action here, and then throw a new exception.
    throw new YourCustomException("Put your error message here.", e);
}
```

También se puede volver a producir una excepción sin una condición específica es true, tal y como se muestra en el ejemplo siguiente.

```csharp
catch (InvalidCastException e)
{
    if (e.Data == null)
    {
        throw;
    }
    else
    {
        // Take some action.
    }
}
```

> [!NOTE]
> También es posible usar un filtro de excepción para obtener un resultado similar de una forma generalmente más limpia (además de no modificar la pila, tal y como se explicó anteriormente en este documento). El ejemplo siguiente tiene un comportamiento similar para los autores de llamada que el ejemplo anterior. La función inicia la excepción `InvalidCastException` de vuelta al autor de la llamada cuando `e.Data` es `null`.
>
> ```csharp
> catch (InvalidCastException e) when (e.Data != null)
> {
>     // Take some action.
> }
> ```

Desde dentro de un bloque `try`, solo deben inicializarse las variables que se declaran en el mismo. De lo contrario, puede ocurrir una excepción antes de que se complete la ejecución del bloque. Por ejemplo, en el siguiente ejemplo de código, la variable `n` se inicializa dentro del bloque `try`. Un intento de utilizar esta variable fuera del bloque `try` en la instrucción `Write(n)` generará un error del compilador.

```csharp
static void Main()
{
    int n;
    try
    {
        // Do not initialize this variable here.
        n = 123;
    }
    catch
    {
    }
    // Error: Use of unassigned local variable 'n'.
    Console.Write(n);
}
```

Para obtener más información sobre la captura,vea [try-catch-finally](try-catch-finally.md) (try-catch-finally [Referencia de C#]).

## <a name="exceptions-in-async-methods"></a>Excepciones en métodos asincrónicos

Un método asincrónico está marcado por un modificador [async](async.md) y normalmente contiene una o más instrucciones o expresiones await. Una expresión await aplica el operador [await](../operators/await.md) a <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>.

Cuando el control alcanza un `await` en el método asincrónico, el progreso del método se suspende hasta que la tarea esperada se completa. Cuando se completa la tarea, la ejecución puede reanudarse en el método. Para más información, vea [Programación asincrónica con Async y Await](../../programming-guide/concepts/async/index.md) y [Controlar el flujo en los programas asincrónicos](../../programming-guide/concepts/async/control-flow-in-async-programs.md).

La tarea completada a la que se aplica `await` puede encontrarse en un estado de error debido a una excepción no controlada en el método que devuelve la tarea. La espera de la tarea produce una excepción. Una tarea también puede terminar en un estado cancelado si se cancela el proceso asincrónico que devuelve. La espera de una tarea cancelada devuelve una `OperationCanceledException`. Para obtener más información sobre cómo cancelar un proceso asincrónico, vea [Ajustar una aplicación asincrónica (C# y Visual Basic)](../../programming-guide/concepts/async/fine-tuning-your-async-application.md).

Para detectar la excepción, espere la tarea en un bloque `try` y detéctela en el bloque asociado `catch`. Para obtener un ejemplo, vea la sección [Ejemplo de método async](#async-method-example).

Una tarea puede encontrarse en un estado de error debido a que ocurrieron varias excepciones en el método asincrónico esperado. Por ejemplo, la tarea podría ser el resultado de una llamada a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>. Cuando espera una tarea de este tipo, solo se captura una de las excepciones y no puede predecir qué excepción se capturará. Para obtener un ejemplo, vea la sección [Ejemplo de Task.WhenAll](#taskwhenall-example).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente, el bloque `try` contiene una llamada al método `ProcessString` que puede causar una excepción. La cláusula `catch` contiene el controlador de excepciones que muestra un mensaje en la pantalla. Cuando la  instrucción `throw` se llama desde dentro `ProcessString`, el sistema busca la instrucción `catch` y muestra el mensaje `Exception caught`.

[!code-csharp[csrefKeywordsExceptions#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#2)]

## <a name="two-catch-blocks-example"></a>Ejemplo de dos bloques catch

En el ejemplo siguiente, se utilizan dos bloques de detección y la excepción más específica, que es la que aparece primero, es la que se captura.

Para capturar la excepción menos específica, puede sustituir la instrucción throw en `ProcessString` por la siguiente instrucción: `throw new Exception()`.

Si coloca primero el bloque catch menos específico en el ejemplo, aparece el siguiente mensaje de error: `A previous catch clause already catches all exceptions of this or a super type ('System.Exception')`.

[!code-csharp[csrefKeywordsExceptions#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#3)]

## <a name="async-method-example"></a>Ejemplo de método async

En el ejemplo siguiente se muestra el control de excepciones de los métodos asincrónicos. Para capturar una excepción que produce una tarea asincrónica, coloque la expresión `await` en un bloque `try` y capture la excepción en un bloque `catch`.

Quite la marca de comentario de la línea `throw new Exception` en el ejemplo para demostrar el control de excepciones. La propiedad de la tarea `IsFaulted` se establece en `True`, la propiedad de la tarea `Exception.InnerException` se establece en la excepción, y la excepción se captura en el bloque `catch`.

Quite la marca de comentario de la línea `throw new OperationCanceledException` para ver lo que pasa cuando se cancela un proceso asincrónico. La propiedad de la tarea `IsCanceled` se establece en `true`, y la excepción se captura en el bloque `catch`. En algunas condiciones que no son aplicables a este ejemplo, la propiedad de la tarea `IsFaulted` se establece en `true` y `IsCanceled` se establece en `false`.

[!code-csharp[csAsyncExceptions#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csasyncexceptions/cs/class1.cs#2)]  

## <a name="taskwhenall-example"></a>Ejemplo de Task.WhenAll

En el ejemplo siguiente se muestra el control de excepciones en el que varias tareas pueden producir varias excepciones. El bloque `try` espera la tarea devuelta por una llamada a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>. La tarea se completa cuando se hayan completado las tres tareas a las que se aplica el método WhenAll.

Cada una de las tres tareas produce una excepción. El bloque `catch` se itera a través de las excepciones, que se encuentran en la propiedad `Exception.InnerExceptions` de la tarea devuelta por <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.

[!code-csharp[csAsyncExceptions#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csasyncexceptions/cs/class1.cs#4)]

## <a name="c-language-specification"></a>especificación del lenguaje C#

Para obtener más información, vea la sección sobre la [instrucción try](~/_csharplang/spec/statements.md#the-try-statement) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Instrucciones try, throw y catch (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [throw](throw.md)
- [try-finally](try-finally.md)
- [Cómo: Iniciar excepciones explícitamente](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
