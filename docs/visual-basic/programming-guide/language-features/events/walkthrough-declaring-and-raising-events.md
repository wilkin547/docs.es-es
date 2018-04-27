---
title: Declarar y generar eventos (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 27db585084703607a7389f5a0aa3eba6f70dd793
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a>Tutorial: Declarar y provocar eventos (Visual Basic)
Este tutorial muestra cómo declarar y provocar eventos para una clase denominada `Widget`. Después de completar los pasos, puede leer el tema complementario, [Tutorial: controlar eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), que muestra cómo utilizar eventos de `Widget` objetos para proporcionar información de estado en una aplicación.  
  
## <a name="the-widget-class"></a>La clase Widget  
 Suponga por el momento en que tiene un `Widget` clase. La `Widget` clase tiene un método que puede tardar mucho tiempo en ejecutarse, y desea que su aplicación pueda establecer alguna clase de indicador de finalización.  
  
 Por supuesto, puede realizar la `Widget` objeto mostrar un cuadro de diálogo de porcentaje finalizado, pero, a continuación, podría bloquearse con ese cuadro de diálogo en cada proyecto en el que utilizó el `Widget` clase. Un buen principio de diseño de objeto consiste en dejar que la aplicación que utiliza un objeto controle la interfaz de usuario, a menos que sea la única finalidad del objeto administrar un formulario o cuadro de diálogo.  
  
 El propósito de `Widget` consiste en realizar otras tareas, por lo que es mejor agregar una `PercentDone` eventos y permita que el procedimiento que llama `Widget`de métodos administran las actualizaciones de estado de evento y la presentación. El `PercentDone` evento también puede proporcionar un mecanismo para cancelar la tarea.  
  
#### <a name="to-build-the-code-example-for-this-topic"></a>Para compilar el ejemplo de código de este tema  
  
1.  Abra un nuevo proyecto de aplicación de Windows de Visual Basic y cree un formulario denominado `Form1`.  
  
2.  Agregue dos botones y una etiqueta para `Form1`.  
  
3.  Asigne nombre a los objetos tal y como se muestra en la tabla siguiente.  
  
    |Objeto|Property|Parámetro|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|Tarea de inicio|  
    |`Button2`|`Text`|Cancelar|  
    |`Label`|`(Name)`, `Text`|lblPercentDone, 0|  
  
4.  En el **proyecto** menú, elija **Agregar clase** para agregar una clase denominada `Widget.vb` al proyecto.  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a>Para declarar un evento para la clase Widget  
  
-   Use la `Event` palabra clave para declarar un evento en el `Widget` clase. Tenga en cuenta que puede tener un evento `ByVal` y `ByRef` argumentos, como `Widget`del `PercentDone` evento muestra:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_1.vb)]  
  
 Cuando el objeto de llamada recibe un `PercentDone` eventos, el `Percent` argumento contiene el porcentaje de la tarea que se ha completado. El `Cancel` argumento se puede establecer en `True` para cancelar el método que generó el evento.  
  
> [!NOTE]
>  Puede declarar argumentos de evento como se hace con los argumentos de procedimientos, con las siguientes excepciones: eventos no pueden tener `Optional` o `ParamArray` argumentos y eventos no tienen valores devueltos.  
  
 El `PercentDone` evento es desencadenado por la `LongTask` método de la `Widget` clase. `LongTask` toma dos argumentos: el período de tiempo que el método pretende esté realizando un trabajo y el intervalo de tiempo mínimo antes de `LongTask` pausas para generar el `PercentDone` eventos.  
  
#### <a name="to-raise-the-percentdone-event"></a>Para generar el evento PercentDone  
  
1.  Para simplificar el acceso a la `Timer` propiedad utilizada por esta clase, agregue un `Imports` instrucción a la parte superior de la sección de declaraciones de su módulo de clase, por encima del `Class Widget` instrucción.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_2.vb)]  
  
2.  Agregue el código siguiente a la clase `Widget` :  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_3.vb)]  
  
 Cuando la aplicación llama a la `LongTask` método, el `Widget` clase genera el `PercentDone` evento cada `MinimumInterval` segundos. El resultado que devuelve el evento `LongTask` comprueba si la `Cancel` argumento se estableció en `True`.  
  
 Declinaciones de responsabilidades unos aquí son necesarios. Para simplificar, el `LongTask` procedimiento se da por supuesto que conoce de antemano cuánto tiempo tardará la tarea. Esto casi nunca es el caso. Dividir las tareas en bloques del mismo tamaño puede resultar difícil y, a menudo lo más importante para los usuarios es simplemente la cantidad de tiempo que transcurre hasta que obtiene un valor que indica que algo se está realizando.  
  
 Puede haber detectado otro error en este ejemplo. El `Timer` propiedad devuelve el número de segundos que han transcurrido desde medianoche; por lo tanto, la aplicación se bloquea si se ha iniciado antes de medianoche. Una forma más cuidadosa de medir el tiempo podría tardar condiciones de límite como esto en cuenta, o evitar por completo, mediante propiedades como `Now`.  
  
 Ahora que el `Widget` clase puede provocar eventos, puede mover en el tutorial siguiente. [Tutorial: Controlar eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) muestra cómo utilizar `WithEvents` para asociar un controlador de eventos con el `PercentDone` eventos.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>  
 <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>  
 [Tutorial: Controlar eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)  
 [Eventos](../../../../visual-basic/programming-guide/language-features/events/index.md)
