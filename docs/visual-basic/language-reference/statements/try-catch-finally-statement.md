---
title: "Try... Catch... Finally (instrucción) (Visual Basic) | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Try...Catch...Finally
- vb.when
- vb.Finally
- vb.Catch
- vb.Try
dev_langs:
- VB
helpviewer_keywords:
- Try...Catch...Finally statements
- Try statement
- try-catch exception handling, Try...Catch...Finally statements
- error handling, while running code
- Try statement, Try...Catch...Finally
- Finally keyword [Visual Basic], Try...Catch...Finally
- Catch statement
- When keyword
- Visual Basic code, handling errors while running
- structured exception handling, Try...Catch...Finally statements
ms.assetid: d6488026-ccb3-42b8-a810-0d97b9d6472b
caps.latest.revision: 69
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 379359e3a338746ccd440dbe1ad58c483e562dbe
ms.lasthandoff: 03/13/2017

---
# <a name="trycatchfinally-statement-visual-basic"></a>Instrucción Try...Catch...Finally (Visual Basic)
Proporciona una manera de controlar algunos o todos los errores posibles que pueden producirse en un determinado bloque de código, mientras sigue ejecutando el código.  
  
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
|`Catch`|Opcional. Varios `Catch` bloques permitido. Si se produce una excepción al procesar el `Try` bloquear cada `Catch` instrucción se examina en orden textual para determinar si controla la excepción con `exception` que representa la excepción que se ha producido.|  
|`exception`|Opcional. Cualquier nombre de variable. El valor inicial de `exception` es el valor del error producido. Se utiliza con `Catch` especificar el error detectado. Si se omite, el `Catch` instrucción detecta cualquier excepción.|  
|`type`|Opcional. Especifica el tipo de filtro de clase. Si el valor de `exception` es del tipo especificado por `type` o de un tipo derivado, el identificador queda enlazado al objeto de excepción.|  
|`When`|Opcional. Un `Catch` instrucción con un `When` cláusula detecta excepciones sólo cuando `expression` se evalúa como `True`. Un `When` cláusula se aplica únicamente después de comprobar el tipo de la excepción, y `expression` pueden hacer referencia al identificador que representa la excepción.|  
|`expression`|Opcional. Debe ser implícitamente convertible a `Boolean`. Cualquier expresión que describe un filtro genérico. Se utiliza normalmente para filtrar por número de error. Se utiliza con `When` (palabra clave) para especificar las circunstancias bajo las que se captura el error.|  
|`catchStatements`|Opcional. Instrucciones para controlar los errores que se producen en el asociado `Try` bloque. Puede ser una instrucción compuesta.|  
|`Exit Try`|Opcional. Palabra clave que interrumpe fuera de la `Try...Catch...Finally` estructura. La ejecución se reanuda con el código que sigue el `End Try` instrucción. El `Finally` todavía se ejecutará la instrucción. No se permite en `Finally` bloques.|  
|`Finally`|Opcional. Un `Finally` bloque siempre se ejecuta cuando la ejecución sale de cualquier parte de la `Try...Catch` instrucción.|  
|`finallyStatements`|Opcional. Instrucciones que se ejecutan una vez realizado el resto del procesamiento de error.|  
|`End Try`|Finaliza el `Try...Catch...Finally` estructura.|  
  
## <a name="remarks"></a>Comentarios  
 Si piensa que podría producir una excepción determinada en una sección concreta del código, coloque el código en un `Try` bloquear y usar un `Catch` bloque para conservar el control y controlar la excepción si se produce.  
  
 Un `Try…Catch` instrucción consta de un `Try` bloque seguido de uno o varios `Catch` cláusulas que especifican controladores para diferentes excepciones. Cuando se produce una excepción un `Try` bloque, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] busca el `Catch` instrucción que controla la excepción. Si una coincidencia `Catch` no se encuentra la instrucción, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] examina el método que llamó al método actual, y así sucesivamente la pila de llamadas. Si no hay ningún `Catch` bloque se encuentra, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] muestra al usuario un mensaje de excepción no controlada y detiene la ejecución del programa.  
  
 Puede usar más de una `Catch` instrucción en un `Try…Catch` instrucción. Si lo hace, el orden de la `Catch` cláusulas es importante, ya que se examinan en orden. Detectar las excepciones más específicas antes que las menos específicas.  
  
 El siguiente `Catch` condiciones de instrucción son menos específicos y todas las detectará excepciones que derivan de la <xref:System.Exception>clase.</xref:System.Exception> Normalmente debe usar una de estas variaciones en la última `Catch` bloquear el `Try...Catch...Finally` estructura después de detectar todas las excepciones específicas que espera. Flujo de control nunca puede alcanzar un `Catch` cualquiera de estas variaciones en el siguiente bloque.  
  
-   El `type` es `Exception`, por ejemplo:`Catch ex As Exception`  
  
-   La instrucción no tiene ningún `exception` variable, por ejemplo:`Catch`  
  
 Cuando un `Try…Catch…Finally` instrucción está anidada en otro `Try` bloque, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] primero examina cada `Catch` instrucción interno `Try` bloque. Si no hay coincidencia `Catch` se encuentra una instrucción, la búsqueda continúa en la `Catch` instrucciones de externo `Try…Catch…Finally` bloque.  
  
 Las variables locales de un `Try` bloque no están disponibles en un `Catch` bloquear porque se trata de bloques independientes. Si desea utilizar una variable en más de un bloque, declare la variable fuera del `Try...Catch...Finally` estructura.  
  
> [!TIP]
>  El `Try…Catch…Finally` instrucción está disponible como un fragmento de código de IntelliSense. En el Administrador de fragmentos de código, expanda **modelos de código - si, para cada uno, Try Catch, propiedad, etcetera**y, a continuación, **control de errores (excepciones)**. Para obtener más información, vea [Fragmentos de código](https://docs.microsoft.com/visualstudio/ide/code-snippets).  
  
## <a name="finally-block"></a>Bloque finally  
 Si tiene una o más instrucciones que deben ejecutarse antes de salir de la `Try` estructura, use un `Finally` bloque. El control pasa a la `Finally` bloquear antes de transferirlos fuera de la `Try…Catch` estructura. Esto es así incluso si se produce una excepción en cualquier lugar dentro de la `Try` estructura.  
  
 Un `Finally` bloque es útil para ejecutar cualquier código que deba ejecutarse incluso si hay una excepción. El control pasa a la `Finally` bloque con independencia del `Try...Catch` bloquear salidas.  
  
 El código en un `Finally` bloque se ejecuta incluso si el código encuentra un `Return` instrucción en un `Try` o `Catch` bloque. El control no pasar de un `Try` o `Catch` bloquear correspondiente `Finally` bloquear en los casos siguientes:  
  
-   Un [instrucción End](../../../visual-basic/language-reference/statements/end-statement.md) se encuentra en la `Try` o `Catch` bloque.  
  
-   Un <xref:System.StackOverflowException>se produce en el `Try` o `Catch` bloque.</xref:System.StackOverflowException>  
  
 No es válido transferir explícitamente la ejecución en un `Finally` bloque. Transferir la ejecución fuera de un `Finally` bloque no es válido, excepto a través de una excepción.  
  
 Si un `Try` instrucción no contiene al menos una `Catch` bloque, debe contener una `Finally` bloque.  
  
> [!TIP]
>  Si no tiene que capturar excepciones específicas, la `Using` instrucción se comporta como un `Try…Finally` bloque y garantiza la disposición de los recursos, independientemente de cómo salga del bloque. Esto es cierto incluso con una excepción no controlada. Para obtener más información, consulte [instrucción Using](../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="exception-argument"></a>Argumento de excepción  
 El `Catch` bloque `exception` argumento es una instancia de la <xref:System.Exception>clase o una clase que deriva de la `Exception` clase</xref:System.Exception> El `Exception` instancia de la clase que corresponde al error que se produjo en el `Try` bloque.  
  
 Las propiedades de la `Exception` objeto ayuda a identificar la causa y la ubicación de una excepción. Por ejemplo, el <xref:System.Exception.StackTrace%2A>listas de propiedades de los métodos llamados que produjeron la excepción, lo que le ayuda a encontrar dónde se produjo el error en el código.</xref:System.Exception.StackTrace%2A> <xref:System.Exception.Message%2A>Devuelve un mensaje que describe la excepción.</xref:System.Exception.Message%2A> <xref:System.Exception.HelpLink%2A>Devuelve un vínculo a un archivo de ayuda asociado.</xref:System.Exception.HelpLink%2A> <xref:System.Exception.InnerException%2A>Devuelve el `Exception` devuelve el objeto que produjo la excepción actual, o bien `Nothing` si no hay ningún original `Exception`.</xref:System.Exception.InnerException%2A>  
  
## <a name="considerations-when-using-a-trycatch-statement"></a>Consideraciones al usar un bloque Try... Catch (instrucción)  
 Use un `Try…Catch` instrucción sólo para señalizar la aparición de eventos de programa inusuales o inesperados. Las razones siguientes:  
  
-   Detectar excepciones en tiempo de ejecución crea una sobrecarga adicional y es probable que sea más lenta que la comprobación previa para evitar las excepciones.  
  
-   Si un `Catch` bloque no se administra correctamente, la excepción podría no mostrarse correctamente a los usuarios.  
  
-   Control de excepciones hace que un programa más complejo.  
  
 No necesita siempre un `Try…Catch` instrucción para comprobar una condición que es probable que ocurra. En el ejemplo siguiente se comprueba si existe un archivo antes de intentar abrirlo. Esto reduce la necesidad de detectar una excepción producida por el <xref:System.IO.File.OpenText%2A>método.</xref:System.IO.File.OpenText%2A>  
  
 [!code-vb[VbVbalrStatements&#94;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_1.vb)]  
  
 Garantizar que el código en `Catch` bloques pueden comunicar correctamente las excepciones a los usuarios, ya sea a través de subprocesos registro o los mensajes adecuados. De lo contrario, las excepciones pueden permanecer desconocidas.  
  
## <a name="async-methods"></a>Métodos asincrónicos  
 Si marca un método con la [Async](../../../visual-basic/language-reference/modifiers/async.md) modificador, puede utilizar el [Await](../../../visual-basic/language-reference/operators/await-operator.md) operador en el método. Una instrucción con el `Await` operador suspende la ejecución del método hasta que se complete la tarea esperada. La tarea representa el trabajo en curso. Cuando la tarea que está asociada la `Await` operador finalice, se reanuda la ejecución en el mismo método. Para obtener más información, consulte [flujo de Control en programas Async](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md).  
  
 Una tarea devuelta por un método asincrónico puede encontrarse en un estado de error que indica que ha completado debido a una excepción no controlada. También puede finalizar una tarea en un estado cancelado, lo que resulta en una `OperationCanceledException` que se producen fuera de la expresión await. Para detectar cualquier tipo de excepción, coloque el `Await` expresión asociada con la tarea en un `Try` bloquear y detectar la excepción en el `Catch` bloque. Más adelante en este tema se proporciona un ejemplo.  
  
 Una tarea puede estar en un estado de error porque varias excepciones eran responsables de su ausencia. Por ejemplo, la tarea podría ser el resultado de una llamada a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> Cuando se espera dicha tarea, la excepción detectada es sólo una de las excepciones y no se puede predecir qué excepción será detectada. Más adelante en este tema se proporciona un ejemplo.  
  
 Un `Await` expresión no puede estar dentro de un `Catch` bloque o `Finally` bloque.  
  
## <a name="iterators"></a>Iteradores  
 Una función de iterador o `Get` descriptor de acceso realiza una iteración personalizada en una colección. Un iterador se usa un [producen](../../../visual-basic/language-reference/statements/yield-statement.md) instrucción para devolver cada elemento de la colección a la vez. Puede llamar a una función de iterador con un [For Each... Next (instrucción)](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
 Un `Yield` instrucción puede estar dentro de un `Try` bloque. Un `Try` bloque que contiene un `Yield` instrucción puede tener `Catch` bloquea y puede tener un `Finally` bloque. Consulte la sección "Probar bloques en Visual Basic" de [iteradores](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7) para obtener un ejemplo.  
  
 Un `Yield` instrucción no puede estar dentro de un `Catch` bloque o una `Finally` bloque.  
  
 Si el `For Each` cuerpo (fuera de la función de iterador) produce una excepción, un `Catch` no se ejecuta el bloque de la función del iterador, pero un `Finally` se ejecuta el bloque de la función del iterador. Un `Catch` bloque dentro de una función de iterador captura solo las excepciones que se producen dentro de la función de iterador.  
  
## <a name="partial-trust-situations"></a>Situaciones de confianza parcial  
 En situaciones de confianza parcial, como una aplicación hospedada en un recurso compartido de red, `Try...Catch...Finally` no detecta excepciones de seguridad que se producen antes de invocar el método que contiene la llamada. El siguiente ejemplo, cuando se coloca en un recurso compartido de servidor y se ejecuta desde allí, produce el error "System.Security.SecurityException: error de solicitud." Para obtener más información acerca de las excepciones de seguridad, vea la <xref:System.Security.SecurityException>clase.</xref:System.Security.SecurityException>  
  
 [!code-vb[VbVbalrStatements&#85;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_2.vb)]  
  
 En esta situación de confianza parcial, tiene que poner el `Process.Start` instrucción en otro `Sub`. La llamada inicial a la `Sub` se producirá un error. Esto permite `Try...Catch` capturarla antes de la `Sub` que contiene `Process.Start` se inicia y se produce la excepción de seguridad.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra la estructura de la `Try...Catch...Finally` instrucción.  
  
 [!code-vb[VbVbalrStatements&#86;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_3.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, la `CreateException` método produce un `NullReferenceException`. El código que genera la excepción no está en un `Try` bloque. Por lo tanto, la `CreateException` método no controla la excepción. El `RunSample` método controlar la excepción porque la llamada a la `CreateException` método está en un `Try` bloque.  
  
 El ejemplo incluye `Catch` instrucciones para varios tipos de excepciones, se ordenan desde el más específico al más general.  
  
 [!code-vb[VbVbalrStatements&#91;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_4.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar un `Catch When` instrucción para filtrar en una expresión condicional. Si la expresión condicional se evalúa como `True`, el código en el `Catch` bloquear ejecuciones.  
  
 [!code-vb[VbVbalrStatements&#92;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_5.vb)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente tiene un `Try…Catch` instrucción que se encuentra en un `Try` bloque. Interno `Catch` bloque produce una excepción que tiene su `InnerException` propiedad establecida en la excepción original. Externo `Catch` bloque informa acerca de su propia excepción y la excepción interna.  
  
 [!code-vb[VbVbalrStatements&#93;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_6.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra el control de excepciones de los métodos asincrónicos. Para detectar una excepción que se aplica a una tarea asincrónica, el `Await` expresión está en un `Try` bloque del llamador y la excepción se detecta en el `Catch` bloque.  
  
 Quite la marca de comentario de la línea `Throw New Exception` en el ejemplo para demostrar el control de excepciones. La excepción es detectada en el `Catch` bloquear la tarea `IsFaulted` propiedad está establecida en `True`y la tarea `Exception.InnerException` propiedad se establece en la excepción.  
  
 Quite el `Throw New OperationCancelledException` línea para mostrar qué ocurre cuando se cancela un proceso asincrónico. La excepción es detectada en el `Catch` bloque y la tarea `IsCanceled` propiedad está establecida en `True`. Sin embargo, en algunas condiciones que no se aplican a este ejemplo, `IsFaulted` está establecido en `True` y `IsCanceled` está establecido en `False`.  
  
 [!code-vb[csAsyncExceptions n.º&1;](../../../csharp/language-reference/keywords/codesnippet/VisualBasic/try-catch-finally-statement_7.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra el control de excepciones en el que varias tareas pueden producir varias excepciones. El `Try` bloque tiene el `Await` expresión para la tarea que <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>devuelto.</xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> La tarea está completa cuando las tres tareas que <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>se aplica completados.</xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>  
  
 Cada una de las tres tareas produce una excepción. El `Catch` bloque itera a través de las excepciones, que se encuentran en la `Exception.InnerExceptions` propiedad de la tarea que `Task.WhenAll` devuelto.  
  
 [!code-vb[csAsyncExceptions&3;](../../../csharp/language-reference/keywords/codesnippet/VisualBasic/try-catch-finally-statement_8.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Information.Err%2A></xref:Microsoft.VisualBasic.Information.Err%2A>   
 <xref:System.Exception></xref:System.Exception>   
 [Exit (instrucción)](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [On Error (instrucción)](../../../visual-basic/language-reference/statements/on-error-statement.md)   
 [Procedimientos recomendados para utilizar fragmentos de código](https://docs.microsoft.com/visualstudio/ide/best-practices-for-using-code-snippets)   
 [Control de excepciones](https://msdn.microsoft.com/library/dd997415)   
 [Throw (instrucción)](../../../visual-basic/language-reference/statements/throw-statement.md)
