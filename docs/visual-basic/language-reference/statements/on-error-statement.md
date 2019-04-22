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
ms.openlocfilehash: 0a5a5261e6b71178adce02a5635c1f91a1469f3d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58834275"
---
# <a name="on-error-statement-visual-basic"></a>Instrucción On Error (Visual Basic)
Habilita una rutina de control de errores y se especifica la ubicación de la rutina dentro de un procedimiento; También puede usarse para deshabilitar una rutina de control de errores.  
  
 Sin control de errores, cualquier error de tiempo de ejecución que se produce es irrecuperable: se muestra un mensaje de error y detiene la ejecución.  
  
 Siempre que sea posible, se recomienda usar en el código de control, en lugar de utilizar el control no estructurado de excepciones estructurado de excepciones y el `On Error` instrucción. Para obtener más información, vea [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) (Try...Catch...Finally [Instrucción, Visual Basic]).  
  
> [!NOTE]
>  El `Error` también se utiliza la palabra clave en el [Error (instrucción)](../../../visual-basic/language-reference/statements/error-statement.md), que se admite por compatibilidad con versiones anteriores.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
On Error { GoTo [ line | 0 | -1 ] | Resume Next }  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`GoTo` `line`|Habilita la rutina de control de errores que comienza en la línea especificada en la sección necesario `line` argumento. El `line` argumento es cualquier etiqueta de línea o el número de línea. Si se produce un error en tiempo de ejecución, el control se transfiere a la línea especificada, que hace el controlador de errores activos. La línea especificada debe estar en el mismo procedimiento que la `On Error` se producirá la instrucción o un error en tiempo de compilación.|  
|`GoTo` 0|Deshabilita el controlador de errores habilitado en el procedimiento actual y la restablece a `Nothing`.|  
|`GoTo` -1|Deshabilita la excepción habilitada en el procedimiento actual y la restablece a `Nothing`.|  
|`Resume Next`|Especifica que cuando se produce un error en tiempo de ejecución, el control pasa a la instrucción inmediatamente posterior a la instrucción donde se produjo el error y la ejecución continúa desde ese punto. Utilice este formulario en lugar de `On Error GoTo` al tener acceso a objetos.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Le recomendamos que use el control de excepciones estructurado en el código siempre que sea posible, en lugar de utilizar el control no estructurado de excepciones y el `On Error` instrucción. Para obtener más información, vea [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) (Try...Catch...Finally [Instrucción, Visual Basic]).  
  
 Un controlador de errores "habilitado" es aquel que está activado de forma un `On Error` instrucción. Un controlador de errores "activo" es un controlador habilitado que está en proceso de controlar un error.  
  
 Si se produce un error mientras está activo un controlador de errores (entre la repetición del error y un `Resume`, `Exit Sub`, `Exit Function`, o `Exit Property` instrucción), controlador de errores del procedimiento actual no puede controlar el error. El control vuelve al procedimiento que realiza la llamada.  
  
 Si el procedimiento que realiza la llamada tiene un controlador de errores habilitado, se activa para controlar el error. Si el controlador de errores del procedimiento que realiza la llamada también está activo, control pasa a través de procedimientos que realiza la llamada anteriores hasta que se encuentra un controlador de errores habilitado, pero inactivo. Si no se encuentra ningún controlador de errores de este tipo, el error es irrecuperable en el momento en que ocurrió realmente.  
  
 Cada vez que el controlador de errores devuelve el control a un procedimiento que realiza la llamada, ese procedimiento se convierte en el procedimiento actual. Una vez que un error se controla mediante un controlador de errores en cualquier procedimiento, se reanuda la ejecución del procedimiento actual en el punto designado por el `Resume` instrucción.  
  
> [!NOTE]
>  Una rutina de control de errores no es un `Sub` procedimiento o un `Function` procedimiento. Es una sección de código marcada por una etiqueta de línea o un número de línea.  
  
## <a name="number-property"></a>Propiedad de número  
 Rutinas de control de errores se basan en el valor de la `Number` propiedad de la `Err` para determinar la causa del error. La rutina debe probar o guardar los valores de propiedad correspondiente en el `Err` antes que cualquier otro error puede producirse o antes de un procedimiento que puede provocar que se llama a un error. Los valores de propiedad en el `Err` objeto reflejan solo el error más reciente. El mensaje de error asociado con `Err.Number` se encuentra en `Err.Description`.  
  
## <a name="throw-statement"></a>Throw (Instrucción)  
 Un error que se genera con el `Err.Raise` método establece el `Exception` propiedad a una instancia recién creada de la <xref:System.Exception> clase. Para poder provocar excepciones de tipos de excepción derivada, una `Throw` se admite la instrucción en el lenguaje. Esto toma un parámetro único que es la instancia de excepción que se produzca. El ejemplo siguiente muestra cómo se pueden usar estas características con el control de excepciones existente:  
  
 [!code-vb[VbVbalrErrorHandling#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#17)]  
  
 Tenga en cuenta que el `On Error GoTo` instrucción intercepta todos los errores, independientemente de la clase de excepción.  
  
## <a name="on-error-resume-next"></a>On Error Resume Next  
 `On Error Resume Next` hace que la ejecución puede continuar con la instrucción inmediatamente posterior a la instrucción que produjo el error de tiempo de ejecución, o con la instrucción inmediatamente posterior a la más reciente llamar fuera del procedimiento que contiene el `On Error Resume Next` instrucción. Esta instrucción permite la ejecución continúe aunque se produzca un error en tiempo de ejecución. Puede colocar la rutina de control de errores que se produciría el error, en lugar de transferir el control a otra ubicación dentro del procedimiento. Un `On Error Resume Next` instrucción se vuelve inactiva cuando se llama a otro procedimiento, por lo que debe ejecutar un `On Error Resume Next` llama a instrucción en cada rutina si desea que el error en línea dentro de esa rutina de control.  
  
> [!NOTE]
>  El `On Error Resume Next` construcción puede ser preferible `On Error GoTo` al controlar errores generados durante el acceso a otros objetos. Comprobando `Err` después de cada interacción con un objeto elimina la ambigüedad sobre qué objeto se obtuvo acceso por el código. Puede estar seguro de qué objeto coloca el código de error `Err.Number`, así como el objeto que generó originalmente el error (el objeto especificado en `Err.Source`).  
  
## <a name="on-error-goto-0"></a>On Error GoTo 0  
 `On Error GoTo 0` deshabilita el control de errores en el procedimiento actual. No especifica la línea 0 como el inicio del código de control de errores, incluso si el procedimiento contiene una línea numerada de 0. Sin un `On Error GoTo 0` (instrucción), un controlador de errores se deshabilita automáticamente cuando se sale de un procedimiento.  
  
## <a name="on-error-goto--1"></a>On Error GoTo -1  
 `On Error GoTo -1` deshabilita la excepción en el procedimiento actual. No especifica la línea -1 como el inicio del código de control de errores, incluso si el procedimiento contiene una línea numerada -1. Sin un `On Error GoTo -1` instrucción, una excepción se deshabilita automáticamente cuando se sale de un procedimiento.  
  
 Para evitar que código de control de errores de la ejecución cuando no se ha producido ningún error, coloque una `Exit Sub`, `Exit Function`, o `Exit Property` instrucción inmediatamente antes de la rutina de control de errores, como se muestra en el siguiente fragmento:  
  
 [!code-vb[VbVbalrErrorHandling#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#18)]  
  
 En este caso, el código de control de errores sigue el `Exit Sub` instrucción y precede a la `End Sub` instrucción para separarlo del flujo del procedimiento. Puede colocar el código de control de errores en cualquier lugar en un procedimiento.  
  
## <a name="untrapped-errors"></a>Errores no interceptados  
 Errores no interceptados en objetos se devuelven a la aplicación de control cuando el objeto se ejecuta como un archivo ejecutable. Dentro del entorno de desarrollo, sin capturar los errores se devuelven a la aplicación de control solo si se establecen las opciones apropiadas. Consulte la documentación de la aplicación host para obtener una descripción de los cuales deben ser opciones conjunto durante la depuración, cómo configurarlos y si el host puede crear clases.  
  
 Si crea un objeto que tiene acceso a otros objetos, debe intentar controlar los errores no controlados que devuelvan. Si no es posible, asigne los códigos de error en `Err.Number` a uno de sus propios errores y a continuación, pasa de nuevo al llamador del objeto. Debe especificar el error agregando el código de error para el `VbObjectError` constante. Por ejemplo, si el código de error es 1052, asignarlo como sigue:  
  
 [!code-vb[VbVbalrErrorHandling#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#19)]  
  
> [!CAUTION]
>  Errores del sistema durante las llamadas a bibliotecas de vínculos dinámicos (DLL) de Windows no provocan excepciones y no se pueden interceptar con interceptación de errores de Visual Basic. Al llamar a funciones DLL, debe comprobar cada valor devuelto para el éxito o error (de acuerdo con las especificaciones de API) y si se produce un error, compruebe el valor el `Err` del objeto `LastDLLError` propiedad.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo usa primero el `On Error GoTo` instrucción para especificar la ubicación de una rutina de control de errores dentro de un procedimiento. En el ejemplo, intenta dividir por cero genera el error número 6. El error se controla en la rutina de control de errores y, a continuación, se devuelve el control a la instrucción que produjo el error. El `On Error GoTo 0` instrucción desactiva la interceptación de errores. El `On Error Resume Next` instrucción se utiliza para aplazar la intercepción de errores para que se puede conocer el contexto para el error generado por la instrucción siguiente. Tenga en cuenta que `Err.Clear` se usa para borrar el `Err` las propiedades del objeto una vez controlado el error.  
  
 [!code-vb[VbVbalrErrorHandling#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#20)]  
  
## <a name="requirements"></a>Requisitos  
 **Espacio de nombres**: [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Ensamblado:** Biblioteca en tiempo de ejecución de Visual Basic (en Microsoft.VisualBasic.dll)  
  
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
