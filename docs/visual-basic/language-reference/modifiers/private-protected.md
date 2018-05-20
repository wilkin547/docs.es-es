---
title: Privado protegido (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 23fd6583182a1fee544d0458dc3fc390aed86b9f
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2018
---
# <a name="private-protected-visual-basic"></a>Privado protegido (Visual Basic)

El `Private Protected` combinación de palabra clave es un modificador de acceso de miembro. Un `Private Protected` miembro es accesible por todos los miembros de su clase contenedora, así como con tipos derivados de la clase contenedora, pero solo si se encuentran en el ensamblado que lo contiene. 

Puede especificar `Private Protected` sólo en los miembros de clases; no se puede aplicar `Private Protected` a los miembros de una estructura porque las estructuras no puede heredarse.

El `Private Protected` modificador de acceso es compatible con Visual Basic 15,5 y versiones posteriores. Para usarlo, puede agregar el elemento siguiente en el archivo de proyecto (*.vbproj) de Visual Basic. Como siempre que 15,5 de Visual Basic o una versión posterior está instalado en el sistema, le permite aprovechar todas las características de lenguaje compatible con la última versión del compilador de Visual Basic:

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> En Visual Studio, seleccione Ayuda de F1 en `private protected` proporciona ayuda para cualquiera [privada](private.md) o [protegido](protected.md). El IDE elige el token único en el cursor en lugar de la palabra compuesta.

## <a name="rules"></a>Reglas

- **Contexto de la declaración.** Puede usar `Private Protected` en el nivel de clase. Esto significa que el contexto de la declaración de un `Protected` elemento debe ser una clase y no puede ser un archivo de código fuente, espacio de nombres, interfaz, módulo, estructura o procedimiento.

## <a name="behavior"></a>Comportamiento

- **Nivel de acceso.** Todo el código en una clase puede tener acceso a sus elementos. Código de cualquier clase que deriva de una clase base y se encuentra en el mismo ensamblado puede tener acceso a toda la `Private Protected` elementos de la clase base. Sin embargo, el código de cualquier clase que deriva de una clase base y se encuentra en un ensamblado diferente no puede tener acceso a la clase base `Private Protected` elementos.

- **Modificadores de acceso.** Las palabras clave que especifican el nivel de acceso se denominan *los modificadores de acceso*. Para obtener una comparación de los modificadores de acceso, consulte [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).
  
 El modificador `Private Protected` se puede utilizar en los contextos siguientes:  
  
 [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md) de una clase anidada  
  
 [Const (instrucción)](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Delegate (instrucción)](../../../visual-basic/language-reference/statements/delegate-statement.md) de un delegado anidada en una clase  
  
 [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Enum (instrucción)](../../../visual-basic/language-reference/statements/enum-statement.md) de un eumeration anidados en una clase 
  
 [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md) de una interfaz anidada en una clase 
  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Instrucción de la estructura](../../../visual-basic/language-reference/statements/structure-statement.md) de una estructura anidada en una clase 
  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vea también

[Public](../../../visual-basic/language-reference/modifiers/public.md)  
[Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
[Friend](friend.md)   
[Private](../../../visual-basic/language-reference/modifiers/private.md)  
[Protected Friend](./protected-friend.md)   
[Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
[Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
[Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
[Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
