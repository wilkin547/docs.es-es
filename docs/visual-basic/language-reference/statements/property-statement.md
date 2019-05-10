---
title: Declaración de propiedad (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.PropertySet
- vb.Property
- vb.PropertyGet
helpviewer_keywords:
- Property statement [Visual Basic]
- default modifier
- property procedures [Visual Basic], Property statements
- Property keyword [Visual Basic]
ms.assetid: 3155edaf-8ebd-45c6-9cef-11d5d2dc8d38
ms.openlocfilehash: 55da13eec9dc555c320ecd48d22d984dfcfea84c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64751053"
---
# <a name="property-statement"></a>Property Statement

Declara el nombre de una propiedad y los procedimientos de propiedad que se utiliza para almacenar y recuperar el valor de la propiedad.

## <a name="syntax"></a>Sintaxis

```vb
[ <attributelist> ] [ Default ] [ accessmodifier ]
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ] [ Iterator ]
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]
    [ <attributelist> ] [ accessmodifier ] Get
        [ statements ]
    End Get
    [ <attributelist> ] [ accessmodifier ] Set ( ByVal value As returntype [, parameterlist ] )
        [ statements ]
    End Set
End Property
- or -
[ <attributelist> ] [ Default ] [ accessmodifier ]
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ]
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]
```

## <a name="parts"></a>Elementos

- `attributelist`

  Opcional. Lista de atributos que se aplican a esta propiedad o `Get` o `Set` procedimiento. Consulte [lista de los atributos](../../../visual-basic/language-reference/statements/attribute-list.md).

- `Default`

  Opcional. Especifica que esta propiedad es la propiedad predeterminada para la clase o estructura en el que está definida. Las propiedades predeterminadas deben aceptar parámetros y se pueden establecer y recuperar sin especificar el nombre de propiedad. Si se declara la propiedad como `Default`, no puede usar `Private` en la propiedad o en cualquiera de sus procedimientos de propiedad.

- `accessmodifier`

  Opcional en el `Property` instrucción y en al menos uno de los `Get` y `Set` instrucciones. Puede ser uno de los siguientes:

  - [Public](../../../visual-basic/language-reference/modifiers/public.md)

  - [Protected](../../../visual-basic/language-reference/modifiers/protected.md)

  - [Friend](../../../visual-basic/language-reference/modifiers/friend.md)

  - [Private](../../../visual-basic/language-reference/modifiers/private.md)

  - [Protected Friend](../../language-reference/modifiers/protected-friend.md)

  - [Private Protected](../../language-reference/modifiers/private-protected.md)

  Vea [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

- `propertymodifiers`

  Opcional. Puede ser uno de los siguientes:

  - [Sobrecargas](../../../visual-basic/language-reference/modifiers/overloads.md)

  - [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)

  - [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)

  - [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)

  - [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  Opcional. Consulte [compartido](../../../visual-basic/language-reference/modifiers/shared.md).

- `Shadows`

  Opcional. Consulte [sombras](../../../visual-basic/language-reference/modifiers/shadows.md).

- `ReadOnly`

  Opcional. Consulte [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).

- `WriteOnly`

  Opcional. Consulte [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).

- `Iterator`

  Opcional. Consulte [iterador](../../../visual-basic/language-reference/modifiers/iterator.md).

- `name`

  Obligatorio. Nombre de la propiedad. Vea [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).

- `parameterlist`

  Opcional. Lista de nombres de variable local que representa los parámetros de esta propiedad y los posibles parámetros adicionales de la `Set` procedimiento. Consulte [Lista_de_parámetros](../../../visual-basic/language-reference/statements/parameter-list.md).

- `returntype`

  Es necesario si `Option Strict` es `On`. Tipo de datos del valor devuelto por esta propiedad.

- `Implements`

  Opcional. Indica que esta propiedad implementa una o varias propiedades, cada uno definido en una interfaz implementada por la clase o estructura contenedora de esta propiedad. Consulte [implementa instrucción](../../../visual-basic/language-reference/statements/implements-statement.md).

- `implementslist`

  Es necesario si se proporciona `Implements`. Lista de propiedades que se implementan.

  `implementedproperty [ , implementedproperty ... ]`

  Cada `implementedproperty` tiene la sintaxis y las partes siguientes:

  `interface.definedname`

  |Parte|Descripción|
  |---|---|
  |`interface`|Obligatorio. Nombre de una interfaz implementada por esta propiedad contenedora de clase o estructura.|
  |`definedname`|Obligatorio. Nombre por el que se define la propiedad en `interface`.|

- `Get`

  Opcional. Necesario si la propiedad se marca `WriteOnly`. Se inicia un `Get` procedimiento de propiedad que se usa para devolver el valor de la propiedad.

- `statements`

  Opcional. Bloque de instrucciones que se ejecutan dentro de la `Get` o `Set` procedimiento.

- `End Get`

  Finaliza el `Get` procedimiento de propiedad.

- `Set`

  Opcional. Necesario si la propiedad se marca `ReadOnly`. Se inicia un `Set` procedimiento de propiedad que se usa para almacenar el valor de la propiedad.

- `End Set`

  Finaliza el `Set` procedimiento de propiedad.

- `End Property`

  Termina la definición de esta propiedad.

## <a name="remarks"></a>Comentarios

El `Property` instrucción introduce la declaración de una propiedad. Una propiedad puede tener un `Get` procedimiento (solo lectura), un `Set` procedimiento (solo escritura), o ambas (lectura y escritura). Puede omitir el `Get` y `Set` procedimiento cuando se usa una propiedad implementada automáticamente. Para obtener más información, vea [Propiedades implementadas automáticamente](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).

Puede usar `Property` sólo en el nivel de clase. Esto significa que el *contexto de declaración* para una propiedad debe ser una clase, estructura, módulo o interfaz y no puede ser un archivo de código fuente, espacio de nombres, procedimiento o bloque. Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).

De forma predeterminada, las propiedades utilizan acceso público. Puede ajustar el nivel de acceso de una propiedad con un modificador de acceso en el `Property` statement y, opcionalmente, puede ajustar uno de sus procedimientos de propiedad a un nivel de acceso más restrictivo.

Visual Basic pasa un parámetro a la `Set` procedimiento durante las asignaciones de propiedad. Si no proporciona un parámetro para `Set`, el entorno de desarrollo integrado (IDE) utiliza un parámetro implícito denominado `value`. Este parámetro contiene el valor que se asignará a la propiedad. Se suele almacenar este valor en una variable local privada y devolverlo cada vez que el `Get` se llama al procedimiento.

## <a name="rules"></a>Reglas

- **Niveles de acceso mixtos.** Si va a definir una propiedad de lectura y escritura, opcionalmente, puede especificar un nivel de acceso diferente para el `Get` o `Set` procedimiento, pero no ambos. Si lo hace, el nivel de acceso del procedimiento debe ser más restrictivo que el nivel de acceso de la propiedad. Por ejemplo, si se declara la propiedad `Friend`, puede declarar el `Set` procedimiento `Private`, pero no `Public`.

  Si está definiendo un `ReadOnly` o `WriteOnly` propiedad, el procedimiento de propiedad único (`Get` o `Set`, respectivamente) representa toda la propiedad. No se puede declarar un nivel de acceso diferente para este tipo de procedimiento, porque se establecerían dos niveles de acceso para la propiedad.

- **Tipo de valor devuelto.** El `Property` instrucción puede declarar el tipo de datos del valor que devuelve. Puede especificar cualquier tipo de datos o el nombre de una enumeración, estructura, clase o interfaz.

  Si no especifica `returntype`, la propiedad devuelve `Object`.

- **Implementación de.** Si usa esta propiedad la `Implements` debe tener la palabra clave, la clase o estructura que contiene un `Implements` instrucción inmediatamente posterior a su `Class` o `Structure` instrucción. El `Implements` instrucción debe incluir cada interfaz especificada en `implementslist`. Sin embargo, el nombre por el que una interfaz define el `Property` (en `definedname`) no tiene que ser el mismo que el nombre de esta propiedad (en `name`).

## <a name="behavior"></a>Comportamiento

- **Devolución desde un procedimiento de propiedad.** Cuando el `Get` o `Set` procedimiento vuelve al código de llamada, la ejecución continúa con la instrucción que sigue a la instrucción que lo invocó.

  El `Exit Property` y `Return` instrucciones provocan una salida inmediata de un procedimiento de propiedad. Cualquier número de `Exit Property` y `Return` instrucciones pueden aparecer en cualquier lugar en el procedimiento, y puede mezclar `Exit Property` y `Return` instrucciones.

- **Valor devuelto.** Para devolver un valor de un `Get` procedimiento, puede asignar el valor al nombre de propiedad o incluirlo en un `Return` instrucción. En el ejemplo siguiente se asigna el valor devuelto al nombre de propiedad `quoteForTheDay` y, a continuación, usa el `Exit Property` instrucción para devolver.

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]

  Si usas `Exit Property` sin asignar un valor a `name`, el `Get` procedimiento devuelve el valor predeterminado para el tipo de datos.

  El `Return` instrucción al mismo tiempo asigna el `Get` procedimiento devolver valor y sale del procedimiento. En el ejemplo siguiente se muestra esto.

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]

## <a name="example"></a>Ejemplo

El ejemplo siguiente declara una propiedad en una clase.

[!code-vb[VbVbalrStatements#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#51)]

## <a name="see-also"></a>Vea también

- [Propiedades autoimplementadas](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)
- [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Get (instrucción)](../../../visual-basic/language-reference/statements/get-statement.md)
- [Set (instrucción)](../../../visual-basic/language-reference/statements/set-statement.md)
- [Lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md)
- [Predetermiado](../../../visual-basic/language-reference/modifiers/default.md)
