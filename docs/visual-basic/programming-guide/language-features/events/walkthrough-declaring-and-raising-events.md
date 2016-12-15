---
title: "Tutorial: Declarar y provocar eventos (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "declaraciones, eventos"
  - "declarar eventos, tutoriales"
  - "eventos [Visual Basic], declarar"
  - "eventos [Visual Basic], provocar"
  - "eventos [Visual Basic], tutoriales"
  - "generar eventos, tutoriales"
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Tutorial: Declarar y provocar eventos (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Este tutorial explica cómo declarar y provocar eventos para una clase denominada `Widget`.  Cuando finalice los pasos tal vez desee leer el tema complementario, [Tutorial: Controlar eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), que muestra cómo utilizar eventos de objetos `Widget` para proporcionar información de estado en una aplicación.  
  
## La clase Widget  
 Suponga por el momento que tiene una clase `Widget`.  Su clase `Widget` tiene un método que puede tardar bastante tiempo en ejecutarse, y desea que la aplicación pueda establecer alguna clase de indicador de finalización.  
  
 Por supuesto, podría hacer que el objeto `Widget` mostrara un cuadro de diálogo de porcentaje finalizado, pero entonces ese cuadro de diálogo aparecería en cada proyecto en el que utilizase la clase `Widget`.  Un buen principio del diseño de objetos consiste en dejar que la aplicación que utiliza un objeto controle la interfaz de usuario, a no ser que el objeto tenga como única finalidad administrar un formulario o un cuadro de diálogo.  
  
 La finalidad de `Widget` es realizar otras tareas, de modo que es mejor agregar un evento `PercentDone` y dejar que el procedimiento que llama a los métodos de `Widget` lo controle y muestre las actualizaciones del estado.  El evento `PercentDone` también puede proporcionar un mecanismo para cancelar la tarea.  
  
#### Para compilar el ejemplo de código para este tema  
  
1.  Abra un nuevo proyecto de aplicación para Windows de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] y cree un formulario llamado `Form1`.  
  
2.  Agregue dos botones y una etiqueta a `Form1`.  
  
3.  Dé nombre a los objetos como se muestra en la tabla siguiente.  
  
    |Objeto.|Propiedad.|Configuración|  
    |-------------|----------------|-------------------|  
    |`Button1`|`Text`|Iniciar tarea|  
    |`Button2`|`Text`|Cancelar|  
    |`Label`|`(Name)`, `Text`|lblPercentDone, 0|  
  
4.  En el menú **Proyecto**, elija **Agregar clase** para agregar al proyecto una clase denominada `Widget.vb`.  
  
#### Para declarar un evento para la clase Widget  
  
-   Utilice la palabra clave `Event` para declarar un evento en la clase `Widget`.  Observe que un evento puede tener argumentos `ByVal` y `ByRef`, como se puede ver en el evento `PercentDone` de `Widget`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_1.vb)]  
  
 Cuando el objeto de llamada recibe un evento `PercentDone`, el argumento `Percent` contiene el porcentaje de la tarea que se ha finalizado.  El argumento `Cancel` se puede establecer en `True` para cancelar el método que provocó el evento.  
  
> [!NOTE]
>  Los argumentos de eventos se pueden declarar igual que se hace con los argumentos de procedimientos, con las siguientes excepciones: los eventos no pueden tener argumentos `Optional`, `ParamArray`, ni valores devueltos.  
  
 El método `LongTask` de la clase `Widget` genera el evento `PercentDone`.  `LongTask` toma dos argumentos: el período de tiempo durante el cual el método va a trabajar y el intervalo de tiempo mínimo antes de que `LongTask` pause para generar el evento `PercentDone`.  
  
#### Para provocar el evento PercentDone  
  
1.  Para simplificar el acceso a la propiedad `Timer` utilizada por esta clase, agregue una instrucción `Imports` a la parte superior de la sección de declaraciones del módulo de clase, por encima de la instrucción `Class Widget`.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_2.vb)]  
  
2.  Agregue el código siguiente a la clase `Widget`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_3.vb)]  
  
 Cuando su aplicación llama al método `LongTask`, la clase `Widget` provoca el evento `PercentDone` cada vez que transcurran los especificados en `MinimumInterval`.  Cuando se vuelve del evento, `LongTask` comprueba si se estableció en `True` el argumento `Cancel`.  
  
 En este punto son necesarias algunas aclaraciones.  Para simplificar, en el procedimiento `LongTask` se supone que el usuario conoce de antemano cuánto tarda en realizarse la tarea.  Esto casi nunca es así.  Dividir las tareas en bloques del mismo tamaño puede resultar difícil y, a menudo, lo que es más importante para los usuarios es simplemente el tiempo que transcurre antes de recibir una indicación de que algo está ocurriendo.  
  
 También puede haber detectado otro error en este ejemplo.  La propiedad `Timer` devuelve el número de segundos transcurridos desde medianoche; por lo tanto, la aplicación se bloquea si se inicia inmediatamente antes de medianoche.  Una forma más cuidadosa de medir el tiempo tendría en cuenta condiciones de límite como ésta, o las evitaría globalmente utilizando propiedades como `Now`.  
  
 Ahora que la clase `Widget` puede generar eventos, puede pasar al siguiente tutorial.  En [Tutorial: Controlar eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), se muestra cómo utilizar `WithEvents` para asociar un controlador de eventos al evento `PercentDone`.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>   
 <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>   
 [Tutorial: Controlar eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)   
 [Eventos](../../../../visual-basic/programming-guide/language-features/events/events.md)