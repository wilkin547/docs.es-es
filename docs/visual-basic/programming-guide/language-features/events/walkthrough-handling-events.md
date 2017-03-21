---
title: Control de eventos (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword, walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
caps.latest.revision: 18
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 17cd0bddbe8c89cf60e19f3f2af6f448ad465d70
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-handling-events-visual-basic"></a>Tutorial: Controlar eventos (Visual Basic)
Éste es el segundo de los dos temas que muestran cómo trabajar con eventos. El primer tema, [Tutorial: declarar y provocar eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), se muestra cómo declarar y provocar eventos. En esta sección se utiliza el formulario y la clase del tutorial para mostrar cómo controlar eventos cuando tienen lugar.  
  
 La `Widget` clase ejemplo utiliza instrucciones tradicionales de control de eventos. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]proporciona otras técnicas para trabajar con eventos. Como ejercicio, puede modificar este ejemplo para utilizar el `AddHandler` y `Handles` instrucciones.  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a>Para controlar el evento PercentDone de la clase Widget  
  
1.  Coloque el código siguiente en `Form1`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents Nº&4;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_1.vb)]  
  
     El `WithEvents` palabra clave especifica que la variable `mWidget` se utiliza para controlar eventos de un objeto. Especifique el tipo de objeto proporcionando el nombre de la clase desde la que se creará el objeto.  
  
     La variable `mWidget` se declara en `Form1` porque `WithEvents` variables deben ser de nivel de clase. Esto es cierto independientemente del tipo de clase en que colocarlos.  
  
     La variable `mblnCancel` se utiliza para cancelar la `LongTask` método.  
  
## <a name="writing-code-to-handle-an-event"></a>Escribir código para controlar un evento  
 En cuanto se declara una variable utilizando `WithEvents`, el nombre de variable aparece en la lista desplegable izquierda de la clase **Editor de código**. Al seleccionar `mWidget`, el `Widget` eventos de clase aparecen en la lista desplegable derecha. Al seleccionar un evento muestra el procedimiento de evento correspondiente, con el prefijo `mWidget` y un carácter de subrayado. Todos los procedimientos de evento asociados a un `WithEvents` variable reciben el nombre de variable como prefijo.  
  
#### <a name="to-handle-an-event"></a>Para controlar un evento  
  
1.  Seleccione `mWidget` en la lista desplegable izquierda en el **Editor de código**.  
  
2.  Seleccione las `PercentDone` eventos de la lista desplegable derecha. El **Editor de código** abre el `mWidget_PercentDone` el procedimiento de evento.  
  
    > [!NOTE]
    >  El **Editor de código** es útil, aunque no necesario, para insertar los nuevos controladores de eventos. En este tutorial, es más directo copiar simplemente los controladores de eventos directamente en el código.  
  
3.  Agregue el código siguiente al controlador de eventos `mWidget_PercentDone`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&#5;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_2.vb)]  
  
     Siempre que el `PercentDone` provoca el evento, el procedimiento de evento muestra el porcentaje completo en un `Label` control. El `DoEvents` método permite a dibujar, la etiqueta y también ofrece al usuario la oportunidad de hacer clic en el **cancelar** botón.  
  
4.  Agregue el siguiente código para el `Button2_Click` controlador de eventos:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&6;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_3.vb)]  
  
 Si el usuario hace clic en el **cancelar** botón mientras `LongTask` se está ejecutando, el `Button2_Click` evento se ejecuta tan pronto como el `DoEvents` instrucción permite el procesamiento de eventos que se produzcan. La variable de nivel de clase `mblnCancel` está establecido en `True`y el `mWidget_PercentDone` evento lo comprueba luego y establece el `ByRef Cancel` argumento `True`.  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a>Conectar la Variable WithEvents a un objeto  
 `Form1`Ahora está configurado para controlar un `Widget` eventos del objeto. Todo lo que queda es encontrar un `Widget` en algún lugar.  
  
 Cuando se declara una variable `WithEvents` en tiempo de diseño no tiene asociado ningún objeto. Un `WithEvents` variable es igual que cualquier otra variable de objeto. Tiene que crear un objeto y asignar una referencia a él con el `WithEvents` variable.  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a>Para crear un objeto y asignar una referencia a ella  
  
1.  Seleccione **(eventos Form1)** en la lista desplegable izquierda en el **Editor de código**.  
  
2.  Seleccione las `Load` eventos de la lista desplegable derecha. El **Editor de código** abre el `Form1_Load` el procedimiento de evento.  
  
3.  Agregue el siguiente código para el `Form1_Load` el procedimiento de evento para crear el `Widget`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&#7;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_4.vb)]  
  
 Cuando se ejecuta este código, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] crea un `Widget` de objetos y conecta sus eventos a los procedimientos de evento asociados con `mWidget`. Desde ese punto, siempre que el `Widget` genera su `PercentDone` evento, el `mWidget_PercentDone` se ejecuta el procedimiento de evento.  
  
#### <a name="to-call-the-longtask-method"></a>Para llamar al método LongTask  
  
-   Agregue el código siguiente al controlador de eventos `Button1_Click`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents Nº&8;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_5.vb)]  
  
 Antes de la `LongTask` se llama el método, la etiqueta que muestra el porcentaje completo debe inicializarse y el nivel de clase `Boolean` marca para cancelar el método debe establecerse en `False`.  
  
 `LongTask`se llama con una duración de tarea de 12,2 segundos. El `PercentDone` evento se desencadena una vez cada tercio de segundo. Cada vez que se genera el evento, el `mWidget_PercentDone` se ejecuta el procedimiento de evento.  
  
 Cuando `LongTask` se realiza, `mblnCancel` se prueba para ver si `LongTask` finalizó normalmente, o si se ha detenido porque `mblnCancel` se estableció en `True`. Sólo en el caso anterior, se actualiza el porcentaje completado.  
  
#### <a name="to-run-the-program"></a>Para ejecutar el programa  
  
1.  Presione F5 para poner el proyecto en modo de ejecución.  
  
2.  Haga clic en el **Iniciar tarea** botón. Cada vez que la `PercentDone` provoca el evento, se actualiza la etiqueta con el porcentaje de la tarea que se ha completado.  
  
3.  Haga clic en el **cancelar** botón para detener la tarea. Tenga en cuenta que la apariencia de la **cancelar** botón no cambia inmediatamente al hacer clic. El `Click` eventos no pueden suceder hasta el `My.Application.DoEvents` instrucción permite el procesamiento de eventos.  
  
    > [!NOTE]
    >  El `My.Application.DoEvents` método procesa los eventos exactamente del mismo modo que el formulario. Por ejemplo, en este tutorial, debe hacer clic el **cancelar** botón dos veces. Para permitir que el formulario controle directamente los eventos, puede usar multithreading. Para obtener más información, consulte [subprocesos](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).  
  
 Quizá resulte instructivo ejecutar el programa con F11 y recorrer el código de una línea cada vez. Puede ver claramente cómo la ejecución escribe `LongTask`y, a continuación, brevemente vuelve a entrar `Form1` cada vez que la `PercentDone` provoca el evento.  
  
 ¿Qué ocurriría if, durante la ejecución en el código de `Form1`, el `LongTask` método se llama de nuevo? En el peor de los casos, puede producirse un desbordamiento de pila si `LongTask` se llama cada vez que se provocó el evento.  
  
 Puede hacer que la variable `mWidget` para controlar los eventos de otra `Widget` objeto asignando una referencia al nuevo `Widget` a `mWidget`. De hecho, puede hacer que el código en `Button1_Click` hacer esto cada vez que haga clic en el botón.  
  
#### <a name="to-handle-events-for-a-different-widget"></a>Controlar eventos para un widget distinto  
  
-   Agregue la siguiente línea de código para el `Button1_Click` procedimiento, inmediatamente antes de la línea que dice `mWidget.LongTask(12.2, 0.33)`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&#9;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_6.vb)]  
  
 El código anterior crea un nuevo `Widget` cada vez que se hace clic en el botón. Tan pronto como el `LongTask` método finaliza, la referencia a la `Widget` se publica y el `Widget` se destruye.  
  
 Un `WithEvents` variable puede contener sólo una referencia de objeto a la vez, por lo que si asigna otro `Widget` objeto `mWidget`, el anterior `Widget` ya no se controlarán los eventos del objeto. Si `mWidget` es la única variable de objeto que contiene una referencia a la antigua `Widget`, se destruye el objeto. Si desea controlar eventos desde varios `Widget` objetos, utilice el `AddHandler` instrucción para procesar eventos de cada objeto por separado.  
  
> [!NOTE]
>  Se pueden declarar tantas `WithEvents` variables que usted necesitan, pero las matrices de `WithEvents` no se admiten variables.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Declarar y provocar eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)   
 [Eventos](../../../../visual-basic/programming-guide/language-features/events/index.md)
