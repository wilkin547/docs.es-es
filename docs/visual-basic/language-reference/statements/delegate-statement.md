---
title: Instrucción Delegate (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Delegate
helpviewer_keywords:
- delegate keyword [Visual Basic]
- Delegate statement [Visual Basic]
ms.assetid: f799c518-0817-40cc-ad0b-4da846fdba57
ms.openlocfilehash: 4a8260da4d2224551de71fd54f734007c7fa214f
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583457"
---
# <a name="delegate-statement"></a>Delegate (Instrucción)
Se usa para declarar un delegado. Un delegado es un tipo de referencia que hace referencia a un método `Shared` de un tipo o a un método de instancia de un objeto. Cualquier procedimiento con parámetros coincidentes y tipos de valor devueltos se puede utilizar para crear una instancia de esta clase de delegado. Posteriormente, el procedimiento se puede invocar mediante la instancia del delegado.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
[ <attrlist> ] [ accessmodifier ] _  
[ Shadows ] Delegate [ Sub | Function ] name [( Of typeparamlist )] [([ parameterlist ])] [ As type ]  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|de esquema JSON|  
|---|---|  
|`attrlist`|Opcional. Lista de atributos que se aplican a este delegado. Los diversos atributos se separan con comas. Debe incluir la [lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md) entre corchetes angulares ("`<`" y "`>`").|  
|`accessmodifier`|Opcional. Especifica qué código puede tener acceso al delegado. Puede ser uno de los siguientes:<br /><br /> - [público](../../../visual-basic/language-reference/modifiers/public.md). Cualquier código que pueda tener acceso al elemento que declara el delegado puede tener acceso al mismo.<br />-   [protegido](../../../visual-basic/language-reference/modifiers/protected.md). Solo el código dentro de la clase del delegado o de una clase derivada puede tener acceso al mismo.<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md). Solo el código del mismo ensamblado puede tener acceso al delegado.<br />- [privado](../../../visual-basic/language-reference/modifiers/private.md). Solo el código dentro del elemento que declara el delegado puede tener acceso al mismo.<br /><br /> -  código solo[Friend protegido](../../language-reference/modifiers/protected-friend.md) dentro de la clase del delegado, una clase derivada o el mismo ensamblado puede tener acceso al delegado. <br />-  código[privado protegido](../../language-reference/modifiers/private-protected.md) solo dentro de la clase del delegado o en una clase derivada del mismo ensamblado puede tener acceso al delegado. |  
|`Shadows`|Opcional. Indica que este delegado vuelve a declarar y oculta un elemento de programación con el mismo nombre, o un conjunto de elementos sobrecargados, en una clase base. Puede reemplazar cualquier tipo de elemento declarado con cualquier otro tipo.<br /><br /> Un elemento reemplazado no está disponible desde la clase derivada que lo reemplaza, excepto desde donde el elemento reemplazado es inaccesible. Por ejemplo, si un elemento `Private` sombrea un elemento de clase base, el código que no tiene permiso para obtener acceso al elemento `Private` tiene acceso al elemento de clase base en su lugar.|  
|`Sub`|Opcional, pero debe aparecer `Sub` o `Function`. Declara este procedimiento como un delegado `Sub` procedimiento que no devuelve un valor.|  
|`Function`|Opcional, pero debe aparecer `Sub` o `Function`. Declara este procedimiento como un delegado `Function` procedimiento que devuelve un valor.|  
|`name`|Requerido. Nombre del tipo de delegado; sigue las convenciones de nomenclatura de variables estándar.|  
|`typeparamlist`|Opcional. Lista de parámetros de tipo para este delegado. Varios parámetros de tipo se separan mediante comas. Opcionalmente, cada parámetro de tipo se puede declarar como variante mediante el uso de `In` y `Out` modificadores genéricos. Debe incluir la [lista de tipos](../../../visual-basic/language-reference/statements/type-list.md) entre paréntesis y presentarla con la palabra clave `Of`.|  
|`parameterlist`|Opcional. Lista de parámetros que se pasan al procedimiento cuando se llama. Debe incluir la [lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md) entre paréntesis.|  
|`type`|Obligatorio si se especifica un procedimiento `Function`. Tipo de datos del valor devuelto.|  
  
## <a name="remarks"></a>Comentarios  
 La instrucción `Delegate` define el parámetro y los tipos devueltos de una clase de delegado. Cualquier procedimiento con parámetros coincidentes y tipos de valor devueltos se puede utilizar para crear una instancia de esta clase de delegado. Posteriormente, el procedimiento se puede invocar mediante la instancia de delegado, llamando al método `Invoke` del delegado.  
  
 Los delegados se pueden declarar en el nivel de espacio de nombres, módulo, clase o estructura, pero no dentro de un procedimiento.  
  
 Cada clase delegada define un constructor que se pasa la especificación de un método de objeto. Un argumento para un constructor delegado debe ser una referencia a un método o una expresión lambda.  
  
 Para especificar una referencia a un método, utilice la siguiente sintaxis:  
  
 `AddressOf` [`expression`.]`methodname`  
  
 El tipo de tiempo de compilación de `expression` debe ser el nombre de una clase o una interfaz que contiene un método del nombre especificado cuya firma coincida con la firma de la clase delegada. `methodname` puede ser un método compartido o un método de instancia. `methodname` no es opcional, incluso si se crea un delegado para el método predeterminado de la clase.  
  
 Para especificar una expresión lambda, utilice la siguiente sintaxis:  
  
 `Function` ([`parm` As `type`, `parm2` As `type2`, ...]) `expression`  
  
 La firma de la función debe coincidir con la del tipo de delegado. Para obtener más información sobre las expresiones lambda, vea [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 Para obtener más información sobre los delegados, consulte [Delegados](../../../visual-basic/programming-guide/language-features/delegates/index.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa la instrucción `Delegate` para declarar un delegado para que opere con dos números y devolver un número. El método `DelegateTest` toma una instancia de un delegado de este tipo y lo usa para operar en pares de números.  
  
 [!code-vb[VbVbalrDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>Vea también

- [AddressOf (operador)](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Of](../../../visual-basic/language-reference/statements/of-clause.md)
- [Delegados](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Utilizar una clase genérica](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Covarianza y contravarianza](../../programming-guide/concepts/covariance-contravariance/index.md)
- [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
