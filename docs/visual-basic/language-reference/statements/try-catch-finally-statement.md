---
title: Instrucción Try...Catch...Finally (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 69
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 701475d41d24ad89e6c83796f7cc5cd4b7802a32
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="trycatchfinally-statement-visual-basic"></a>Instrucción Try...Catch...Finally (Visual Basic)
Proporciona un medio para controlar algunos o todos los errores posibles que pueden producirse en un bloque de código determinado mientras se sigue ejecutando el código.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`tryStatements`|Opcional. Instrucciones donde puede producirse un error. Puede ser una instrucción compuesta.|  
|`Catch`|Opcional. Varios `Catch` bloques permitido. Si se produce una excepción al procesar el `Try` bloquear, cada uno de ellos `Catch` instrucción se examina en orden textual para determinar si controla la excepción, con `exception` que representa la excepción que se ha producido.|  
|`exception`|Opcional. Cualquier nombre de variable. El valor inicial de `exception` es el valor del error producido. Usar con `Catch` especificar el error detectado. Si se omite, el `Catch` instrucción detecta cualquier excepción.|  
|`type`|Opcional. Especifica el tipo de filtro de clase. Si el valor de `exception` es del tipo especificado por `type` o de un tipo derivado, el identificador queda enlazado al objeto de excepción.|  
|`When`|Opcional. A `Catch` instrucción con un `When` cláusula detecta excepciones sólo cuando `expression` se evalúa como `True`. A `When` cláusula se aplica después de comprobar el tipo de la excepción, y `expression` pueden hacer referencia al identificador que representa la excepción.|  
|`expression`|Opcional. Debe poder convertirse implícitamente al `Boolean`. Cualquier expresión que describe un filtro genérico. Se utiliza normalmente para filtrar por número de error. Usar con `When` palabra clave para especificar las circunstancias bajo las que se captura el error.|  
|`catchStatements`|Opcional. Instrucciones para controlar los errores que se producen en el asociado `Try` bloque. Puede ser una instrucción compuesta.|  
|`Exit Try`|Opcional. Palabra clave que interrumpe fuera de la `Try...Catch...Finally` estructura. Reanuda la ejecución con el código que sigue inmediatamente el `End Try` instrucción. El `Finally` todavía se ejecutará la instrucción. No se permite en `Finally` bloques.|  
|`Finally`|Opcional. A `Finally` bloque siempre se ejecuta cuando la ejecución sale de cualquier parte de la `Try...Catch` instrucción.|  
|`finallyStatements`|Opcional. Instrucciones que se ejecutan una vez realizado el resto del procesamiento de error.|  
|`End Try`|Finaliza el `Try...Catch...Finally` estructura.|  
  
## <a name="remarks"></a>Comentarios  
 Si espera que una excepción determinada podría producirse durante una sección concreta del código, coloque el código en un `Try` bloquear y usar un `Catch` bloque para mantener el control y controlar la excepción si se produce.  
  
 A `Try…Catch` instrucción consta de un `Try` bloque seguido de uno o más `Catch` cláusulas que especifican controladores para diferentes excepciones. Cuando se produce una excepción un `Try` bloquear, Visual Basic busca el `Catch` instrucción que controla la excepción. Si una coincidencia `Catch` no se encontró la instrucción, Visual Basic examina el método que llamó al método actual, y así sucesivamente hasta la pila de llamadas. Si no hay ningún `Catch` bloque se encuentra, Visual Basic se muestra al usuario un mensaje de excepción no controlada y detiene la ejecución del programa.  
  
 Puede usar más de una `Catch` instrucción en un `Try…Catch` instrucción. Si lo hace, el orden de la `Catch` cláusulas es importante, ya que se examinan por orden. Detectar las excepciones más específicas antes que las menos específicas.  
  
 El siguiente `Catch` condiciones de instrucción son las menos específicas y todas las capturará excepciones que derivan de la <xref:System.Exception> clase. Normalmente debe usar una de estas variaciones como el último `Catch` bloquear el `Try...Catch...Finally` estructura después de detectar todas las excepciones específicas que espera. Flujo de control nunca puede alcanzar un `Catch` bloque que sigue a cualquiera de estas variaciones.  
  
-   El `type` es `Exception`, por ejemplo: `Catch ex As Exception`  
  
-   La instrucción no tiene ningún `exception` variable, por ejemplo: `Catch`  
  
 Cuando un `Try…Catch…Finally` instrucción está anidada en otro `Try` bloque, Visual Basic primero examina cada `Catch` instrucción interior `Try` bloque. Si no hay coincidencia `Catch` se encuentra una instrucción, la búsqueda continúa en el `Catch` las instrucciones de la externa `Try…Catch…Finally` bloque.  
  
 Las variables locales de un `Try` bloque no están disponibles en un `Catch` bloquearse porque trata de bloques independientes. Si desea utilizar una variable en más de un bloque, declare la variable fuera de la `Try...Catch...Finally` estructura.  
  
> [!TIP]
>  El `Try…Catch…Finally` instrucción está disponible como un fragmento de código de IntelliSense. En el Administrador de fragmentos de código, expanda **patrones de código - si, para cada uno, Try Catch, propiedad, etcetera**y, a continuación, **control de errores (excepciones)**. Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).  
  
## <a name="finally-block"></a>Bloque finally  
 Si tiene una o más instrucciones que se deben ejecutar antes de salir de la `Try` estructura, use un `Finally` bloque. El control se transfiere a la `Finally` bloquear justo antes de transferirlos fuera de la `Try…Catch` estructura. Esto es cierto incluso si se produce una excepción en cualquier lugar dentro de la `Try` estructura.  
  
 Un `Finally` bloque es útil para ejecutar cualquier código que deba ejecutarse incluso si hay una excepción. El control pasa a la `Finally` bloque independientemente de cómo `Try...Catch` bloquear se cierra.  
  
 El código en un `Finally` bloquear ejecuciones, incluso si el código encuentra una `Return` instrucción en un `Try` o `Catch` bloque. El control no pasar de un `Try` o `Catch` bloquear a los correspondientes `Finally` bloquear en los casos siguientes:  
  
-   Un [End (instrucción)](../../../visual-basic/language-reference/statements/end-statement.md) se encuentra en la `Try` o `Catch` bloque.  
  
-   A <xref:System.StackOverflowException> se produce en el `Try` o `Catch` bloque.  
  
 No es válido para transferir explícitamente la ejecución en un `Finally` bloque. Transferir la ejecución de un `Finally` bloque no es válido, excepto a través de una excepción.  
  
 Si un `Try` instrucción no contiene al menos una `Catch` bloque, debe contener un `Finally` bloque.  
  
> [!TIP]
>  Si no tiene que detectar excepciones específicas, el `Using` instrucción se comporta como un `Try…Finally` bloque y garantiza la disposición de los recursos, independientemente de cómo salga del bloque. Esto es cierto incluso con una excepción no controlada. Para obtener más información, vea [Using (Instrucción)](../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="exception-argument"></a>Argumento de excepción  
 El `Catch` bloque `exception` argumento es una instancia de la <xref:System.Exception> clase o una clase que deriva de la `Exception` clase. El `Exception` instancia de la clase que corresponde al error que se produjo en el `Try` bloque.  
  
 Las propiedades de la `Exception` objeto ayudan a identificar la causa y la ubicación de una excepción. Por ejemplo, el <xref:System.Exception.StackTrace%2A> listas de propiedades de los métodos llamados que produjeron la excepción, le ayuda a encontrar donde se produjo el error en el código. <xref:System.Exception.Message%2A> Devuelve un mensaje que describe la excepción. <xref:System.Exception.HelpLink%2A> Devuelve un vínculo a un archivo de ayuda asociado. <xref:System.Exception.InnerException%2A> Devuelve el `Exception` devuelve el objeto que produjo la excepción actual, o `Nothing` si no hay ningún original `Exception`.  
  
## <a name="considerations-when-using-a-trycatch-statement"></a>Consideraciones al usar un bloque Try... Catch (instrucción)  
 Use un `Try…Catch` instrucción solo para señalizar la aparición de eventos de programa inusuales o inesperados. Razones para esto son los siguientes:  
  
-   Detectar excepciones en tiempo de ejecución crea una sobrecarga adicional y es probable que sea más lenta que la comprobación previa para evitar excepciones.  
  
-   Si un `Catch` bloque no se controla correctamente, la excepción no se puede notificar correctamente a los usuarios.  
  
-   Control de excepciones hace que un programa más complejo.  
  
 No necesita siempre un `Try…Catch` instrucción para comprobar una condición que es probable que suceda. En el ejemplo siguiente se comprueba si existe un archivo antes de intentar abrirlo. Esto reduce la necesidad de detectar una excepción producida por el <xref:System.IO.File.OpenText%2A> método.  
  
 [!code-vb[VbVbalrStatements#94](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_1.vb)]  
  
 Asegúrese de que el código en `Catch` bloques correctamente pueden notificar excepciones a los usuarios, ya sea a través de subprocesos registro o los mensajes adecuados. De lo contrario, las excepciones pueden permanecer desconocidas.  
  
## <a name="async-methods"></a>Métodos asincrónicos  
 Si marca un método con el [Async](../../../visual-basic/language-reference/modifiers/async.md) modificador, puede usar el [Await](../../../visual-basic/language-reference/operators/await-operator.md) operador en el método. Una instrucción con el `Await` operador suspende la ejecución del método hasta que se complete la tarea esperada. La tarea representa el trabajo en curso. Cuando la tarea que está asociada el `Await` operador finaliza, se reanuda la ejecución en el mismo método. Para obtener más información, consulte [flujo de Control en programas Async](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md).  
  
 Una tarea devuelta por un método asincrónico puede terminar en un estado de error, que indica que ha completado debido a una excepción no controlada. También puede finalizar una tarea en un estado cancelado, lo que resulta en una `OperationCanceledException` que se producen fuera de la expresión await. Para detectar cualquier tipo de excepción, coloque el `Await` expresión asociada a la tarea en un `Try` bloquear y detecte la excepción en el `Catch` bloque. Más adelante en este tema se proporciona un ejemplo.  
  
 Una tarea puede encontrarse en un estado de error porque eran responsables de la cual varias excepciones. Por ejemplo, la tarea podría ser el resultado de una llamada a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>. Cuando espera dicha tarea, la excepción detectada es solo una de las excepciones y no se puede predecir qué excepción se capturará. Más adelante en este tema se proporciona un ejemplo.  
  
 Un `Await` expresión no puede estar dentro de un `Catch` bloque o `Finally` bloque.  
  
## <a name="iterators"></a>Iterators  
 Una función de iterador o `Get` descriptor de acceso realiza una iteración personalizada en una colección. Un iterador utiliza un [producen](../../../visual-basic/language-reference/statements/yield-statement.md) instrucción para devolver cada elemento de la colección a la vez. Llamar a una función de iterador mediante un [For Each... Next (instrucción)](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
 A `Yield` instrucción puede estar dentro de un `Try` bloque. A `Try` bloque que contiene un `Yield` instrucción puede tener `Catch` bloquea y puede tener un `Finally` bloque. Vea la sección "intente bloques en Visual Basic" de [iteradores](../../programming-guide/concepts/iterators.md) para obtener un ejemplo.  
  
 A `Yield` instrucción no puede estar dentro de un `Catch` bloque o una `Finally` bloque.  
  
 Si el `For Each` cuerpo (fuera de la función del iterador) produce una excepción, un `Catch` no se ejecuta el bloque de la función del iterador, pero un `Finally` se ejecuta el bloque de la función del iterador. Un `Catch` bloque dentro de una función de iterador captura solo las excepciones que se producen dentro de la función de iterador.  
  
## <a name="partial-trust-situations"></a>Situaciones de confianza parcial  
 En situaciones de confianza parcial, como una aplicación hospedada en un recurso compartido de red, `Try...Catch...Finally` no detecta excepciones de seguridad que se producen antes de invocar el método que contiene la llamada. El siguiente ejemplo, cuando se coloca en un recurso compartido de servidor y se ejecuta desde allí, genera el error "System.Security.SecurityException: error de solicitud." Para obtener más información acerca de las excepciones de seguridad, consulte la <xref:System.Security.SecurityException> clase.  
  
 [!code-vb[VbVbalrStatements#85](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_2.vb)]  
  
 En esta situación de confianza parcial, tendrá que colocar el `Process.Start` instrucción en otro `Sub`. La llamada inicial a la `Sub` se producirá un error. Esto permite `Try...Catch` para detectar con anterioridad la `Sub` que contiene `Process.Start` se inicia y se produce la excepción de seguridad.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra la estructura de la `Try...Catch...Finally` instrucción.  
  
 [!code-vb[VbVbalrStatements#86](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_3.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, la `CreateException` método produce un `NullReferenceException`. El código que genera la excepción no está en un `Try` bloque. Por lo tanto, la `CreateException` método no controla la excepción. El `RunSample` método controlar la excepción porque la llamada a la `CreateException` método está en un `Try` bloque.  
  
 El ejemplo incluye `Catch` instrucciones para varios tipos de excepciones, se ordenan desde el más específico al más general.  
  
 [!code-vb[VbVbalrStatements#91](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_4.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar un `Catch When` instrucción para filtrar según una expresión condicional. Si la expresión condicional se evalúa como `True`, el código en el `Catch` bloquear ejecuciones.  
  
 [!code-vb[VbVbalrStatements#92](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_5.vb)]  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo tiene un `Try…Catch` instrucción que se encuentra en un `Try` bloque. Interna `Catch` bloque produce una excepción que tenga su `InnerException` propiedad establecida en la excepción original. El exterior `Catch` bloque informa acerca de su propia excepción y la excepción interna.  
  
 [!code-vb[VbVbalrStatements#93](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_6.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra el control de excepciones de los métodos asincrónicos. Para detectar una excepción que se aplica a una tarea asincrónica, el `Await` la expresión tiene un `Try` bloque del autor de la llamada y la excepción se captura en el `Catch` bloque.  
  
 Quite la marca de comentario de la línea `Throw New Exception` en el ejemplo para demostrar el control de excepciones. Se detectó la excepción en el `Catch` bloquear, la tarea `IsFaulted` propiedad está establecida en `True`y la tarea `Exception.InnerException` propiedad se establece en la excepción.  
  
 Quite la marca de comentario de la línea `Throw New OperationCancelledException` para ver lo que pasa cuando se cancela un proceso asincrónico. Se detectó la excepción en el `Catch` bloque y la tarea `IsCanceled` propiedad está establecida en `True`. Sin embargo, en algunas condiciones que no son aplicables a este ejemplo, `IsFaulted` está establecido en `True` y `IsCanceled` está establecido en `False`.  
  
 [!code-vb[csAsyncExceptions#1](../../../csharp/language-reference/keywords/codesnippet/VisualBasic/try-catch-finally-statement_7.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra el control de excepciones en el que varias tareas pueden producir varias excepciones. El `Try` bloque tiene el `Await` expresión para la tarea que <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> devuelto. La tarea está completa cuando las tres tareas a la que <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> se aplica están completos.  
  
 Cada una de las tres tareas produce una excepción. El `Catch` bloque recorre en iteración las excepciones, que se encuentran en el `Exception.InnerExceptions` propiedad de la tarea que `Task.WhenAll` devuelto.  
  
 [!code-vb[csAsyncExceptions#3](../../../csharp/language-reference/keywords/codesnippet/VisualBasic/try-catch-finally-statement_8.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Information.Err%2A>  
 <xref:System.Exception>  
 [Exit (instrucción)](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [On Error (instrucción)](../../../visual-basic/language-reference/statements/on-error-statement.md)  
 [Procedimientos recomendados para usar fragmentos de código](/visualstudio/ide/best-practices-for-using-code-snippets)  
 [Control de excepciones](../../../standard/parallel-programming/exception-handling-task-parallel-library.md)  
 [Throw (instrucción)](../../../visual-basic/language-reference/statements/throw-statement.md)
