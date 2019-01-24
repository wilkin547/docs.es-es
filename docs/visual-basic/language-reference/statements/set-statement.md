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
ms.openlocfilehash: d77c7d3f2e70edcc1028c207150944c5394afbe0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685378"
---
# <a name="set-statement-visual-basic"></a>Instrucción Set (Visual Basic)
Declara un `Set` procedimiento de propiedad que se utiliza para asignar un valor a una propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a>Elementos  
 `attributelist`  
 Opcional. Consulte [lista de los atributos](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `accessmodifier`  
 Opcional en al menos uno de los `Get` y `Set` instrucciones de esta propiedad. Puede ser uno de los siguientes:  
  
-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
-   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
-   `Protected Friend`  
  
 Vea [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `value`  
 Obligatorio. Parámetro que contiene el nuevo valor para la propiedad.  
  
 `datatype`  
 Es necesario si `Option Strict` es `On`. Tipo de datos de la `value` parámetro. El tipo de datos especificado debe ser el mismo que el tipo de datos de la propiedad donde esto `Set` se declara la instrucción.  
  
 `statements`  
 Opcional. Una o varias instrucciones que se ejecutan cuando el `Set` se llama al procedimiento de propiedad.  
  
 `End Set`  
 Obligatorio. Termina la definición de la `Set` procedimiento de propiedad.  
  
## <a name="remarks"></a>Comentarios  
 Cada propiedad debe tener un `Set` procedimiento de propiedad, a menos que la propiedad se marca `ReadOnly`. El `Set` procedimiento se usa para establecer el valor de la propiedad.  
  
 Visual Basic llama automáticamente una propiedad `Set` procedimiento cuando una instrucción de asignación proporciona un valor que se almacenará en la propiedad.  
  
 Visual Basic pasa un parámetro a la `Set` procedimiento durante las asignaciones de propiedad. Si no proporciona un parámetro para `Set`, el entorno de desarrollo integrado (IDE) utiliza un parámetro implícito denominado `value`. El parámetro contiene el valor que se asignará a la propiedad. Se suele almacenar este valor en una variable local privada y devolverlo cada vez que el `Get` se llama al procedimiento.  
  
 El cuerpo de la declaración de propiedad puede contener sólo la propiedad `Get` y `Set` procedimientos entre el [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) y `End Property` instrucción. No puede almacenar algo distinto de esos procedimientos. En concreto, no puede almacenar el valor actual de la propiedad. Debe almacenar este valor fuera de la propiedad, porque si lo guarda dentro de cualquiera de los procedimientos de propiedad, el procedimiento de la propiedad no puede acceder a él. El enfoque habitual consiste en almacenar el valor en un [privada](../../../visual-basic/language-reference/modifiers/private.md) variable declarada en el mismo nivel que la propiedad. Debe definir un `Set` procedimiento dentro de la propiedad a la que se aplica.  
  
 El `Set` procedimiento tiene como valor predeterminado para el nivel de acceso de su propiedad contenedora a menos que use `accessmodifier` en el `Set` instrucción.  
  
## <a name="rules"></a>Reglas  
  
-   **Niveles de acceso mixtos.** Si va a definir una propiedad de lectura y escritura, opcionalmente, puede especificar un nivel de acceso diferente para el `Get` o `Set` procedimiento, pero no ambos. Si lo hace, el nivel de acceso del procedimiento debe ser más restrictivo que el nivel de acceso de la propiedad. Por ejemplo, si se declara la propiedad `Friend`, puede declarar el `Set` procedimiento `Private`, pero no `Public`.  
  
     Si está definiendo un `WriteOnly` propiedad, el `Set` procedimiento representa toda la propiedad. No se puede declarar un acceso diferente nivel `Set`, ya que establecería dos niveles de acceso para la propiedad.  
  
## <a name="behavior"></a>Comportamiento  
  
-   **Devolución desde un procedimiento de propiedad.** Cuando el `Set` procedimiento vuelve al código de llamada, la ejecución continúa después de la instrucción que proporciona el valor que se almacenará.  
  
     `Set` procedimientos de propiedad pueden devolver mediante el [instrucción Return](../../../visual-basic/language-reference/statements/return-statement.md) o [instrucción Exit](../../../visual-basic/language-reference/statements/exit-statement.md).  
  
     El `Exit Property` y `Return` instrucciones provocan una salida inmediata de un procedimiento de propiedad. Cualquier número de `Exit Property` y `Return` instrucciones pueden aparecer en cualquier lugar en el procedimiento, y puede mezclar `Exit Property` y `Return` instrucciones.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Set` instrucción para establecer el valor de una propiedad.  
  
 [!code-vb[VbVbalrStatements#55](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/set-statement_1.vb)]  
  
## <a name="see-also"></a>Vea también
- [Get (instrucción)](../../../visual-basic/language-reference/statements/get-statement.md)
- [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)
- [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Procedimientos de propiedades](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
