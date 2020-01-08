---
title: Try... Detectar... Finally (instrucción)
description: Aprenda a usar el control de excepciones con Visual Basic instrucciones try/catch/finally.
ms.date: 12/07/2018
f1_keywords:
- vb.Try...Catch...Finally
- vb.when
- vb.Finally
- vb.Catch
- vb.Try
helpviewer_keywords:
- Try...Catch...Finally statements
- Try statement [Visual Basic]
- try-catch exception handling, Try...Catch...Finally statements
- error handling, while running code
- Try statement [Visual Basic], Try...Catch...Finally
- Finally keyword [Visual Basic], Try...Catch...Finally
- Catch statement [Visual Basic]
- When keyword [Visual Basic]
- Visual Basic code, handling errors while running
- structured exception handling, Try...Catch...Finally statements
ms.assetid: d6488026-ccb3-42b8-a810-0d97b9d6472b
ms.custom: seodec18
ms.openlocfilehash: eb04b6cff0847009407e38a3696e9be7c700356c
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337329"
---
# <a name="trycatchfinally-statement-visual-basic"></a>Instrucción Try...Catch...Finally (Visual Basic)

Proporciona una manera de controlar algunos o todos los errores posibles que se pueden producir en un bloque de código determinado, mientras se sigue ejecutando el código.

## <a name="syntax"></a>Sintaxis

```vb
Try
    [ tryStatements ]
    [ Exit Try ]
[ Catch [ exception [ As type ] ] [ When expression ]
    [ catchStatements ]
    [ Exit Try ] ]
[ Catch ... ]
[ Finally
    [ finallyStatements ] ]
End Try
```

## <a name="parts"></a>Componentes de

|Término|de esquema JSON|
|---|---|
|`tryStatements`|Opcional. Instrucciones en las que se puede producir un error. Puede ser una instrucción compuesta.|
|`Catch`|Opcional. Se permiten varios bloques `Catch`. Si se produce una excepción al procesar el bloque de `Try`, cada instrucción de `Catch` se examina en orden textual para determinar si controla la excepción, con `exception` que representa la excepción que se ha producido.|
|`exception`|Opcional. Cualquier nombre de variable. El valor inicial de `exception` es el valor del error producido. Se utiliza con `Catch` para especificar el error detectado. Si se omite, la instrucción `Catch` detecta cualquier excepción.|
|`type`|Opcional. Especifica el tipo de filtro de clase. Si el valor de `exception` es del tipo especificado por `type` o de un tipo derivado, el identificador se enlaza al objeto de excepción.|
|`When`|Opcional. Una instrucción `Catch` con una cláusula `When` solo detecta excepciones cuando `expression` se evalúa como `True`. Una cláusula `When` se aplica solo después de comprobar el tipo de la excepción y `expression` puede hacer referencia al identificador que representa la excepción.|
|`expression`|Opcional. Se debe poder convertir implícitamente en `Boolean`. Cualquier expresión que describa un filtro genérico. Normalmente se usa para filtrar por número de error. Se utiliza con la palabra clave `When` para especificar las circunstancias en las que se detecta el error.|
|`catchStatements`|Opcional. Instrucciones para controlar los errores que se producen en el bloque de `Try` asociado. Puede ser una instrucción compuesta.|
|`Exit Try`|Opcional. Palabra clave que sale de la estructura de `Try...Catch...Finally`. La ejecución se reanuda con el código inmediatamente posterior a la instrucción `End Try`. La instrucción `Finally` se seguirá ejecutando. No se permite en los bloques de `Finally`.|
|`Finally`|Opcional. Un bloque `Finally` siempre se ejecuta cuando la ejecución deja parte de la instrucción `Try...Catch`.|
|`finallyStatements`|Opcional. Instrucciones que se ejecutan después de que se haya producido el otro procesamiento de errores.|
|`End Try`|Finaliza la estructura de `Try...Catch...Finally`.|

## <a name="remarks"></a>Notas

Si espera que se produzca una excepción determinada durante una sección de código determinada, coloque el código en un bloque de `Try` y use un bloque de `Catch` para conservar el control y controlar la excepción si se produce.

Una instrucción `Try…Catch` está formada por un bloque `Try` seguido de una o varias cláusulas `Catch`, que especifican Controladores para distintas excepciones. Cuando se produce una excepción en un bloque `Try`, Visual Basic busca la instrucción `Catch` que controla la excepción. Si no se encuentra una instrucción `Catch` coincidente, Visual Basic examina el método que llamó al método actual, y así sucesivamente en la pila de llamadas. Si no se encuentra ningún bloque `Catch`, Visual Basic muestra al usuario un mensaje de excepción no controlada y detiene la ejecución del programa.

Puede usar más de una instrucción `Catch` en una instrucción `Try…Catch`. Si lo hace, el orden de las cláusulas `Catch` es significativo porque se examinan en orden. Detectar las excepciones más específicas antes que las menos específicas.

Las siguientes condiciones de la instrucción `Catch` son las menos específicas y detectarán todas las excepciones que derivan de la clase <xref:System.Exception>. Normalmente, debe usar una de estas variaciones como último `Catch` bloque en la estructura `Try...Catch...Finally`, después de detectar todas las excepciones específicas que espera. El flujo de control nunca puede llegar a un bloque `Catch` que siga cualquiera de estas variaciones.

- El `type` es `Exception`, por ejemplo: `Catch ex As Exception`

- La instrucción no tiene `exception` variable, por ejemplo: `Catch`

Cuando una instrucción `Try…Catch…Finally` está anidada en otro bloque de `Try`, Visual Basic primero examina cada instrucción `Catch` en el bloque de `Try` más interno. Si no se encuentra ninguna instrucción `Catch` coincidente, la búsqueda continúa en las instrucciones de `Catch` del bloque de `Try…Catch…Finally` exterior.

Las variables locales de un bloque `Try` no están disponibles en un bloque de `Catch` porque son bloques independientes. Si desea utilizar una variable en más de un bloque, declare la variable fuera de la estructura de `Try...Catch...Finally`.

> [!TIP]
> La instrucción `Try…Catch…Finally` está disponible como fragmento de código de IntelliSense. En el administrador de fragmentos de código, expanda **patrones de código: Si, para cada uno, pruebe Catch, Property, etc**. y, a continuación, **control de errores (excepciones)** . Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).

## <a name="finally-block"></a>Bloque Finally

Si tiene una o más instrucciones que se deben ejecutar antes de salir de la estructura de `Try`, utilice un bloque de `Finally`. El control pasa al bloque `Finally` justo antes de salir de la estructura de `Try…Catch`. Esto es así incluso si se produce una excepción en cualquier parte dentro de la estructura de `Try`.

Un bloque `Finally` es útil para ejecutar cualquier código que deba ejecutarse incluso si se produce una excepción. El control se pasa al bloque `Finally` independientemente de cómo salga el bloque de `Try...Catch`.

El código de un bloque de `Finally` se ejecuta incluso si el código encuentra una instrucción `Return` en un bloque `Try` o `Catch`. El control no pasa de un bloque `Try` o `Catch` al bloque `Finally` correspondiente en los casos siguientes:

- Se encuentra una [instrucción end](end-statement.md) en el bloque `Try` o `Catch`.

- Se produce una <xref:System.StackOverflowException> en el bloque de `Try` o `Catch`.

No es válido transferir explícitamente la ejecución a un bloque `Finally`. La transferencia de la ejecución fuera de un bloque `Finally` no es válida, excepto a través de una excepción.

Si una instrucción `Try` no contiene al menos un bloque de `Catch`, debe contener un bloque de `Finally`.

> [!TIP]
> Si no tiene que detectar excepciones específicas, la instrucción `Using` se comporta como un bloque `Try…Finally` y garantiza la eliminación de los recursos, independientemente de cómo salga del bloque. Esto es así incluso con una excepción no controlada. Para obtener más información, vea [Using (Instrucción)](using-statement.md).

## <a name="exception-argument"></a>Argumento de excepción

El `exception` argumento `Catch` bloque es una instancia de la clase <xref:System.Exception> o una clase que deriva de la clase `Exception`. La instancia de la clase `Exception` se corresponde con el error que se produjo en el bloque de `Try`.

Las propiedades del objeto `Exception` ayudan a identificar la causa y la ubicación de una excepción. Por ejemplo, la propiedad <xref:System.Exception.StackTrace%2A> muestra los métodos llamados que dieron lugar a la excepción, lo que le ayuda a encontrar el lugar en el que se produjo el error en el código. <xref:System.Exception.Message%2A> devuelve un mensaje que describe la excepción. <xref:System.Exception.HelpLink%2A> devuelve un vínculo a un archivo de ayuda asociado. <xref:System.Exception.InnerException%2A> devuelve el objeto `Exception` que causó la excepción actual, o devuelve `Nothing` si no hay ningún `Exception`original.

## <a name="considerations-when-using-a-trycatch-statement"></a>Consideraciones al usar una instrucción try... Catch (instrucción)

Use una instrucción `Try…Catch` solo para indicar la aparición de eventos de programa inusuales o imprevistos. Entre los motivos se incluyen los siguientes:

- La detección de excepciones en tiempo de ejecución crea una sobrecarga adicional y es probable que sea más lenta que la comprobación previa para evitar excepciones.

- Si no se controla correctamente un bloque `Catch`, es posible que la excepción no se notifique correctamente a los usuarios.

- El control de excepciones hace que un programa sea más complejo.

No siempre se necesita una instrucción `Try…Catch` para comprobar si hay una condición que es probable que se produzca. En el ejemplo siguiente se comprueba si existe un archivo antes de intentar abrirlo. Esto reduce la necesidad de detectar una excepción producida por el método <xref:System.IO.File.OpenText%2A>.

[!code-vb[VbVbalrStatements#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#94)]

Asegúrese de que el código de los bloques de `Catch` pueda notificar correctamente las excepciones a los usuarios, ya sea a través del registro seguro para subprocesos o de los mensajes adecuados. De lo contrario, es posible que las excepciones sigan siendo desconocidas.

## <a name="async-methods"></a>Métodos asincrónicos

Si marca un método con el modificador [Async](../modifiers/async.md) , puede usar el operador [Await](../operators/await-operator.md) en el método. Una instrucción con el operador `Await` suspende la ejecución del método hasta que se completa la tarea esperada. La tarea representa el trabajo en curso. Cuando finaliza la tarea asociada al operador de `Await`, la ejecución se reanuda en el mismo método. Para obtener más información, vea [flujo de control en programas Async](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md).

Una tarea devuelta por un método asincrónico puede finalizar en un estado de error, lo que indica que se completó debido a una excepción no controlada. Una tarea también puede terminar en un estado cancelado, lo que provoca que se produzca una `OperationCanceledException` fuera de la expresión Await. Para detectar cualquier tipo de excepción, coloque la `Await` expresión asociada a la tarea en un bloque de `Try` y Capture la excepción en el bloque de `Catch`. Más adelante en este tema se proporciona un ejemplo.

Una tarea puede tener un estado de error porque varias excepciones eran responsables de su error. Por ejemplo, la tarea podría ser el resultado de una llamada a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>. Cuando espera una tarea de este tipo, la excepción detectada es solo una de las excepciones y no puede predecir qué excepción se detectará. Más adelante en este tema se proporciona un ejemplo.

Una expresión de `Await` no puede estar dentro de un bloque de `Catch` o de `Finally`.

## <a name="iterators"></a>Iterators

Una función de iterador o `Get` descriptor de acceso realiza una iteración personalizada en una colección. Un iterador usa una instrucción [yield](yield-statement.md) para devolver cada elemento de la colección de uno en uno. Se llama a una función de iterador mediante un método [for each... Instrucción siguiente](for-each-next-statement.md).

Una instrucción `Yield` puede estar dentro de un bloque `Try`. Un bloque `Try` que contiene una instrucción `Yield` puede tener bloques `Catch` y puede tener un bloque `Finally`. Vea la sección "Try blocks in Visual Basic" de [iteradores](../../programming-guide/concepts/iterators.md) para obtener un ejemplo.

Una instrucción `Yield` no puede estar dentro de un bloque de `Catch` o un bloque `Finally`.

Si el cuerpo de `For Each` (fuera de la función de iterador) produce una excepción, no se ejecuta un bloque de `Catch` en la función de iterador, pero se ejecuta un bloque de `Finally` en la función de iterador. Un bloque `Catch` dentro de una función de iterador solo detecta las excepciones que se producen dentro de la función de iterador.

## <a name="partial-trust-situations"></a>Situaciones de confianza parcial

En situaciones de confianza parcial, como una aplicación hospedada en un recurso compartido de red, `Try...Catch...Finally` no detecta las excepciones de seguridad que se producen antes de que se invoque el método que contiene la llamada. En el ejemplo siguiente, cuando se coloca en un recurso compartido de servidor y se ejecuta desde allí, se genera el error "System. Security. SecurityException: error en la solicitud." Para obtener más información sobre las excepciones de seguridad, vea la clase <xref:System.Security.SecurityException>.

[!code-vb[VbVbalrStatements#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#85)]

En una situación de confianza parcial, tiene que colocar la instrucción `Process.Start` en un `Sub`independiente. Se producirá un error en la llamada inicial a la `Sub`. Esto permite a `Try...Catch` detectarla antes de que se inicie el `Sub` que contiene `Process.Start` y se produzca la excepción de seguridad.

## <a name="examples"></a>Ejemplos

### <a name="the-structure-of-trycatchfinally"></a>La estructura de try... Detectar... Terminar

En el ejemplo siguiente se muestra la estructura de la instrucción `Try...Catch...Finally`.

[!code-vb[VbVbalrStatements#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#86)]  

### <a name="exception-in-a-method-called-from-a-try-block"></a>Excepción en un método llamado desde un bloque try

En el ejemplo siguiente, el método `CreateException` produce una `NullReferenceException`. El código que genera la excepción no está en un bloque `Try`. Por lo tanto, el método `CreateException` no controla la excepción. El método `RunSample` controla la excepción porque la llamada al método `CreateException` está en un bloque `Try`.

En el ejemplo se incluyen `Catch` instrucciones para varios tipos de excepciones, ordenadas de la más específica a la más general.

[!code-vb[VbVbalrStatements#91](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#91)]

### <a name="the-catch-when-statement"></a>La instrucción Catch When

En el ejemplo siguiente se muestra cómo usar una instrucción `Catch When` para filtrar por una expresión condicional. Si la expresión condicional se evalúa como `True`, se ejecuta el código del bloque de `Catch`.

[!code-vb[VbVbalrStatements#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#92)]

### <a name="nested-try-statements"></a>Instrucciones try anidadas

El ejemplo siguiente tiene una instrucción `Try…Catch` que se encuentra en un bloque `Try`. El bloque `Catch` interno produce una excepción que tiene su propiedad `InnerException` establecida en la excepción original. El bloque `Catch` externo notifica su propia excepción y la excepción interna.

[!code-vb[VbVbalrStatements#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#93)]

### <a name="exception-handling-for-async-methods"></a>Control de excepciones para métodos asincrónicos

En el ejemplo siguiente se muestra el control de excepciones de los métodos asincrónicos. Para detectar una excepción que se aplica a una tarea asincrónica, la expresión `Await` está en un bloque de `Try` del llamador y la excepción se detecta en el bloque `Catch`.

Quite la marca de comentario de la línea `Throw New Exception` en el ejemplo para demostrar el control de excepciones. La excepción se detecta en el bloque `Catch`, la propiedad `IsFaulted` de la tarea se establece en `True`y la propiedad `Exception.InnerException` de la tarea se establece en la excepción.

Quite la marca de comentario de la línea `Throw New OperationCancelledException` para ver lo que pasa cuando se cancela un proceso asincrónico. La excepción se captura en el bloque `Catch` y la propiedad `IsCanceled` de la tarea se establece en `True`. Sin embargo, en algunas condiciones que no se aplican a este ejemplo, `IsFaulted` se establece en `True` y `IsCanceled` se establece en `False`.

[!code-vb[csAsyncExceptions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncexceptions/vb/class1.vb#1)]

### <a name="handling-multiple-exceptions-in-async-methods"></a>Controlar varias excepciones en métodos asincrónicos

En el ejemplo siguiente se muestra el control de excepciones en el que varias tareas pueden producir varias excepciones. El bloque `Try` tiene la expresión de `Await` para la tarea que <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> devuelve. La tarea se completa cuando se completan las tres tareas a las que se aplica <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.

Cada una de las tres tareas produce una excepción. El bloque `Catch` recorre en iteración las excepciones, que se encuentran en la propiedad `Exception.InnerExceptions` de la tarea que `Task.WhenAll` devuelve.

[!code-vb[csAsyncExceptions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncexceptions/vb/class1.vb#3)]

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:System.Exception>
- [Exit (instrucción)](exit-statement.md)
- [On Error (instrucción)](on-error-statement.md)
- [Procedimientos recomendados para usar fragmentos de código](/visualstudio/ide/best-practices-for-using-code-snippets)
- [Control de excepciones](../../../standard/parallel-programming/exception-handling-task-parallel-library.md)
- [Throw (instrucción)](throw-statement.md)
