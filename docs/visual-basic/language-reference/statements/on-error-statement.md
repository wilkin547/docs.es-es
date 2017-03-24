---
title: "Instrucci&#243;n On Error (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.OnError"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "bifurcación, on error"
  - "instrucciones condicionales, On Error"
  - "flujo de control, bifurcación"
  - "control de errores, On Error (instrucción)"
  - "Error (palabra clave)"
  - "Error (instrucción), y la instrucción On Error"
  - "errores [Visual Basic], interceptar"
  - "ejecución, conditional"
  - "GoTo (instrucción), y la instrucción On Error"
  - "Next (instrucción), On Error"
  - "On Error (instrucción)"
  - "On Error (instrucción), sintaxis"
  - "On (palabra clave)"
  - "Resume Next (instrucción)"
  - "Resume (instrucción), y la instrucción On Error"
  - "errores en tiempo de ejecución, controlar"
  - "código de Visual Basic, flujo de control"
ms.assetid: ff947930-fb84-40cf-bd66-1ea219561d5c
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Instrucci&#243;n On Error (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Habilita una rutina de control de errores y especifica la ubicación de la rutina dentro de un procedimiento; también se puede utilizar para deshabilitar la rutina de control de errores.  
  
 Sin una instrucción `On Error`, cualquier error en tiempo de ejecución será fatal: aparecerá un mensaje de error y se detendrá la ejecución.  
  
 Siempre que sea posible, sugiramos utiliza el control de excepciones estructurado en el código, en lugar de utilizar el control no estructurado de excepciones y la instrucción de `On Error` .  Para obtener más información, vea [Try...Catch...Finally \(Instrucción\)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
> [!NOTE]
>  La palabra clave `Error` también se utiliza en [Error \(Instrucción\)](../../../visual-basic/language-reference/statements/error-statement.md), lo que se admite a efectos de compatibilidad con versiones anteriores.  
  
## Sintaxis  
  
```  
On Error { GoTo [ line | 0 | -1 ] | Resume Next }  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`GoTo` `line`|Habilita la rutina de control de errores que empieza en la línea especificada en el argumento `line` requerido.  El argumento `line` es cualquier etiqueta de línea o número de línea.  Si se produce un error en tiempo de ejecución, el control se transfiere a la línea especificada, con lo que se activa el controlador de errores.  La línea especificada debe estar en el mismo procedimiento que la instrucción `On Error`; de lo contrario, se producirá un error de compilación.|  
|`GoTo` 0|Deshabilita un controlador de errores habilitado en el procedimiento actual y lo restablece en `Nothing`.|  
|`GoTo` \-1|Deshabilita una excepción habilitada en el procedimiento actual y restablece el objeto con el valor `Nothing`.|  
|`Resume Next`|Especifica que, cuando se produce un error en tiempo de ejecución, el control se transfiere a la instrucción inmediatamente posterior a la que produjo el error y la ejecución continúa desde ese punto.  Utilice este formato en lugar de `On Error GoTo` al tener acceso a los objetos.|  
  
## Comentarios  
  
> [!NOTE]
>  Se recomienda usar el control estructurado de excepciones en el código siempre que sea posible, en lugar de utilizar el control no estructurado de excepciones y la instrucción de `On Error` .  Para obtener más información, vea [Try...Catch...Finally \(Instrucción\)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
 Un controlador de errores "habilitado" es uno activado por una instrucción `On Error`.  Un controlador de errores "activo" es un controlador habilitado que está en el proceso de controlar un error.  
  
 Si se produce un error mientras un controlador de errores está activo \(desde que se genera el error hasta que se ejecuta una instrucción `Resume`, `Exit Sub`, `Exit Function` o `Exit Property`\), el controlador de errores del procedimiento actual no podrá controlar el error.  El control se devuelve al procedimiento que realizó la llamada.  
  
 Si el procedimiento de llamada posee un controlador de errores habilitado, se activa para procesar el error.  Si el controlador de errores del procedimiento de llamada también está activo, el control se devuelve a los procedimientos de llamada anteriores hasta encontrar un controlador de error habilitado pero inactivo.  Si no se encuentra ese controlador de errores, el error se convierte en fatal en el punto en que se produjo originalmente.  
  
 Cada vez que el controlador de errores devuelve el control a un procedimiento de llamada, ese procedimiento se convierte en el procedimiento actual.  Cuando un controlador de errores termina de procesar un error en cualquier procedimiento, la ejecución continúa en el procedimiento actual en el punto designado por la instrucción `Resume`.  
  
> [!NOTE]
>  Una rutina de control de errores no es un procedimiento `Sub` ni `Function`.  Se trata de una sección de código identificada por una etiqueta de línea o un número de línea.  
  
## Number \(Propiedad\)  
 Las rutinas de control de errores utilizan el valor de la propiedad `Number` del objeto `Err` para determinar la causa del error.  La rutina debería comprobar o guardar los valores de propiedades relevantes del objeto `Err` antes de que se produzca otro error o de que se realice una llamada a un procedimiento que pueda causar un error.  Los valores de propiedades del objeto `Err` sólo reflejan el error más reciente.  El mensaje de error asociado a `Err.Number` está contenido en `Err.Description`.  
  
## Throw \(Instrucción\)  
 Un error que se produce con el método `Err.Raise` establece la propiedad `Exception` en una instancia recientemente creada de la clase <xref:System.Exception>.  Para poder provocar excepciones de tipos de excepción derivados, el lenguaje incluye la instrucción `Throw`.  Ésta acepta un único parámetro, que es la instancia de excepción que se va a desencadenar.  En el siguiente ejemplo se muestra cómo se pueden utilizar estas características con el control de excepciones existente:  
  
 [!code-vb[VbVbalrErrorHandling#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_1.vb)]  
  
 Observe que la instrucción `On Error GoTo` intercepta todos los errores, sin tener en cuenta la clase de excepción.  
  
## On Error Resume Next  
 `On Error Resume Next` hace que la ejecución continúe en la instrucción que sigue a la instrucción que produjo el error en tiempo de ejecución, o en la instrucción que sigue a la llamada más reciente a otro procedimiento externo al procedimiento que contiene la instrucción `On Error Resume Next`.  Esta instrucción permite que la ejecución continúe aunque se produzca un error en tiempo de ejecución.  Se puede colocar la rutina de control de errores donde se prevea que puede ocurrir el error, en vez de transferir el control a otro punto del procedimiento.  Una instrucción `On Error Resume Next` queda inactiva cuando se llama a otro procedimiento, por lo que se debe ejecutar una instrucción `On Error Resume Next` en cada rutina llamada si se desea controlar el error en línea dentro de esa rutina.  
  
> [!NOTE]
>  La construcción `On Error Resume Next` puede ser preferible a `On Error GoTo` cuando se controlan errores generados durante el acceso a otros objetos.  La comprobación de `Err` después de cada interacción con un objeto quita la ambigüedad acerca de cuál fue el objeto al que obtuvo acceso el código.  Se puede conocer con seguridad qué objeto colocó el código de error en `Err.Number`, así como qué objeto generó originalmente el error \(el objeto especificado en `Err.Source`\).  
  
## On Error GoTo 0  
 `On Error GoTo 0` deshabilita el control de errores en el procedimiento actual.  No especifica la línea 0 en el inicio del código de control de errores, aunque el procedimiento contenga una línea numerada con 0.  Sin una instrucción `On Error GoTo 0`, un controlador de errores se deshabilita automáticamente cuando se sale de un procedimiento.  
  
## On Error GoTo \-1  
 `On Error GoTo -1` deshabilita la excepción en el procedimiento actual.  No especifica la línea \-1 en el inicio del código de control de errores, aunque el procedimiento contenga una línea numerada con \-1.  Sin una instrucción `On Error GoTo -1`, una instrucción se deshabilita automáticamente cuando se sale de un procedimiento.  
  
 Para impedir que el código de control de errores se ejecute cuando no se ha producido ningún error, coloque una instrucción `Exit Sub`, `Exit Function` o `Exit Property` inmediatamente antes de la rutina de control de errores, como en el siguiente fragmento:  
  
 [!code-vb[VbVbalrErrorHandling#18](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_2.vb)]  
  
 Aquí, el código de control de errores sigue a la instrucción `Exit Sub` y precede a la instrucción `End Sub` para separarlo del flujo de instrucciones del procedimiento.  El código de control de errores se puede colocar en cualquier lugar de un procedimiento.  
  
## Errores no interceptados  
 Los errores no interceptados que se producen en objetos se devuelven a la aplicación controladora cuando el objeto se ejecuta como un archivo ejecutable.  En el entorno de desarrollo, los errores no interceptados sólo se devuelven a la aplicación controladora si están configuradas las opciones apropiadas.  Consulte la documentación de la aplicación host para obtener una descripción de qué opciones se deben configurar durante la depuración, cómo configurarlas y si la aplicación host puede crear clases.  
  
 Si se crea un objeto que tiene acceso a otros objetos, se debería intentar controlar cualquier error no controlado que devuelvan.  Si no es posible, asigne los códigos de error de `Err.Number` a uno de sus errores y, a continuación, devuélvalos al elemento que realizó la llamada al objeto.  Debería especificar el error agregando el código de error a la constante `VbObjectError`.  Por ejemplo, si el código de error es 1052, asígnelo del siguiente modo:  
  
 [!code-vb[VbVbalrErrorHandling#19](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_3.vb)]  
  
> [!CAUTION]
>  Los errores del sistema que se producen durante las llamadas a bibliotecas de vínculos dinámicos \(DLL\) de Windows no provocan excepciones y no se pueden interceptar con el mecanismo de interceptación de errores de Visual Basic.  Al llamar a funciones de DLL, se debe comprobar, para cada valor devuelto, si la llamada se ha realizado correctamente o si se ha producido algún error \(según las especificaciones de la API\) y, en ese caso, comprobar el valor de la propiedad `LastDLLError` del objeto `Err`.  
  
## Ejemplo  
 En este ejemplo primero se utiliza la instrucción `On Error GoTo` para especificar la ubicación de una rutina de control de errores en un procedimiento.  En el ejemplo, el intento de dividir entre cero genera el número de error 6.  El error se administra en la rutina de control de errores y a continuación, el control se devuelve a la instrucción que produjo el error.  La instrucción `On Error GoTo 0` activa la interceptación de errores.  A continuación, se utiliza la instrucción `On Error Resume Next` para aplazar la interceptación de errores, así se puede conocer el contexto para el error generado por la siguiente instrucción.  Observe que `Err.Clear` se utiliza para borrar las propiedades del objeto `Err` una vez que se ha controlado el error.  
  
 [!code-vb[VbVbalrErrorHandling#20](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_4.vb)]  
  
## Requisitos  
 **Espacio de nombres:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Ensamblado:** biblioteca en tiempo de ejecución de Visual Basic \(en Microsoft.VisualBasic.dll\)  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Information.Err%2A>   
 <xref:Microsoft.VisualBasic.ErrObject.Number%2A>   
 <xref:Microsoft.VisualBasic.ErrObject.Description%2A>   
 <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>   
 [End \(Instrucción\)](../../../visual-basic/language-reference/statements/end-statement.md)   
 [Exit \(Instrucción\)](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [Resume \(Instrucción\)](../../../visual-basic/language-reference/statements/resume-statement.md)   
 [Mensajes de error](../../../visual-basic/language-reference/error-messages/index.md)   
 [Try...Catch...Finally \(Instrucción\)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)