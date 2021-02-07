---
description: 'Más información acerca de: Private Protected (Visual Basic)'
title: Private Protected
ms.date: 05/10/2018
f1_keywords:
- vb.PrivateProtected
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: eb521ace77cd16f4904657cbdc035575e98e98fa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700967"
---
# <a name="private-protected-visual-basic"></a>Privado protegido (Visual Basic)

La combinación de palabras claves `Private Protected` es un modificador de acceso de miembro. Un `Private Protected` miembro es accesible para todos los miembros de la clase contenedora, así como para los tipos derivados de la clase contenedora, pero solo si se encuentran en el ensamblado contenedor.

Solo se puede especificar `Private Protected` en miembros de clases; no se puede aplicar `Private Protected` a los miembros de una estructura porque las estructuras no se pueden heredar.

`Private Protected`Visual Basic 15,5 y versiones posteriores admiten el modificador de acceso. Para usarlo, puede Agregar el siguiente elemento al archivo de proyecto de Visual Basic ( \* . vbproj). Siempre que Visual Basic 15,5 o posterior esté instalado en el sistema, le permite aprovechar todas las características de lenguaje compatibles con la versión más reciente del compilador de Visual Basic:

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

Para obtener más información, vea [establecer la versión de lenguaje Visual Basic](../configure-language-version.md).

> [!NOTE]
> En Visual Studio, la selección de la ayuda F1 en `private protected` proporciona ayuda para [privado](private.md) o [protegido](protected.md). El IDE elige el token único bajo el cursor en lugar de la palabra compuesta.

## <a name="rules"></a>Reglas

- **Contexto de declaración.** Solo se puede usar `Private Protected` en el nivel de clase. Esto significa que el contexto de la declaración de un `Protected` elemento debe ser una clase y no puede ser un archivo de código fuente, un espacio de nombres, una interfaz, un módulo, una estructura o un procedimiento.

## <a name="behavior"></a>Comportamiento

- **Nivel de acceso.** Todo el código de una clase puede tener acceso a sus elementos. El código de cualquier clase que se deriva de una clase base y se encuentra en el mismo ensamblado puede tener acceso a todos los `Private Protected` elementos de la clase base. Sin embargo, el código de cualquier clase que deriva de una clase base y se encuentra en un ensamblado diferente no puede tener acceso a los elementos de la clase base `Private Protected` .

- **Modificadores de acceso.** Las palabras clave que especifican el nivel de acceso se denominan *modificadores de acceso*. Para obtener una comparación de los modificadores de acceso, vea [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

El modificador `Private Protected` se puede utilizar en los contextos siguientes:

- [Instrucción de clase](../statements/class-statement.md) de una clase anidada

- [Instrucción Const](../statements/const-statement.md)

- [Declare Statement](../statements/declare-statement.md)

- [Instrucción delegada](../statements/delegate-statement.md) de un delegado anidado en una clase

- [Instrucción Dim](../statements/dim-statement.md)

- [Instrucción enum](../statements/enum-statement.md) de una enumeración anidada en una clase

- [Event (Instrucción)](../statements/event-statement.md)

- [Instrucción Function](../statements/function-statement.md)

- [Instrucción de interfaz](../statements/interface-statement.md) de una interfaz anidada en una clase

- [Property Statement](../statements/property-statement.md)

- [Instrucción Structure](../statements/structure-statement.md) de una estructura anidada en una clase

- [Instrucción Sub](../statements/sub-statement.md)

## <a name="see-also"></a>Vea también

- [Público](public.md)
- [Protegido](protected.md)
- [Friend](friend.md)
- [Privado](private.md)
- [Protected Friend](./protected-friend.md)
- [Niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Procedimientos](../../programming-guide/language-features/procedures/index.md)
- [Estructuras](../../programming-guide/language-features/data-types/structures.md)
- [Objetos y clases](../../programming-guide/language-features/objects-and-classes/index.md)
