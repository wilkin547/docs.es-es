---
title: "Instrucci&#243;n Try...Catch...Finally (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Try...Catch...Finally"
  - "vb.when"
  - "vb.Finally"
  - "vb.Catch"
  - "vb.Try"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Catch (instrucción)"
  - "control de errores, mientras se ejecuta el código"
  - "Finally (palabra clave) [Visual Basic], Try...Catch...Finally"
  - "control estructurado de excepciones, Try...Catch...Finally (instrucciones)"
  - "Try (instrucción)"
  - "Try (instrucción), Try...Catch...Finally"
  - "Try...Catch...Finally (instrucciones)"
  - "control de excepciones try-catch, Try...Catch...Finally (instrucciones)"
  - "código de Visual Basic, controlar errores durante la ejecución"
  - "When (palabra clave)"
ms.assetid: d6488026-ccb3-42b8-a810-0d97b9d6472b
caps.latest.revision: 69
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 69
---
# Instrucci&#243;n Try...Catch...Finally (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Esta instrucción proporciona una manera de controlar algunos o todos los errores posibles que pueden ocurrir en un bloque de código determinado mientras se ejecuta el código.  
  
## Sintaxis  
  
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
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`tryStatements`|Opcional.  Instrucciones en las que puede ocurrir un error.  Puede ser una instrucción compuesta.|  
|`Catch`|Opcional.  Se permite utilizar varios bloques `Catch`.  Si se produce una excepción al procesar el bloque `Try`, cada instrucción `Catch` se examina en orden textual para determinar si controla la excepción; el parámetro `exception` representa la excepción que se ha producido.|  
|`exception`|Opcional.  Cualquier nombre de variable.  El valor inicial de `exception` es el valor del error producido.  Se utiliza con `Catch` para especificar la captura del error.  Si se omite, la instrucción `Catch` detecta cualquier excepción.|  
|`type`|Opcional.  Especifica el tipo de filtro de clase.  Si el valor de `exception` es del tipo especificado en `type` o de un tipo derivado, el identificador queda enlazado al objeto de excepción.|  
|`When`|Opcional.  Una instrucción `Catch` con una cláusula `When` sólo detecta las excepciones cuando `expression` se evalúa como `True`.  Una cláusula `When` sólo se aplica después de comprobar el tipo de la excepción y `expression` puede hacer referencia al identificador que representa la excepción.|  
|`expression`|Opcional.  Debe ser convertible implícitamente a `Boolean`.  Cualquier expresión que describe un filtro genérico.  Se utiliza normalmente para filtrar por número de error.  Se utiliza con la palabra clave `When` para especificar las circunstancias bajo las que se captura el error.|  
|`catchStatements`|Opcional.  Instrucciones para controlar los errores que se producen en el bloque `Try` asociado.  Puede ser una instrucción compuesta.|  
|`Exit Try`|Opcional.  Palabra clave que interrumpe la ejecución de la estructura `Try...Catch...Finally`.  La ejecución se reanuda con el código que sigue inmediatamente a la instrucción `End Try`.  Se ejecutará la instrucción `Finally` todavía.  No se permite en bloques `Finally`.|  
|`Finally`|Opcional.  Siempre se ejecuta un bloque `Finally` cuando la ejecución sale de cualquier parte de la instrucción `Try...Catch`.|  
|`finallyStatements`|Opcional.  Instrucciones que se ejecutan después de las demás operaciones de procesamiento de error.|  
|`End Try`|Finaliza la estructura `Try...Catch...Finally`.|  
  
## Comentarios  
 Si piensa que se puede producir una excepción determinada en una sección concreta del código, incluya éste en un bloque `Try` y utilice un bloque `Catch` para conservar el control y tratar la excepción que se produce.  
  
 Una instrucción `Try…Catch` consiste en un bloque `Try` seguido de una o más cláusulas `Catch`, que especifican controladores para varias excepciones.  Cuando se produce una excepción en un bloque `Try`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] busca la instrucción `Catch` que controla la excepción.  Si no se encuentra una instrucción `Catch` coincidente, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] examina el método que llamó al método actual, y así sucesivamente hasta la pila de llamadas.  Si no se encuentra ningún bloque `Catch`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] muestra al usuario un mensaje de excepción no controlada y detiene la ejecución del programa.  
  
 Puede utilizar más de una instrucción `Catch` en una instrucción `Try…Catch` .  Si lo hace, el orden de las cláusulas `Catch` es significativo debido a que se examinan en orden.  Las excepciones más específicas se capturan antes que las menos específicas.  
  
 Las siguientes condiciones de la instrucción `Catch` son las menos específicas y detectarán todas las excepciones que se deriven de la clase <xref:System.Exception>.  Normalmente debe utilizar una de estas variaciones como el último bloque `Catch` de la estructura `Try...Catch...Finally`, después de detectar todas las excepciones específicas que espera.  El flujo de control nunca puede alcanzar un bloque `Catch` situado detrás de cualquiera de estas variaciones.  
  
-   El `type` es `Exception`, por ejemplo: `Catch ex As Exception`  
  
-   La instrucción no tiene ninguna variable `exception`, por ejemplo: `Catch`  
  
 Cuando una instrucción `Try…Catch…Finally` está anidada en otro bloque `Try`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] primero examina cada instrucción `Catch` en el bloque `Try` más interno.  Si no encuentra ninguna instrucción `Catch` coincidente, la búsqueda continúa en las instrucciones `Catch` del bloque `Try…Catch…Finally` exterior.  
  
 Las variables locales de un bloque `Try` no se encuentran disponibles en un bloque `Catch` porque se trata de bloques independientes.  Si se desea utilizar una variable en más de un bloque, se debe declarar la variable fuera de la estructura `Try...Catch...Finally`.  
  
> [!TIP]
>  La instrucción `Try…Catch…Finally` está disponible como un fragmento de código de IntelliSense.  En el Administrador de fragmentos de código, expanda **Modelos de código \- If, For Each, Try Catch, Property, etc**, y **Control de errores \(excepciones\)**.  Para obtener más información, vea [Fragmentos de código](/visual-studio/ide/code-snippets).  
  
## Bloque Finally  
 Si tiene una o más instrucciones que se deben ejecutar antes de salir de la estructura `Try`, utilice un bloque `Finally`.  El control pasa al bloque `Finally` justo antes de salir de la estructura `Try…Catch`.  Esto se produce incluso si aparece una excepción dentro de la estructura `Try`.  
  
 Un bloque `Finally` es útil para ejecutar cualquier código que debe ejecutar incluso si hay una excepción.  El control se pasa al bloque `Finally` independientemente de cómo se sale del bloque `Try...Catch`.  
  
 El código de un bloque `Finally` se ejecuta incluso si el código encuentra una instrucción `Return` en un bloque `Try` o `Catch`.  El control no pasa de un bloque `Try` o `Catch` al bloque `Finally` correspondiente en los casos siguientes:  
  
-   Se encuentra [End \(Instrucción\)](../../../visual-basic/language-reference/statements/end-statement.md) en el bloque `Try` o `Catch`.  
  
-   Se produce <xref:System.StackOverflowException> en el bloque `Try` o `Catch`.  
  
 No es válido explícitamente transferir la ejecución en un bloque de `Finally` .  Transferir la ejecución de un bloque de `Finally` no es válido, pero con una excepción.  
  
 Si una instrucción `Try` no contiene al menos un bloque `Catch`, debe contener un bloque `Finally`.  
  
> [!TIP]
>  Si no tiene que detectar excepciones específicas, la instrucción `Using` se comporta como un bloque `Try…Finally` y garantiza la disposición de los recursos, independientemente de cómo salga del bloque.  Esto es cierto incluso con una excepción no controlada.  Para obtener más información, vea [Using \(Instrucción\)](../../../visual-basic/language-reference/statements/using-statement.md).  
  
## Argumento de la excepción  
 El argumento `exception` del bloque `Catch` es una instancia de la clase <xref:System.Exception> o una clase que se deriva de la clase `Exception`.  La instancia de la clase `Exception` corresponde al error que se produjo en el bloque `Try`.  
  
 Las propiedades del objeto `Exception` ayudan a identificar la causa y la ubicación de una excepción.  Por ejemplo, la propiedad <xref:System.Exception.StackTrace%2A> muestra una lista de los métodos llamados que generaron la excepción, lo que ayuda a detectar el lugar del código en el que ocurrió el error.  <xref:System.Exception.Message%2A> devuelve un mensaje que describe la excepción.  <xref:System.Exception.HelpLink%2A> devuelve un vínculo a un archivo de ayuda asociado.  <xref:System.Exception.InnerException%2A> devuelve el objeto `Exception` que causó la excepción actual, o devuelve `Nothing` si no hay ninguna `Exception` original.  
  
## Consideraciones sobre cuándo utilizar una instrucción Try…Catch  
 Utilice una instrucción `Try…Catch` solo para indicar la ocurrencia de eventos de programa inusuales o imprevistos.  Esto pasa por las siguientes razones:  
  
-   Detectar excepciones en tiempo de ejecución crea sobrecarga adicional, y es probable que sea más lento que la comprobación previa para evitar excepciones.  
  
-   Si un bloque `Catch` no se maneja correctamente, puede que no se informe correctamente a los usuarios acerca de la excepción.  
  
-   El control de excepciones hace a un programa más complejo.  
  
 No siempre es necesario una instrucción `Try…Catch` para comprobar una condición que es probable que ocurra.  El siguiente ejemplo comprueba si existe un archivo antes de intentar abrirlo.  Esto reduce la necesidad de detectar una excepción iniciada por el método <xref:System.IO.File.OpenText%2A> .  
  
 [!code-vb[VbVbalrStatements#94](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_1.vb)]  
  
 Asegúrese de que el código de los bloques `Catch` puede informar correctamente de las excepciones a los usuarios, ya sea a través del registro seguro para subprocesos o de mensajes adecuados.  De lo contrario, las excepciones podrían seguir siendo desconocidas.  
  
## Métodos Async  
 Si marca un método con el modificador de [Asincrónica](../../../visual-basic/language-reference/modifiers/async.md) , puede utilizar el operador de [Espera](../../../visual-basic/language-reference/operators/await-operator.md) en el método.  Un fragmento con el operador de `Await` suspende la ejecución del método hasta que la tarea aguardada complete.  La tarea representa el trabajo en curso.  Cuando la tarea asociada a los finals de operador de `Await` , ejecución se reanuda en el mismo método.  Para obtener más información, vea [Flujo de control en programas Async](../Topic/Control%20Flow%20in%20Async%20Programs%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Una tarea devuelta por un método Async puede finalizar con errores, indicando que completó debido a una excepción no controlada.  Una tarea también puede finalizar en un estado cancelado, que da lugar a `OperationCanceledException` que se va a iniciar de la expresión de aguardar.  Para detectar cualquier tipo de excepción, coloque la expresión de `Await` asociado a la tarea en un bloque de `Try` , y detectar la excepción en el bloque de `Catch` .  Un ejemplo se explica más adelante en este tema.  
  
 Una tarea puede estar con errores porque varias excepciones son responsables del error.  Por ejemplo, la tarea puede ser el resultado de una llamada a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.  Cuando se espera por tarea, la excepción detectada es solo una de las excepciones, y no puede predecir qué excepción se detectar.  Un ejemplo se explica más adelante en este tema.  
  
 Una expresión de `Await` no puede estar dentro de un bloque de `Catch` o de bloque de `Finally` .  
  
## Iteradores  
 Una función de iterador o un descriptor de acceso de `Get` realiza una iteración personalizada en una colección.  Un iterador utiliza un fragmento de [producción](../../../visual-basic/language-reference/statements/yield-statement.md) para devolver cada elemento de la colección de uno en uno.  Llama a una función de iterador mediante [For Each...Next \(Instrucción\)](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
 Un fragmento de `Yield` puede estar dentro de un bloque de `Try` .  `Try` bloqueos que contiene un fragmento de `Yield` puede tener bloques de `Catch` , y un bloque de `Finally` .  Vea “bloque Try en la sección de Visual Basic” de [Iteradores](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md) para obtener un ejemplo.  
  
 Un fragmento de `Yield` no puede estar dentro de un bloque de `Catch` o bloque de `Finally` .  
  
 Si el cuerpo de `For Each` \(fuera de la función de iterador\) produce una excepción, un bloque de `Catch` en la función de iterador no se ejecuta, pero un bloque de `Finally` en la función de iterador se ejecuta.  Un bloque de `Catch` dentro de una función de iterador detecta las excepciones que se producen dentro de la función de iterador.  
  
## Situaciones de confianza parcial  
 En situaciones de confianza parcial, como una aplicación hospedada en un recurso compartido de red, `Try...Catch...Finally` no detectará las excepciones de seguridad que se produzcan antes de llamar al método que contiene la llamada.  El ejemplo siguiente, si se coloca en un recurso compartido de servidor y se ejecuta desde el mismo, producirá el error: "Sub System.Security.SecurityException: Error de solicitud". Para obtener más información sobre excepciones de seguridad, vea la clase <xref:System.Security.SecurityException>.  
  
 [!code-vb[VbVbalrStatements#85](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_2.vb)]  
  
 En este tipo de situación de confianza parcial, debe colocar la instrucción `Process.Start` en un procedimiento `Sub` independiente.  La llamada inicial a `Sub` producirá un error.  Esto permite que `Try...Catch` lo capture antes de que se inicie el procedimiento `Sub` que contiene `Process.Start` y se produzca la excepción de seguridad.  
  
## Ejemplo  
 El ejemplo siguiente muestra la estructura de la instrucción `Try...Catch...Finally`.  
  
 [!code-vb[VbVbalrStatements#86](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_3.vb)]  
  
## Ejemplo  
 En el ejemplo siguiente, el método `CreateException` arroja una `NullReferenceException`.  El código que genera la excepción no está en un bloque `Try` .  Por lo tanto, el método `CreateException` no controla la excepción.  El método `RunSample` no controla la excepción porque la llamada al método `CreateException` está en un bloque `Try`.  
  
 El ejemplo incluye instrucciones `Catch` para varios tipos de excepciones, ordenadas de la más específica a la más general.  
  
 [!code-vb[VbVbalrStatements#91](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_4.vb)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar una instrucción `Catch When` para filtrar una expresión condicional.  Si la expresión condicional se evalúa a `True`, se ejecuta el código en el bloque `Catch`.  
  
 [!code-vb[VbVbalrStatements#92](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_5.vb)]  
  
## Ejemplo  
 El ejemplo siguiente tiene una instrucción `Try…Catch` incluida en un bloque `Try` .  El bloque `Catch` interior produce una excepción que tiene su propiedad `InnerException` establecida en la excepción original.  El bloque exterior `Catch` informa de su propia excepción y de la excepción interna.  
  
 [!code-vb[VbVbalrStatements#93](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_6.vb)]  
  
## Ejemplo  
 El ejemplo siguiente se muestra el control de excepciones para los métodos async.  Para detectar una excepción que se aplique a una tarea async, la expresión de `Await` está en un bloque de `Try` del llamador, y la excepción se detecta en el bloque de `Catch` .  
  
 Quite los comentarios de la línea de `Throw New Exception` en el ejemplo para mostrar el control de excepciones.  La excepción se detecta en el bloque de `Catch` , la propiedad de `IsFaulted` de la tarea se establece en `True`, y la propiedad de `Exception.InnerException` de la tarea se establece en la excepción.  
  
 Quite los comentarios de la línea de `Throw New OperationCancelledException` para mostrar qué ocurre al cancelar un proceso asincrónico.  La excepción se detecta en el bloque de `Catch` , y la propiedad de `IsCanceled` de la tarea se establece en `True`.  Sin embargo, en algunas condiciones que no se aplican a este ejemplo, `IsFaulted` se establece en `True` y `IsCanceled` se establece en `False`.  
  
 [!code-vb[csAsyncExceptions#1](../../../csharp/language-reference/keywords/codesnippet/VisualBasic/try-catch-finally-statement_7.vb)]  
  
## Ejemplo  
 El ejemplo siguiente se muestra el control de excepciones donde varias tareas pueden producir excepciones.  El bloque de `Try` tiene la expresión de `Await` para la tarea que <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> devolvió.  Finaliza la tarea cuando se completan las tres tareas a las que se aplica <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> .  
  
 Cada una de las tres causas de tareas una excepción.  El bloque de `Catch` recorre las excepciones, que se encuentran en la propiedad de `Exception.InnerExceptions` de la tarea que `Task.WhenAll` devolvió.  
  
 [!code-vb[csAsyncExceptions#3](../../../csharp/language-reference/keywords/codesnippet/VisualBasic/try-catch-finally-statement_8.vb)]  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Information.Err%2A>   
 <xref:System.Exception>   
 [Exit \(Instrucción\)](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [On Error \(Instrucción\)](../../../visual-basic/language-reference/statements/on-error-statement.md)   
 [Procedimientos recomendados para usar fragmentos de código](/visual-studio/ide/best-practices-for-using-code-snippets)   
 [Control de excepciones](../Topic/Exception%20Handling%20\(Task%20Parallel%20Library\).md)   
 [Throw \(Instrucción\)](../../../visual-basic/language-reference/statements/throw-statement.md)