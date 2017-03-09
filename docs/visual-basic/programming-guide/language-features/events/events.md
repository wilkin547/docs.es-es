---
title: "Eventos (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "02/25/2017"
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
  - "eventos [Visual Basic]"
  - "eventos [Visual Basic], acerca de los eventos"
ms.assetid: 8fb0353a-e41b-4e23-b78f-da65db832f70
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Eventos (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

A pesar de que se puede visualizar un proyecto de [!INCLUDE[vsprvs](../../../../csharp/includes/vsprvs-md.md)] como una serie de procedimientos que se ejecutan consecutivamente, en realidad la mayoría de los programas están dirigidos por eventos, es decir, el flujo de ejecución está determinado por elementos externos denominados *eventos*.  
  
 Un evento es una señal que comunica a una aplicación que ha sucedido algo importante.  Por ejemplo, cuando un usuario hace clic en un control de un formulario, el formulario puede provocar un evento `Click` y llamar a un procedimiento que controla el evento.  Los eventos también permiten que las tareas separadas se comuniquen.  Suponga, por ejemplo, que una aplicación realiza una tarea de ordenación independientemente de la aplicación principal.  Si un usuario cancela la ordenación, la aplicación puede enviar un evento de cancelación que ordene la detención del proceso de ordenación.  
  
## Conceptos y términos de los eventos  
 Esta sección describe los términos y conceptos que se utilizan con eventos en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
### Declarar eventos  
 Los eventos se declaran en clases, estructuras, módulos e interfaces mediante la palabra clave `Event`, como se muestra en el siguiente ejemplo:  
  
 [!code-vb[VbVbalrEvents#24](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#24)]  
  
### Producir eventos  
 Un evento es como un mensaje que anuncia que ha pasado algo importante.  A la acción de difundir el mensaje se le llama *producir* el evento.  En [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], los eventos se generan con la instrucción `RaiseEvent`, como en el ejemplo siguiente:  
  
 [!code-vb[VbVbalrEvents#25](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#25)]  
  
 Los eventos se deben provocar dentro del ámbito de la clase, módulo o estructura donde se declaran.  Por ejemplo, una clase derivada no puede producir eventos heredados de una clase base.  
  
### Remitentes de eventos  
 Cualquier objeto capaz de producir un evento es un *remitente de eventos*, y también recibe el nombre de *origen de eventos*.  Los formularios, controles y objetos definidos por el usuario son ejemplos de remitentes de eventos.  
  
### Controladores de eventos  
 Los *controladores de eventos* son procedimientos llamados cuando se produce un evento correspondiente.  Puede utilizar cualquier subrutina válida con una firma coincidente como controlador de eventos.  No obstante, no puede utilizar una función como controlador de eventos, porque no puede devolver un valor al origen del evento.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] utiliza una convención de nomenclatura estándar para controladores de eventos que combina el nombre del remitente del evento, un signo de subrayado y el nombre del evento.  Por ejemplo, el evento `Click` de un botón denominado `button1` recibiría el nombre de `Sub button1_Click`.  
  
> [!NOTE]
>  Es recomendable utilizar esta convención de nomenclatura al definir controladores de eventos para sus propios eventos, pero no es estrictamente necesario; puede utilizar cualquier nombre de subrutina válido.  
  
## Asociar eventos a controladores de eventos  
 Para que un controlador de eventos se pueda utilizar, primero debe asociarse a un evento mediante la instrucción `Handles` o `AddHandler`.  
  
### WithEvents y la cláusula Handles  
 La instrucción `WithEvents` y la cláusula `Handles` proporcionan una forma declarativa de especificar controladores de eventos.  Los eventos provocados por un objeto declarado con la palabra clave `WithEvents` pueden controlarse mediante cualquier procedimiento con una instrucción `Handles` para ese evento, tal y como se muestra en el ejemplo siguiente:  
  
 [!code-vb[VbVbalrEvents#1](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#1)]  
  
 La instrucción `WithEvents` y la cláusula `Handles` son a menudo la mejor opción para los controladores de eventos, ya que la sintaxis declarativa que utilizan hace que el control de eventos sea más sencillo de codificar, leer y depurar.  No obstante, tenga en cuenta las siguientes limitaciones en la utilización de las variables `WithEvents`:  
  
-   No se puede utilizar una variable `WithEvents` como variable de objeto.  Es decir, no es posible declararla como `Object`; se debe especificar el nombre de clase al declarar la variable.  
  
-   Dado que los eventos compartidos `` no están asociados a instancias de clase, no se puede usar `WithEvents` para controlar eventos compartidos mediante declaración.  De forma parecida, no se puede utilizar `WithEvents` ni `Handles` para controlar los eventos desde una estructura `Structure`.  En ambos casos, puede utilizar la instrucción `AddHandler` para controlar esos eventos.  
  
-   No se pueden crear matrices de variables `WithEvents`.  
  
 Las variables `WithEvents` permiten que un solo controlador controle uno o más tipos de eventos, así como que uno o más controladores de eventos controlen el mismo tipo de evento.  
  
 Aunque la cláusula `Handles` es la forma estándar de asociar un evento a un controlador de eventos, está limitada a asociar eventos a controladores de eventos en tiempo de compilación.  
  
 En algunos casos, como con eventos asociados a formularios o controles, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] desactiva automáticamente un controlador de eventos vacío y lo asocia a un evento.  Por ejemplo, al hacer doble clic en un botón de comando en un formulario en modo de diseño, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] crea un controlador de eventos vacío y una variable `WithEvents` para el botón de comando, como en el código siguiente:  
  
 [!code-vb[VbVbalrEvents#26](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#26)]  
  
### AddHandler y RemoveHandler  
 La instrucción `AddHandler` se parece a la cláusula `Handles` en que las dos permiten especificar un controlador de eventos.  Sin embargo, `AddHandler`, utilizado con `RemoveHandler`, proporciona más flexibilidad que la cláusula `Handles`, lo que permite agregar, quitar y cambiar de forma dinámica el controlador de errores asociado con un evento.  Si desea controlar eventos compartidos o eventos de una estructura, debe utilizar `AddHandler`.  
  
 `AddHandler` toma dos argumentos: el nombre de un evento de un remitente de evento, como un control, y una expresión que evalúa a un delegado.  No necesita especificar explícitamente la clase delegada al utilizar `AddHandler`, ya que la instrucción `AddressOf` siempre devuelve una referencia al delegado.  El ejemplo siguiente asocia un controlador de eventos a un evento provocado por un objeto:  
  
 [!code-vb[VbVbalrEvents#28](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#28)]  
  
 `RemoveHandler`, que desconecta un evento de un controlador de eventos, utiliza la misma sintaxis que `AddHandler`.  Por ejemplo:  
  
 [!code-vb[VbVbalrEvents#29](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#29)]  
  
 En el ejemplo siguiente, un controlador de eventos se asocia a un evento y se genera el evento.  El controlador de eventos detecta el evento y muestra un mensaje.  
  
 A continuación, se quita el primer controlador de eventos y se asocia al evento un controlador de eventos diferente.  Cuando el evento se vuelve a generar, se muestra un mensaje diferente.  
  
 Finalmente, se quita el segundo controlador de eventos y el evento se genera por tercera vez.  Dado que ya no hay ningún controlador de eventos asociado al evento, no se realiza ninguna acción.  
  
 [!code-vb[VbVbalrEvents#38](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class2.vb#38)]  
  
## Controlar eventos heredados de una clase base  
 Las *clases derivadas* \(clases que heredan características de una clase base\) pueden controlar eventos provocados por su clase base mediante la instrucción `Handles` `MyBase`.  
  
#### Controlar eventos de una clase base  
  
-   Declare un controlador de eventos en la clase derivada agregando una instrucción `Handles MyBase.`*nombreDeEvento* a la línea de declaración del procedimiento controlador de eventos, donde *nombreDeEvento* es el nombre del evento de la clase base que está controlando.  Por ejemplo:  
  
     [!code-vb[VbVbalrEvents#12](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#12)]  
  
## Secciones relacionadas  
  
|Título|Descripción|  
|------------|-----------------|  
|[Tutorial: Declarar y provocar eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)|Proporciona una descripción paso a paso de cómo declarar y provocar los eventos de una clase.|  
|[Tutorial: Controlar eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)|Muestra cómo escribir un procedimiento controlador de eventos.|  
|[Cómo: Declarar eventos personalizados para evitar bloqueos](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)|Muestra cómo definir un evento personalizado que permite llamar a sus controladores de eventos de forma asincrónica.|  
|[Cómo: Declarar eventos personalizados para conservar memoria](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)|Muestra cómo definir un evento personalizado que sólo utiliza la memoria cuando se controla el evento.|  
|[Solucionar problemas de controladores de eventos heredados en Visual Basic](../../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)|Enumera problemas comunes que surgen con controladores de eventos en componentes heredados.|  
|[Eventos](../Topic/Handling%20and%20Raising%20Events.md)|Proporciona información general sobre el modelo de eventos de [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)].|  
|[Creating Event Handlers in Windows Forms](../Topic/Creating%20Event%20Handlers%20in%20Windows%20Forms.md)|Describe cómo trabajar con eventos asociados a objetos de formularios Windows Forms.|  
|[Delegados](../../../../visual-basic/programming-guide/language-features/delegates/delegates.md)|Proporciona información general sobre los delegados en Visual Basic.|