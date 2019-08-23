---
title: Instrucción On Error (Visual Basic)
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
ms.openlocfilehash: df2bd232a870e17eeb5106cf0b60a9e77641969d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963533"
---
# <a name="on-error-statement-visual-basic"></a>Instrucción On Error (Visual Basic)
Habilita una rutina de control de errores y especifica la ubicación de la rutina dentro de un procedimiento. también se puede usar para deshabilitar una rutina de control de errores. La `On Error` instrucción se utiliza en el control de errores no estructurado y se puede usar en lugar de en el control de excepciones estructurado. El [control estructurado de excepciones](../../../standard/exceptions/index.md) está integrado en .net, suele ser más eficaz y, por lo tanto, se recomienda al controlar los errores en tiempo de ejecución en la aplicación.

 Sin el control de errores o el control de excepciones, cualquier error en tiempo de ejecución que se produzca es grave: se muestra un mensaje de error y se detiene la ejecución.

> [!NOTE]
> La `Error` palabra clave también se usa en la [instrucción de error](../../../visual-basic/language-reference/statements/error-statement.md), que se admite por compatibilidad con versiones anteriores.

## <a name="syntax"></a>Sintaxis

```vb
On Error { GoTo [ line | 0 | -1 ] | Resume Next }
```

## <a name="parts"></a>Elementos

|Término|Definición|
|---|---|
|`GoTo`*línea* de|Habilita la rutina de control de errores que se inicia en la línea especificada en el argumento de *línea* requerido. El argumento *line* es cualquier etiqueta de línea o número de línea. Si se produce un error en tiempo de ejecución, el control se bifurca en la línea especificada, lo que activa el controlador de errores. La línea especificada debe estar en el mismo procedimiento que la `On Error` instrucción o se producirá un error en tiempo de compilación.|
|`GoTo 0`|Deshabilita el controlador de errores habilitado en el procedimiento actual y lo `Nothing`restablece en.|
|`GoTo -1`|Deshabilita la excepción habilitada en el procedimiento actual y la restablece `Nothing`en.|
|`Resume Next`|Especifica que cuando se produce un error en tiempo de ejecución, el control va a la instrucción inmediatamente posterior a la instrucción en la que se produjo el error y la ejecución continúa a partir de ese punto. Utilice este formulario en lugar `On Error GoTo` de al obtener acceso a los objetos.|

## <a name="remarks"></a>Comentarios

> [!NOTE]
> Se recomienda usar el control de excepciones estructurado en el código siempre que sea posible, en lugar de usar el control de excepciones `On Error` no estructurado y la instrucción. Para obtener más información, vea [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) (Try...Catch...Finally [Instrucción, Visual Basic]).

 Un controlador de errores "habilitado" es el que está activado por `On Error` una instrucción. Un controlador de errores "activo" es un controlador habilitado que se encuentra en el proceso de control de un error.

 Si se produce un error mientras un controlador de errores está activo (entre la aparición del error y `Resume`una `Exit Sub`instrucción `Exit Function`,, `Exit Property` o), el controlador de errores del procedimiento actual no puede controlar el error. El control vuelve al procedimiento que realiza la llamada.
  
 Si el procedimiento de llamada tiene un controlador de errores habilitado, se activa para controlar el error. Si el controlador de errores del procedimiento que realiza la llamada también está activo, el control pasa a través de los procedimientos de llamada anteriores hasta que se encuentra un controlador de errores habilitado, pero inactivo. Si no se encuentra ningún controlador de errores, el error es grave en el punto en el que se produjo realmente.
  
 Cada vez que el controlador de errores vuelve a pasar el control a un procedimiento que realiza la llamada, ese procedimiento se convierte en el procedimiento actual. Una vez que un controlador de errores controla un error en cualquier procedimiento, la ejecución se reanuda en el procedimiento actual en el punto designado `Resume` por la instrucción.
  
> [!NOTE]
> Una rutina de control de errores no es `Sub` un procedimiento o `Function` un procedimiento. Es una sección de código marcada por una etiqueta de línea o un número de línea.
  
## <a name="number-property"></a>Propiedad Number
 Las rutinas de control de errores se basan en el `Number` valor de la `Err` propiedad del objeto para determinar la causa del error. La rutina debe probar o guardar los valores de propiedad relevantes `Err` en el objeto antes de que pueda producirse cualquier otro error o antes de que se llame a un procedimiento que puede provocar un error. Los valores de `Err` propiedad del objeto reflejan solo el error más reciente. El mensaje de error asociado `Err.Number` a está incluido `Err.Description`en.  
  
## <a name="throw-statement"></a>Throw (Instrucción)  
 Un error que se genera con el `Err.Raise` método establece la `Exception` propiedad en una instancia recién creada de la <xref:System.Exception> clase. Con el fin de admitir la generación de excepciones de tipos de excepción derivados `Throw` , se admite una instrucción en el lenguaje. Esto toma un parámetro único que es la instancia de excepción que se va a producir. En el ejemplo siguiente se muestra cómo se pueden usar estas características con la compatibilidad con el control de excepciones existente:

 [!code-vb[VbVbalrErrorHandling#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#17)]  
  
 Observe que la `On Error GoTo` instrucción captura todos los errores, independientemente de la clase de excepción.
  
## <a name="on-error-resume-next"></a>Al reanudar el error siguiente
 `On Error Resume Next`hace que la ejecución continúe con la instrucción inmediatamente posterior a la instrucción que causó el error en tiempo de ejecución, o con la instrucción inmediatamente posterior a la llamada más reciente fuera del `On Error Resume Next` procedimiento que contiene la instrucción. Esta instrucción permite que la ejecución continúe a pesar de un error en tiempo de ejecución. Puede colocar la rutina de control de errores en la que se produciría el error en lugar de transferir el control a otra ubicación dentro del procedimiento. Una `On Error Resume Next` instrucción pasa a estar inactiva cuando se llama a otro procedimiento, por lo `On Error Resume Next` que debe ejecutar una instrucción en cada rutina llamada si desea controlar los errores en línea dentro de esa rutina.
  
> [!NOTE]
> La `On Error Resume Next` construcción puede ser preferible a `On Error GoTo` cuando se controlan los errores generados durante el acceso a otros objetos. La `Err` comprobación después de cada interacción con un objeto elimina la ambigüedad sobre el objeto al que tuvo acceso el código. Puede asegurarse del objeto en el que se colocó el código `Err.Number`de error, así como el objeto que generó originalmente el error (el objeto `Err.Source`especificado en).

## <a name="on-error-goto-0"></a>On error GoTo 0
 `On Error GoTo 0`deshabilita el control de errores en el procedimiento actual. No especifica la línea 0 como el inicio del código de control de errores, aunque el procedimiento contenga una línea numerada como 0. Sin una `On Error GoTo 0` instrucción, un controlador de errores se deshabilita automáticamente cuando se sale de un procedimiento.

## <a name="on-error-goto--1"></a>On error GoTo-1
 `On Error GoTo -1`deshabilita la excepción en el procedimiento actual. No especifica line-1 como el inicio del código de control de errores, aunque el procedimiento contenga una línea numerada-1. Sin una `On Error GoTo -1` instrucción, se deshabilita automáticamente una excepción cuando se sale de un procedimiento.

 Para evitar que se ejecute código de control de errores cuando no se ha producido ningún `Exit Sub`error `Exit Function`, coloque `Exit Property` una instrucción, o inmediatamente antes de la rutina de control de errores, como en el fragmento siguiente:

 [!code-vb[VbVbalrErrorHandling#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#18)]

 Aquí, el código de control de errores sigue `Exit Sub` la instrucción y precede `End Sub` a la instrucción para separarlo del flujo de procedimiento. Puede colocar el código de control de errores en cualquier parte de un procedimiento.

## <a name="untrapped-errors"></a>Errores no interceptados
 Los errores no interceptados de los objetos se devuelven a la aplicación de control cuando el objeto se ejecuta como un archivo ejecutable. En el entorno de desarrollo, los errores no interceptados se devuelven a la aplicación de control solo si se establecen las opciones adecuadas. Consulte la documentación de la aplicación host para obtener una descripción de las opciones que se deben establecer durante la depuración, cómo establecerlas y si el host puede crear clases.

 Si crea un objeto que tiene acceso a otros objetos, debe tratar de tratar cualquier error no controlado que pase. Si no es posible, asigne los códigos de `Err.Number` error de a uno de sus propios errores y, a continuación, devuelvalos al autor de la llamada del objeto. Debe especificar el error agregando el código de error a la `VbObjectError` constante. Por ejemplo, si el código de error es 1052, asígnelo como se indica a continuación:

 [!code-vb[VbVbalrErrorHandling#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#19)]

> [!CAUTION]
>  Los errores del sistema durante las llamadas a las bibliotecas de vínculos dinámicos (dll) de Windows no generan excepciones y no se pueden interceptar con Visual Basic la interceptación de errores. Al llamar a funciones de dll, debe comprobar si cada valor devuelto es correcto o incorrecto (según las especificaciones de la API) y, en caso de que se produzca un error `Err` , compruebe `LastDLLError` el valor de la propiedad del objeto.

## <a name="example"></a>Ejemplo
 En primer lugar, en `On Error GoTo` este ejemplo se usa la instrucción para especificar la ubicación de una rutina de control de errores dentro de un procedimiento. En el ejemplo, un intento de dividir por cero genera el número de error 6. El error se controla en la rutina de control de errores y, a continuación, el control se devuelve a la instrucción que provocó el error. La `On Error GoTo 0` instrucción desactiva la interceptación de errores. A continuación `On Error Resume Next` , la instrucción se utiliza para aplazar la interceptación de errores de modo que el contexto del error generado por la siguiente instrucción pueda ser conocido para ciertos. Tenga en `Err.Clear` cuenta que se utiliza para `Err` borrar las propiedades del objeto después de que se controle el error.

 [!code-vb[VbVbalrErrorHandling#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#20)]

## <a name="requirements"></a>Requisitos
 **Espacio de nombres**: [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)

 **Assembl** Biblioteca en tiempo de ejecución de Visual Basic (en Microsoft.VisualBasic.dll)

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
