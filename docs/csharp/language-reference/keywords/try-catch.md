---
title: try-catch (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- try
- try_CSharpKeyword
- catch
- catch_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- catch keyword [C#]
- try-catch statement [C#]
ms.assetid: cb5503c7-bfa1-4610-8fc2-ddcd2e84c438
caps.latest.revision: 45
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 13684c7e32c52765f4d45d6a5bd2c6f8194efefe
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017

---
# <a name="try-catch-c-reference"></a>try-catch (Referencia de C#)
La instrucción try-catch consta de un bloque `try` seguido de una o más cláusulas `catch` que especifican controladores para diferentes excepciones.  
  
## <a name="remarks"></a>Comentarios  
 Cuando se produce una excepción, Common Language Runtime (CLR) busca la instrucción `catch` que controla esta excepción. Si el método que se ejecuta actualmente no contiene un bloque `catch`, CLR busca el método que llamó el método actual, y así sucesivamente hasta la pila de llamadas. Si no existe ningún bloque `catch`, CLR muestra al usuario un mensaje de excepción no controlada y detiene la ejecución del programa.  
  
 El bloque `try` contiene el código protegido que puede producir la excepción. El bloque se ejecuta hasta que se produce una excepción o hasta que se completa correctamente. Por ejemplo, el intento siguiente de convertir un objeto `null` genera la excepción <xref:System.NullReferenceException>:  
  
```csharp  
object o2 = null;  
try  
{  
    int i2 = (int)o2;   // Error  
}  
```  
  
 Aunque la cláusula `catch` puede utilizarse sin argumentos para detectar cualquier tipo de excepción, no se recomienda este uso. En general, solo debe convertir las excepciones que sabe cómo recuperar. Por consiguiente, siempre debe especificar un argumento de objeto derivado de <xref:System.Exception?displayProperty=fullName>; por ejemplo:  
  
```csharp  
catch (InvalidCastException e)   
{  
}  
```  
  
 Es posible utilizar más de una cláusula `catch` específica en la misma instrucción try-catch. En este caso, el orden de las cláusulas  `catch` es importante, puesto que las cláusulas `catch` se examinan por orden. Detectar las excepciones más específicas antes que las menos específicas. El compilador genera un error si ordena los bloques de detección para que un bloque posterior nunca pueda alcanzarse.  
  
 La utilización de los argumentos `catch` es una manera de filtrar las excepciones que desea controlar.  También puede utilizar una expresión de predicado que examine aún más la excepción para decidir si controlarla.  Si la expresión de predicado devuelve false, prosigue la búsqueda de un controlador.  
  
```csharp  
catch (ArgumentException e) when (e.ParamName == "…")  
{  
}  
```  
  
 Los filtros de excepción son preferibles para detectar y volver a producir (se explica a continuación) porque los filtros dejan la pila intacta.  Si un controlador posterior vuelca la pila, puede ver la procedencia original de la excepción, más que solo la ubicación en la que se volvió a producir.  Un uso común de las expresiones de filtro de excepciones es el registro.  Puede crear una función de predicado que siempre devuelva false y que también resulte en un registro o puede registrar excepciones a medida que se produzcan sin tener que controlarlas y volver a producirlas.  
  
 Se puede usar una instrucción [throw](../../../csharp/language-reference/keywords/throw.md) en un bloque `catch` para volver a iniciar la excepción detectada por la instrucción `catch`. En el ejemplo siguiente se extrae información de origen de una excepción <xref:System.IO.IOException> y luego se inicia la excepción en el método principal.  
  
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
  
 Para obtener más información sobre la captura,vea [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md) (try-catch-finally [Referencia de C#]).  
  
## <a name="exceptions-in-async-methods"></a>Excepciones en métodos asincrónicos  
 Un método asincrónico está marcado por un modificador [async](../../../csharp/language-reference/keywords/async.md) y normalmente contiene una o más instrucciones o expresiones await. Una expresión await aplica el operador [await](../../../csharp/language-reference/keywords/await.md) a una <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>.  
  
 Cuando el control alcanza un `await` en el método asincrónico, el progreso del método se suspende hasta que la tarea esperada se completa. Cuando se completa la tarea, la ejecución puede reanudarse en el método. Para más información, vea [Programación asincrónica con Async y Await](../../../csharp/programming-guide/concepts/async/index.md) y [Controlar el flujo en los programas asincrónicos](../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md).  
  
 La tarea completada a la que se aplica `await` puede encontrarse en un estado de error debido a una excepción no controlada en el método que devuelve la tarea. La espera de la tarea produce una excepción. Una tarea también puede terminar en un estado cancelado si se cancela el proceso asincrónico que devuelve. La espera de una tarea cancelada devuelve una `OperationCanceledException`. Para obtener más información sobre cómo cancelar un proceso asincrónico, vea [Ajustar una aplicación asincrónica (C# y Visual Basic)](http://msdn.microsoft.com/library/daaa32ea-c84c-4761-8230-c8292ffebd74).  
  
 Para detectar la excepción, espere la tarea en un bloque `try` y detéctela en el bloque asociado `catch`. Para obtener un ejemplo, vea la sección "Ejemplo".  
  
 Una tarea puede encontrarse en un estado de error debido a que ocurrieron varias excepciones en el método asincrónico esperado. Por ejemplo, la tarea podría ser el resultado de una llamada a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>. Cuando espera una tarea de este tipo, solo se captura una de las excepciones y no puede predecir qué excepción se capturará. Para obtener un ejemplo, vea la sección "Ejemplo".  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, el bloque `try` contiene una llamada al método `ProcessString` que puede causar una excepción. La cláusula `catch` contiene el controlador de excepciones que muestra un mensaje en la pantalla. Cuando la  instrucción `throw` se llama desde dentro `MyMethod`, el sistema busca la instrucción `catch` y muestra el mensaje `Exception caught`.  
  
 [!code-cs[csrefKeywordsExceptions#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, se utilizan dos bloques de detección y la excepción más específica, que es la que aparece primero, es la que se captura.  
  
 Para capturar la excepción menos específica, puede sustituir la instrucción throw en `ProcessString` por la siguiente instrucción: `throw new Exception()`.  
  
 Si coloca primero el bloque catch menos específico en el ejemplo, aparece el siguiente mensaje de error: `A previous catch clause already catches all exceptions of this or a super type ('System.Exception')`.  
  
 [!code-cs[csrefKeywordsExceptions#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_2.cs)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra el control de excepciones de los métodos asincrónicos. Para capturar una excepción que produce una tarea asincrónica, coloque la expresión `await` en un bloque `try` y capture la excepción en un bloque `catch`.  
  
 Quite la marca de comentario de la línea `throw new Exception` en el ejemplo para demostrar el control de excepciones. La propiedad de la tarea `IsFaulted` se establece en `True`, la propiedad de la tarea `Exception.InnerException` se establece en la excepción, y la excepción se captura en el bloque `catch`.  
  
 Quite la marca de comentario de la línea `throw new OperationCancelledException` para ver lo que pasa cuando se cancela un proceso asincrónico. La propiedad de la tarea `IsCanceled` se establece en `true`, y la excepción se captura en el bloque `catch`. En algunas condiciones que no son aplicables a este ejemplo, la propiedad de la tarea `IsFaulted` se establece en `true` y `IsCanceled` se establece en `false`.  
  
 [!code-cs[csAsyncExceptions#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_3.cs)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra el control de excepciones en el que varias tareas pueden producir varias excepciones. El bloque `try` espera la tarea que devuelve una llamada a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>. La tarea se completa cuando se hayan completado las tres tareas a las que se aplica el método WhenAll.  
  
 Cada una de las tres tareas produce una excepción. El bloque `catch` se itera por las excepciones, que se encuentran en la propiedad `Exception.InnerExceptions` de la tarea que devuelve <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.  
  
 [!code-cs[csAsyncExceptions#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_4.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [try, throw, and catch Statements (C++)](https://docs.microsoft.com/cpp/cpp/try-throw-and-catch-statements-cpp)  (try, throw y catch [Instrucciones, C++])  
 [Exception Handling Statements](../../../csharp/language-reference/keywords/exception-handling-statements.md)  (Instrucciones para el control de excepciones [Referencia de C#])  
 [throw](../../../csharp/language-reference/keywords/throw.md)   
 [try-finally](../../../csharp/language-reference/keywords/try-finally.md)   
 [Cómo: Iniciar excepciones explícitamente](https://msdn.microsoft.com/library/xhcbs8fz)

