---
title: "Event (instrucción) | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Event
- vb.Custom
dev_langs:
- VB
helpviewer_keywords:
- Event statement
- declaring events, syntax
- Public keyword, Event statements
- Custom keyword
- declarations, events
- event keyword [Visual Basic]
- WithEvents keyword, Event statements
- events [Visual Basic], declaring
- ByVal keyword, Event statements
- events [Visual Basic], custom
- ByRef keyword, Event statements
- declaring user-defined events
ms.assetid: 306ff8ed-74dd-4b6a-bd2f-e91b17474042
caps.latest.revision: 33
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
ms.openlocfilehash: b0ea8074f996622df3cd88a7e87fc1156b63dcaf
ms.lasthandoff: 03/13/2017

---
# <a name="event-statement"></a>Event (Instrucción)
Declara un evento definido por el usuario.  
  
## <a name="syntax"></a>Sintaxis  
  
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
  
## <a name="parts"></a>Elementos  
  
|Parte|Descripción|  
|---|---|  
|`attrlist`|Opcional. Lista de atributos que se aplican a este evento. Los diversos atributos se separan con comas. Debe incluir el [lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md) en corchetes angulares ("`<`"y"`>`").|  
|`accessmodifier`|Opcional. Especifica qué código puede tener acceso al evento. Puede ser uno de los siguientes:<br /><br /> -   [Pública](../../../visual-basic/language-reference/modifiers/public.md): cualquier código que puede tener acceso al elemento que lo declara puede tener acceso a él.<br />-   [Protegido](../../../visual-basic/language-reference/modifiers/protected.md): sólo el código dentro de su clase o una clase derivada.<br />-   [Amigo](../../../visual-basic/language-reference/modifiers/friend.md): sólo el código en el mismo ensamblado.<br />-   [Privada](../../../visual-basic/language-reference/modifiers/private.md): sólo el código en el elemento que lo declara puede tener acceso a él.<br /><br /> Puede especificar `Protected Friend` para habilitar el acceso desde el código de la clase del evento, una clase derivada o el mismo ensamblado.|  
|`Shared`|Opcional. Especifica que este evento no está asociado a una instancia específica de una clase o estructura.|  
|`Shadows`|Opcional. Indica que este evento vuelve a declarar y oculta un elemento de programación con el mismo nombre, o un conjunto de elementos sobrecargados, en una clase base. Puede reemplazar cualquier tipo de elemento declarado con cualquier otro tipo.<br /><br /> Un elemento reemplazado no está disponible desde la clase derivada que lo reemplaza, excepto desde donde el elemento reemplazado es inaccesible. Por ejemplo, si un elemento `Private` reemplaza un elemento de clase base, el código que no tiene permiso para acceder al elemento `Private` accede en su lugar al elemento de clase base.|  
|`eventname`|Obligatorio. Nombre del evento; sigue las convenciones estándar de nomenclatura de variables.|  
|`parameterlist`|Opcional. Lista de variables locales que representan los parámetros de este evento. Debe incluir el [lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md) entre paréntesis.|  
|`Implements`|Opcional. Indica que este evento implementa un evento de una interfaz.|  
|`implementslist`|Es necesario si se proporciona `Implements`. Lista de procedimientos `Sub` que se implementan. Los diversos procedimientos se separan con comas:<br /><br /> *procedimientoImplementado* [, *implementedprocedure* ...]<br /><br /> Cada `implementedprocedure` tiene la sintaxis y las partes siguientes:<br /><br /> `interface`.`definedname`<br /><br /> -   `interface`-Required. Nombre de una interfaz que implementan la estructura o clase contenedora de este procedimiento.<br />-   `Definedname`-Required. Nombre por el que se define el procedimiento en `interface`. No tiene que ser el mismo que `name`, el nombre que usa este procedimiento para implementar el procedimiento definido.|  
|`Custom`|Obligatorio. Los eventos declarados como `Custom` deben definir descriptores de acceso `AddHandler`, `RemoveHandler` y `RaiseEvent` personalizados.|  
|`delegatename`|Opcional. Nombre de un delegado que especifica la firma del controlador de eventos.|  
|`AddHandler`|Obligatorio. Declara un descriptor de acceso `AddHandler`, que especifica las instrucciones que se deben ejecutar cuando se agrega un controlador de eventos, ya sea explícitamente mediante la instrucción `AddHandler` o implícitamente mediante la cláusula `Handles`.|  
|`End AddHandler`|Obligatorio. Finaliza el bloque `AddHandler`.|  
|`value`|Obligatorio. Nombre del parámetro.|  
|`RemoveHandler`|Obligatorio. Declara un descriptor de acceso `RemoveHandler`, que especifica las instrucciones que se ejecutan cuando se quita un controlador de eventos mediante la instrucción `RemoveHandler`.|  
|`End RemoveHandler`|Obligatorio. Finaliza el bloque `RemoveHandler`.|  
|`RaiseEvent`|Obligatorio. Declara un descriptor de acceso `RaiseEvent`, que especifica las instrucciones que se ejecutan cuando se produce el evento mediante la instrucción `RaiseEvent`. Normalmente, invoca una lista de delegados mantenida por los descriptores de acceso `AddHandler` y `RemoveHandler`.|  
|`End RaiseEvent`|Obligatorio. Finaliza el bloque `RaiseEvent`.|  
|`delegatesignature`|Obligatorio. Lista de parámetros que coincide con los parámetros requeridos por el delegado `delegatename`. Debe incluir el [lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md) entre paréntesis.|  
|`statements`|Opcional. Instrucciones que contienen los cuerpos de los métodos `AddHandler`, `RemoveHandler` y `RaiseEvent`.|  
|`End Event`|Obligatorio. Finaliza el bloque `Event`.|  
  
## <a name="remarks"></a>Comentarios  
 Una vez declarado el evento, use la instrucción `RaiseEvent` para generar el evento. Un evento típico podría declararse y provocarse tal como se muestra en los fragmentos siguientes:  
  
 [!code-vb[VbVbalrEvents&#13;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/event-statement_1.vb)]  
  
> [!NOTE]
>  Puede declarar argumentos de evento del mismo modo que los argumentos de procedimientos, con las siguientes excepciones: los eventos no pueden tener argumentos con nombre, argumentos `ParamArray` o argumentos `Optional`. Los eventos no tienen valores devueltos.  
  
 Para controlar un evento, debe asociarlo a una subrutina del controlador de eventos mediante la instrucción `Handles` o `AddHandler`. Las firmas de la subrutina y del evento deben coincidir. Para controlar un evento compartido, debe usar la instrucción `AddHandler`.  
  
 Solo se puede usar `Event` en un nivel de módulo. Esto significa que la *contexto de la declaración* de un evento debe ser una clase, estructura, módulo o interfaz y no puede ser un archivo de código fuente, un espacio de nombres, un procedimiento ni un bloque. Para obtener más información, consulte [contextos de declaración y niveles de acceso predeterminados](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 En la mayoría de los casos, puede usar la primera sintaxis de la sección Sintaxis de este tema para declarar los eventos. Sin embargo, algunos escenarios requieren un mayor control sobre el comportamiento detallado del evento. La última sintaxis de la sección Sintaxis de este tema, que usa la palabra clave `Custom`, proporciona ese control permitiéndole definir eventos personalizados. En un evento personalizado, debe especificar exactamente lo que sucede cuando el código agrega o quita un controlador de eventos a o desde el evento, o cuando el código provoca el evento. Para obtener ejemplos, vea [Cómo: declarar personalizados para conservar la memoria de eventos](../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md) y [Cómo: declarar personalizado eventos para evitar bloquear](../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usan eventos para contar los segundos de 10 a 0. El código muestra algunos de los métodos, propiedades e instrucciones relacionados con eventos. Esto incluye la instrucción `RaiseEvent`.  
  
 La clase que provoca un evento es el origen del evento, y los métodos que procesan el evento son los controladores de eventos. Un origen de eventos puede tener varios controladores para los eventos que genera. Cuando la clase genera el evento, ese evento se genera en cada clase que eligió controlar eventos para esa instancia del objeto.  
  
 El ejemplo también usa un formulario (`Form1`) con un botón (`Button1`) y un cuadro de texto (`TextBox1`). Al hacer clic en el botón, el primer cuadro de texto muestra una cuenta atrás de 10 a 0 segundos. Cuando transcurre el tiempo (10 segundos), el primer cuadro de texto muestra "Done".  
  
 El código de `Form1` especifica los estados inicial y terminal del formulario. También contiene el código que se ejecuta cuando se producen eventos.  
  
 Para usar este ejemplo, abra un nuevo proyecto de Windows Forms. Agregue un botón denominado `Button1` y un cuadro de texto denominado `TextBox1` al formulario principal, denominado `Form1`. A continuación, haga clic en el formulario y haga clic en **ver código** para abrir el editor de código.  
  
 Agregue una variable `WithEvents` a la sección de declaraciones de la clase `Form1`:  
  
 [!code-vb[VbVbalrEvents&#14;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/event-statement_2.vb)]  
  
 Agregue el código siguiente al código de `Form1`. Sustituya los procedimientos duplicados que existan, como `Form_Load` o `Button_Click`.  
  
 [!code-vb[VbVbalrEvents&#15;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/event-statement_3.vb)]  
  
 Presione F5 para ejecutar el ejemplo anterior y haga clic en el botón **iniciar**. El primer cuadro de texto empieza la cuenta atrás de los segundos. Cuando transcurre el tiempo (10 segundos), el primer cuadro de texto muestra "Done".  
  
> [!NOTE]
>  El método `My.Application.DoEvents` no procesa los eventos de la misma manera que el formulario. Para habilitar el formulario de modo que controle directamente los eventos, puede usar multithreading. Para obtener más información, consulte [subprocesos](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).  
  
## <a name="see-also"></a>Vea también  
 [RaiseEvent (instrucción)](../../../visual-basic/language-reference/statements/raiseevent-statement.md)   
 [Implements (instrucción)](../../../visual-basic/language-reference/statements/implements-statement.md)   
 [Eventos](../../../visual-basic/programming-guide/language-features/events/index.md)   
 [AddHandler (instrucción)](../../../visual-basic/language-reference/statements/addhandler-statement.md)   
 [RemoveHandler (instrucción)](../../../visual-basic/language-reference/statements/removehandler-statement.md)   
 [Identificadores](../../../visual-basic/language-reference/statements/handles-clause.md)   
 [Delegate (instrucción)](../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Cómo: declarar eventos personalizados para conservar memoria](../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)   
 [Cómo: declarar eventos personalizados para evitar bloqueos](../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)   
 [Compartido](../../../visual-basic/language-reference/modifiers/shared.md)   
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
