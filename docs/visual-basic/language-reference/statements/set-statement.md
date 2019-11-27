---
title: Set (Instrucción)
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
ms.openlocfilehash: 75ad6d87f1785fea13a282d953f117c9c234e203
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349569"
---
# <a name="set-statement-visual-basic"></a>Instrucción Set (Visual Basic)
Declara un procedimiento de propiedad `Set` que se usa para asignar un valor a una propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a>Elementos  
 `attributelist`  
 Opcional. Vea [lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `accessmodifier`  
 Opcional en, como máximo, una de las instrucciones `Get` y `Set` de esta propiedad. Puede ser uno de los siguientes:  
  
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
- [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
- `Protected Friend`  
  
 Vea [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `value`  
 Obligatorio. Parámetro que contiene el nuevo valor para la propiedad.  
  
 `datatype`  
 Es obligatorio si se `On``Option Strict`. Tipo de datos del parámetro `value`. El tipo de datos especificado debe ser el mismo que el del tipo de datos de la propiedad donde se declara esta instrucción `Set`.  
  
 `statements`  
 Opcional. Una o varias instrucciones que se ejecutan cuando se llama al procedimiento de propiedad `Set`.  
  
 `End Set`  
 Obligatorio. Finaliza la definición del procedimiento de propiedad `Set`.  
  
## <a name="remarks"></a>Comentarios  
 Cada propiedad debe tener un procedimiento de propiedad `Set` a menos que la propiedad esté marcada `ReadOnly`. El procedimiento `Set` se utiliza para establecer el valor de la propiedad.  
  
 Visual Basic llama automáticamente al procedimiento `Set` de una propiedad cuando una instrucción de asignación proporciona un valor que se va a almacenar en la propiedad.  
  
 Visual Basic pasa un parámetro al procedimiento `Set` durante las asignaciones de propiedades. Si no proporciona un parámetro para `Set`, el entorno de desarrollo integrado (IDE) utiliza un parámetro implícito denominado `value`. El parámetro contiene el valor que se va a asignar a la propiedad. Normalmente, este valor se almacena en una variable local privada y se devuelve cada vez que se llama al procedimiento `Get`.  
  
 El cuerpo de la declaración de propiedad solo puede contener los procedimientos `Get` y `Set` de la propiedad entre la [instrucción Property](../../../visual-basic/language-reference/statements/property-statement.md) y la instrucción `End Property`. No puede almacenar nada que no sea esos procedimientos. En concreto, no puede almacenar el valor actual de la propiedad. Debe almacenar este valor fuera de la propiedad, porque si lo almacena dentro de cualquiera de los procedimientos de propiedad, el otro procedimiento de propiedad no podrá tener acceso a él. El enfoque habitual es almacenar el valor en una variable [privada](../../../visual-basic/language-reference/modifiers/private.md) declarada en el mismo nivel que la propiedad. Debe definir un procedimiento de `Set` dentro de la propiedad a la que se aplica.  
  
 El procedimiento `Set` toma como valor predeterminado el nivel de acceso de la propiedad que lo contiene a menos que use `accessmodifier` en la instrucción `Set`.  
  
## <a name="rules"></a>Reglas  
  
- **Niveles de acceso mixtos.** Si va a definir una propiedad de lectura y escritura, puede especificar opcionalmente un nivel de acceso diferente para el `Get` o el procedimiento de `Set`, pero no ambos. Si lo hace, el nivel de acceso del procedimiento debe ser más restrictivo que el nivel de acceso de la propiedad. Por ejemplo, si la propiedad se declara `Friend`, puede declarar el `Set` procedimiento `Private`, pero no `Public`.  
  
     Si va a definir una propiedad `WriteOnly`, el procedimiento `Set` representa la propiedad completa. No se puede declarar un nivel de acceso diferente para `Set`, porque esto establecería dos niveles de acceso para la propiedad.  
  
## <a name="behavior"></a>Comportamiento  
  
- **Devolver desde un procedimiento de propiedad.** Cuando el procedimiento `Set` devuelve al código de llamada, la ejecución continúa después de la instrucción que proporcionó el valor que se va a almacenar.  
  
     `Set` procedimientos de propiedad pueden devolver mediante la [instrucción return](../../../visual-basic/language-reference/statements/return-statement.md) o la [instrucción Exit](../../../visual-basic/language-reference/statements/exit-statement.md).  
  
     Las instrucciones `Exit Property` y `Return` producen una salida inmediata de un procedimiento de propiedad. Cualquier número de instrucciones `Exit Property` y `Return` puede aparecer en cualquier parte del procedimiento y se pueden mezclar instrucciones `Exit Property` y `Return`.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa la instrucción `Set` para establecer el valor de una propiedad.  
  
 [!code-vb[VbVbalrStatements#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#55)]  
  
## <a name="see-also"></a>Vea también

- [Get (instrucción)](../../../visual-basic/language-reference/statements/get-statement.md)
- [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)
- [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Procedimientos de propiedades](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
