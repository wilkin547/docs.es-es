---
title: "RaiseEvent (Instrucci&#243;n) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.RaiseEventMethod"
  - "vb.RaiseEvent"
  - "RaiseEvent"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "controladores de eventos, conectar eventos"
  - "RaiseEvent (instrucción)"
  - "generar eventos, RaiseEvent (instrucción)"
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# RaiseEvent (Instrucci&#243;n)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Desencadena un evento declarado en el nivel de módulo dentro de una clase, formulario o documento.  
  
## Sintaxis  
  
```  
RaiseEvent eventname[( argumentlist )]  
```  
  
## Elementos  
 `eventname`  
 Obligatorio.  Nombre del evento que se va a desencadenar.  
  
 `argumentlist`  
 Opcional.  Lista de variables, matrices o expresiones delimitadas por comas.  El argumento `argumentlist` debe estar entre paréntesis.  Si no hay argumentos, deben omitirse los paréntesis.  
  
## Comentarios  
 El parámetro `eventname` requerido es el nombre de un evento declarado en el módulo.  Sigue las convenciones de nomenclatura de Visual Basic.  
  
 Si el evento no se ha declarado dentro del módulo en el que se produce, ocurrirá un error.  El siguiente fragmento de código muestra una declaración de evento y un procedimiento en el que se produce el evento.  
  
 [!code-vb[VbVbalrEvents#37](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_1.vb)]  
  
 No se puede utilizar `RaiseEvent` para generar eventos que no estén explícitamente declarados en el módulo.  Por ejemplo, todos los formularios heredan un evento <xref:System.Windows.Forms.Control.Click> de <xref:System.Windows.Forms.Form?displayProperty=fullName>; no se puede producir utilizando `RaiseEvent` en un formulario derivado.  Si se declara un evento `Click` en el módulo de formulario, sombrea el propio evento <xref:System.Windows.Forms.Control.Click> del formulario.  Sin embargo, todavía se puede invocar el evento <xref:System.Windows.Forms.Control.Click> del formulario llamando al método <xref:System.Windows.Forms.Control.OnClick%2A>.  
  
 De manera predeterminada, un evento definido en Visual Basic provoca sus controladores de eventos en el orden en que se establecen las conexiones.  Como los eventos pueden tener parámetros `ByRef`, un proceso que se conecta tarde puede recibir parámetros modificados por un controlador de eventos anterior.  Después de que se ejecutan los controladores de eventos, el control se devuelve a la subrutina que provocó el evento.  
  
> [!NOTE]
>  Los eventos no compartidos no se deben provocar dentro del constructor de la clase en la que están declarados.  Aunque dichos eventos no provocan errores en tiempo de ejecución, es posible que los controladores de eventos asociados no los puedan capturar.  Se debe utilizar el modificador `Shared` para crear un evento compartido si es necesario provocar un evento a partir de un constructor.  
  
> [!NOTE]
>  El comportamiento predeterminado de eventos se puede cambiar definiendo un evento personalizado.  En los eventos personalizados, la instrucción `RaiseEvent` invoca al descriptor de acceso `RaiseEvent` del evento.  Para obtener más información sobre eventos personalizados, vea [Event \(Instrucción\)](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## Ejemplo  
 En el siguiente ejemplo se utilizan eventos para hacer una cuenta atrás de los segundos de 10 a 0.  El código muestra algunos de los métodos, propiedades e instrucciones relacionados con eventos, incluyendo la instrucción `RaiseEvent`.  
  
 La clase que produce un evento es el origen de evento, y los métodos que procesan el evento son los controladores de eventos.  Un origen de evento puede tener múltiples controladores para los eventos que genera.  Cuando una clase produce el evento, ese evento se genera en cada clase que ha elegido para controlar eventos para esa instancia del objeto.  
  
 En el ejemplo también se utiliza un formulario \(`Form1`\) con un botón \(`Button1`\) y un cuadro de texto \(`TextBox1`\).  Al hacer clic en el botón, el primer cuadro de texto presenta una cuenta atrás de 10 a 0 segundos.  Cuando ha transcurrido todo el tiempo \(10 segundos\), el primer cuadro de texto presenta "Done".  
  
 El código para `Form1` especifica los estados inicial y terminal del formulario.  También contiene el código que se ejecuta cuando se producen eventos.  
  
 Para utilizar este ejemplo, abra un nuevo proyecto de aplicación para Windows, agregue un botón denominado `Button1` y un cuadro de texto denominado `TextBox1` al formulario principal, denominado `Form1`.  A continuación, haga clic con el botón secundario del mouse en el formulario y haga clic en **Ver código** para abrir el editor de código.  
  
 Agregue una variable `WithEvents` a la sección de declaraciones de la clase `Form1`.  
  
 [!code-vb[VbVbalrEvents#14](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_2.vb)]  
  
## Ejemplo  
 Agregue el código siguiente al código de `Form1`.  Sustituya los procedimientos que estén duplicados, como `Form_Load` o `Button_Click`.  
  
 [!code-vb[VbVbalrEvents#15](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_3.vb)]  
  
 Presione F5 para ejecutar el ejemplo anterior y haga clic en el botón que tiene la etiqueta **Iniciar**.  El primer cuadro de texto empieza la cuenta atrás.  Cuando ha transcurrido todo el tiempo \(10 segundos\), el primer cuadro de texto presenta "Done".  
  
> [!NOTE]
>  El método `My.Application.DoEvents` no procesa los eventos exactamente de la misma manera en que lo hace el formulario.  Para permitir que el formulario controle directamente los eventos, puede utilizar el multithreading.  Para obtener más información, vea [Subprocesos](../Topic/Threading%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Vea también  
 [Eventos](../../../visual-basic/programming-guide/language-features/events/events.md)   
 [Event \(Instrucción\)](../../../visual-basic/language-reference/statements/event-statement.md)   
 [AddHandler \(Instrucción\)](../../../visual-basic/language-reference/statements/addhandler-statement.md)   
 [RemoveHandler \(Instrucción\)](../../../visual-basic/language-reference/statements/removehandler-statement.md)   
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)