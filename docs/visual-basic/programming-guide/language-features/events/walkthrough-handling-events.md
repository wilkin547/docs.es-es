---
title: Controlar eventos
ms.date: 07/20/2015
helpviewer_keywords:
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword [Visual Basic], walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
ms.openlocfilehash: cb42f2e41e366cf8765cb9395d1a5641434bab40
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345081"
---
# <a name="walkthrough-handling-events-visual-basic"></a>Tutorial: Controlar eventos (Visual Basic)
Este es el segundo de los dos temas que muestran cómo trabajar con eventos. En el primer tema, [Tutorial: declarar y provocar eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), se muestra cómo declarar y generar eventos. En esta sección se usa el formulario y la clase de ese tutorial para mostrar cómo controlar los eventos cuando tienen lugar.  
  
 En el ejemplo de clase `Widget` se usan las instrucciones de control de eventos tradicionales. Visual Basic proporciona otras técnicas para trabajar con eventos. Como ejercicio, puede modificar este ejemplo para usar las instrucciones `AddHandler` y `Handles`.  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a>Para controlar el evento PercentDone de la clase widget  
  
1. Coloque el código siguiente en `Form1`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#4)]  
  
     La palabra clave `WithEvents` especifica que la variable `mWidget` se utiliza para controlar los eventos de un objeto. Especifique el tipo de objeto proporcionando el nombre de la clase a partir de la cual se creará el objeto.  
  
     La variable `mWidget` se declara en `Form1` porque las variables de `WithEvents` deben ser de nivel de clase. Esto es así independientemente del tipo de clase en la que se colocan.  
  
     La variable `mblnCancel` se utiliza para cancelar el método `LongTask`.  
  
## <a name="writing-code-to-handle-an-event"></a>Escribir código para controlar un evento  
 En cuanto se declara una variable mediante `WithEvents`, el nombre de la variable aparece en la lista desplegable de la izquierda del **Editor de código**de la clase. Al seleccionar `mWidget`, los eventos de la clase `Widget` aparecen en la lista desplegable derecha. Al seleccionar un evento, se muestra el procedimiento de evento correspondiente, con el prefijo `mWidget` y un carácter de subrayado. Todos los procedimientos de eventos asociados a una variable de `WithEvents` reciben el nombre de la variable como prefijo.  
  
#### <a name="to-handle-an-event"></a>Para controlar un evento  
  
1. Seleccione `mWidget` de la lista desplegable izquierda en el **Editor de código**.  
  
2. Seleccione el evento `PercentDone` de la lista desplegable derecha. El **Editor de código** abre el procedimiento de evento `mWidget_PercentDone`.  
  
    > [!NOTE]
    > El **Editor de código** es útil, pero no es necesario, para insertar nuevos controladores de eventos. En este tutorial, es más directo simplemente copiar los controladores de eventos directamente en el código.  
  
3. Agregue el código siguiente al controlador de eventos `mWidget_PercentDone` :  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#5)]  
  
     Siempre que se genera el evento `PercentDone`, el procedimiento de evento muestra el porcentaje completado en un control `Label`. El método `DoEvents` permite que la etiqueta se vuelva a dibujar y también proporciona al usuario la oportunidad de hacer clic en el botón **Cancelar** .  
  
4. Agregue el código siguiente para el controlador de eventos `Button2_Click`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#6)]  
  
 Si el usuario hace clic en el botón **Cancelar** mientras `LongTask` está en ejecución, se ejecuta el evento `Button2_Click` en cuanto la instrucción `DoEvents` permite que se produzca el procesamiento de eventos. La variable de nivel de clase `mblnCancel` se establece en `True`, y el evento `mWidget_PercentDone` la prueba y establece el argumento de `ByRef Cancel` en `True`.  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a>Conectar una variable WithEvents a un objeto  
 ahora `Form1` está configurado para controlar los eventos de un objeto `Widget`. Todo lo que queda es encontrar una `Widget` en algún lugar.  
  
 Cuando se declara una variable `WithEvents` en tiempo de diseño, no hay ningún objeto asociado a ella. Una variable `WithEvents` es igual que cualquier otra variable de objeto. Tiene que crear un objeto y asignarle una referencia con la variable `WithEvents`.  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a>Para crear un objeto y asignarle una referencia  
  
1. Seleccione **(eventos de Form1)** en la lista desplegable de la izquierda en el **Editor de código**.  
  
2. Seleccione el evento `Load` de la lista desplegable derecha. El **Editor de código** abre el procedimiento de evento `Form1_Load`.  
  
3. Agregue el código siguiente para el procedimiento de evento `Form1_Load` para crear el `Widget`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#7)]  
  
 Cuando se ejecuta este código, Visual Basic crea un objeto `Widget` y conecta sus eventos a los procedimientos de evento asociados a `mWidget`. A partir de ese momento, cada vez que el `Widget` genera su evento `PercentDone`, se ejecuta el procedimiento de evento `mWidget_PercentDone`.  
  
#### <a name="to-call-the-longtask-method"></a>Para llamar al método LongTask  
  
- Agregue el código siguiente al controlador de eventos `Button1_Click` :  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#8)]  
  
 Antes de llamar al método `LongTask`, se debe inicializar la etiqueta que muestra el porcentaje completado y la marca `Boolean` de nivel de clase para cancelar el método debe estar establecida en `False`.  
  
 se llama a `LongTask` con una duración de tarea de 12,2 segundos. El evento `PercentDone` se genera una vez cada tercio de segundo. Cada vez que se produce el evento, se ejecuta el procedimiento de evento `mWidget_PercentDone`.  
  
 Cuando se realiza `LongTask`, se prueba `mblnCancel` para ver si `LongTask` finalizó con normalidad, o si se detuvo porque `mblnCancel` se estableció en `True`. El porcentaje completado solo se actualiza en el caso anterior.  
  
#### <a name="to-run-the-program"></a>Para ejecutar el programa  
  
1. Presione F5 para poner el proyecto en modo de ejecución.  
  
2. Haga clic en el botón **Iniciar tarea** . Cada vez que se genera el evento de `PercentDone`, la etiqueta se actualiza con el porcentaje de la tarea que se ha completado.  
  
3. Haga clic en el botón **Cancelar** para detener la tarea. Tenga en cuenta que la apariencia del botón **Cancelar** no cambia inmediatamente al hacer clic en él. No se puede producir el evento `Click` hasta que la instrucción `My.Application.DoEvents` permita el procesamiento de eventos.  
  
    > [!NOTE]
    > El método `My.Application.DoEvents` no procesa los eventos exactamente del mismo modo que el formulario. Por ejemplo, en este tutorial, debe hacer clic dos veces en el botón **Cancelar** . Para permitir que el formulario controle los eventos directamente, puede usar multithreading. Para obtener más información, vea [subprocesamiento administrado](../../../../standard/threading/index.md).
  
 Es posible que le resulte instructivo ejecutar el programa con F11 y recorrer el código una línea a la vez. Puede ver claramente cómo la ejecución entra en `LongTask`y, a continuación, volver a entrar brevemente `Form1` cada vez que se genera el evento `PercentDone`.  
  
 ¿Qué ocurriría si, mientras la ejecución vuelve al código de `Form1`, se llamó de nuevo al método `LongTask`? En el peor de los tiempos, podría producirse un desbordamiento de pila si se llamara a `LongTask` cada vez que se produjera el evento.  
  
 Puede hacer que la variable `mWidget` controle los eventos de un objeto `Widget` diferente asignando una referencia al nuevo `Widget` a `mWidget`. De hecho, puede hacer que el código en `Button1_Click` hacerlo cada vez que haga clic en el botón.  
  
#### <a name="to-handle-events-for-a-different-widget"></a>Para controlar los eventos de un widget diferente  
  
- Agregue la siguiente línea de código al procedimiento `Button1_Click`, inmediatamente antes de la línea que lee `mWidget.LongTask(12.2, 0.33)`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#9)]  
  
 El código anterior crea un nuevo `Widget` cada vez que se hace clic en el botón. En cuanto finaliza el método de `LongTask`, se libera la referencia al `Widget` y se destruye la `Widget`.  
  
 Una variable `WithEvents` solo puede contener una referencia de objeto cada vez, por lo que si asigna un objeto `Widget` diferente a `mWidget`, los eventos del objeto `Widget` anterior dejarán de estar controlados. Si `mWidget` es la única variable de objeto que contiene una referencia al `Widget`anterior, el objeto se destruye. Si desea controlar eventos de varios objetos `Widget`, utilice la instrucción `AddHandler` para procesar los eventos de cada objeto por separado.  
  
> [!NOTE]
> Puede declarar tantas variables de `WithEvents` como necesite, pero no se admiten matrices de variables de `WithEvents`.  
  
## <a name="see-also"></a>Vea también

- [Tutorial: Declarar y provocar eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)
- [Eventos](../../../../visual-basic/programming-guide/language-features/events/index.md)
