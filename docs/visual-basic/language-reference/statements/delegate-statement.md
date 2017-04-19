---
title: "Delegate (instrucción) | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Delegate
dev_langs:
- VB
helpviewer_keywords:
- delegate keyword
- Delegate statement
ms.assetid: f799c518-0817-40cc-ad0b-4da846fdba57
caps.latest.revision: 27
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
ms.openlocfilehash: 9ac9e28c82f8a6b5a9c1398961d831c956a649e0
ms.lasthandoff: 03/13/2017

---
# <a name="delegate-statement"></a>Delegate (Instrucción)
Se utiliza para declarar a un delegado. Un delegado es un tipo de referencia que hace referencia a un `Shared` método de un tipo o a un método de instancia de un objeto. Cualquier procedimiento con parámetros y tipos devueltos de coincidencia puede utilizarse para crear una instancia de esta clase de delegado. Puede llamar al procedimiento mediante la instancia de delegado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[ <attrlist> ] [ accessmodifier ] _  
[ Shadows ] Delegate [ Sub | Function ] name [( Of typeparamlist )] [([ parameterlist ])] [ As type ]  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`attrlist`|Opcional. Lista de atributos que se aplican a este delegado. Los diversos atributos se separan con comas. Debe incluir el [lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md) en corchetes angulares ("`<`"y"`>`").|  
|`accessmodifier`|Opcional. Especifica qué código puede tener acceso al delegado. Puede ser uno de los siguientes:<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md). Cualquier código que puede tener acceso al elemento que declara al delegado puede tener acceso a él.<br />-   [Protegido](../../../visual-basic/language-reference/modifiers/protected.md). Sólo el código de la clase del delegado o una clase derivada puede tener acceso a él.<br />-   [Amigo](../../../visual-basic/language-reference/modifiers/friend.md). Sólo el código dentro del mismo ensamblado puede tener acceso al delegado.<br />-   [Privada](../../../visual-basic/language-reference/modifiers/private.md). Sólo el código dentro del elemento que declara al delegado puede tener acceso a él.<br /><br /> Puede especificar `Protected Friend` para habilitar el acceso desde el código dentro del mismo ensamblado, una clase derivada o la clase del delegado.|  
|`Shadows`|Opcional. Indica que este delegado vuelve a declarar y oculta un elemento de programación denominado de forma idéntica, o un conjunto de elementos sobrecargados, en una clase base. Puede reemplazar cualquier tipo de elemento declarado con cualquier otro tipo.<br /><br /> Un elemento reemplazado no está disponible desde la clase derivada que lo reemplaza, excepto desde donde el elemento reemplazado es inaccesible. Por ejemplo, si un `Private` elemento sombrea un elemento de clase base, el código que no tiene permiso para tener acceso a la `Private` elemento tiene acceso al elemento de clase base en su lugar.|  
|`Sub`|Opcional, pero bien `Sub` o `Function` deben aparecer. Declara este procedimiento como un delegado `Sub` procedimiento que no devuelve un valor.|  
|`Function`|Opcional, pero bien `Sub` o `Function` deben aparecer. Declara este procedimiento como un delegado `Function` procedimiento que devuelve un valor.|  
|`name`|Obligatorio. Nombre del tipo delegado. sigue las convenciones de nomenclatura estándares.|  
|`typeparamlist`|Opcional. Lista de parámetros de tipo para este delegado. Varios parámetros de tipo están separados por comas. Opcionalmente, cada parámetro de tipo puede declararse variante mediante `In` y `Out` modificadores genéricos. Debe incluir el [lista tipo](../../../visual-basic/language-reference/statements/type-list.md) entre paréntesis y anteponer con el `Of` (palabra clave).|  
|`parameterlist`|Opcional. Lista de parámetros que se pasan al procedimiento cuando se llama. Debe incluir el [lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md) entre paréntesis.|  
|`type`|Es obligatorio si especifica un `Function` procedimiento. Tipo de datos del valor devuelto.|  
  
## <a name="remarks"></a>Comentarios  
 El `Delegate` instrucción define los tipos de parámetro y valor devuelto de una clase de delegado. Cualquier procedimiento con parámetros de coincidencia y tipos de valor devuelto puede utilizarse para crear una instancia de esta clase de delegado. El procedimiento más adelante puede invocar por medio de la instancia de delegado, llamando al delegado `Invoke` método.  
  
 Los delegados se pueden declarar en el espacio de nombres, módulo, clase o estructura, pero no dentro de un procedimiento.  
  
 Cada clase delegada define un constructor que se pasa la especificación de un método de objeto. Un argumento para un constructor delegado debe ser una referencia a un método o una expresión lambda.  
  
 Para especificar una referencia a un método, utilice la siguiente sintaxis:  
  
 `AddressOf` [`expression`.]`methodname`  
  
 El tipo de tiempo de compilación de la `expression` debe ser el nombre de una clase o interfaz que contiene un método del nombre especificado cuya firma coincida con la firma de la clase de delegado. La `methodname` puede ser un método compartido o un método de instancia. El `methodname` no es opcional, incluso si se crea un delegado para el método predeterminado de la clase.  
  
 Para especificar una expresión lambda, utilice la siguiente sintaxis:  
  
 `Function`([`parm` As `type`, `parm2` As `type2`, ...])`expression`  
  
 La firma de la función debe coincidir con la del tipo de delegado. Para obtener más información sobre las expresiones lambda, vea [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 Para obtener más información sobre los delegados, vea [delegados](../../../visual-basic/programming-guide/language-features/delegates/index.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Delegate` instrucción para declarar un delegado para operar con dos números y devuelve un número. El `DelegateTest` método toma una instancia de un delegado de este tipo y se utiliza para operar en los pares de números.  
  
 [!code-vb[VbVbalrDelegates&#14;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/delegate-statement_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [AddressOf (operador)](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)   
 [Delegados](../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [Cómo: utilizar una clase genérica](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)   
 [Tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Covarianza y contravarianza](http://msdn.microsoft.com/library/a58cc086-276f-4f91-a366-85b7f95f38b8)   
 [En](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)   
 [Horizontal](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
