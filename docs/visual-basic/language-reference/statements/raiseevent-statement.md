---
title: RaiseEvent (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.RaiseEventMethod
- vb.RaiseEvent
- RaiseEvent
helpviewer_keywords:
- raising events [Visual Basic], RaiseEvent statement
- RaiseEvent statement [Visual Basic]
- event handlers, connecting events to
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
ms.openlocfilehash: 19949fbdb1c1c54556876323d839b16fc01608f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="raiseevent-statement"></a>RaiseEvent (Instrucción)
Desencadena un evento declarado en el nivel de módulo dentro de una clase, un formulario o un documento.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a>Elementos  
 `eventname`  
 Requerido. Nombre del evento que se va a desencadenar.  
  
 `argumentlist`  
 Opcional. Lista delimitada por comas de variables, matrices o expresiones. El `argumentlist` argumento debe aparecer entre paréntesis. Si no hay ningún argumento, se deben omitir los paréntesis.  
  
## <a name="remarks"></a>Comentarios  
 Requerido `eventname` es el nombre de un evento declarado dentro del módulo. Sigue convenciones de nomenclatura de Visual Basic.  
  
 Si el evento no se ha declarado dentro del módulo en el que se produce, se produce un error. El siguiente fragmento de código muestra una declaración de evento y un procedimiento en el que se genera el evento.  
  
 [!code-vb[VbVbalrEvents#37](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_1.vb)]  
  
 No se puede utilizar `RaiseEvent` para generar eventos que no estén explícitamente declarados en el módulo. Por ejemplo, todos los formularios heredan un <xref:System.Windows.Forms.Control.Click> eventos de <xref:System.Windows.Forms.Form?displayProperty=nameWithType>, no se produce mediante `RaiseEvent` en un formulario derivado. Si declara un `Click` eventos en el módulo de formulario, sombrea el propio formulario <xref:System.Windows.Forms.Control.Click> eventos. Se puede invocar el formulario <xref:System.Windows.Forms.Control.Click> eventos mediante una llamada a la <xref:System.Windows.Forms.Control.OnClick%2A> método.  
  
 De manera predeterminada, un evento definido en Visual Basic provoca sus controladores de eventos en el orden en que se establezcan las conexiones. Dado que pueden tener eventos `ByRef` parámetros, un proceso que se conecta tarde puede recibir parámetros que se han cambiado por un controlador de eventos anterior. Después de ejecutan los controladores de eventos, el control se devuelve a la subrutina que provocó el evento.  
  
> [!NOTE]
>  No se deben generar los eventos no compartidos dentro del constructor de la clase en que se declaran. Aunque dichos eventos no provocan errores en tiempo de ejecución, no pueden detectar mediante los controladores de eventos asociados. Use la `Shared` modificador para crear un evento compartido si tiene que genere un evento desde un constructor.  
  
> [!NOTE]
>  Puede cambiar el comportamiento predeterminado de eventos mediante la definición de un evento personalizado. Para los eventos personalizados, la `RaiseEvent` instrucción invoca el evento `RaiseEvent` descriptor de acceso. Para obtener más información sobre eventos personalizados, vea [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usan eventos para contar los segundos de 10 a 0. El código muestra algunos de los métodos relacionados con eventos, propiedades e instrucciones, incluidas la `RaiseEvent` instrucción.  
  
 La clase que provoca un evento es el origen del evento, y los métodos que procesan el evento son los controladores de eventos. Un origen de eventos puede tener varios controladores para los eventos que genera. Cuando la clase genera el evento, ese evento se genera en cada clase que eligió controlar eventos para esa instancia del objeto.  
  
 El ejemplo también usa un formulario (`Form1`) con un botón (`Button1`) y un cuadro de texto (`TextBox1`). Al hacer clic en el botón, el primer cuadro de texto muestra una cuenta atrás de 10 a 0 segundos. Cuando transcurre el tiempo (10 segundos), el primer cuadro de texto muestra "Done".  
  
 El código de `Form1` especifica los estados inicial y terminal del formulario. También contiene el código que se ejecuta cuando se producen eventos.  
  
 Para usar este ejemplo, abra un nuevo proyecto de aplicación de Windows, agregue un botón denominado `Button1` y un cuadro de texto denominado `TextBox1` al formulario principal, denominado `Form1`. A continuación, haga clic en el formulario y haga clic en **ver código** para abrir el Editor de código.  
  
 Agregar un `WithEvents` variable a la sección de declaraciones de la `Form1` clase.  
  
 [!code-vb[VbVbalrEvents#14](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_2.vb)]  
  
## <a name="example"></a>Ejemplo  
 Agregue el código siguiente al código de `Form1`. Sustituya los procedimientos duplicados que existan, como `Form_Load`, o `Button_Click`.  
  
 [!code-vb[VbVbalrEvents#15](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_3.vb)]  
  
 Presione F5 para ejecutar el ejemplo anterior y haga clic en el botón con la etiqueta **iniciar**. El primer cuadro de texto empieza la cuenta atrás de los segundos. Cuando transcurre el tiempo (10 segundos), el primer cuadro de texto muestra "Done".  
  
> [!NOTE]
>  El `My.Application.DoEvents` método no procesa los eventos exactamente la misma manera como lo hace el formulario. Para permitir que el formulario controle directamente los eventos, puede usar multithreading. Para obtener más información, consulte [subprocesos](../../programming-guide/concepts/threading/index.md).  
  
## <a name="see-also"></a>Vea también  
 [Eventos](../../../visual-basic/programming-guide/language-features/events/index.md)  
 [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)  
 [AddHandler (instrucción)](../../../visual-basic/language-reference/statements/addhandler-statement.md)  
 [RemoveHandler (instrucción)](../../../visual-basic/language-reference/statements/removehandler-statement.md)  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
