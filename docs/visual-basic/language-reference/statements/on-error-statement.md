---
title: On Error (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.OnError
helpviewer_keywords:
- Visual Basic code, control flow
- Resume Next statement [Visual Basic]
- errors [Visual Basic], trapping
- error handling, On Error statement
- Next statement [Visual Basic], On Error
- control flow [Visual Basic], branching
- Error keyword [Visual Basic]
- execution [Visual Basic], conditional
- Resume statement [Visual Basic], and On Error statement
- Error statement [Visual Basic], and On Error statement
- GoTo statement [Visual Basic], and On Error statement
- branching [Visual Basic], on error
- conditional statements [Visual Basic], On Error
- On Error statement [Visual Basic], syntax
- On keyword [Visual Basic]
- run-time errors [Visual Basic], handling
- On Error statement [Visual Basic]
ms.assetid: ff947930-fb84-40cf-bd66-1ea219561d5c
ms.openlocfilehash: d62c2ba1849b7015ed877d503220026a2dfeff57
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353817"
---
# <a name="on-error-statement-visual-basic"></a>Instrucción On Error (Visual Basic)
Habilita una rutina de control de errores y especifica la ubicación de la rutina dentro de un procedimiento. también se puede usar para deshabilitar una rutina de control de errores. La instrucción `On Error` se usa en el control de errores no estructurado y se puede usar en lugar de un control de excepciones estructurado. El [control estructurado de excepciones](../../../standard/exceptions/index.md) está integrado en .net, suele ser más eficaz y, por lo tanto, se recomienda al controlar los errores en tiempo de ejecución en la aplicación.

 Sin el control de errores o el control de excepciones, cualquier error en tiempo de ejecución que se produzca es grave: se muestra un mensaje de error y se detiene la ejecución.

> [!NOTE]
> La palabra clave `Error` también se usa en la [instrucción de error](../../../visual-basic/language-reference/statements/error-statement.md), que se admite por compatibilidad con versiones anteriores.

## <a name="syntax"></a>Sintaxis

```vb
On Error { GoTo [ line | 0 | -1 ] | Resume Next }
```

## <a name="parts"></a>Elementos

|Término|Definición|
|---|---|
|*línea* `GoTo`|Habilita la rutina de control de errores que se inicia en la línea especificada en el argumento de *línea* requerido. El argumento *line* es cualquier etiqueta de línea o número de línea. Si se produce un error en tiempo de ejecución, el control se bifurca en la línea especificada, lo que activa el controlador de errores. La línea especificada debe estar en el mismo procedimiento que la instrucción `On Error` o se producirá un error en tiempo de compilación.|
|`GoTo 0`|Deshabilita el controlador de errores habilitado en el procedimiento actual y lo restablece en `Nothing`.|
|`GoTo -1`|Deshabilita la excepción habilitada en el procedimiento actual y la restablece en `Nothing`.|
|`Resume Next`|Especifica que cuando se produce un error en tiempo de ejecución, el control va a la instrucción inmediatamente posterior a la instrucción en la que se produjo el error y la ejecución continúa a partir de ese punto. Utilice este formulario en lugar de `On Error GoTo` al obtener acceso a los objetos.|

## <a name="remarks"></a>Comentarios

> [!NOTE]
> Se recomienda usar el control de excepciones estructurado en el código siempre que sea posible, en lugar de usar el control de excepciones no estructurado y la instrucción `On Error`. Para obtener más información, vea [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) (Try...Catch...Finally [Instrucción, Visual Basic]).

 Un controlador de errores "habilitado" es el que está activado por una instrucción `On Error`. Un controlador de errores "activo" es un controlador habilitado que se encuentra en el proceso de control de un error.

 Si se produce un error mientras un controlador de errores está activo (entre la aparición del error y una instrucción `Resume`, `Exit Sub`, `Exit Function`o `Exit Property`), el controlador de errores del procedimiento actual no puede controlar el error. El control vuelve al procedimiento que realiza la llamada.
  
 Si el procedimiento de llamada tiene un controlador de errores habilitado, se activa para controlar el error. Si el controlador de errores del procedimiento que realiza la llamada también está activo, el control pasa a través de los procedimientos de llamada anteriores hasta que se encuentra un controlador de errores habilitado, pero inactivo. Si no se encuentra ningún controlador de errores, el error es grave en el punto en el que se produjo realmente.
  
 Cada vez que el controlador de errores vuelve a pasar el control a un procedimiento que realiza la llamada, ese procedimiento se convierte en el procedimiento actual. Una vez que un controlador de errores controla un error en cualquier procedimiento, la ejecución se reanuda en el procedimiento actual en el punto designado por la instrucción `Resume`.
  
> [!NOTE]
> Una rutina de control de errores no es un procedimiento `Sub` o un procedimiento `Function`. Es una sección de código marcada por una etiqueta de línea o un número de línea.
  
## <a name="number-property"></a>Propiedad Number
 Las rutinas de control de errores se basan en el valor de la propiedad `Number` del objeto `Err` para determinar la causa del error. La rutina debe probar o guardar los valores de propiedad relevantes en el objeto `Err` antes de que pueda producirse cualquier otro error o antes de que se llame a un procedimiento que puede provocar un error. Los valores de propiedad del objeto `Err` reflejan solo el error más reciente. El mensaje de error asociado a `Err.Number` está contenido en `Err.Description`.  
  
## <a name="throw-statement"></a>Throw (Instrucción)  
 Un error que se produce con el método `Err.Raise` establece la propiedad `Exception` en una instancia recién creada de la clase <xref:System.Exception>. Con el fin de admitir la generación de excepciones de tipos de excepción derivados, se admite una instrucción `Throw` en el lenguaje. Esto toma un parámetro único que es la instancia de excepción que se va a producir. En el ejemplo siguiente se muestra cómo se pueden usar estas características con la compatibilidad con el control de excepciones existente:

 [!code-vb[VbVbalrErrorHandling#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#17)]  
  
 Tenga en cuenta que la instrucción `On Error GoTo` captura todos los errores, independientemente de la clase de excepción.
  
## <a name="on-error-resume-next"></a>Al reanudar el error siguiente
 `On Error Resume Next` hace que la ejecución continúe con la instrucción inmediatamente posterior a la instrucción que causó el error en tiempo de ejecución, o con la instrucción inmediatamente posterior a la llamada más reciente del procedimiento que contiene la instrucción `On Error Resume Next`. Esta instrucción permite que la ejecución continúe a pesar de un error en tiempo de ejecución. Puede colocar la rutina de control de errores en la que se produciría el error en lugar de transferir el control a otra ubicación dentro del procedimiento. Una instrucción `On Error Resume Next` se vuelve inactiva cuando se llama a otro procedimiento, por lo que debe ejecutar una instrucción `On Error Resume Next` en cada rutina llamada si desea controlar los errores en línea dentro de esa rutina.
  
> [!NOTE]
> La construcción `On Error Resume Next` puede ser preferible a `On Error GoTo` al controlar los errores generados durante el acceso a otros objetos. La comprobación de `Err` después de cada interacción con un objeto elimina la ambigüedad sobre el objeto al que tuvo acceso el código. Puede asegurarse de que el objeto colocó el código de error en `Err.Number`, así como el objeto que generó originalmente el error (el objeto especificado en `Err.Source`).

## <a name="on-error-goto-0"></a>On error GoTo 0
 `On Error GoTo 0` deshabilita el control de errores en el procedimiento actual. No especifica la línea 0 como el inicio del código de control de errores, aunque el procedimiento contenga una línea numerada como 0. Sin una instrucción `On Error GoTo 0`, se deshabilita automáticamente un controlador de errores cuando se sale de un procedimiento.

## <a name="on-error-goto--1"></a>On error GoTo-1
 `On Error GoTo -1` deshabilita la excepción en el procedimiento actual. No especifica line-1 como el inicio del código de control de errores, aunque el procedimiento contenga una línea numerada-1. Sin una instrucción `On Error GoTo -1`, se deshabilita automáticamente una excepción cuando se sale de un procedimiento.

 Para evitar que se ejecute código de control de errores cuando no se ha producido ningún error, coloque una instrucción `Exit Sub`, `Exit Function`o `Exit Property` inmediatamente antes de la rutina de control de errores, como en el fragmento siguiente:

 [!code-vb[VbVbalrErrorHandling#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#18)]

 Aquí, el código de control de errores sigue la instrucción `Exit Sub` y precede a la instrucción `End Sub` para separarlo del flujo de procedimiento. Puede colocar el código de control de errores en cualquier parte de un procedimiento.

## <a name="untrapped-errors"></a>Errores no interceptados
 Los errores no interceptados de los objetos se devuelven a la aplicación de control cuando el objeto se ejecuta como un archivo ejecutable. En el entorno de desarrollo, los errores no interceptados se devuelven a la aplicación de control solo si se establecen las opciones adecuadas. Consulte la documentación de la aplicación host para obtener una descripción de las opciones que se deben establecer durante la depuración, cómo establecerlas y si el host puede crear clases.

 Si crea un objeto que tiene acceso a otros objetos, debe tratar de tratar cualquier error no controlado que pase. Si no es posible, asigne los códigos de error de `Err.Number` a uno de sus propios errores y, a continuación, vuelva a pasarlos al autor de la llamada del objeto. Debe especificar el error agregando el código de error a la constante `VbObjectError`. Por ejemplo, si el código de error es 1052, asígnelo como se indica a continuación:

 [!code-vb[VbVbalrErrorHandling#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#19)]

> [!CAUTION]
> Los errores del sistema durante las llamadas a las bibliotecas de vínculos dinámicos (dll) de Windows no generan excepciones y no se pueden interceptar con Visual Basic la interceptación de errores. Al llamar a funciones de DLL, debe comprobar si cada valor devuelto es correcto o incorrecto (de acuerdo con las especificaciones de la API) y, en caso de que se produzca un error, compruebe el valor de la propiedad `LastDLLError` del objeto `Err`.

## <a name="example"></a>Ejemplo
 En primer lugar, en este ejemplo se usa la instrucción `On Error GoTo` para especificar la ubicación de una rutina de control de errores dentro de un procedimiento. En el ejemplo, un intento de dividir por cero genera el número de error 6. El error se controla en la rutina de control de errores y, a continuación, el control se devuelve a la instrucción que provocó el error. La instrucción `On Error GoTo 0` desactiva la interceptación de errores. A continuación, se utiliza la instrucción `On Error Resume Next` para aplazar la interceptación de errores de modo que el contexto del error generado por la siguiente instrucción pueda ser conocido para ciertos. Tenga en cuenta que `Err.Clear` se utiliza para borrar las propiedades del objeto de `Err` una vez que se ha controlado el error.

 [!code-vb[VbVbalrErrorHandling#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#20)]

## <a name="requirements"></a>Requisitos
 **Espacio de nombres:** [Microsoft. VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)

 **Ensamblado:** Biblioteca en tiempo de ejecución de Visual Basic (en Microsoft. VisualBasic. dll)

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Number%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Description%2A>
- <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>
- [End (instrucción)](../../../visual-basic/language-reference/statements/end-statement.md)
- [Exit (instrucción)](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Resume (instrucción)](../../../visual-basic/language-reference/statements/resume-statement.md)
- [Mensajes de error](../../../visual-basic/language-reference/error-messages/index.md)
- [Try...Catch...Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
