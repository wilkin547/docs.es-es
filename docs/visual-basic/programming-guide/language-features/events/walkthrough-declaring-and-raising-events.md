---
title: Declarar y provocar eventos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: cab6c90947eae8abeb9387535eadb2f89e71454a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59320696"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a>Tutorial: Declarar y provocar eventos (Visual Basic)
Este tutorial muestra cómo declarar y provocar eventos para una clase denominada `Widget`. Después de completar los pasos, que es posible que desee leer el tema complementario, [Tutorial: Control de eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), que muestra cómo utilizar eventos de `Widget` objetos que se va a proporcionar información de estado en una aplicación.  
  
## <a name="the-widget-class"></a>La clase Widget  
 Suponga por un momento que tenga un `Widget` clase. Su `Widget` clase tiene un método que puede tardar mucho tiempo en ejecutarse, y desea que su aplicación pueda poner a algún tipo de indicador de finalización.  
  
 Por supuesto, puede hacer que el `Widget` objeto mostrar un cuadro de diálogo de porcentaje completado, pero, a continuación, aparecería con ese cuadro de diálogo en todos los proyectos en el que utilizó el `Widget` clase. Un buen principio de diseño de objeto es dejar que la aplicación que utiliza un objeto controle la interfaz de usuario, a menos que sea la única finalidad del objeto administrar un formulario o cuadro de diálogo.  
  
 El propósito de `Widget` consiste en realizar otras tareas, por lo que es mejor agregar una `PercentDone` eventos y permita que el procedimiento que llama `Widget`del métodos controlan que actualiza el estado de evento y la presentación. El `PercentDone` evento también puede proporcionar un mecanismo para cancelar la tarea.  
  
#### <a name="to-build-the-code-example-for-this-topic"></a>Para compilar el ejemplo de código de este tema  
  
1. Abra un nuevo proyecto de aplicación de Windows de Visual Basic y cree un formulario denominado `Form1`.  
  
2. Agregue dos botones y una etiqueta para `Form1`.  
  
3. Asigne nombre a los objetos tal y como se muestra en la tabla siguiente.  
  
    |Objeto|Propiedad|Parámetro|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|Tarea de inicio|  
    |`Button2`|`Text`|Cancelar|  
    |`Label`|`(Name)`, `Text`|lblPercentDone, 0|  
  
4. En el **proyecto** menú, elija **Agregar clase** para agregar una clase denominada `Widget.vb` al proyecto.  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a>Para declarar un evento para la clase de Widget  
  
-   Use la `Event` palabra clave para declarar un evento en el `Widget` clase. Tenga en cuenta que puede tener un evento `ByVal` y `ByRef` argumentos, como `Widget`del `PercentDone` muestra eventos:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 Cuando el objeto de llamada recibe una `PercentDone` eventos, el `Percent` argumento contiene el porcentaje de la tarea que se ha completado. El `Cancel` argumento se puede establecer en `True` para cancelar el método que generó el evento.  
  
> [!NOTE]
>  Puede declarar argumentos de evento, tal como se hace con los argumentos de procedimientos, con las siguientes excepciones: No pueden tener eventos `Optional` o `ParamArray` argumentos y los eventos no tienen valores devueltos.  
  
 El `PercentDone` evento es desencadenado por la `LongTask` método de la `Widget` clase. `LongTask` toma dos argumentos: el período de tiempo que el método finge hasta la realización de trabajo y el intervalo de tiempo mínimo antes de `LongTask` pausas para generar el `PercentDone` eventos.  
  
#### <a name="to-raise-the-percentdone-event"></a>Para generar el evento PercentDone  
  
1. Para simplificar el acceso a la `Timer` propiedad utilizada por esta clase, agregue un `Imports` instrucción a la parte superior de la sección de declaraciones de módulo de la clase, por encima el `Class Widget` instrucción.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2. Agregue el código siguiente a la clase `Widget`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 Cuando la aplicación llama el `LongTask` método, el `Widget` clase genera el `PercentDone` eventos cada `MinimumInterval` segundos. Devuelve el evento `LongTask` comprueba si el `Cancel` argumento se estableció en `True`.  
  
 Algunas declinaciones de responsabilidades son necesarios. Por motivos de simplicidad, el `LongTask` procedimiento se supone que sabe de antemano cuánto tiempo tardará la tarea. Esto casi nunca es el caso. Dividir las tareas en fragmentos de tamaño incluso puede resultar difícil y, a menudo lo más importante para los usuarios es simplemente la cantidad de tiempo que transcurre antes de que lleguen a un valor que indica que está ocurriendo algo.  
  
 Puede haber detectado otro error en este ejemplo. El `Timer` propiedad devuelve el número de segundos que han transcurrido desde medianoche; por lo tanto, la aplicación se bloquea si se ha iniciado justo antes de medianoche. Un enfoque más cuidadoso para medir el tiempo lleve las condiciones de límite como este en cuenta, o evitar por completo, con propiedades como `Now`.  
  
 Ahora que la `Widget` clase puede provocar eventos, puede mover al siguiente tutorial. [Tutorial: Control de eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) muestra cómo usar `WithEvents` para asociar un controlador de eventos con el `PercentDone` eventos.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [Tutorial: Controlar eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)
- [Eventos](../../../../visual-basic/programming-guide/language-features/events/index.md)
