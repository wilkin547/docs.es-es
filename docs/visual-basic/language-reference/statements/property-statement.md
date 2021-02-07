---
description: 'Más información acerca de: Property (instrucción)'
title: Property Statement
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
ms.openlocfilehash: 95f2ac1f993fc8698d2033dfe50d925cd55a7dc4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741398"
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

## <a name="parts"></a>Partes

- `attributelist`

  Opcional. Lista de atributos que se aplican a esta propiedad o `Get` `Set` procedimiento. Vea [lista de atributos](attribute-list.md).

- `Default`

  Opcional. Especifica que esta propiedad es la propiedad predeterminada de la clase o estructura en la que se define. Las propiedades predeterminadas deben aceptar parámetros y se pueden establecer y recuperar sin especificar el nombre de la propiedad. Si declara la propiedad como `Default` , no puede usar `Private` en la propiedad o en cualquiera de sus procedimientos de propiedad.

- `accessmodifier`

  Opcional en la `Property` instrucción y en, como máximo, una de las `Get` `Set` instrucciones y. Puede ser uno de los siguientes:

  - [Público](../modifiers/public.md)

  - [Protegido](../modifiers/protected.md)

  - [Friend](../modifiers/friend.md)

  - [Privado](../modifiers/private.md)

  - [Protected Friend](../modifiers/protected-friend.md)

  - [Private Protected](../modifiers/private-protected.md)

  Consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

- `propertymodifiers`

  Opcional. Puede ser uno de los siguientes:

  - [Sobrecargas](../modifiers/overloads.md)

  - [Invalidaciones](../modifiers/overrides.md)

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

  Necesario. Nombre de la propiedad. Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).

- `parameterlist`

  Opcional. Lista de nombres de variables locales que representan los parámetros de esta propiedad y posibles parámetros adicionales del `Set` procedimiento. Vea [lista de parámetros](parameter-list.md).

- `returntype`

  Obligatorio si `Option Strict` es `On` . Tipo de datos del valor devuelto por esta propiedad.

- `Implements`

  Opcional. Indica que esta propiedad implementa una o más propiedades, cada una de las cuales se define en una interfaz implementada por la clase o estructura que contiene esta propiedad. Vea [Implements (instrucción](implements-statement.md)).

- `implementslist`

  Es necesario si se proporciona `Implements`. Lista de propiedades que se implementan.

  `implementedproperty [ , implementedproperty ... ]`

  Cada `implementedproperty` tiene la sintaxis y las partes siguientes:

  `interface.definedname`

  |Parte|Descripción|
  |---|---|
  |`interface`|Necesario. Nombre de una interfaz implementada por la clase o estructura que contiene esta propiedad.|
  |`definedname`|Necesario. Nombre por el que se define la propiedad en `interface` .|

- `Get`

  Opcional. Es obligatorio si la propiedad está marcada `ReadOnly` . Inicia un `Get` procedimiento de propiedad que se usa para devolver el valor de la propiedad.  La `Get` instrucción no se utiliza con [las propiedades implementadas automáticamente](../../programming-guide/language-features/procedures/auto-implemented-properties.md).

- `statements`

  Opcional. Bloque de instrucciones que se ejecutarán dentro del `Get` `Set` procedimiento o.

- `End Get`

  Finaliza el `Get` procedimiento de propiedad.

- `Set`

  Opcional. Es obligatorio si la propiedad está marcada `WriteOnly` . Inicia un `Set` procedimiento de propiedad que se usa para almacenar el valor de la propiedad.  La `Set` instrucción no se utiliza con [las propiedades implementadas automáticamente](../../programming-guide/language-features/procedures/auto-implemented-properties.md).

- `End Set`

  Finaliza el `Set` procedimiento de propiedad.

- `End Property`

  Finaliza la definición de esta propiedad.

## <a name="remarks"></a>Observaciones

La `Property` instrucción presenta la declaración de una propiedad. Una propiedad puede tener un `Get` procedimiento (solo lectura), un `Set` procedimiento (solo escritura) o ambos (lectura y escritura). Puede omitir el `Get` `Set` procedimiento y cuando use una propiedad implementada automáticamente. Para obtener más información, vea [Propiedades implementadas automáticamente](../../programming-guide/language-features/procedures/auto-implemented-properties.md).

Solo se puede usar `Property` en el nivel de clase. Esto significa que el contexto de la *declaración* de una propiedad debe ser una clase, una estructura, un módulo o una interfaz, y no puede ser un archivo de código fuente, un espacio de nombres, un procedimiento o un bloque. Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).

De forma predeterminada, las propiedades usan el acceso público. Puede ajustar el nivel de acceso de una propiedad con un modificador de acceso en la `Property` instrucción y, opcionalmente, puede ajustar uno de sus procedimientos de propiedad a un nivel de acceso más restrictivo.

Visual Basic pasa un parámetro al `Set` procedimiento durante las asignaciones de propiedades. Si no proporciona un parámetro para `Set` , el entorno de desarrollo integrado (IDE) utiliza un parámetro implícito denominado `value` . Este parámetro contiene el valor que se va a asignar a la propiedad. Normalmente, este valor se almacena en una variable local privada y se devuelve cada vez que `Get` se llama al procedimiento.

## <a name="rules"></a>Reglas

- **Niveles de acceso mixtos.** Si va a definir una propiedad de lectura y escritura, puede especificar opcionalmente un nivel de acceso diferente para el `Get` procedimiento o `Set` , pero no para ambos. Si lo hace, el nivel de acceso del procedimiento debe ser más restrictivo que el nivel de acceso de la propiedad. Por ejemplo, si se declara la propiedad `Friend` , puede declarar el `Set` procedimiento `Private` , pero no `Public` .

  Si está definiendo una `ReadOnly` `WriteOnly` propiedad o, el procedimiento de propiedad única ( `Get` o `Set` , respectivamente) representa toda la propiedad. No se puede declarar un nivel de acceso diferente para este procedimiento, ya que esto establecería dos niveles de acceso para la propiedad.

- **Tipo de valor devuelto.** La `Property` instrucción puede declarar el tipo de datos del valor que devuelve. Puede especificar cualquier tipo de datos o el nombre de una enumeración, estructura, clase o interfaz.

  Si no se especifica `returntype` , la propiedad devuelve `Object` .

- **Aplicación.** Si esta propiedad utiliza la `Implements` palabra clave, la clase contenedora o la estructura deben tener una `Implements` instrucción inmediatamente después de su `Class` `Structure` instrucción o. La `Implements` instrucción debe incluir cada interfaz especificada en `implementslist` . Sin embargo, el nombre por el que una interfaz define `Property` (en `definedname` ) no tiene que ser el mismo que el nombre de esta propiedad (en `name` ).

## <a name="behavior"></a>Comportamiento

- **Devolver desde un procedimiento de propiedad.** Cuando el `Get` `Set` procedimiento o vuelve al código de llamada, la ejecución continúa con la instrucción que sigue a la instrucción que lo invocó.

  Las `Exit Property` `Return` instrucciones y producen una salida inmediata de un procedimiento de propiedad. Cualquier número de `Exit Property` `Return` instrucciones y puede aparecer en cualquier parte del procedimiento y se pueden mezclar `Exit Property` e `Return` instrucciones.

- **Valor devuelto.** Para devolver un valor de un `Get` procedimiento, puede asignar el valor al nombre de la propiedad o incluirlo en una `Return` instrucción. En el ejemplo siguiente se asigna el valor devuelto al nombre de la propiedad `quoteForTheDay` y, a continuación, se usa la `Exit Property` instrucción para devolver.

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]

  Si usa `Exit Property` sin asignar un valor a `name` , el `Get` procedimiento devuelve el valor predeterminado para el tipo de datos de la propiedad.

  La `Return` instrucción al mismo tiempo asigna el `Get` valor devuelto del procedimiento y sale del procedimiento. Esto se muestra en el ejemplo siguiente.

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se declara una propiedad en una clase.

[!code-vb[VbVbalrStatements#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#51)]

## <a name="see-also"></a>Vea también

- [Propiedades autoimplementadas](../../programming-guide/language-features/procedures/auto-implemented-properties.md)
- [Objetos y clases](../../programming-guide/language-features/objects-and-classes/index.md)
- [Get (Instrucción)](get-statement.md)
- [Set (instrucción)](set-statement.md)
- [Lista de parámetros](parameter-list.md)
- [Valor predeterminado](../modifiers/default.md)
