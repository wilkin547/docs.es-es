---
title: "Tutorial: Controlar eventos (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "controladores de eventos [Visual Basic], tutoriales"
  - "control de eventos [Visual Basic], tutoriales"
  - "eventos [Visual Basic], tutoriales"
  - "variables [Visual Basic], WithEvents"
  - "tutoriales [Visual Basic], control de eventos"
  - "WithEvents (palabra clave), tutoriales"
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Tutorial: Controlar eventos (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Éste es el segundo de los dos temas que muestran cómo trabajar con eventos.  En el primer tema, [Tutorial: Declarar y provocar eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), se muestra cómo declarar y provocar eventos.  Esta sección utiliza el formulario y la clase del tutorial para mostrar cómo controlar eventos cuando tienen lugar.  
  
 En el ejemplo de la clase `Widget`, se usan las instrucciones de control de eventos tradicionales.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] proporciona otras técnicas para trabajar con eventos.  Como ejercicio, puede modificar este ejemplo para utilizar las instrucciones `AddHandler` y `Handles`.  
  
### Para controlar el evento PercentDone de la clase Widget  
  
1.  Coloque el código siguiente en `Form1`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](../../../../visual-basic/programming-guide/language-features/events/codesnippet/visualbasic/VbEventWalkthrough/Form1.vb#4)]  
  
     La palabra clave `WithEvents` especifica que se utiliza la variable `mWidget` para controlar los eventos de un objeto.  Puede especificar el tipo de objeto proporcionando el nombre de la clase de la que se creará el objeto.  
  
     La variable `mWidget` se declara en `Form1` porque las variables `WithEvents` deben ser de nivel de clase.  Esto es cierto independientemente del tipo de módulo donde se coloquen.  
  
     Se utiliza la variable `mblnCancel` para cancelar el método `LongTask`.  
  
## Escritura de código para controlar eventos  
 Tan pronto como declara una variable utilizando `WithEvents`, el nombre de variable aparece en la lista desplegable izquierda del **Editor de código** de la clase.  Cuando selecciona `mWidget`, aparecen los eventos de la clase `Widget` en la lista desplegable derecha.  Al seleccionar un evento se muestra el procedimiento de evento correspondiente, con el prefijo `mWidget` y un carácter de subrayado.  Se da a todos los procedimientos de eventos asociados a la variable `WithEvents` el nombre de variable como prefijo.  
  
#### Para controlar un evento  
  
1.  Seleccione `mWidget` en la lista desplegable izquierda del **Editor de código**.  
  
2.  Seleccione el evento `PercentDone` en la lista desplegable derecha.  El **Editor de código** abre el procedimiento de evento `mWidget_PercentDone`.  
  
    > [!NOTE]
    >  El **Editor de código** es útil, pero no necesario, para insertar los nuevos controladores de eventos.  En este tutorial, es más directo copiar simplemente los controladores de eventos en el código.  
  
3.  Agregue el código siguiente al controlador de eventos `mWidget_PercentDone`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](../../../../visual-basic/programming-guide/language-features/events/codesnippet/visualbasic/VbEventWalkthrough/Form1.vb#5)]  
  
     Siempre que se provoca el evento `PercentDone`, el procedimiento de evento muestra el porcentaje completo en un control `Label`.  El método `DoEvents` permite volver a dibujar la etiqueta y también le da al usuario la oportunidad de hacer clic en el botón **Cancel**.  
  
4.  Agregue el código siguiente para el controlador de eventos `Button2_Click`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](../../../../visual-basic/programming-guide/language-features/events/codesnippet/visualbasic/VbEventWalkthrough/Form1.vb#6)]  
  
 Si el usuario hace clic en el botón **Cancel** cuando se está ejecutando `LongTask`, se ejecuta el evento `Button2_Click` tan pronto como la instrucción `DoEvents` permite que se produzca el procesamiento de eventos.  La variable `mblnCancel` de nivel de clase se establece como `True` y el evento `mWidget_PercentDone` lo comprueba luego y establece el argumento `ByRef Cancel` como `True`.  
  
## Conectar la variable WithEvents con un objeto  
 `Form1` está ahora configurado para controlar los eventos de un objeto `Widget`.  Sólo queda buscar un objeto `Widget` en alguna parte.  
  
 Cuando declara una variable `WithEvents` en tiempo de diseño, no se asocia ningún objeto a ésta.  La variable `WithEvents` es como cualquier otra variable de objeto.  Tendrá que crear un objeto y asignar una referencia a éste con la variable `WithEvents`.  
  
#### Para crear un objeto y asignarlo una referencia  
  
1.  Seleccione **\(Eventos Form1\)** en la lista desplegable izquierda del **Editor de código**.  
  
2.  Seleccione el evento `Load` en la lista desplegable derecha.  El **Editor de código** abre el procedimiento de evento `Form1_Load`.  
  
3.  Agregue el código siguiente para el procedimiento de evento `Form1_Load` a fin de crear el objeto `Widget`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](../../../../visual-basic/programming-guide/language-features/events/codesnippet/visualbasic/VbEventWalkthrough/Form1.vb#7)]  
  
 Cuando se ejecuta este código, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] crea un objeto `Widget` y conecta sus eventos a los procedimientos de evento asociados con `mWidget`.  Desde este momento en adelante, siempre que el objeto `Widget` provoque el evento `PercentDone`, se ejecutará el procedimiento de evento `mWidget_PercentDone`.  
  
#### Para llamar al método LongTask  
  
-   Agregue el código siguiente al controlador de eventos `Button1_Click`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](../../../../visual-basic/programming-guide/language-features/events/codesnippet/visualbasic/VbEventWalkthrough/Form1.vb#8)]  
  
 Antes de llamar al método `LongTask`, la etiqueta que muestra el porcentaje completo debe inicializarse y el marcador `Boolean` de nivel de clase que cancela el método debe establecerse como `False`.  
  
 `LongTask` se llama con una duración de tarea de 12,2 segundos.  Se provoca el evento `PercentDone` una vez cada tercio de segundo.  Cada vez que se provoca el evento, se ejecuta el procedimiento de evento `mWidget_PercentDone`.  
  
 Cuando termina `LongTask`, se comprueba `mblnCancel` para ver si `LongTask` ha finalizado de forma normal o si se ha detenido porque `mblnCancel` estaba establecido como `True`.  El porcentaje completo se actualiza sólo en el primer caso.  
  
#### Para ejecutar el programa  
  
1.  Presione F5 para poner el proyecto en modo de ejecución.  
  
2.  Haga clic en el botón **Iniciar tarea**.  Cada vez que se provoca el evento `PercentDone`, se actualiza la etiqueta con el porcentaje de la tarea que se ha completado.  
  
3.  Haga clic en el botón **Cancelar** para detener la tarea.  Observe que la apariencia del botón **Cancelar** no cambia inmediatamente cuando se hace clic en él.  El evento `Click` no puede tener lugar hasta que la instrucción `My.Application.DoEvents` permita el procesamiento del evento.  
  
    > [!NOTE]
    >  El método `My.Application.DoEvents` no procesa los eventos exactamente de la misma manera en que lo hace el formulario.  Por ejemplo, en este tutorial, debe hacer clic dos veces en el botón **Cancelar**.  Para permitir que el formulario controle directamente los eventos, puede utilizar el multithreading.  Para obtener más información, vea [Subprocesos](../Topic/Threading%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Puede resultarle instructivo ejecutar el programa con F11 y recorrer el código línea a línea.  Puede ver claramente cómo la ejecución escribe `LongTask` y luego vuelve a escribir `Form1` brevemente cada vez que se provoca el evento `PercentDone`.  
  
 ¿Qué sucedería si cuando se estaba devolviendo la ejecución al código de `Form1`, se llamara al método `LongTask` de nuevo?  En el peor de los casos, podría ocurrir un desbordamiento de la pila si se llamara a `LongTask` cada vez que se provocara el evento.  
  
 Puede hacer que la variable `mWidget` controle los eventos de un objeto `Widget` distinto asignando una referencia al nuevo `Widget` con `mWidget`.  De hecho, puede hacer que el código de `Button1_Click` realice esto cada vez que hace clic en el botón.  
  
#### Para controlar eventos para un Widget distinto  
  
-   Agregue la línea de código siguiente al procedimiento `Button1_Click`, inmediatamente antes de la línea que indica `mWidget.LongTask(12.2, 0.33)`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](../../../../visual-basic/programming-guide/language-features/events/codesnippet/visualbasic/VbEventWalkthrough/Form1.vb#9)]  
  
 El código anterior crea un nuevo `Widget` cada vez que se hace clic en el botón.  Tan pronto como finaliza el método `LongTask`, se libera la referencia al objeto `Widget` y se destruye este último.  
  
 Las variables `WithEvents` pueden contener sólo una referencia a objeto a la vez, de modo que si asigna otro objeto `Widget` a `mWidget`, los eventos del objeto `Widget` anterior ya no se controlarán.  Si `mWidget` es la única variable de objeto que contiene una referencia al objeto `Widget` antiguo, éste se destruirá.  Si desea controlar eventos desde varios objetos `Widget`, utilice la instrucción `AddHandler` para procesar independientemente los eventos de cada objeto.  
  
> [!NOTE]
>  Puede declarar todas las variables `WithEvents` que sean necesarias, pero no se admiten las matrices de variables `WithEvents`.  
  
## Vea también  
 [Tutorial: Declarar y provocar eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)   
 [Eventos](../../../../visual-basic/programming-guide/language-features/events/events.md)