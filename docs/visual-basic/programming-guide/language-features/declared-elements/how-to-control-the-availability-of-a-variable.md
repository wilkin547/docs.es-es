---
title: Procedimiento para controlar la disponibilidad de una variable
ms.date: 07/20/2015
helpviewer_keywords:
- access levels, declared elements
- Private keyword [Visual Basic], accessing variables
- access levels, variables
- Public keyword [Visual Basic], accessing variables
- Friend keyword [Visual Basic], accessing variables
- variables [Visual Basic], access level
- declared elements [Visual Basic], access level
- Protected keyword [Visual Basic], accessing variables
ms.assetid: eaf4f073-7922-43ce-ae1e-90ff376ae947
ms.openlocfilehash: e6173a0eaa0bf84abb1979711c6df932533c5ce9
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91086119"
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a>Cómo: Controlar la disponibilidad de una variable (Visual Basic)

Puede controlar la disponibilidad de una variable especificando su *nivel de acceso*. El nivel de acceso determina qué código tiene permiso para leer o escribir en la variable.  
  
- *Las variables de miembro* (definidas en el nivel de módulo y fuera de cualquier procedimiento) tienen como valor predeterminado el acceso público, lo que significa que cualquier código que pueda verlas puede tener acceso a ellas. Puede cambiar esto especificando un modificador de acceso.  
  
- *Las variables locales* (definidas dentro de un procedimiento) tienen un acceso público nominal, aunque solo el código de su procedimiento puede tener acceso a ellas. No se puede cambiar el nivel de acceso de una variable local, pero se puede cambiar el nivel de acceso del procedimiento que lo contiene.  
  
 Para obtener más información, consulte [niveles de acceso en Visual Basic](access-levels.md).  
  
## <a name="private-and-public-access"></a>Acceso privado y público  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a>Para hacer que una variable sea accesible solo desde dentro de su módulo, clase o estructura  
  
1. Coloque la [instrucción Dim](../../../language-reference/statements/dim-statement.md) para la variable dentro del módulo, la clase o la estructura, pero fuera de cualquier procedimiento.  
  
2. Incluya la palabra clave [Private](../../../language-reference/modifiers/private.md) en la `Dim` instrucción.  
  
     Puede leer o escribir en la variable desde cualquier lugar dentro del módulo, clase o estructura, pero no desde fuera de ella.  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a>Para hacer que una variable sea accesible desde cualquier código que pueda verla  
  
1. En el caso de una variable miembro, coloque la `Dim` instrucción para la variable dentro de un módulo, clase o estructura, pero fuera de cualquier procedimiento.  
  
2. Incluya la palabra clave [Public](../../../language-reference/modifiers/public.md) en la `Dim` instrucción.  
  
     Puede leer o escribir en la variable desde cualquier código que interopere con el ensamblado.  
  
 o bien  
  
1. En el caso de una variable local, coloque la `Dim` instrucción para la variable dentro de un procedimiento.  
  
2. No incluya la `Public` palabra clave en la `Dim` instrucción.  
  
     Puede leer o escribir en la variable desde cualquier lugar dentro del procedimiento, pero no desde fuera de ella.  
  
## <a name="protected-and-friend-access"></a>Acceso protegido y de confianza  

 Puede limitar el nivel de acceso de una variable a su clase y las clases derivadas, o a su ensamblado. También puede especificar la Unión de estas limitaciones, lo que permite el acceso desde el código de cualquier clase derivada o en cualquier otro lugar del mismo ensamblado. Esta Unión se especifica combinando las `Protected` `Friend` palabras clave y en la misma declaración.  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a>Para hacer que una variable sea accesible solo desde dentro de su clase y las clases derivadas  
  
1. Coloque la `Dim` instrucción para la variable dentro de una clase, pero fuera de cualquier procedimiento.  
  
2. Incluya la palabra clave [Protected](../../../language-reference/modifiers/protected.md) en la `Dim` instrucción.  
  
     Puede leer o escribir en la variable desde cualquier parte dentro de la clase, así como desde cualquier clase derivada de ella, pero no desde fuera de cualquier clase de la cadena de derivación.  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a>Para hacer que una variable sea accesible solo desde dentro del mismo ensamblado  
  
1. Coloque la `Dim` instrucción para la variable dentro de un módulo, clase o estructura, pero fuera de cualquier procedimiento.  
  
2. Incluya la palabra clave [Friend](../../../language-reference/modifiers/friend.md) en la `Dim` instrucción.  
  
     Puede leer o escribir en la variable desde cualquier lugar dentro del módulo, clase o estructura, así como desde cualquier código del mismo ensamblado, pero no desde fuera del ensamblado.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestran las declaraciones de variables con `Public` `Protected` `Friend` los niveles de acceso,,, `Protected Friend` y `Private` . Tenga en cuenta que cuando la `Dim` instrucción especifica un nivel de acceso, no es necesario incluir la `Dim` palabra clave.  
  
```vb  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  

 Cuanto más restrictiva sea el nivel de acceso de una variable, menor será la probabilidad de que el código malintencionado pueda usarse de forma inadecuada.  
  
## <a name="see-also"></a>Vea también

- [Niveles de acceso en Visual Basic](access-levels.md)
- [Instrucción Dim](../../../language-reference/statements/dim-statement.md)
- [Pública](../../../language-reference/modifiers/public.md)
- [Contra](../../../language-reference/modifiers/protected.md)
- [Friend](../../../language-reference/modifiers/friend.md)
- [Privado](../../../language-reference/modifiers/private.md)
