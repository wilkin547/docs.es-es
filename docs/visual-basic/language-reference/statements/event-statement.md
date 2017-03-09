---
title: "Event (Instrucci&#243;n) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Event"
  - "vb.Custom"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ByRef (palabra clave), Event (instrucciones)"
  - "ByVal (palabra clave), Event (instrucciones)"
  - "Custom (palabra clave)"
  - "declaraciones, eventos"
  - "declarar eventos, sintaxis"
  - "declarar eventos definidos por el usuario"
  - "event (palabra clave) [Visual Basic]"
  - "Event (instrucción)"
  - "eventos [Visual Basic], personalizadas"
  - "eventos [Visual Basic], declarar"
  - "Public (palabra clave), Event (instrucciones)"
  - "WithEvents (palabra clave), Event (instrucciones)"
ms.assetid: 306ff8ed-74dd-4b6a-bd2f-e91b17474042
caps.latest.revision: 33
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 33
---
# Event (Instrucci&#243;n)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Declara un evento definido por el usuario.  
  
## Sintaxis  
  
```  
[ <attrlist> ] [ accessmodifier ] _  
[ Shared ] [ Shadows ] Event eventname[(parameterlist)] _  
[ Implements implementslist ]  
' -or-  
[ <attrlist> ] [ accessmodifier ] _  
[ Shared ] [ Shadows ] Event eventname As delegatename _  
[ Implements implementslist ]  
' -or-  
 [ <attrlist> ] [ accessmodifier ] _  
[ Shared ] [ Shadows ] Custom Event eventname As delegatename _  
[ Implements implementslist ]  
   [ <attrlist> ] AddHandler(ByVal value As delegatename)  
      [ statements ]  
   End AddHandler  
   [ <attrlist> ] RemoveHandler(ByVal value As delegatename)  
      [ statements ]  
   End RemoveHandler  
   [ <attrlist> ] RaiseEvent(delegatesignature)  
      [ statements ]  
   End RaiseEvent  
End Event  
```  
  
## Elementos  
  
|||  
|-|-|  
|Parte|Descripción|  
|`attrlist`|Opcional.  Lista de atributos que se aplican a este evento.  Los diversos atributos se separan con comas.  Debe incluir la [Lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md) entre corchetes angulares \("`<`" y "`>`"\).|  
|`accessmodifier`|Opcional.  Especifica qué código puede tener acceso al evento.  Puede ser uno de los siguientes:<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md): cualquier código con acceso al elemento que lo declara puede tener acceso a él.<br />-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md): solo el código de su clase o de una clase derivada puede tener acceso a él.<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md): solo el código del mismo ensamblado puede tener acceso a él.<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md): solo el código del elemento que lo declara puede tener acceso a él.<br /><br /> Puede especificar `Protected Friend` para habilitar el acceso desde el código de la clase del evento, una clase derivada o el mismo ensamblado.|  
|`Shared`|Opcional.  Especifica que este evento no está asociado a una instancia específica de una clase o estructura.|  
|`Shadows`|Opcional.  Indica que este evento vuelve a declarar y oculta un elemento de programación con el mismo nombre, o un conjunto de elementos sobrecargados, en una clase base.  Puede reemplazar cualquier tipo de elemento declarado con cualquier otro tipo.<br /><br /> Un elemento reemplazado no está disponible desde la clase derivada que lo reemplaza, excepto desde donde el elemento reemplazado es inaccesible.  Por ejemplo, si un elemento `Private` reemplaza un elemento de clase base, el código que no tiene permiso para acceder al elemento `Private` accede en su lugar al elemento de clase base.|  
|`eventname`|Requerido.  Nombre del evento; sigue las convenciones estándar de nomenclatura de variables.|  
|`parameterlist`|Opcional.  Lista de variables locales que representan los parámetros de este evento.  Debe incluir la [Lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md) entre paréntesis.|  
|`Implements`|Opcional.  Indica que este evento implementa un evento de una interfaz.|  
|`implementslist`|Es necesario si se proporciona `Implements`.  Lista de procedimientos `Sub` que se implementan.  Los diversos procedimientos se separan con comas:<br /><br /> *implementedprocedure* \[ , *implementedprocedure* ...  \]<br /><br /> Cada `implementedprocedure` tiene la sintaxis y las partes siguientes:<br /><br /> `interface`.`definedname`<br /><br /> -   `interface` \- Requerido.  Nombre de una interfaz que implementan la estructura o clase contenedora de este procedimiento.<br />-   `Definedname` \- Requerido.  Nombre por el que se define el procedimiento en `interface`.  No tiene que ser el mismo que `name`, el nombre que usa este procedimiento para implementar el procedimiento definido.|  
|`Custom`|Requerido.  Los eventos declarados como `Custom` deben definir descriptores de acceso `AddHandler`, `RemoveHandler` y `RaiseEvent` personalizados.|  
|`delegatename`|Opcional.  Nombre de un delegado que especifica la firma del controlador de eventos.|  
|`AddHandler`|Requerido.  Declara un descriptor de acceso `AddHandler`, que especifica las instrucciones que se deben ejecutar cuando se agrega un controlador de eventos, ya sea explícitamente mediante la instrucción `AddHandler` o implícitamente mediante la cláusula `Handles`.|  
|`End AddHandler`|Requerido.  Finaliza el bloque `AddHandler`.|  
|`value`|Requerido.  Nombre del parámetro.|  
|`RemoveHandler`|Requerido.  Declara un descriptor de acceso `RemoveHandler`, que especifica las instrucciones que se ejecutan cuando se quita un controlador de eventos mediante la instrucción `RemoveHandler`.|  
|`End RemoveHandler`|Requerido.  Finaliza el bloque `RemoveHandler`.|  
|`RaiseEvent`|Requerido.  Declara un descriptor de acceso `RaiseEvent`, que especifica las instrucciones que se ejecutan cuando se produce el evento mediante la instrucción `RaiseEvent`.  Normalmente, invoca una lista de delegados mantenida por los descriptores de acceso `AddHandler` y `RemoveHandler`.|  
|`End RaiseEvent`|Requerido.  Finaliza el bloque `RaiseEvent`.|  
|`delegatesignature`|Requerido.  Lista de parámetros que coincide con los parámetros requeridos por el delegado `delegatename`.  Debe incluir la [Lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md) entre paréntesis.|  
|`statements`|Opcional.  Instrucciones que contienen los cuerpos de los métodos `AddHandler`, `RemoveHandler` y `RaiseEvent`.|  
|`End Event`|Requerido.  Finaliza el bloque `Event`.|  
  
## Comentarios  
 Una vez declarado el evento, use la instrucción `RaiseEvent` para generar el evento.  Un evento típico podría declararse y provocarse tal como se muestra en los fragmentos siguientes:  
  
 [!code-vb[VbVbalrEvents#13](../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#13)]  
  
> [!NOTE]
>  Puede declarar argumentos de evento del mismo modo que los argumentos de procedimientos, con las siguientes excepciones: los eventos no pueden tener argumentos con nombre, argumentos `ParamArray` o argumentos `Optional`.  Los eventos no tienen valores devueltos.  
  
 Para controlar un evento, debe asociarlo a una subrutina del controlador de eventos mediante la instrucción `Handles` o `AddHandler`.  Las firmas de la subrutina y del evento deben coincidir.  Para controlar un evento compartido, debe usar la instrucción `AddHandler`.  
  
 Solo se puede usar `Event` en un nivel de módulo.  Esto significa que el *contexto de la declaración* de un evento debe ser una clase, una estructura, un módulo o una interfaz y no puede ser un archivo de código fuente, un espacio de nombres, un procedimiento ni un bloque.  Para obtener más información, consulte [Contextos de declaración y niveles de acceso predeterminados](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 En la mayoría de los casos, puede usar la primera sintaxis de la sección Sintaxis de este tema para declarar los eventos.  Sin embargo, algunos escenarios requieren un mayor control sobre el comportamiento detallado del evento.  La última sintaxis de la sección Sintaxis de este tema, que usa la palabra clave `Custom`, proporciona ese control permitiéndole definir eventos personalizados.  En un evento personalizado, debe especificar exactamente lo que sucede cuando el código agrega o quita un controlador de eventos a o desde el evento, o cuando el código provoca el evento.  Para obtener ejemplos, vea [Cómo: Declarar eventos personalizados para conservar memoria](../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md) y [Cómo: Declarar eventos personalizados para evitar bloqueos](../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md).  
  
## Ejemplo  
 En el ejemplo siguiente se usan eventos para contar los segundos de 10 a 0.  El código muestra algunos de los métodos, propiedades e instrucciones relacionados con eventos.  Esto incluye la instrucción `RaiseEvent`.  
  
 La clase que provoca un evento es el origen del evento, y los métodos que procesan el evento son los controladores de eventos.  Un origen de eventos puede tener varios controladores para los eventos que genera.  Cuando la clase genera el evento, ese evento se genera en cada clase que eligió controlar eventos para esa instancia del objeto.  
  
 El ejemplo también usa un formulario \(`Form1`\) con un botón \(`Button1`\) y un cuadro de texto \(`TextBox1`\).  Al hacer clic en el botón, el primer cuadro de texto muestra una cuenta atrás de 10 a 0 segundos.  Cuando transcurre el tiempo \(10 segundos\), el primer cuadro de texto muestra "Done".  
  
 El código de `Form1` especifica los estados inicial y terminal del formulario.  También contiene el código que se ejecuta cuando se producen eventos.  
  
 Para usar este ejemplo, abra un nuevo proyecto de Windows Forms.  Agregue un botón denominado `Button1` y un cuadro de texto denominado `TextBox1` al formulario principal, denominado `Form1`.  A continuación, haga clic con el botón derecho en el formulario y haga clic en **Ver código** para abrir el editor de código.  
  
 Agregue una variable `WithEvents` a la sección de declaraciones de la clase `Form1`:  
  
 [!code-vb[VbVbalrEvents#14](../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#14)]  
  
 Agregue el código siguiente al código de `Form1`.  Sustituya los procedimientos duplicados que existan, como `Form_Load` o `Button_Click`.  
  
 [!code-vb[VbVbalrEvents#15](../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#15)]  
  
 Presione F5 para ejecutar el ejemplo anterior y haga clic en el botón **Iniciar**.  El primer cuadro de texto empieza la cuenta atrás de los segundos.  Cuando transcurre el tiempo \(10 segundos\), el primer cuadro de texto muestra "Done".  
  
> [!NOTE]
>  El método `My.Application.DoEvents` no procesa los eventos de la misma manera que el formulario.  Para habilitar el formulario de modo que controle directamente los eventos, puede usar multithreading.  Para obtener más información, vea la [Subprocesos](../Topic/Threading%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Vea también  
 [RaiseEvent \(Instrucción\)](../../../visual-basic/language-reference/statements/raiseevent-statement.md)   
 [Implements \(Instrucción\)](../../../visual-basic/language-reference/statements/implements-statement.md)   
 [Eventos](../../../visual-basic/programming-guide/language-features/events/events.md)   
 [AddHandler \(Instrucción\)](../../../visual-basic/language-reference/statements/addhandler-statement.md)   
 [RemoveHandler \(Instrucción\)](../../../visual-basic/language-reference/statements/removehandler-statement.md)   
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)   
 [Delegate \(Instrucción\)](../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Cómo: Declarar eventos personalizados para conservar memoria](../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)   
 [Cómo: Declarar eventos personalizados para evitar bloqueos](../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)   
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)   
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)