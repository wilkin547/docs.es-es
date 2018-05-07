---
title: Get (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.Get
helpviewer_keywords:
- Get statement [Visual Basic], syntax
- Get statement [Visual Basic]
- properties [Visual Basic], read-only
- read-only properties
- Get keyword [Visual Basic]
- property procedures [Visual Basic], Get statements
ms.assetid: 56b05cdc-bd64-4dfd-bb12-824eacec6f94
ms.openlocfilehash: d6a6fdfd191de76871619dea3bd1794b487698aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="get-statement"></a>Get (Instrucción)
Declara un `Get` procedimiento de propiedad que se usa para recuperar el valor de una propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`attributelist`|Opcional. Vea [lista de los atributos](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Opcional en al menos uno de los `Get` y `Set` las instrucciones de esta propiedad. Puede ser uno de los siguientes:<br /><br /> -   [Protegido](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Privada](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Vea [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`statements`|Opcional. Una o más instrucciones que se ejecutan cuando el `Get` se llama al procedimiento de propiedad.|  
|`End Get`|Requerido. Termina la definición de la `Get` procedimiento de propiedad.|  
  
## <a name="remarks"></a>Comentarios  
 Cada propiedad debe tener un `Get` procedimiento de propiedad, a menos que la propiedad está marcada como `WriteOnly`. El `Get` procedimiento se utiliza para devolver el valor actual de la propiedad.  
  
 Visual Basic llama automáticamente a una propiedad `Get` procedimiento cuando una expresión solicita el valor de la propiedad.  
  
 El cuerpo de la declaración de propiedad puede contener solo la propiedad `Get` y `Set` procedimientos entre el [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md) y `End Property` instrucción. No puede almacenar nada distinto de esos procedimientos. En concreto, no puede almacenar el valor la propiedad actual. Debe almacenar este valor fuera de la propiedad, porque si almacena dentro de cualquiera de los procedimientos de propiedad, el procedimiento de la propiedad no puede acceder a él. El enfoque habitual consiste en almacenar el valor en un [privada](../../../visual-basic/language-reference/modifiers/private.md) variable declarada en el mismo nivel que la propiedad. Debe definir un `Get` procedimiento dentro de la propiedad a la que se aplica.  
  
 El `Get` procedimiento tiene como valor predeterminado para el nivel de acceso de su propiedad que contiene a menos que use `accessmodifier` en el `Get` instrucción.  
  
## <a name="rules"></a>Reglas  
  
-   **Niveles de acceso mixtos.** Si va a definir una propiedad de lectura y escritura, puede especificar opcionalmente un nivel de acceso diferente para el `Get` o `Set` procedimiento, pero no ambos. Si lo hace, el nivel de acceso del procedimiento debe ser más restrictivo que el nivel de acceso de la propiedad. Por ejemplo, si se declara la propiedad `Friend`, puede declarar el `Get` procedimiento `Private`, pero no `Public`.  
  
     Si va a definir un `ReadOnly` propiedad, el `Get` procedimiento representa toda la propiedad. No se puede declarar un acceso diferente nivel para `Get`, porque se establecerían dos niveles de acceso para la propiedad.  
  
-   **Tipo de valor devuelto.** El [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md) puede declarar el tipo de datos del valor que devuelve. El `Get` procedimiento devuelve automáticamente ese tipo de datos. Puede especificar cualquier tipo de datos o el nombre de una estructura, clase, interfaz o enumeración.  
  
     Si el `Property` instrucción no especifica `returntype`, el procedimiento devuelve `Object`.  
  
## <a name="behavior"></a>Comportamiento  
  
-   **Devolver desde un procedimiento.** Cuando el `Get` procedimiento vuelve al código de llamada, la ejecución continúa en la instrucción que solicita el valor de propiedad.  
  
     `Get` procedimientos de propiedad pueden devolver un valor mediante la [instrucción Return](../../../visual-basic/language-reference/statements/return-statement.md) o asignando el valor devuelto al nombre de propiedad. Para obtener más información, vea "Valor devuelto" en [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md).  
  
     El `Exit Property` y `Return` instrucciones provocan una salida inmediata de un procedimiento de propiedad. Cualquier número de `Exit Property` y `Return` instrucciones pueden aparecer en cualquier lugar en el procedimiento y se pueden mezclar `Exit Property` y `Return` las instrucciones.  
  
-   **Valor devuelto.** Para devolver un valor de un `Get` procedimiento, puede asignar el valor al nombre de propiedad o incluirlo en una [instrucción Return](../../../visual-basic/language-reference/statements/return-statement.md). El `Return` instrucción asigna simultáneamente el `Get` procedimiento devolver valor y sale del procedimiento.  
  
     Si usa `Exit Property` sin asignar un valor al nombre de propiedad, el `Get` procedimiento devuelve el valor predeterminado para el tipo de datos de la propiedad. Para obtener más información, vea "Valor devuelto" en [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md).  
  
     El ejemplo siguiente muestra dos formas de la propiedad de solo lectura `quoteForTheDay` puede devolver el valor contenido en la variable privada `quoteValue`.  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_2.vb)]  
  
     [!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_3.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Get` instrucción para devolver el valor de una propiedad.  
  
 [!code-vb[VbVbalrStatements#30](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_4.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Set (instrucción)](../../../visual-basic/language-reference/statements/set-statement.md)  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Exit (instrucción)](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Tutorial: Definir clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)
