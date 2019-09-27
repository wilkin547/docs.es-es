---
title: Property (instrucción) (Visual Basic)
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
ms.openlocfilehash: 2c3e417aad404171a43342dc92773615ec350ef5
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332746"
---
# <a name="property-statement"></a>Property Statement

Declara el nombre de una propiedad y los procedimientos de propiedad que se usan para almacenar y recuperar el valor de la propiedad.

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

  Opcional. Lista de atributos que se aplican a esta propiedad o @no__t procedimiento-0 o `Set`. Vea [lista de atributos](attribute-list.md).

- `Default`

  Opcional. Especifica que esta propiedad es la propiedad predeterminada de la clase o estructura en la que se define. Las propiedades predeterminadas deben aceptar parámetros y se pueden establecer y recuperar sin especificar el nombre de la propiedad. Si declara la propiedad como `Default`, no puede usar `Private` en la propiedad o en cualquiera de sus procedimientos de propiedad.

- `accessmodifier`

  Opcional en la instrucción `Property` y en, como máximo, una de las instrucciones `Get` y `Set`. Puede ser uno de los siguientes:

  - [Public](../modifiers/public.md)

  - [Protected](../modifiers/protected.md)

  - [Friend](../modifiers/friend.md)

  - [Private](../modifiers/private.md)

  - [Protected Friend](../modifiers/protected-friend.md)

  - [Private Protected](../modifiers/private-protected.md)

  Vea [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

- `propertymodifiers`

  Opcional. Puede ser uno de los siguientes:

  - [Sobrecargas](../modifiers/overloads.md)

  - [Overrides](../modifiers/overrides.md)

  - [Overridable](../modifiers/overridable.md)

  - [NotOverridable](../modifiers/notoverridable.md)

  - [MustOverride](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  Opcional. Vea [Shared](../modifiers/shared.md).

- `Shadows`

  Opcional. Vea [Shadows](../modifiers/shadows.md).

- `ReadOnly`

  Opcional. Vea [ReadOnly](../modifiers/readonly.md).

- `WriteOnly`

  Opcional. Vea [WriteOnly](../modifiers/writeonly.md).

- `Iterator`

  Opcional. Vea [iterator](../modifiers/iterator.md).

- `name`

  Obligatorio. Nombre de la propiedad. Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).

- `parameterlist`

  Opcional. Lista de nombres de variables locales que representan los parámetros de esta propiedad y posibles parámetros adicionales del procedimiento `Set`. Vea [lista de parámetros](parameter-list.md).

- `returntype`

  Obligatorio si `Option Strict` es `On`. Tipo de datos del valor devuelto por esta propiedad.

- `Implements`

  Opcional. Indica que esta propiedad implementa una o más propiedades, cada una de las cuales se define en una interfaz implementada por la clase o estructura que contiene esta propiedad. Vea [Implements (instrucción](implements-statement.md)).

- `implementslist`

  Es necesario si se proporciona `Implements`. Lista de propiedades que se implementan.

  `implementedproperty [ , implementedproperty ... ]`

  Cada `implementedproperty` tiene la sintaxis y las partes siguientes:

  `interface.definedname`

  |Parte|Descripción|
  |---|---|
  |`interface`|Obligatorio. Nombre de una interfaz implementada por la clase o estructura que contiene esta propiedad.|
  |`definedname`|Obligatorio. Nombre por el que se define la propiedad en `interface`.|

- `Get`

  Opcional. Obligatorio si la propiedad está marcada como `ReadOnly`. Inicia un procedimiento de propiedad `Get` que se usa para devolver el valor de la propiedad.  La instrucción `Get` no se utiliza con [las propiedades implementadas automáticamente](../../programming-guide/language-features/procedures/auto-implemented-properties.md).

- `statements`

  Opcional. Bloque de instrucciones que se va a ejecutar en el procedimiento `Get` o `Set`.

- `End Get`

  Finaliza el procedimiento de propiedad `Get`.

- `Set`

  Opcional. Obligatorio si la propiedad está marcada como `WriteOnly`. Inicia un procedimiento de propiedad `Set` que se utiliza para almacenar el valor de la propiedad.  La instrucción `Set` no se utiliza con [las propiedades implementadas automáticamente](../../programming-guide/language-features/procedures/auto-implemented-properties.md).

- `End Set`

  Finaliza el procedimiento de propiedad `Set`.

- `End Property`

  Finaliza la definición de esta propiedad.

## <a name="remarks"></a>Comentarios

La instrucción `Property` presenta la declaración de una propiedad. Una propiedad puede tener un procedimiento `Get` (solo lectura), un procedimiento `Set` (solo escritura) o ambos (lectura y escritura). Puede omitir el procedimiento `Get` y `Set` al usar una propiedad implementada automáticamente. Para obtener más información, vea [Propiedades implementadas automáticamente](../../programming-guide/language-features/procedures/auto-implemented-properties.md).

Solo se puede usar `Property` en el nivel de clase. Esto significa que el contexto de la *declaración* de una propiedad debe ser una clase, una estructura, un módulo o una interfaz, y no puede ser un archivo de código fuente, un espacio de nombres, un procedimiento o un bloque. Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).

De forma predeterminada, las propiedades usan el acceso público. Puede ajustar el nivel de acceso de una propiedad con un modificador de acceso en la instrucción `Property` y, opcionalmente, puede ajustar uno de sus procedimientos de propiedad a un nivel de acceso más restrictivo.

Visual Basic pasa un parámetro al procedimiento `Set` durante las asignaciones de propiedades. Si no proporciona un parámetro para `Set`, el entorno de desarrollo integrado (IDE) usa un parámetro implícito denominado `value`. Este parámetro contiene el valor que se va a asignar a la propiedad. Normalmente, este valor se almacena en una variable local privada y se devuelve cada vez que se llama al procedimiento `Get`.

## <a name="rules"></a>Reglas

- **Niveles de acceso mixtos.** Si va a definir una propiedad de lectura y escritura, puede especificar opcionalmente un nivel de acceso diferente para el procedimiento `Get` o `Set`, pero no ambos. Si lo hace, el nivel de acceso del procedimiento debe ser más restrictivo que el nivel de acceso de la propiedad. Por ejemplo, si la propiedad se declara `Friend`, puede declarar el procedimiento `Set` `Private`, pero no `Public`.

  Si va a definir una propiedad `ReadOnly` o `WriteOnly`, el procedimiento de propiedad única (`Get` o `Set`, respectivamente) representa toda la propiedad. No se puede declarar un nivel de acceso diferente para este procedimiento, ya que esto establecería dos niveles de acceso para la propiedad.

- **Tipo de valor devuelto.** La instrucción `Property` puede declarar el tipo de datos del valor que devuelve. Puede especificar cualquier tipo de datos o el nombre de una enumeración, estructura, clase o interfaz.

  Si no especifica `returntype`, la propiedad devuelve `Object`.

- **Aplicación.** Si esta propiedad usa la palabra clave `Implements`, la clase o estructura contenedora debe tener una instrucción `Implements` inmediatamente después de su instrucción `Class` o `Structure`. La instrucción `Implements` debe incluir cada interfaz especificada en `implementslist`. Sin embargo, el nombre por el que una interfaz define el `Property` (en `definedname`) no tiene que ser el mismo que el nombre de esta propiedad (en `name`).

## <a name="behavior"></a>Comportamiento

- **Devolver desde un procedimiento de propiedad.** Cuando el procedimiento `Get` o `Set` vuelve al código de llamada, la ejecución continúa con la instrucción que sigue a la instrucción que lo invocó.

  Las instrucciones `Exit Property` y `Return` producen una salida inmediata de un procedimiento de propiedad. Cualquier número de instrucciones `Exit Property` y `Return` puede aparecer en cualquier parte del procedimiento y se pueden mezclar instrucciones `Exit Property` y `Return`.

- **Valor devuelto.** Para devolver un valor de un procedimiento `Get`, puede asignar el valor al nombre de la propiedad o incluirlo en una instrucción `Return`. En el ejemplo siguiente se asigna el valor devuelto al nombre de propiedad `quoteForTheDay` y, a continuación, se usa la instrucción `Exit Property` para devolver.

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]

  Si usa `Exit Property` sin asignar un valor a `name`, el procedimiento `Get` devuelve el valor predeterminado para el tipo de datos de la propiedad.

  La instrucción `Return` al mismo tiempo asigna el valor devuelto del procedimiento `Get` y sale del procedimiento. En el ejemplo siguiente se muestra esto.

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se declara una propiedad en una clase.

[!code-vb[VbVbalrStatements#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#51)]

## <a name="see-also"></a>Vea también

- [Propiedades autoimplementadas](../../programming-guide/language-features/procedures/auto-implemented-properties.md)
- [Objetos y clases](../../programming-guide/language-features/objects-and-classes/index.md)
- [Get (instrucción)](get-statement.md)
- [Set (instrucción)](set-statement.md)
- [Lista de parámetros](parameter-list.md)
- [Predetermiado](../modifiers/default.md)
