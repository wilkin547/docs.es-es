---
title: Controlar eventos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword [Visual Basic], walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
ms.openlocfilehash: 12267e0a70419298bc581421c4f3a220088d205f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956312"
---
# <a name="walkthrough-handling-events-visual-basic"></a>Tutorial: Controlar eventos (Visual Basic)
Este es el segundo de los dos temas que muestran cómo trabajar con eventos. El primer tema, [Tutorial: La declaración y la generación](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)de eventos, muestra cómo declarar y generar eventos. En esta sección se usa el formulario y la clase de ese tutorial para mostrar cómo controlar los eventos cuando tienen lugar.  
  
 En `Widget` el ejemplo de clase se usan las instrucciones de control de eventos tradicionales. Visual Basic proporciona otras técnicas para trabajar con eventos. Como ejercicio, puede modificar este ejemplo para usar las `AddHandler` instrucciones y. `Handles`  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a>Para controlar el evento PercentDone de la clase widget  
  
1. Coloque el código siguiente en `Form1`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#4)]  
  
     La `WithEvents` palabra clave especifica que la `mWidget` variable se utiliza para controlar los eventos de un objeto. Especifique el tipo de objeto proporcionando el nombre de la clase a partir de la cual se creará el objeto.  
  
     La variable `mWidget` se declara en `Form1` porque `WithEvents` las variables deben ser de nivel de clase. Esto es así independientemente del tipo de clase en la que se colocan.  
  
     La variable `mblnCancel` se utiliza para cancelar el `LongTask` método.  
  
## <a name="writing-code-to-handle-an-event"></a>Escribir código para controlar un evento  
 En cuanto declare una variable mediante `WithEvents`, el nombre de la variable aparecerá en la lista desplegable de la izquierda del editor de **código**de la clase. Al seleccionar `mWidget`, los `Widget` eventos de la clase aparecen en la lista desplegable derecha. Al seleccionar un evento se muestra el procedimiento de evento correspondiente, `mWidget` con el prefijo y un carácter de subrayado. Todos los procedimientos de eventos asociados a `WithEvents` una variable reciben el nombre de la variable como prefijo.  
  
#### <a name="to-handle-an-event"></a>Para controlar un evento  
  
1. Seleccione `mWidget` en la lista desplegable izquierda en el **Editor de código**.  
  
2. Seleccione el `PercentDone` evento en la lista desplegable derecha. El **Editor de código** abre `mWidget_PercentDone` el procedimiento de evento.  
  
    > [!NOTE]
    > El **Editor de código** es útil, pero no es necesario, para insertar nuevos controladores de eventos. En este tutorial, es más directo simplemente copiar los controladores de eventos directamente en el código.  
  
3. Agregue el código siguiente al controlador de eventos `mWidget_PercentDone` :  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#5)]  
  
     Siempre que `PercentDone` se genera el evento, el procedimiento de evento muestra el porcentaje completado `Label` en un control. El `DoEvents` método permite que la etiqueta se vuelva a dibujar y también proporciona al usuario la oportunidad de hacer clic en el botón **Cancelar** .  
  
4. Agregue el código siguiente para el `Button2_Click` controlador de eventos:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#6)]  
  
 Si el usuario hace clic en el botón Cancelar `LongTask` mientras se está ejecutando `Button2_Click` , el evento se ejecuta tan pronto `DoEvents` como la instrucción permite que se produzca el procesamiento de eventos. La variable `mblnCancel` de nivel de clase se establece `True`en, y `mWidget_PercentDone` el evento lo prueba y establece el `ByRef Cancel` argumento en `True`.  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a>Conectar una variable WithEvents a un objeto  
 `Form1`ahora está configurado para controlar los eventos `Widget` de un objeto. Todo lo que queda es encontrar un `Widget` en algún lugar.  
  
 Cuando se declara una variable `WithEvents` en tiempo de diseño, no hay ningún objeto asociado. Una `WithEvents` variable es igual que cualquier otra variable de objeto. Tendrá que crear un objeto y asignarle una referencia con la `WithEvents` variable.  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a>Para crear un objeto y asignarle una referencia  
  
1. Seleccione **(eventos de Form1)** en la lista desplegable de la izquierda en el **Editor de código**.  
  
2. Seleccione el `Load` evento en la lista desplegable derecha. El **Editor de código** abre `Form1_Load` el procedimiento de evento.  
  
3. Agregue el código siguiente para el `Form1_Load` procedimiento de evento para `Widget`crear:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#7)]  
  
 Cuando se ejecuta este código, Visual Basic crea un `Widget` objeto y conecta sus eventos a los procedimientos de evento `mWidget`asociados a. A partir de ese momento, siempre `Widget` que genere `PercentDone` su evento, `mWidget_PercentDone` se ejecutará el procedimiento de evento.  
  
#### <a name="to-call-the-longtask-method"></a>Para llamar al método LongTask  
  
- Agregue el código siguiente al controlador de eventos `Button1_Click` :  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#8)]  
  
 Antes de `LongTask` llamar al método, se debe inicializar la etiqueta que muestra el porcentaje completado y la marca de nivel `Boolean` de clase para cancelar el método debe establecerse en `False`.  
  
 `LongTask`se llama a con una duración de tarea de 12,2 segundos. El `PercentDone` evento se genera una vez cada tercio de segundo. Cada vez que se genera el evento, `mWidget_PercentDone` se ejecuta el procedimiento de evento.  
  
 Cuando `LongTask` se hace, `mblnCancel` se prueba para ver si `LongTask` finalizó normalmente, o si se detuvo porque `mblnCancel` se `True`estableció en. El porcentaje completado solo se actualiza en el caso anterior.  
  
#### <a name="to-run-the-program"></a>Para ejecutar el programa  
  
1. Presione F5 para poner el proyecto en modo de ejecución.  
  
2. Haga clic en el botón **Iniciar tarea** . Cada vez que `PercentDone` se genera el evento, la etiqueta se actualiza con el porcentaje de la tarea que ha finalizado.  
  
3. Haga clic en el botón **Cancelar** para detener la tarea. Tenga en cuenta que la apariencia del botón **Cancelar** no cambia inmediatamente al hacer clic en él. El `Click` evento no se puede producir `My.Application.DoEvents` hasta que la instrucción permite el procesamiento de eventos.  
  
    > [!NOTE]
    > El `My.Application.DoEvents` método no procesa los eventos exactamente del mismo modo que el formulario. Por ejemplo, en este tutorial, debe hacer clic dos veces en el botón **Cancelar** . Para permitir que el formulario controle los eventos directamente, puede usar multithreading. Para obtener más información, vea [subprocesamiento administrado](../../../../standard/threading/index.md).
  
 Es posible que le resulte instructivo ejecutar el programa con F11 y recorrer el código una línea a la vez. Puede ver claramente cómo entra `LongTask`en ejecución y, después, volver a entrar `Form1` brevemente cada vez que se genere el `PercentDone` evento.  
  
 ¿Qué ocurriría si, mientras la ejecución vuelve al código de `Form1`, se `LongTask` llamó de nuevo al método? En el peor de los tiempos, podría producirse un desbordamiento de pila si `LongTask` se llamara cada vez que se produjera el evento.  
  
 Puede hacer que la variable `mWidget` controle los eventos de un `Widget` objeto diferente asignando una referencia al nuevo `Widget` a `mWidget`. De hecho, puede hacer que el código en `Button1_Click` haga esto cada vez que haga clic en el botón.  
  
#### <a name="to-handle-events-for-a-different-widget"></a>Para controlar los eventos de un widget diferente  
  
- Agregue la siguiente línea de código al `Button1_Click` procedimiento, inmediatamente antes de la línea que dice: `mWidget.LongTask(12.2, 0.33)`  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#9)]  
  
 El código anterior crea un nuevo `Widget` cada vez que se hace clic en el botón. En cuanto `LongTask` secompleta`Widget` el método, se libera la referencia a y sedestruyeel.`Widget`  
  
 Una `WithEvents` variable solo puede contener una referencia de objeto cada vez, por lo que si asigna un `Widget` objeto diferente `mWidget`a, los `Widget` eventos del objeto anterior dejarán de estar controlados. Si `mWidget` es la única variable de objeto que contiene una referencia al `Widget`antiguo, el objeto se destruye. Si desea controlar los eventos de varios `Widget` objetos, utilice la `AddHandler` instrucción para procesar los eventos de cada objeto por separado.  
  
> [!NOTE]
> Puede declarar tantas `WithEvents` variables como sea necesario, pero no se admiten `WithEvents` matrices de variables.  
  
## <a name="see-also"></a>Vea también

- [Tutorial: Declarar y generar eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)
- [Eventos](../../../../visual-basic/programming-guide/language-features/events/index.md)
