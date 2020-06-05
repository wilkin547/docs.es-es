---
title: Declarar y generar eventos
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: 3da60014d7ac95189c5d56c3e339ff1b054a40dc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405098"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a>Tutorial: Declarar y provocar eventos (Visual Basic)
En este tutorial se muestra cómo declarar y generar eventos para una clase denominada `Widget` . Después de completar los pasos, es posible que desee leer el tema complementario [: control de eventos](walkthrough-handling-events.md), que muestra cómo utilizar los eventos de los `Widget` objetos para proporcionar información de estado en una aplicación.  
  
## <a name="the-widget-class"></a>La clase widget  
 Supongamos por el momento que tiene una `Widget` clase. La `Widget` clase tiene un método que puede tardar mucho tiempo en ejecutarse y desea que la aplicación pueda incluir algún tipo de indicador de finalización.  
  
 Por supuesto, puede hacer que el `Widget` objeto muestre un cuadro de diálogo porcentaje de finalización, pero a continuación se bloqueará este cuadro de diálogo en todos los proyectos en los que se haya utilizado la `Widget` clase. Un buen principio de diseño de objetos es permitir que la aplicación que usa un objeto controle la interfaz de usuario, a menos que el propósito completo del objeto sea administrar un formulario o un cuadro de diálogo.  
  
 El propósito de `Widget` es realizar otras tareas, por lo que es mejor agregar un `PercentDone` evento y dejar que el procedimiento que llama a los `Widget` métodos de llame a ese evento y muestre las actualizaciones de estado. El `PercentDone` evento también puede proporcionar un mecanismo para cancelar la tarea.  
  
#### <a name="to-build-the-code-example-for-this-topic"></a>Para compilar el ejemplo de código de este tema  
  
1. Abra un nuevo proyecto de aplicación de Windows Visual Basic y cree un formulario denominado `Form1` .  
  
2. Agregue dos botones y una etiqueta a `Form1` .  
  
3. Asigne nombre a los objetos tal y como se muestra en la tabla siguiente.  
  
    |Object|Propiedad.|Parámetro|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|Tarea de inicio|  
    |`Button2`|`Text`|Cancelar|  
    |`Label`|`(Name)`, `Text`|lblPercentDone, 0|  
  
4. En el menú **proyecto** , elija **Agregar clase** para agregar una clase denominada `Widget.vb` al proyecto.  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a>Para declarar un evento para la clase widget  
  
- Use la `Event` palabra clave para declarar un evento en la `Widget` clase. Tenga en cuenta que un evento puede tener `ByVal` `ByRef` argumentos y, como `Widget` se muestra en el `PercentDone` evento:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 Cuando el objeto que realiza la llamada recibe un `PercentDone` evento, el `Percent` argumento contiene el porcentaje de la tarea que ha finalizado. El `Cancel` argumento se puede establecer en `True` para cancelar el método que provocó el evento.  
  
> [!NOTE]
> Puede declarar argumentos de evento del mismo modo que los argumentos de procedimientos, con las siguientes excepciones: los eventos no pueden tener `Optional` `ParamArray` argumentos o, y los eventos no tienen valores devueltos.  
  
 El `PercentDone` evento es desencadenado por el `LongTask` método de la `Widget` clase. `LongTask`toma dos argumentos: la cantidad de tiempo que el método está realizando el trabajo y el intervalo de tiempo mínimo antes `LongTask` de que se ponga en pausa para generar el `PercentDone` evento.  
  
#### <a name="to-raise-the-percentdone-event"></a>Para generar el evento PercentDone  
  
1. Para simplificar el acceso a la `Timer` propiedad utilizada por esta clase, agregue una `Imports` instrucción al principio de la sección de declaraciones del módulo de clase, encima de la `Class Widget` instrucción.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2. Agregue el siguiente código a la clase `Widget`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 Cuando la aplicación llama al `LongTask` método, la `Widget` clase genera el `PercentDone` evento cada `MinimumInterval` segundos. Cuando el evento vuelve, `LongTask` comprueba si el `Cancel` argumento se estableció en `True` .  
  
 Aquí se necesitan algunas renuncias. Para simplificar, el `LongTask` procedimiento presupone que sabe de antemano cuánto tiempo tardará la tarea en realizarse. Esto casi nunca es el caso. Dividir las tareas en fragmentos de tamaño uniforme puede ser difícil y, a menudo, lo más importante para los usuarios es simplemente la cantidad de tiempo que pasa antes de que obtengan una indicación de que se está produciendo algo.  
  
 Es posible que haya detectado otro problema en este ejemplo. La `Timer` propiedad devuelve el número de segundos transcurridos desde la medianoche; por lo tanto, la aplicación se bloquea si se inicia justo antes de medianoche. Un enfoque más cuidadoso para medir el tiempo tomaría condiciones de límite, como esto, o evitar que se consuman por completo, mediante propiedades como `Now` .  
  
 Ahora que la `Widget` clase puede generar eventos, puede pasar al siguiente tutorial. [Tutorial: controlar eventos](walkthrough-handling-events.md) muestra cómo utilizar `WithEvents` para asociar un controlador de eventos al `PercentDone` evento.  
  
## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [Tutorial: Controlar eventos](walkthrough-handling-events.md)
- [Eventos](index.md)
