---
description: 'Más información sobre: instrucción set (Visual Basic)'
title: Instrucción Set
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
ms.openlocfilehash: 5ee27b35a4639bc20d5b6634de8332c6ede9bf12
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741125"
---
# <a name="set-statement-visual-basic"></a>Instrucción Set (Visual Basic)

Declara un `Set` procedimiento de propiedad que se usa para asignar un valor a una propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a>Partes  

 `attributelist`  
 Opcional. Vea [lista de atributos](attribute-list.md).  
  
 `accessmodifier`  
 Opcional en, como máximo, una de las `Get` `Set` instrucciones y de esta propiedad. Puede ser uno de los siguientes:  
  
- [Protegido](../modifiers/protected.md)  
  
- [Friend](../modifiers/friend.md)  
  
- [Privado](../modifiers/private.md)  
  
- `Protected Friend`  
  
 Consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).  
  
 `value`  
 Necesario. Parámetro que contiene el nuevo valor para la propiedad.  
  
 `datatype`  
 Obligatorio si `Option Strict` es `On` . Tipo de datos del `value` parámetro. El tipo de datos especificado debe ser el mismo que el del tipo de datos de la propiedad donde `Set` se declara esta instrucción.  
  
 `statements`  
 Opcional. Una o varias instrucciones que se ejecutan cuando `Set` se llama al procedimiento de propiedad.  
  
 `End Set`  
 Necesario. Finaliza la definición del procedimiento de `Set` propiedad.  
  
## <a name="remarks"></a>Observaciones  

 Cada propiedad debe tener un `Set` procedimiento de propiedad a menos que se marque la propiedad `ReadOnly` . El `Set` procedimiento se utiliza para establecer el valor de la propiedad.  
  
 Visual Basic llama automáticamente al procedimiento de una propiedad `Set` cuando una instrucción de asignación proporciona un valor que se va a almacenar en la propiedad.  
  
 Visual Basic pasa un parámetro al `Set` procedimiento durante las asignaciones de propiedades. Si no proporciona un parámetro para `Set` , el entorno de desarrollo integrado (IDE) utiliza un parámetro implícito denominado `value` . El parámetro contiene el valor que se va a asignar a la propiedad. Normalmente, este valor se almacena en una variable local privada y se devuelve cada vez que `Get` se llama al procedimiento.  
  
 El cuerpo de la declaración de propiedad solo puede contener los procedimientos y de la propiedad `Get` `Set` entre la [instrucción Property](property-statement.md) y la `End Property` instrucción. No puede almacenar nada que no sea esos procedimientos. En concreto, no puede almacenar el valor actual de la propiedad. Debe almacenar este valor fuera de la propiedad, porque si lo almacena dentro de cualquiera de los procedimientos de propiedad, el otro procedimiento de propiedad no podrá tener acceso a él. El enfoque habitual es almacenar el valor en una variable [privada](../modifiers/private.md) declarada en el mismo nivel que la propiedad. Debe definir un `Set` procedimiento dentro de la propiedad a la que se aplica.  
  
 El `Set` procedimiento tiene como valor predeterminado el nivel de acceso de la propiedad que lo contiene a menos que use `accessmodifier` en la `Set` instrucción.  
  
## <a name="rules"></a>Reglas  
  
- **Niveles de acceso mixtos.** Si va a definir una propiedad de lectura y escritura, puede especificar opcionalmente un nivel de acceso diferente para el `Get` procedimiento o `Set` , pero no para ambos. Si lo hace, el nivel de acceso del procedimiento debe ser más restrictivo que el nivel de acceso de la propiedad. Por ejemplo, si se declara la propiedad `Friend` , puede declarar el `Set` procedimiento `Private` , pero no `Public` .  
  
     Si está definiendo una `WriteOnly` propiedad, el `Set` procedimiento representa toda la propiedad. No se puede declarar un nivel de acceso diferente para `Set` , ya que esto establecería dos niveles de acceso para la propiedad.  
  
## <a name="behavior"></a>Comportamiento  
  
- **Devolver desde un procedimiento de propiedad.** Cuando el `Set` procedimiento vuelve al código de llamada, la ejecución continúa después de la instrucción que proporcionó el valor que se va a almacenar.  
  
     `Set` los procedimientos de propiedad pueden devolver mediante la [instrucción return](return-statement.md) o la [instrucción Exit](exit-statement.md).  
  
     Las `Exit Property` `Return` instrucciones y producen una salida inmediata de un procedimiento de propiedad. Cualquier número de `Exit Property` `Return` instrucciones y puede aparecer en cualquier parte del procedimiento y se pueden mezclar `Exit Property` e `Return` instrucciones.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se usa la `Set` instrucción para establecer el valor de una propiedad.  
  
 [!code-vb[VbVbalrStatements#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#55)]  
  
## <a name="see-also"></a>Vea también

- [Get (Instrucción)](get-statement.md)
- [Property Statement](property-statement.md)
- [Instrucción Sub](sub-statement.md)
- [Procedimientos de propiedad](../../programming-guide/language-features/procedures/property-procedures.md)
