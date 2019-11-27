---
title: Private Protected
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 265141f77f4a61a61414a07214830feaa8a1ab05
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351339"
---
# <a name="private-protected-visual-basic"></a>Privado protegido (Visual Basic)

La combinación de palabras claves `Private Protected` es un modificador de acceso de miembro. Un miembro de `Private Protected` es accesible para todos los miembros de la clase contenedora, así como para los tipos derivados de la clase contenedora, pero solo si se encuentran en el ensamblado que lo contiene.

Solo puede especificar `Private Protected` en miembros de clases; no se puede aplicar `Private Protected` a los miembros de una estructura porque las estructuras no se pueden heredar.

Visual Basic 15,5 y versiones posteriores admiten el modificador de acceso `Private Protected`. Para usarlo, puede Agregar el siguiente elemento al archivo de proyecto de Visual Basic (\*. vbproj). Siempre que Visual Basic 15,5 o posterior esté instalado en el sistema, le permite aprovechar todas las características de lenguaje compatibles con la versión más reciente del compilador de Visual Basic:

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

Para obtener más información, vea [establecer la versión de lenguaje Visual Basic](../../language-reference/configure-language-version.md).

> [!NOTE]
> En Visual Studio, al seleccionar la ayuda F1 en `private protected` se proporciona ayuda para [privado](private.md) o [protegido](protected.md). El IDE elige el token único bajo el cursor en lugar de la palabra compuesta.

## <a name="rules"></a>Reglas

- **Contexto de declaración.** Solo se puede usar `Private Protected` en el nivel de clase. Esto significa que el contexto de la declaración de un elemento `Protected` debe ser una clase y no puede ser un archivo de código fuente, un espacio de nombres, una interfaz, un módulo, una estructura o un procedimiento.

## <a name="behavior"></a>Comportamiento

- **Nivel de acceso.** Todo el código de una clase puede tener acceso a sus elementos. El código de cualquier clase que se deriva de una clase base y se encuentra en el mismo ensamblado puede tener acceso a todos los elementos `Private Protected` de la clase base. Sin embargo, el código de cualquier clase que deriva de una clase base y se encuentra en un ensamblado diferente no puede tener acceso a la clase base `Private Protected` elementos.

- **Modificadores de acceso.** Las palabras clave que especifican el nivel de acceso se denominan *modificadores de acceso*. Para obtener una comparación de los modificadores de acceso, vea [niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

El modificador `Private Protected` se puede utilizar en los contextos siguientes:

- [Instrucción de clase](../../../visual-basic/language-reference/statements/class-statement.md) de una clase anidada

- [Const (instrucción)](../../../visual-basic/language-reference/statements/const-statement.md)

- [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)

- [Instrucción delegada](../../../visual-basic/language-reference/statements/delegate-statement.md) de un delegado anidado en una clase

- [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)

- [Instrucción enum](../../../visual-basic/language-reference/statements/enum-statement.md) de una enumeración anidada en una clase

- [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)

- [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)

- [Instrucción de interfaz](../../../visual-basic/language-reference/statements/interface-statement.md) de una interfaz anidada en una clase

- [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)

- [Instrucción Structure](../../../visual-basic/language-reference/statements/structure-statement.md) de una estructura anidada en una clase

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
