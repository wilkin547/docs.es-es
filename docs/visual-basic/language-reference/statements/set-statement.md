---
title: Instrucción Set (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Set
helpviewer_keywords:
- property procedures [Visual Basic], Set statements
- Set statement [Visual Basic]
- Set statement [Visual Basic], syntax
- write-only properties
- properties [Visual Basic], write-only
ms.assetid: 9ecc27b4-df84-420d-9075-db25455fb3cd
ms.openlocfilehash: dbc48d14bac54809e4ddd12c87429bf407169950
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604840"
---
# <a name="set-statement-visual-basic"></a>Instrucción Set (Visual Basic)
Declara un `Set` procedimiento de propiedad que se usa para asignar un valor a una propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a>Elementos  
 `attributelist`  
 Opcional. Vea [lista de los atributos](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `accessmodifier`  
 Opcional en al menos uno de los `Get` y `Set` las instrucciones de esta propiedad. Puede ser uno de los siguientes:  
  
-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
-   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
-   `Protected Friend`  
  
 Vea [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `value`  
 Requerido. Parámetro que contiene el nuevo valor para la propiedad.  
  
 `datatype`  
 Obligatorio si `Option Strict` es `On`. Tipo de datos de la `value` parámetro. El tipo de datos especificado debe ser el mismo que el tipo de datos de la propiedad donde esto `Set` instrucción se declara.  
  
 `statements`  
 Opcional. Una o más instrucciones que se ejecutan cuando el `Set` se llama al procedimiento de propiedad.  
  
 `End Set`  
 Requerido. Termina la definición de la `Set` procedimiento de propiedad.  
  
## <a name="remarks"></a>Comentarios  
 Cada propiedad debe tener un `Set` procedimiento de propiedad, a menos que la propiedad está marcada como `ReadOnly`. El `Set` procedimiento se utiliza para establecer el valor de la propiedad.  
  
 Visual Basic llama automáticamente a una propiedad `Set` procedimiento cuando una instrucción de asignación proporciona un valor que se almacenará en la propiedad.  
  
 Visual Basic pasa un parámetro a la `Set` procedimiento durante las asignaciones de propiedad. Si no especifica ningún parámetro para `Set`, el entorno de desarrollo integrado (IDE) utiliza un parámetro implícito denominado `value`. El parámetro contiene el valor que se asignará a la propiedad. Normalmente almacena este valor en una variable local privada y devolverlo cada vez que la `Get` se llama al procedimiento.  
  
 El cuerpo de la declaración de propiedad puede contener solo la propiedad `Get` y `Set` procedimientos entre el [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md) y `End Property` instrucción. No puede almacenar nada distinto de esos procedimientos. En concreto, no puede almacenar el valor la propiedad actual. Debe almacenar este valor fuera de la propiedad, porque si almacena dentro de cualquiera de los procedimientos de propiedad, el procedimiento de la propiedad no puede acceder a él. El enfoque habitual consiste en almacenar el valor en un [privada](../../../visual-basic/language-reference/modifiers/private.md) variable declarada en el mismo nivel que la propiedad. Debe definir un `Set` procedimiento dentro de la propiedad a la que se aplica.  
  
 El `Set` procedimiento tiene como valor predeterminado para el nivel de acceso de su propiedad que contiene a menos que use `accessmodifier` en el `Set` instrucción.  
  
## <a name="rules"></a>Reglas  
  
-   **Niveles de acceso mixtos.** Si va a definir una propiedad de lectura y escritura, puede especificar opcionalmente un nivel de acceso diferente para el `Get` o `Set` procedimiento, pero no ambos. Si lo hace, el nivel de acceso del procedimiento debe ser más restrictivo que el nivel de acceso de la propiedad. Por ejemplo, si se declara la propiedad `Friend`, puede declarar el `Set` procedimiento `Private`, pero no `Public`.  
  
     Si va a definir un `WriteOnly` propiedad, el `Set` procedimiento representa toda la propiedad. No se puede declarar un acceso diferente nivel para `Set`, porque se establecerían dos niveles de acceso para la propiedad.  
  
## <a name="behavior"></a>Comportamiento  
  
-   **Devolver desde un procedimiento de propiedad.** Cuando el `Set` procedimiento vuelve al código de llamada, la ejecución continúa después de la instrucción que proporciona el valor que se almacenará.  
  
     `Set` los procedimientos de propiedad pueden devolver mediante el [instrucción Return](../../../visual-basic/language-reference/statements/return-statement.md) o [instrucción Exit](../../../visual-basic/language-reference/statements/exit-statement.md).  
  
     El `Exit Property` y `Return` instrucciones provocan una salida inmediata de un procedimiento de propiedad. Cualquier número de `Exit Property` y `Return` instrucciones pueden aparecer en cualquier lugar en el procedimiento y se pueden mezclar `Exit Property` y `Return` las instrucciones.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Set` instrucción que se va a establecer el valor de una propiedad.  
  
 [!code-vb[VbVbalrStatements#55](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/set-statement_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Get (instrucción)](../../../visual-basic/language-reference/statements/get-statement.md)  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Procedimientos de propiedades](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
