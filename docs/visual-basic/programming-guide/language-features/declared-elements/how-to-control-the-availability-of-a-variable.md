---
title: Procedimiento Controlar la disponibilidad de una Variable (Visual Basic)
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
ms.openlocfilehash: fb400b113e3f3305f5b724734b2bf9aa9425d03f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59311531"
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a>Procedimiento Controlar la disponibilidad de una Variable (Visual Basic)
Controlar la disponibilidad de una variable especificando su *nivel de acceso*. El nivel de acceso determina qué código tiene permiso para leer o escribir en la variable.  
  
-   *Variables de miembro* (definido en el nivel de módulo y fuera de cualquier procedimiento) predeterminado para el acceso público, lo que significa que cualquier código que pueda verlos puede tener acceso a ellos. Puede cambiar esto especificando un modificador de acceso.  
  
-   *Las variables locales* (definido dentro de un procedimiento) nominalmente tienen acceso público, aunque sólo el código dentro de su procedimiento puede tener acceso a ellos. No se puede cambiar el nivel de acceso de una variable local, pero puede cambiar el nivel de acceso del procedimiento que lo contiene.  
  
 Para obtener más información, consulte [tener acceso a los niveles en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="private-and-public-access"></a>Acceso privado y público  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a>Para hacer que una variable sea accesible únicamente desde dentro de su módulo, clase o estructura  
  
1. Colocar el [instrucción Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) para la variable dentro del módulo, clase o estructura, pero fuera de cualquier procedimiento.  
  
2. Incluir el [privada](../../../../visual-basic/language-reference/modifiers/private.md) palabra clave en el `Dim` instrucción.  
  
     Puede leer o escribir en la variable desde cualquier lugar dentro del módulo, clase o estructura, pero no desde fuera de él.  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a>Para que una variable sea accesible desde cualquier código que pueda verla  
  
1. Para una variable miembro, coloque el `Dim` instrucción para la variable dentro de un módulo, clase o estructura, pero fuera de cualquier procedimiento.  
  
2. Incluir el [pública](../../../../visual-basic/language-reference/modifiers/public.md) palabra clave en el `Dim` instrucción.  
  
     Puede leer o escribir en la variable desde cualquier código que interactúa con el ensamblado.  
  
 -o bien-  
  
1. Para una variable local, coloque el `Dim` instrucción para la variable dentro de un procedimiento.  
  
2. No incluya el `Public` palabra clave en el `Dim` instrucción.  
  
     Puede leer o escribir en la variable desde cualquier lugar dentro del procedimiento, pero no desde fuera de él.  
  
## <a name="protected-and-friend-access"></a>Protegido y el acceso de confianza  
 Puede limitar el nivel de acceso de una variable a su clase y las clases derivadas, o a su ensamblado. También puede especificar la unión de estas limitaciones, que permite el acceso desde el código en cualquier clase derivada o en cualquier otro lugar en el mismo ensamblado. Especifique esta unión combinando el `Protected` y `Friend` palabras clave en la misma declaración.  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a>Para hacer que una variable sea accesible únicamente desde dentro de su clase y cualquiera de las clases derivadas  
  
1. Colocar el `Dim` instrucción para la variable dentro de una clase, pero fuera de cualquier procedimiento.  
  
2. Incluir el [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) palabra clave en el `Dim` instrucción.  
  
     Puede leer o escribir en la variable desde cualquier lugar dentro de la clase, así como desde cualquier clase derivada de él, pero no desde fuera de cualquier clase en la cadena de derivación.  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a>Para hacer que una variable sea accesible únicamente desde dentro del mismo ensamblado  
  
1. Colocar el `Dim` instrucción para la variable dentro de un módulo, clase o estructura, pero fuera de cualquier procedimiento.  
  
2. Incluir el [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) palabra clave en el `Dim` instrucción.  
  
     Puede leer o escribir en la variable desde cualquier lugar dentro del módulo, clase o estructura, así como desde cualquier código en el mismo ensamblado, pero no desde fuera del ensamblado.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra las declaraciones de variables con `Public`, `Protected`, `Friend`, `Protected Friend`, y `Private` niveles de acceso. Tenga en cuenta que, cuando el `Dim` instrucción especifica un nivel de acceso, no es necesario incluir el `Dim` palabra clave.  
  
```  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Los permisos más restrictivos el nivel de acceso de una variable, cuantos menos las posibilidades de que código malintencionado puede hacer incorrecto usar del mismo.  
  
## <a name="see-also"></a>Vea también

- [Niveles de acceso en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Dim (instrucción)](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [Public](../../../../visual-basic/language-reference/modifiers/public.md)
- [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)
- [Private](../../../../visual-basic/language-reference/modifiers/private.md)
