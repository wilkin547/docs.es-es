---
title: "Get (Instrucci&#243;n) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Get"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Get (palabra clave)"
  - "Get (instrucción)"
  - "Get (instrucción), sintaxis"
  - "propiedades [Visual Basic], solo lectura"
  - "procedimientos de propiedades, Get (instrucciones)"
  - "propiedades de solo lectura"
ms.assetid: 56b05cdc-bd64-4dfd-bb12-824eacec6f94
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Get (Instrucci&#243;n)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Declara un procedimiento de propiedad `Get` que se utiliza para recuperar el valor de una propiedad.  
  
## Sintaxis  
  
```  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`attributelist`|Opcional.  Vea la [Lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Opcional en un máximo de una de las instrucciones `Get` y `Set` de esta propiedad.  Puede ser una de las siguientes:<br /><br /> -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Vea [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`statements`|Opcional.  Una o más instrucciones que se ejecutan cuando se llama al procedimiento de propiedad `Get`.|  
|`End Get`|Obligatorio.  Termina la definición de este procedimiento de propiedad `Get`.|  
  
## Comentarios  
 Cada propiedad debe tener un procedimiento de propiedad `Get`, a menos que la propiedad esté marcada como `WriteOnly`.  El procedimiento `Get` se utiliza para devolver el valor actual de la propiedad.  
  
 Visual Basic llama automáticamente al procedimiento `Get` de una propiedad cuando una expresión solicita el valor de la propiedad.  
  
 El cuerpo de la declaración de propiedad sólo puede contener los procedimientos `Get` y `Set` de la propiedad entre [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md) y `End Property` No puede almacenar nada distinto de esos procedimientos.  En particular, no puede almacenar el valor actual de la propiedad.  Este valor debe almacenarse fuera de la propiedad, ya que si lo almacena en uno de los procedimientos de la propiedad, el otro procedimiento no puede tener acceso a él.  El enfoque habitual consiste en almacenar el valor en una variable [Private](../../../visual-basic/language-reference/modifiers/private.md) declarada en el mismo nivel que la propiedad.  Debe definir un procedimiento `Get` dentro de la propiedad a la que se aplica.  
  
 El procedimiento `Get` tiene como valor predeterminado el nivel de acceso de su propiedad contenedora a menos que utilice `accessmodifier` en la instrucción `Get`.  
  
## Reglas  
  
-   **Niveles mixtos de acceso.** Si define una propiedad de lectura y escritura, puede especificar opcionalmente un nivel de acceso diferente para el procedimiento `Get` o `Set`, pero no para ambos.  Si hace esto, el nivel de acceso del procedimiento debe ser más restrictivo que el nivel de acceso de la propiedad.  Por ejemplo, si la propiedad se declara como `Friend`, puede declarar el procedimiento `Get` como `Private`, pero no como `Public`.  
  
     Si está definiendo una propiedad `ReadOnly`, el procedimiento `Get` representa toda la propiedad.  No puede declarar un nivel de acceso diferente para `Get`, porque se establecerían dos niveles de acceso para la propiedad.  
  
-   **Tipo de valor devuelto.** [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md) puede declarar el tipo de datos del valor que devuelve.  El procedimiento `Get` devuelve automáticamente ese tipo de datos.  Puede especificar cualquier tipo de datos o el nombre de una enumeración, estructura, clase o interfaz.  
  
     Si la instrucción `Property` no especifica `returntype`, el procedimiento devuelve `Object`.  
  
## Comportamiento  
  
-   **Volver de un procedimiento.** Cuando el procedimiento `Get` vuelve al código de llamada, la ejecución continúa dentro de la instrucción que solicitó el valor de propiedad.  
  
     Los procedimientos de propiedad `Get` pueden devolver un valor mediante la instrucción [Return \(Instrucción\)](../../../visual-basic/language-reference/statements/return-statement.md) o asignando el valor devuelto al nombre de propiedad.  Para obtener más información, vea "Valor devuelto" en [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md).  
  
     Las instrucciones `Exit Property` y `Return` provocan una salida inmediata de un procedimiento de propiedad.  Puede aparecer cualquier número de instrucciones `Exit Property` y `Return` en cualquier parte del procedimiento y puede combinar instrucciones `Exit Property` y `Return`.  
  
-   **Valor devuelto.** Para devolver un valor desde un procedimiento `Get`, puede asignar el valor al nombre de propiedad o incluirlo en [Return \(Instrucción\)](../../../visual-basic/language-reference/statements/return-statement.md).  La instrucción `Return` asigna simultáneamente el valor devuelto por el procedimiento `Get` y sale del procedimiento.  
  
     Si utiliza `Exit Property` sin asignar un valor al nombre de propiedad, el procedimiento `Get` devuelve el valor predeterminado para el tipo de datos de la propiedad.  Para obtener más información, vea "Valor devuelto" en [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md).  
  
     El ejemplo siguiente muestra dos maneras en que la propiedad `quoteForTheDay` de sólo lectura puede devolver el valor contenido en la variable privada `quoteValue`.  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_2.vb)]  
  
     [!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_3.vb)]  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza la instrucción `Get` para devolver el valor de una propiedad.  
  
 [!code-vb[VbVbalrStatements#30](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_4.vb)]  
  
## Vea también  
 [Set \(Instrucción\)](../../../visual-basic/language-reference/statements/set-statement.md)   
 [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Exit \(Instrucción\)](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Tutorial: Definir clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)