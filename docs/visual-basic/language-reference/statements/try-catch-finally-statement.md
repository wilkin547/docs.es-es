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
ms.openlocfilehash: 22f1611786a3da512632b5b547b7ef141c8f65c6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84391773"
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

## <a name="parts"></a>Partes

|Término|Definición|
|---|---|
|`tryStatements`|Opcional. Instrucciones en las que se puede producir un error. Puede ser una instrucción compuesta.|
|`Catch`|Opcional. Se `Catch` permiten varios bloques. Si se produce una excepción al procesar el `Try` bloque, cada `Catch` instrucción se examina en orden textual para determinar si controla la excepción, con `exception` lo que representa la excepción que se ha producido.|
|`exception`|Opcional. Cualquier nombre de variable. El valor inicial de `exception` es el valor del error producido. Se utiliza con `Catch` para especificar el error detectado. Si se omite, la `Catch` instrucción detecta cualquier excepción.|
|`type`|Opcional. Especifica el tipo de filtro de clase. Si el valor de `exception` es del tipo especificado por `type` o de un tipo derivado, el identificador se enlaza al objeto de excepción.|
|`When`|Opcional. Una `Catch` instrucción con una `When` cláusula solo detecta las excepciones cuando `expression` se evalúa como `True` . Una `When` cláusula solo se aplica después de comprobar el tipo de la excepción y `expression` puede hacer referencia al identificador que representa la excepción.|
|`expression`|Opcional. Se debe poder convertir implícitamente en `Boolean` . Cualquier expresión que describa un filtro genérico. Normalmente se usa para filtrar por número de error. Se utiliza con `When` la palabra clave para especificar las circunstancias en las que se detecta el error.|
|`catchStatements`|Opcional. Instrucciones para controlar los errores que se producen en el bloque asociado `Try` . Puede ser una instrucción compuesta.|
|`Exit Try`|Opcional. Palabra clave que sale de la `Try...Catch...Finally` estructura. La ejecución se reanuda con el código inmediatamente después de la `End Try` instrucción. La `Finally` instrucción se seguirá ejecutando. No se permite en `Finally` bloques.|
|`Finally`|Opcional. Un `Finally` bloque siempre se ejecuta cuando la ejecución deja parte de la `Try...Catch` instrucción.|
|`finallyStatements`|Opcional. Instrucciones que se ejecutan después de que se haya producido el otro procesamiento de errores.|
|`End Try`|Finaliza la `Try...Catch...Finally` estructura.|

## <a name="remarks"></a>Observaciones

Si espera que se produzca una excepción determinada durante una sección de código determinada, coloque el código en un `Try` bloque y use un `Catch` bloque para conservar el control y controle la excepción si se produce.

Una `Try…Catch` instrucción consta de un `Try` bloque seguido de una o más `Catch` cláusulas, que especifican Controladores para distintas excepciones. Cuando se produce una excepción en un `Try` bloque, Visual Basic busca la `Catch` instrucción que controla la excepción. Si `Catch` no se encuentra una instrucción coincidente, Visual Basic examina el método que llamó al método actual, y así sucesivamente en la pila de llamadas. Si no `Catch` se encuentra ningún bloque, Visual Basic muestra al usuario un mensaje de excepción no controlada y detiene la ejecución del programa.

Puede usar más de una `Catch` instrucción en una `Try…Catch` instrucción. Si lo hace, el orden de las `Catch` cláusulas es importante porque se examinan en orden. Detectar las excepciones más específicas antes que las menos específicas.

Las siguientes `Catch` condiciones de instrucción son las menos específicas y detectarán todas las excepciones que derivan de la <xref:System.Exception> clase. Normalmente, debe usar una de estas variaciones como el último `Catch` bloque de la `Try...Catch...Finally` estructura, después de detectar todas las excepciones específicas que espera. El flujo de control no puede llegar nunca a un `Catch` bloque que siga cualquiera de estas variaciones.

- El `type` es `Exception` , por ejemplo:`Catch ex As Exception`

- La instrucción no tiene ninguna `exception` variable, por ejemplo:`Catch`

Cuando una `Try…Catch…Finally` instrucción está anidada en otro `Try` bloque, Visual Basic examina primero cada `Catch` instrucción en el bloque más interno `Try` . Si no `Catch` se encuentra ninguna instrucción coincidente, la búsqueda continúa con las `Catch` instrucciones del bloque exterior `Try…Catch…Finally` .

Las variables locales de un `Try` bloque no están disponibles en un `Catch` bloque porque son bloques independientes. Si desea utilizar una variable en más de un bloque, declare la variable fuera de la `Try...Catch...Finally` estructura.

> [!TIP]
> La `Try…Catch…Finally` instrucción está disponible como fragmento de código de IntelliSense. En el administrador de fragmentos de código, expanda **patrones de código: Si, para cada uno, pruebe Catch, Property, etc**. y, a continuación, **control de errores (excepciones)**. Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).

## <a name="finally-block"></a>Bloque Finally

Si tiene una o más instrucciones que se deben ejecutar antes de salir de la `Try` estructura, utilice un `Finally` bloque. El control pasa al `Finally` bloque justo antes de salir de la `Try…Catch` estructura. Esto es así incluso si se produce una excepción en cualquier parte dentro de la `Try` estructura.

Un `Finally` bloque es útil para ejecutar cualquier código que deba ejecutarse incluso si se produce una excepción. El control se pasa al `Finally` bloque independientemente de cómo `Try...Catch` salga el bloque.

El código de un `Finally` bloque se ejecuta incluso si el código encuentra una `Return` instrucción en un `Try` bloque o `Catch` . El control no pasa de un `Try` `Catch` bloque o al bloque correspondiente `Finally` en los casos siguientes:

- Se encuentra una [instrucción end](end-statement.md) en el `Try` `Catch` bloque o.

- <xref:System.StackOverflowException>Se produce una excepción en `Try` el `Catch` bloque o.

No es válido transferir explícitamente la ejecución a un `Finally` bloque. La transferencia de la ejecución fuera de un `Finally` bloque no es válida, excepto a través de una excepción.

Si una `Try` instrucción no contiene al menos un `Catch` bloque, debe contener un `Finally` bloque.

> [!TIP]
> Si no tiene que detectar excepciones específicas, la `Using` instrucción se comporta como un `Try…Finally` bloque y garantiza la eliminación de los recursos, independientemente de cómo salga del bloque. Esto es así incluso con una excepción no controlada. Para obtener más información, vea [using (instrucción](using-statement.md)).

## <a name="exception-argument"></a>Argumento de excepción

El `Catch` `exception` argumento de bloque es una instancia de la <xref:System.Exception> clase o una clase que deriva de la `Exception` clase. La `Exception` instancia de clase se corresponde con el error que se produjo en el `Try` bloque.

Las propiedades del `Exception` objeto ayudan a identificar la causa y la ubicación de una excepción. Por ejemplo, la <xref:System.Exception.StackTrace%2A> propiedad enumera los métodos a los que se ha provocado la excepción, lo que le ayuda a encontrar el lugar en el que se produjo el error en el código. <xref:System.Exception.Message%2A>Devuelve un mensaje que describe la excepción. <xref:System.Exception.HelpLink%2A>Devuelve un vínculo a un archivo de ayuda asociado. <xref:System.Exception.InnerException%2A>Devuelve el `Exception` objeto que causó la excepción actual, o devuelve si no hay `Nothing` ningún original `Exception` .

## <a name="considerations-when-using-a-trycatch-statement"></a>Consideraciones al usar una instrucción try... Catch (instrucción)

Use una `Try…Catch` instrucción solo para indicar la aparición de eventos de programa inusuales o imprevistos. Entre los motivos se incluyen los siguientes:

- La detección de excepciones en tiempo de ejecución crea una sobrecarga adicional y es probable que sea más lenta que la comprobación previa para evitar excepciones.

- Si un `Catch` bloque no se controla correctamente, es posible que la excepción no se notifique correctamente a los usuarios.

- El control de excepciones hace que un programa sea más complejo.

No siempre se necesita una `Try…Catch` instrucción para comprobar si hay una condición que es probable que se produzca. En el ejemplo siguiente se comprueba si existe un archivo antes de intentar abrirlo. Esto reduce la necesidad de detectar una excepción producida por el <xref:System.IO.File.OpenText%2A> método.

[!code-vb[VbVbalrStatements#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#94)]

Asegúrese de que el código de `Catch` los bloques pueda notificar correctamente las excepciones a los usuarios, ya sea a través de registros seguros para subprocesos o mensajes adecuados. De lo contrario, es posible que las excepciones sigan siendo desconocidas.

## <a name="async-methods"></a>Métodos asincrónicos

Si marca un método con el modificador [Async](../modifiers/async.md) , puede usar el operador [Await](../operators/await-operator.md) en el método. Una instrucción con el `Await` operador suspende la ejecución del método hasta que se completa la tarea esperada. La tarea representa el trabajo en curso. Cuando finaliza la tarea asociada al `Await` operador, la ejecución se reanuda en el mismo método. Para obtener más información, vea [flujo de control en programas Async](../../programming-guide/concepts/async/control-flow-in-async-programs.md).

Una tarea devuelta por un método asincrónico puede finalizar en un estado de error, lo que indica que se completó debido a una excepción no controlada. Una tarea también puede terminar en un estado cancelado, lo que provoca que `OperationCanceledException` se produzca una excepción de la expresión Await. Para detectar cualquier tipo de excepción, coloque la `Await` expresión que está asociada a la tarea en un `Try` bloque y Capture la excepción en el `Catch` bloque. Más adelante en este tema se proporciona un ejemplo.

Una tarea puede tener un estado de error porque varias excepciones eran responsables de su error. Por ejemplo, la tarea podría ser el resultado de una llamada a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>. Cuando espera una tarea de este tipo, la excepción detectada es solo una de las excepciones y no puede predecir qué excepción se detectará. Más adelante en este tema se proporciona un ejemplo.

Una `Await` expresión no puede estar dentro de un `Catch` bloque o `Finally` bloque.

## <a name="iterators"></a>Iterators

Una función de iterador o un `Get` descriptor de acceso realiza una iteración personalizada en una colección. Un iterador usa una instrucción [yield](yield-statement.md) para devolver cada elemento de la colección de uno en uno. Se llama a una función de iterador mediante un método [for each... Instrucción siguiente](for-each-next-statement.md).

Una `Yield` instrucción puede estar dentro de un `Try` bloque. Un `Try` bloque que contiene una `Yield` instrucción puede tener `Catch` bloques y puede tener un `Finally` bloque. Vea la sección "Try blocks in Visual Basic" de [iteradores](../../programming-guide/concepts/iterators.md) para obtener un ejemplo.

Una `Yield` instrucción no puede estar dentro de un `Catch` bloque o un `Finally` bloque.

Si el `For Each` cuerpo (fuera de la función de iterador) produce una excepción, `Catch` no se ejecuta un bloque de la función de iterador, pero `Finally` se ejecuta un bloque en la función de iterador. Un `Catch` bloque dentro de una función de iterador solo detecta las excepciones que se producen dentro de la función de iterador.

## <a name="partial-trust-situations"></a>Situaciones de confianza parcial

En situaciones de confianza parcial, como una aplicación hospedada en un recurso compartido de red, `Try...Catch...Finally` no detecta las excepciones de seguridad que se producen antes de que se invoque el método que contiene la llamada. En el ejemplo siguiente, cuando se coloca en un recurso compartido de servidor y se ejecuta desde allí, se genera el error "System. Security. SecurityException: error en la solicitud." Para obtener más información sobre las excepciones de seguridad, vea la <xref:System.Security.SecurityException> clase.

[!code-vb[VbVbalrStatements#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#85)]

En una situación de confianza parcial, debe colocar la `Process.Start` instrucción en un independiente `Sub` . `Sub`Se producirá un error en la llamada inicial a. Esto permite `Try...Catch` que se detecte antes de `Sub` que `Process.Start` se inicie el que contiene y se produzca la excepción de seguridad.

## <a name="examples"></a>Ejemplos

### <a name="the-structure-of-trycatchfinally"></a>La estructura de try... Detectar... Terminar

En el ejemplo siguiente se muestra la estructura de la `Try...Catch...Finally` instrucción.

[!code-vb[VbVbalrStatements#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#86)]  

### <a name="exception-in-a-method-called-from-a-try-block"></a>Excepción en un método llamado desde un bloque try

En el ejemplo siguiente, el `CreateException` método produce una excepción `NullReferenceException` . El código que genera la excepción no está en un `Try` bloque. Por lo tanto, el `CreateException` método no controla la excepción. El `RunSample` método controla la excepción porque la llamada al `CreateException` método está en un `Try` bloque.

En el ejemplo `Catch` se incluyen instrucciones para varios tipos de excepciones, ordenadas de la más específica a la más general.

[!code-vb[VbVbalrStatements#91](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#91)]

### <a name="the-catch-when-statement"></a>La instrucción Catch When

En el ejemplo siguiente se muestra cómo usar una `Catch When` instrucción para filtrar por una expresión condicional. Si la expresión condicional se evalúa como `True` , se ejecuta el código del `Catch` bloque.

[!code-vb[VbVbalrStatements#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#92)]

### <a name="nested-try-statements"></a>Instrucciones try anidadas

El ejemplo siguiente tiene una `Try…Catch` instrucción que se encuentra en un `Try` bloque. El `Catch` bloque interno produce una excepción que tiene su `InnerException` propiedad establecida en la excepción original. El `Catch` bloque externo notifica su propia excepción y la excepción interna.

[!code-vb[VbVbalrStatements#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#93)]

### <a name="exception-handling-for-async-methods"></a>Control de excepciones para métodos asincrónicos

En el ejemplo siguiente se muestra el control de excepciones de los métodos asincrónicos. Para detectar una excepción que se aplica a una tarea asincrónica, la `Await` expresión se encuentra en un `Try` bloque del llamador y la excepción se captura en el `Catch` bloque.

Quite la marca de comentario de la línea `Throw New Exception` en el ejemplo para demostrar el control de excepciones. La excepción se detecta en el `Catch` bloque, la propiedad de la tarea `IsFaulted` se establece en `True` y la propiedad de la tarea `Exception.InnerException` se establece en la excepción.

Quite la marca de comentario de la línea `Throw New OperationCancelledException` para ver lo que pasa cuando se cancela un proceso asincrónico. La excepción se detecta en el `Catch` bloque y la propiedad de la tarea `IsCanceled` se establece en `True` . Sin embargo, en algunas condiciones que no se aplican a este ejemplo, `IsFaulted` se establece en `True` y `IsCanceled` se establece en `False` .

[!code-vb[csAsyncExceptions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncexceptions/vb/class1.vb#1)]

### <a name="handling-multiple-exceptions-in-async-methods"></a>Controlar varias excepciones en métodos asincrónicos

En el ejemplo siguiente se muestra el control de excepciones en el que varias tareas pueden producir varias excepciones. El `Try` bloque tiene la `Await` expresión de la tarea que <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> devolvió. La tarea se completa cuando se completan las tres tareas a las que <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> se aplica.

Cada una de las tres tareas produce una excepción. El `Catch` bloque recorre en iteración las excepciones, que se encuentran en la `Exception.InnerExceptions` propiedad de la tarea que `Task.WhenAll` devolvió.

[!code-vb[csAsyncExceptions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncexceptions/vb/class1.vb#3)]

## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:System.Exception>
- [Instrucción Exit](exit-statement.md)
- [Instrucción On Error](on-error-statement.md)
- [Procedimientos recomendados para usar fragmentos de código](/visualstudio/ide/best-practices-for-using-code-snippets)
- [Control de excepciones](../../../standard/parallel-programming/exception-handling-task-parallel-library.md)
- [Throw (instrucción)](throw-statement.md)
