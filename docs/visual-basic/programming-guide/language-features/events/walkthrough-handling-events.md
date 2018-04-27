---
title: Control de eventos (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword [Visual Basic], walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c1743e5f5d9dcdf83ab646407cd1fcdc77ff71cd
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-handling-events-visual-basic"></a>Tutorial: Controlar eventos (Visual Basic)
Éste es el segundo de los dos temas que muestran cómo trabajar con eventos. El primer tema, [Tutorial: declarar y provocar eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), se muestra cómo declarar y provocar eventos. Esta sección utiliza el formulario y la clase a partir de este tutorial para mostrar cómo controlar eventos cuando tienen lugar.  
  
 El `Widget` ejemplo de la clase utiliza instrucciones de control de eventos tradicionales. Visual Basic proporciona otras técnicas para trabajar con eventos. Como ejercicio, puede modificar este ejemplo para usar el `AddHandler` y `Handles` las instrucciones.  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a>Para controlar el evento PercentDone de la clase Widget  
  
1.  Coloque el siguiente código en `Form1`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_1.vb)]  
  
     El `WithEvents` palabra clave especifica que la variable `mWidget` se usa para controlar los eventos de un objeto. Especifique el tipo de objeto proporcionando el nombre de la clase desde el que se creará el objeto.  
  
     La variable `mWidget` se declara en `Form1` porque `WithEvents` variables deben ser de nivel de clase. Esto es cierto independientemente del tipo de clase en que colocarlos.  
  
     La variable `mblnCancel` se utiliza para cancelar la `LongTask` método.  
  
## <a name="writing-code-to-handle-an-event"></a>Escribir código para controlar un evento  
 En cuanto se declara una variable utilizando `WithEvents`, el nombre de variable aparece en la lista desplegable izquierda de la clase **Editor de código**. Cuando se selecciona `mWidget`, el `Widget` eventos de la clase aparecen en la lista desplegable derecha. Al seleccionar un evento muestra el procedimiento de evento correspondiente, con el prefijo `mWidget` y un carácter de subrayado. Todos los procedimientos de evento asociados a un `WithEvents` variable reciben el nombre de variable como prefijo.  
  
#### <a name="to-handle-an-event"></a>Para controlar un evento  
  
1.  Seleccione `mWidget` en la lista desplegable izquierda en el **Editor de código**.  
  
2.  Seleccione el `PercentDone` evento en la lista desplegable derecha. El **Editor de código** abre el `mWidget_PercentDone` procedimiento de evento.  
  
    > [!NOTE]
    >  El **Editor de código** es útil, aunque no necesario, para insertar los nuevos controladores de eventos. En este tutorial, es más directo copiar simplemente los controladores de eventos directamente en el código.  
  
3.  Agregue el código siguiente al controlador de eventos `mWidget_PercentDone`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_2.vb)]  
  
     Cada vez que la `PercentDone` evento se desencadena, el procedimiento de evento muestra el porcentaje completo en un `Label` control. El `DoEvents` método permite la etiqueta para volver a pintar y también proporciona al usuario la oportunidad de hacer clic en el **cancelar** botón.  
  
4.  Agregue el código siguiente para el `Button2_Click` controlador de eventos:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_3.vb)]  
  
 Si el usuario hace clic en el **cancelar** botón mientras `LongTask` se está ejecutando, el `Button2_Click` eventos se ejecutan tan pronto como el `DoEvents` instrucción permite el procesamiento de eventos que se produzca. La variable de nivel de clase `mblnCancel` está establecido en `True`y el `mWidget_PercentDone` eventos, a continuación, lo comprueba y establece el `ByRef Cancel` argumento pasado a `True`.  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a>Conectarse a una Variable WithEvents a un objeto  
 `Form1` Ahora está configurado para controlar un `Widget` eventos del objeto. Todo lo que queda es encontrar un `Widget` en algún lugar.  
  
 Cuando se declara una variable `WithEvents` en tiempo de diseño, no hay ningún objeto está asociado a él. Un `WithEvents` variable es igual que cualquier otra variable de objeto. Tendrá que crear un objeto y asignar una referencia a él con el `WithEvents` variable.  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a>Para crear un objeto y asignar una referencia a él  
  
1.  Seleccione **(eventos Form1)** en la lista desplegable izquierda en el **Editor de código**.  
  
2.  Seleccione el `Load` evento en la lista desplegable derecha. El **Editor de código** abre el `Form1_Load` procedimiento de evento.  
  
3.  Agregue el código siguiente para el `Form1_Load` procedimiento de evento para crear el `Widget`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_4.vb)]  
  
 Cuando se ejecuta este código, Visual Basic crea un `Widget` objeto y conecta sus eventos a los procedimientos de evento asociados `mWidget`. Partir de ese punto, siempre que el `Widget` genera su `PercentDone` eventos, el `mWidget_PercentDone` se ejecuta el procedimiento de evento.  
  
#### <a name="to-call-the-longtask-method"></a>Para llamar al método LongTask  
  
-   Agregue el código siguiente al controlador de eventos `Button1_Click`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_5.vb)]  
  
 Antes de la `LongTask` método se llama, la etiqueta que muestra el porcentaje completo debe inicializarse y el nivel de clase `Boolean` marca para cancelar el método debe establecerse en `False`.  
  
 `LongTask` se llama con una duración de la tarea de 12,2 segundos. El `PercentDone` evento se desencadena una vez cada tercio de segundo. Cada vez que se genera el evento, el `mWidget_PercentDone` se ejecuta el procedimiento de evento.  
  
 Cuando `LongTask` se realiza, `mblnCancel` se prueba para ver si `LongTask` finalizado de forma normal, o si se ha detenido porque `mblnCancel` se estableció en `True`. Sólo en el primer caso, se actualiza el porcentaje completado.  
  
#### <a name="to-run-the-program"></a>Para ejecutar el programa  
  
1.  Presione F5 para poner el proyecto en modo de ejecución.  
  
2.  Haga clic en el **Iniciar tarea** botón. Cada vez que la `PercentDone` evento se desencadena, se actualiza la etiqueta con el porcentaje de la tarea que se ha completado.  
  
3.  Haga clic en el **cancelar** botón para detener la tarea. Tenga en cuenta que la apariencia de la **cancelar** botón no cambia inmediatamente al hacer clic. El `Click` eventos no pueden suceder hasta que la `My.Application.DoEvents` instrucción permite el procesamiento de eventos.  
  
    > [!NOTE]
    >  El `My.Application.DoEvents` método no procesa los eventos exactamente la misma manera como lo hace el formulario. Por ejemplo, en este tutorial, debe hacer clic en el **cancelar** botón dos veces. Para permitir que el formulario controle directamente los eventos, puede usar multithreading. Para obtener más información, consulte [subprocesos](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).  
  
 Quizá resulte instructivo para ejecutar el programa con F11 y recorrer el código de una línea a la vez. Podrá ver claramente cómo entra en ejecución `LongTask`y, a continuación, brevemente vuelve a introducir `Form1` cada vez que la `PercentDone` evento se desencadena.  
  
 ¿Qué sucedería si es, durante la ejecución en el código de `Form1`, el `LongTask` se vuelve a llamar al método? En el peor de los casos, podría producirse un desbordamiento de pila si `LongTask` se llama cada vez que se generó el evento.  
  
 Puede hacer que la variable `mWidget` para controlar los eventos para otro `Widget` objeto mediante la asignación de una referencia a la nueva `Widget` a `mWidget`. De hecho, puede hacer que el código en `Button1_Click` hacerlo cada vez que haga clic en el botón.  
  
#### <a name="to-handle-events-for-a-different-widget"></a>Para controlar los eventos para un widget distinto  
  
-   Agregue la siguiente línea de código para el `Button1_Click` procedimiento, inmediatamente anterior a la línea que dice `mWidget.LongTask(12.2, 0.33)`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_6.vb)]  
  
 El código anterior crea un nuevo `Widget` cada vez que se hace clic en el botón. Tan pronto como el `LongTask` método finaliza, la referencia a la `Widget` se publica y la `Widget` se destruye.  
  
 A `WithEvents` variable puede contener solo una referencia de objeto a la vez, por lo que si se asigna otra `Widget` el objeto a `mWidget`, anterior `Widget` ya no se controlarán los eventos del objeto. Si `mWidget` sea la única variable de objeto que contiene una referencia a la antigua `Widget`, se destruye el objeto. Si desea controlar eventos desde varios `Widget` objetos, utilice el `AddHandler` instrucción que se va a procesar los eventos de cada objeto por separado.  
  
> [!NOTE]
>  Puede declarar tantas `WithEvents` variables que usted necesitan, pero las matrices de `WithEvents` no se admiten variables.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Declarar y provocar eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)  
 [Eventos](../../../../visual-basic/programming-guide/language-features/events/index.md)
