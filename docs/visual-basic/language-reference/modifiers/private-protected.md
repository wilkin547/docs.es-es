---
title: Privado protegido (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: fea43558ac0fe8181f2786b69f2621346d446b2e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57376395"
---
# <a name="private-protected-visual-basic"></a>Privado protegido (Visual Basic)

La combinación de palabras claves `Private Protected` es un modificador de acceso de miembro. Un `Private Protected` miembro es accesible por todos los miembros de su clase contenedora, así como tipos derivados de la clase contenedora, pero solo si están presentes en el ensamblado que lo contiene.

Puede especificar `Private Protected` solo en los miembros de clases; no se puede aplicar `Private Protected` a los miembros de una estructura porque las estructuras no se puede heredar.

El `Private Protected` modificador de acceso es compatible con Visual Basic 15.5 y versiones posteriores. Para ello, puede agregar el elemento siguiente a su proyecto de Visual Basic (\*.vbproj) archivo. Siempre que Visual Basic 15.5 o posterior esté instalado en el sistema, le permite aprovechar todas las características del lenguaje compatible con la versión más reciente del compilador de Visual Basic:

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

Para obtener más información, consulte [configuración de la versión de idioma de Visual Basic](../../language-reference/configure-language-version.md).

> [!NOTE]
> En Visual Studio, seleccione Ayuda de F1 en `private protected` proporciona ayuda para cualquiera [privada](private.md) o [protegido](protected.md). El IDE elige el token solo bajo el cursor en lugar de la palabra compuesta.

## <a name="rules"></a>Reglas

- **Contexto de declaración.** Puede usar `Private Protected` sólo en el nivel de clase. Esto significa que el contexto de declaración de un `Protected` elemento debe ser una clase y no puede ser un archivo de código fuente, espacio de nombres, interfaz, módulo, estructura o procedimiento.

## <a name="behavior"></a>Comportamiento

- **Nivel de acceso.** Todo el código en una clase puede tener acceso a sus elementos. Código de cualquier clase que deriva de una clase base y se encuentra en el mismo ensamblado puede tener acceso a todas las `Private Protected` elementos de la clase base. Sin embargo, el código en cualquier clase que deriva de una clase base y se encuentra en un ensamblado diferente no puede acceder a la clase base `Private Protected` elementos.

- **Modificadores de acceso.** Las palabras clave que especifican el nivel de acceso se denominan *modificadores de acceso*. Para obtener una comparación de los modificadores de acceso, consulte [tener acceso a los niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

El modificador `Private Protected` se puede utilizar en los contextos siguientes:

- [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md) de una clase anidada

- [Const (instrucción)](../../../visual-basic/language-reference/statements/const-statement.md)

- [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)

- [Delegate (instrucción)](../../../visual-basic/language-reference/statements/delegate-statement.md) de un delegado anidado en una clase

- [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)

- [Enum (instrucción)](../../../visual-basic/language-reference/statements/enum-statement.md) de una enumeración anidada en una clase

- [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)

- [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)

- [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md) de una interfaz anidada en una clase

- [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)

- [Estructura de la instrucción](../../../visual-basic/language-reference/statements/structure-statement.md) de una estructura anidada en una clase

- [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a>Vea también

- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](friend.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Protected Friend](./protected-friend.md)
- [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
