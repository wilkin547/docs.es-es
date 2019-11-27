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
ms.openlocfilehash: 6f4c303604f9cf55b4ecd500636e0d2772b6234c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345086"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a>Tutorial: Declarar y provocar eventos (Visual Basic)
En este tutorial se muestra cómo declarar y generar eventos para una clase denominada `Widget`. Después de completar los pasos, es posible que desee leer el tema complementario [: control de eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), que muestra cómo utilizar los eventos de `Widget` objetos para proporcionar información de estado en una aplicación.  
  
## <a name="the-widget-class"></a>La clase widget  
 Supongamos por el momento que tiene una clase `Widget`. La clase `Widget` tiene un método que puede tardar mucho tiempo en ejecutarse y desea que la aplicación pueda poner algún tipo de indicador de finalización.  
  
 Por supuesto, podría hacer que el objeto de `Widget` muestre un cuadro de diálogo de porcentaje completado, pero, a continuación, se bloquearía el cuadro de diálogo en todos los proyectos en los que se usara la clase `Widget`. Un buen principio de diseño de objetos es permitir que la aplicación que usa un objeto controle la interfaz de usuario, a menos que el propósito completo del objeto sea administrar un formulario o un cuadro de diálogo.  
  
 El propósito de `Widget` es realizar otras tareas, por lo que es mejor agregar un evento de `PercentDone` y dejar que el procedimiento que llama a los métodos de `Widget`controle ese evento y muestre las actualizaciones de estado. El evento `PercentDone` también puede proporcionar un mecanismo para cancelar la tarea.  
  
#### <a name="to-build-the-code-example-for-this-topic"></a>Para compilar el ejemplo de código de este tema  
  
1. Abra un nuevo proyecto de aplicación de Windows Visual Basic y cree un formulario denominado `Form1`.  
  
2. Agregue dos botones y una etiqueta a `Form1`.  
  
3. Asigne nombre a los objetos tal y como se muestra en la tabla siguiente.  
  
    |Object|Propiedad|Parámetro|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|Tarea de inicio|  
    |`Button2`|`Text`|Cancelar|  
    |`Label`|`(Name)`, `Text`|lblPercentDone, 0|  
  
4. En el menú **proyecto** , elija **Agregar clase** para agregar una clase denominada `Widget.vb` al proyecto.  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a>Para declarar un evento para la clase widget  
  
- Use la palabra clave `Event` para declarar un evento en la clase `Widget`. Tenga en cuenta que un evento puede tener `ByVal` y `ByRef` argumentos, como se muestra en el evento `PercentDone` de `Widget`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 Cuando el objeto que realiza la llamada recibe un evento `PercentDone`, el `Percent` argumento contiene el porcentaje de la tarea que ha finalizado. El argumento `Cancel` se puede establecer en `True` para cancelar el método que provocó el evento.  
  
> [!NOTE]
> Puede declarar argumentos de evento del mismo modo que los argumentos de procedimientos, con las siguientes excepciones: los eventos no pueden tener `Optional` o `ParamArray` argumentos, y los eventos no tienen valores devueltos.  
  
 El método `LongTask` de la clase `Widget` genera el evento `PercentDone`. `LongTask` toma dos argumentos: la cantidad de tiempo que el método va a hacer el trabajo y el intervalo de tiempo mínimo antes de que `LongTask` se ponga en pausa para generar el evento `PercentDone`.  
  
#### <a name="to-raise-the-percentdone-event"></a>Para generar el evento PercentDone  
  
1. Para simplificar el acceso a la propiedad `Timer` utilizada por esta clase, agregue una instrucción `Imports` en la parte superior de la sección declaraciones del módulo de clase, encima de la instrucción `Class Widget`.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2. Agregue el código siguiente a la clase `Widget`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 Cuando la aplicación llama al método `LongTask`, la clase `Widget` genera el evento `PercentDone` cada `MinimumInterval` segundos. Cuando el evento vuelve, `LongTask` comprueba si el argumento de `Cancel` se estableció en `True`.  
  
 Aquí se necesitan algunas renuncias. Para simplificar, en el procedimiento `LongTask` se supone que sabe de antemano cuánto tiempo tardará la tarea en realizarse. Esto casi nunca es el caso. Dividir las tareas en fragmentos de tamaño uniforme puede ser difícil y, a menudo, lo más importante para los usuarios es simplemente la cantidad de tiempo que pasa antes de que obtengan una indicación de que se está produciendo algo.  
  
 Es posible que haya detectado otro problema en este ejemplo. La propiedad `Timer` devuelve el número de segundos transcurridos desde la medianoche; por lo tanto, la aplicación se bloquea si se inicia justo antes de medianoche. Un enfoque más meticuloso para medir el tiempo sería tener en cuenta las condiciones de límite, como esto, o evitar que se consuman, mediante propiedades como `Now`.  
  
 Ahora que la clase `Widget` puede generar eventos, puede pasar al siguiente tutorial. [Tutorial: controlar eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) muestra cómo utilizar `WithEvents` para asociar un controlador de eventos al evento `PercentDone`.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [Tutorial: Controlar eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)
- [Eventos](../../../../visual-basic/programming-guide/language-features/events/index.md)
