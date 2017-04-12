---
title: Declarar y provocar eventos (Visual Basic) | Documentos de Microsoft
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
- declarations, events
- events [Visual Basic], walkthroughs
- declaring events, walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events, walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 233673c1d42684b7caa9042d18fb341a1043a31b
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a>Tutorial: Declarar y provocar eventos (Visual Basic)
Este tutorial muestra cómo declarar y provocar eventos para una clase denominada `Widget`. Después de completar los pasos, puede leer el tema complementario, [Tutorial: controlar eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), que muestra cómo utilizar eventos de `Widget` objetos para proporcionar información de estado en una aplicación.  
  
## <a name="the-widget-class"></a>La clase Widget  
 Suponga por un momento que tiene una `Widget` clase. La `Widget` clase tiene un método que puede tardar mucho tiempo en ejecutarse, y desea que su aplicación pueda establecer alguna clase de indicador de finalización.  
  
 Por supuesto, podría hacer la `Widget` objeto muestra un cuadro de diálogo de porcentaje finalizado, pero, a continuación, aparecería ese cuadro de diálogo en cada proyecto en el que utilizó el `Widget` clase. Un buen principio del diseño de objetos consiste en dejar que la aplicación que utiliza un objeto controle la interfaz de usuario, a menos que sea la única finalidad del objeto administrar un formulario o cuadro de diálogo.  
  
 El propósito de `Widget` es realizar otras tareas, por lo que es mejor agregar un `PercentDone` eventos y permita que el procedimiento que llama `Widget`de métodos controlar que las actualizaciones de estado de evento y la presentación. El `PercentDone` evento también puede proporcionar un mecanismo para cancelar la tarea.  
  
#### <a name="to-build-the-code-example-for-this-topic"></a>Para compilar el ejemplo de código de este tema  
  
1.  Abra una nueva [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] aplicación de Windows del proyecto y cree un formulario denominado `Form1`.  
  
2.  Agregue dos botones y una etiqueta a `Form1`.  
  
3.  Nombre de los objetos como se muestra en la tabla siguiente.  
  
    |Objeto|Propiedad|Configuración|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|Tarea de inicio|  
    |`Button2`|`Text`|Cancelar|  
    |`Label`|`(Name)`, `Text`|lblPercentDone, 0|  
  
4.  En el **proyecto** menú, elija **Agregar clase** para agregar una clase denominada `Widget.vb` al proyecto.  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a>Para declarar un evento para la clase Widget  
  
-   Utilice la `Event` palabra clave para declarar un evento en el `Widget` clase. Tenga en cuenta que puede tener un evento `ByVal` y `ByRef` argumentos, como `Widget`de `PercentDone` en el evento:  
  
     [!code-vb[1 VbVbcnWalkthroughDeclaringAndRaisingEvents](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_1.vb)]  
  
 Cuando el objeto de llamada recibe un `PercentDone` evento, el `Percent` argumento contiene el porcentaje de la tarea que se ha completado. El `Cancel` argumento se puede establecer en `True` para cancelar el método que provocó el evento.  
  
> [!NOTE]
>  Puede declarar argumentos de evento como argumentos de procedimientos, con las siguientes excepciones: los eventos no pueden tener `Optional` o `ParamArray` argumentos y eventos no tienen valores devueltos.  
  
 El `PercentDone` evento es desencadenado por la `LongTask` método de la `Widget` clase. `LongTask`toma dos argumentos: el período de tiempo el método pretende realizar trabajo y el intervalo de tiempo mínimo antes de `LongTask` pausas para generar el `PercentDone` eventos.  
  
#### <a name="to-raise-the-percentdone-event"></a>Para generar el evento PercentDone  
  
1.  Para simplificar el acceso a la `Timer` propiedad utilizada por esta clase, agregue una `Imports` en la parte superior de la sección de declaraciones del módulo de clase, por encima del `Class Widget` instrucción.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&#2;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_2.vb)]  
  
2.  Agregue el código siguiente a la clase `Widget` :  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&3;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_3.vb)]  
  
 Cuando la aplicación llama el `LongTask` (método), el `Widget` clase provoca la `PercentDone` evento cada `MinimumInterval` segundos. Devuelve el evento `LongTask` comprueba si la `Cancel` argumento se estableció en `True`.  
  
 Algunas aclaraciones son necesarios. Para simplificar, el `LongTask` procedimiento se supone que sabe de antemano cuánto tiempo tardará la tarea. Esto ocurre casi nunca. Dividir las tareas en bloques del mismo tamaño puede resultar difícil y, a menudo lo más importante para los usuarios es simplemente la cantidad de tiempo que transcurre antes de recibir una indicación de que está ocurriendo algo.  
  
 Puede haber detectado otro error en este ejemplo. El `Timer` propiedad devuelve el número de segundos que han transcurrido desde medianoche; por lo tanto, la aplicación se bloquea si se ha iniciado antes de medianoche. Una forma más cuidadosa de medir el tiempo lleve las condiciones de límite como ésta en consideración o evitar totalmente, mediante propiedades como `Now`.  
  
 Ahora que la `Widget` clase puede provocar eventos, puede mover al siguiente tutorial. [Tutorial: Controlar eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) muestra cómo utilizar `WithEvents` para asociar un controlador de eventos con el `PercentDone` eventos.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A></xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>   
 <xref:Microsoft.VisualBasic.DateAndTime.Now%2A></xref:Microsoft.VisualBasic.DateAndTime.Now%2A>   
 [Tutorial: Controlar eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)   
 [Eventos](../../../../visual-basic/programming-guide/language-features/events/index.md)
