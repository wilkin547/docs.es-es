---
title: "Delegate (Instrucci&#243;n) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Delegate"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "delegate (palabra clave)"
  - "Delegate (instrucción)"
ms.assetid: f799c518-0817-40cc-ad0b-4da846fdba57
caps.latest.revision: 27
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 27
---
# Delegate (Instrucci&#243;n)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Se utiliza para declarar un delegado.  Un delegado es un tipo de referencia que se establece para un método `Shared` de un tipo o para un método de instancia de un objeto.  Se puede usar cualquier procedimiento con parámetro de coincidencia y tipos devueltos para crear una instancia de esta clase delegada.  Se puede llamar al procedimiento por medio de la instancia de delegado.  
  
## Sintaxis  
  
```  
[ <attrlist> ] [ accessmodifier ] _  
[ Shadows ] Delegate [ Sub | Function ] name [( Of typeparamlist )] [([ parameterlist ])] [ As type ]  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`attrlist`|Opcional.  Lista de atributos que se aplican a este delegado.  Los atributos múltiples se separan por comas.  Debe incluir [Lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md) entre corchetes angulares \("`<`" y "`>`"\).|  
|`accessmodifier`|Opcional.  Especifica qué código puede tener acceso al delegado.  Puede ser una de las siguientes:<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md) Cualquier código que puede tener acceso al elemento que declara el delegado.<br />-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md) Sólo el código de la clase del delegado o de una clase derivada.<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md) Sólo el código incluido en el mismo ensamblado.<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md) Sólo el código incluido en el elemento que declara el delegado.<br /><br /> Puede especificar `Protected Friend` para habilitar el acceso desde el código incluido en la clase delegada, en una clase derivada o en el mismo ensamblado.|  
|`Shadows`|Opcional.  Indica que este delegado vuelve a declarar y ocultar un elemento de programación con el mismo nombre, o un conjunto de elementos sobrecargados, en una clase base.  Puede hacer que cualquier tipo de elemento declarado prevalezca sobre cualquier otro tipo.<br /><br /> Un elemento sombreado no está disponible desde la clase derivada que lo sombrea, a menos que el elemento que produce el sombreado no esté accesible.  Por ejemplo, si un elemento `Private` sombrea un elemento de clase base, el código que no tiene el permiso para obtener acceso al elemento `Private` obtiene acceso al elemento de clase base.|  
|`Sub`|Opcional, pero debe aparecer `Sub` o `Function`.  Declara este procedimiento como un procedimiento `Sub` delegado que no devuelve ningún valor.|  
|`Function`|Opcional, pero debe aparecer `Sub` o `Function`.  Declara este procedimiento como un procedimiento `Function` delegado que devuelve un valor.|  
|`name`|Obligatorio.  Nombre del tipo delegado. Sigue las convenciones de nomenclatura estándar de las variables.|  
|`typeparamlist`|Opcional.  Lista de parámetros de tipo de este delegado.  Los parámetros de tipo están separados por comas.  Opcionalmente, cada parámetro de tipo se puede declarar como variant utilizando los modificadores genéricos `In` y `Out`.  Debe incluir la lista [Lista de tipos](../../../visual-basic/language-reference/statements/type-list.md) entre paréntesis y anteponer la palabra clave `Of`.|  
|`parameterlist`|Opcional.  Lista de parámetros que se transfieren al procedimiento cuando se llama.  Debe incluir la lista [Lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md) entre paréntesis.|  
|`type`|Obligatorio si se especifica un procedimiento `Function`.  Tipo de datos del valor devuelto.|  
  
## Comentarios  
 La instrucción `Delegate` define el parámetro y los tipos devueltos de una clase delegada.  Se puede usar cualquier procedimiento con tipos de parámetros de coincidencia y tipos de valor devuelto para crear una instancia de esta clase delegada.  Se puede llamar al procedimiento mediante la instancia de delegado, llamando al método `Invoke` del delegado.  
  
 Los delegados se pueden declarar en el nivel de espacio de nombres, módulo, clase o estructura, pero no en un procedimiento.  
  
 Cada clase delegada define un constructor al cual se pasa la especificación de un método de objeto.  Un argumento para un constructor delegado debe ser una referencia a un método o una expresión lambda.  
  
 Para especificar una referencia a un método, utilice la sintaxis siguiente:  
  
 `AddressOf` \[`expression`.\]`methodname`  
  
 El tipo de tiempo de compilación de `expression` debe ser el nombre de una clase o interfaz que contenga un método del nombre especificado cuya firma coincida con la firma de la clase delegada.  `methodname` puede ser un método compartido o un método de instancia.  Aunque se cree un delegado para el método predeterminado de la clase, `methodname` no es opcional.  
  
 Para especificar una expresión lambda, utilice la sintaxis siguiente:  
  
 `Function` \(\[`parm` como `type`, `parm2` como `type2`, ...\]\) `expression`  
  
 La firma de la función debe coincidir con la del tipo de delegado.  Para obtener más información sobre las expresiones lambda, vea [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 Para obtener más información acerca de delegados, vea [Delegados](../../../visual-basic/programming-guide/language-features/delegates/delegates.md).  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza la instrucción `Delegate` para declarar un delegado que opere con dos números y devuelva un número.  El método `DelegateTest` toma una instancia de un delegado de este tipo y la utiliza para ordenar los números en pares.  
  
 [!code-vb[VbVbalrDelegates#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/delegate-statement_1.vb)]  
  
## Vea también  
 [AddressOf \(Operador\)](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)   
 [Delegados](../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [Cómo: Utilizar una clase genérica](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)   
 [Tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Covarianza y contravarianza](../Topic/Covariance%20and%20Contravariance%20\(C%23%20and%20Visual%20Basic\).md)   
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)   
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)