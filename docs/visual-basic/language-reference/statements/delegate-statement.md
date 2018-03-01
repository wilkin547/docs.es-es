---
title: "Delegate (Instrucción)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Delegate
helpviewer_keywords:
- delegate keyword [Visual Basic]
- Delegate statement [Visual Basic]
ms.assetid: f799c518-0817-40cc-ad0b-4da846fdba57
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7e79a261f74cbc7aa067af63629e31bedf65d163
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="delegate-statement"></a>Delegate (Instrucción)
Se utiliza para declarar a un delegado. Un delegado es un tipo de referencia que hace referencia a un `Shared` método de un tipo o a un método de instancia de un objeto. Cualquier procedimiento con la coincidencia de parámetros y tipos devueltos puede usarse para crear una instancia de esta clase de delegado. Puede llamar al procedimiento por medio de la instancia del delegado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[ <attrlist> ] [ accessmodifier ] _  
[ Shadows ] Delegate [ Sub | Function ] name [( Of typeparamlist )] [([ parameterlist ])] [ As type ]  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`attrlist`|Opcional. Lista de atributos que se aplican a este delegado. Los diversos atributos se separan con comas. Debe incluir el [lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md) corchetes angulares ("`<`"y"`>`").|  
|`accessmodifier`|Opcional. Especifica qué código puede tener acceso al delegado. Puede ser uno de los siguientes:<br /><br /> -   [Pública](../../../visual-basic/language-reference/modifiers/public.md). Cualquier código que puede tener acceso al elemento que se declara al delegado puede tener acceso a él.<br />-   [Protegido](../../../visual-basic/language-reference/modifiers/protected.md). Solo el código de la clase del delegado o una clase derivada puede tener acceso a él.<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md). Sólo el código dentro del mismo ensamblado puede tener acceso al delegado.<br />-   [Privada](../../../visual-basic/language-reference/modifiers/private.md). Sólo el código dentro del elemento que se declara al delegado puede tener acceso a él.<br /><br /> Puede especificar `Protected Friend` para habilitar el acceso desde el código dentro de la clase del delegado, una clase derivada o el mismo ensamblado.|  
|`Shadows`|Opcional. Indica que este delegado vuelve a declarar y oculta un elemento de programación denominado de forma idéntica, o un conjunto de elementos sobrecargados, en una clase base. Puede reemplazar cualquier tipo de elemento declarado con cualquier otro tipo.<br /><br /> Un elemento reemplazado no está disponible desde la clase derivada que lo reemplaza, excepto desde donde el elemento reemplazado es inaccesible. Por ejemplo, si un `Private` elemento sombrea un elemento de clase base, el código que no tiene permiso para tener acceso a la `Private` elemento accede al elemento de clase base en su lugar.|  
|`Sub`|Opcional, pero cualquiera `Sub` o `Function` deben aparecer. Declara este procedimiento como un delegado `Sub` procedimiento que no devuelve un valor.|  
|`Function`|Opcional, pero cualquiera `Sub` o `Function` deben aparecer. Declara este procedimiento como un delegado `Function` procedimiento que devuelve un valor.|  
|`name`|Obligatorio. Nombre del tipo de delegado; sigue las convenciones estándar de nomenclaturas de variables.|  
|`typeparamlist`|Opcional. Lista de parámetros de tipo para este delegado. Varios parámetros de tipo están separados por comas. Opcionalmente, cada parámetro de tipo puede declararse variante mediante `In` y `Out` modificadores genéricos. Debe incluir el [lista tipo](../../../visual-basic/language-reference/statements/type-list.md) entre paréntesis y se presentan con el `Of` palabra clave.|  
|`parameterlist`|Opcional. Lista de parámetros que se pasan al procedimiento cuando se llama. Debe incluir el [lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md) entre paréntesis.|  
|`type`|Resulta necesario si se especifica un `Function` procedimiento. Tipo de datos del valor devuelto.|  
  
## <a name="remarks"></a>Comentarios  
 El `Delegate` instrucción define los tipos de parámetro y valor devuelto de una clase de delegado. Cualquier procedimiento con parámetros y tipos devueltos coincidentes puede usarse para crear una instancia de esta clase de delegado. El procedimiento más adelante puede invocar por medio de la instancia del delegado, mediante una llamada del delegado `Invoke` método.  
  
 Los delegados se pueden declarar en el espacio de nombres, módulo, clase o estructura, pero no dentro de un procedimiento.  
  
 Cada clase delegada define un constructor que se pasa la especificación de un método de objeto. Un argumento para un constructor delegado debe ser una referencia a un método o una expresión lambda.  
  
 Para especificar una referencia a un método, utilice la siguiente sintaxis:  
  
 `AddressOf` [`expression`.]`methodname`  
  
 El tipo de tiempo de compilación de `expression` debe ser el nombre de una clase o una interfaz que contiene un método del nombre especificado cuya firma coincida con la firma de la clase delegada. `methodname` puede ser un método compartido o un método de instancia. `methodname` no es opcional, incluso si se crea un delegado para el método predeterminado de la clase.  
  
 Para especificar una expresión lambda, utilice la siguiente sintaxis:  
  
 `Function` ([`parm` As `type`, `parm2` As `type2`, ...]) `expression`  
  
 La firma de la función debe coincidir con la del tipo de delegado. Para obtener más información sobre las expresiones lambda, vea [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 Para obtener más información sobre los delegados, vea [delegados](../../../visual-basic/programming-guide/language-features/delegates/index.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Delegate` instrucción para declarar un delegado para operar en dos números y devuelve un número. El `DelegateTest` método toma una instancia de un delegado de este tipo y lo utiliza para operar en pares de números.  
  
 [!code-vb[VbVbalrDelegates#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/delegate-statement_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [AddressOf (operador)](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)  
 [Delegados](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Utilizar una clase genérica](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [Tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Covarianza y contravarianza](../../programming-guide/concepts/covariance-contravariance/index.md)  
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)  
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
