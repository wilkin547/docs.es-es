---
description: 'Más información sobre: instrucción enum (Visual Basic)'
title: Instrucción Enum
ms.date: 07/20/2015
f1_keywords:
- vb.Enum
helpviewer_keywords:
- enumerated constants [Visual Basic]
- Enum statement [Visual Basic]
- Private keyword [Visual Basic], Enum statements
- Public keyword [Visual Basic], in Enum statement
- variables [Visual Basic], enumeration
- constants [Visual Basic], enumerated
ms.assetid: a45e51f1-65ff-48e1-bf32-79130f137377
ms.openlocfilehash: dcaf28e949f8d34b8d72b07d8029ea10d6baeabf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769174"
---
# <a name="enum-statement-visual-basic"></a>Instrucción Enum (Visual Basic)

Declara una enumeración y define los valores de sus miembros.

## <a name="syntax"></a>Sintaxis

```vb
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]
Enum enumerationname [ As datatype ]
   memberlist
End Enum
```

## <a name="parts"></a>Partes

- `attributelist`

  Opcional. Lista de atributos que se aplican a esta enumeración. Debe incluir la [lista de atributos](attribute-list.md) entre corchetes angulares (" `<` " y " `>` ").

  El <xref:System.FlagsAttribute> atributo indica que el valor de una instancia de la enumeración puede incluir varios miembros de enumeración y que cada miembro representa un campo de bits en el valor de enumeración.

- `accessmodifier`

  Opcional. Especifica qué código puede tener acceso a esta enumeración. Puede ser uno de los siguientes:

  - [Público](../modifiers/public.md)

  - [Protegido](../modifiers/protected.md)

  - [Friend](../modifiers/friend.md)

  - [Privado](../modifiers/private.md)

  - [Protected Friend](../modifiers/protected-friend.md)

  - [Private Protected](../modifiers/private-protected.md)

- `Shadows`

  Opcional. Especifica que esta enumeración vuelve a declarar y oculta un elemento de programación con el mismo nombre, o un conjunto de elementos sobrecargados, en una clase base. Solo puede especificar [Shadows](../modifiers/shadows.md) en la propia enumeración, no en ninguno de sus miembros.

- `enumerationname`

  Necesario. Nombre de la enumeración. Para obtener información sobre los nombres válidos, vea [nombres de elementos declarados](../../programming-guide/language-features/declared-elements/declared-element-names.md).

- `datatype`

  Opcional. Tipo de datos de la enumeración y de todos sus miembros.

- `memberlist`

  Necesario. Lista de constantes de miembro que se declaran en esta instrucción. Aparecen varios miembros en líneas de código fuente individuales.

  Cada una `member` de ellas tiene la sintaxis y las partes siguientes: `[<attribute list>] member name [ = initializer ]`

  |Parte|Descripción|
  |---|---|
  |`membername`|Necesario. Nombre de este miembro.|
  |`initializer`|Opcional. Expresión que se evalúa en tiempo de compilación y se asigna a este miembro.|

- `End` `Enum`

  Finaliza el bloque `Enum`.

## <a name="remarks"></a>Observaciones

Si tiene un conjunto de valores invariables que están relacionados lógicamente entre sí, puede definirlos juntos en una enumeración. Esto proporciona nombres descriptivos para la enumeración y sus miembros, que son más fáciles de recordar que sus valores. Después, puede usar los miembros de enumeración en muchos lugares del código.

Las ventajas de utilizar enumeraciones son las siguientes:

- Reduce los errores causados por la transposición o la escritura indebida de números.

- Facilita el cambio de valores en el futuro.

- Facilita la lectura del código, lo que significa que es menos probable que se introduzcan errores.

- Garantiza la compatibilidad con versiones posteriores. Si usa enumeraciones, es menos probable que se produzca un error en el código si en el futuro alguien cambia los valores correspondientes a los nombres de miembro.

Una enumeración tiene un nombre, un tipo de datos subyacente y un conjunto de miembros. Cada miembro representa una constante.

Una enumeración declarada en el nivel de clase, estructura, módulo o interfaz, fuera de cualquier procedimiento, es una *enumeración de miembros*. Es miembro de la clase, estructura, módulo o interfaz que lo declara.

Se puede tener acceso a las enumeraciones de miembros desde cualquier lugar dentro de su clase, estructura, módulo o interfaz. El código fuera de una clase, estructura o módulo debe calificar el nombre de la enumeración de un miembro con el nombre de esa clase, estructura o módulo. Puede evitar la necesidad de usar nombres completos agregando una instrucción [Imports](imports-statement-net-namespace-and-type.md) al archivo de código fuente.

Una enumeración declarada en el nivel de espacio de nombres, fuera de cualquier clase, estructura, módulo o interfaz, es un miembro del espacio de nombres en el que aparece.

El *contexto* de la declaración de una enumeración debe ser un archivo de código fuente, un espacio de nombres, una clase, una estructura, un módulo o una interfaz y no puede ser un procedimiento. Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).

Puede aplicar atributos a una enumeración en su totalidad, pero no a sus miembros individualmente. Un atributo contribuye a la información en los metadatos del ensamblado.

## <a name="data-type"></a>Tipo de datos

La `Enum` instrucción puede declarar el tipo de datos de una enumeración. Cada miembro toma el tipo de datos de la enumeración. Puede especificar `Byte` , `Integer` , `Long` , `SByte` , `Short` , `UInteger` , `ULong` o `UShort` .

Si no especifica `datatype` para la enumeración, cada miembro toma el tipo de datos de su `initializer` . Si especifica `datatype` y `initializer` , el tipo de datos de `initializer` debe ser convertible a `datatype` . Si ni `datatype` ni `initializer` están presentes, el tipo de datos tiene como valor predeterminado `Integer` .

## <a name="initializing-members"></a>Inicializar miembros

La `Enum` instrucción puede inicializar el contenido de los miembros seleccionados en `memberlist` . Se usa `initializer` para proporcionar una expresión que se va a asignar al miembro.

Si no especifica `initializer` para un miembro, Visual Basic lo inicializa en cero (si es el primero `member` en `memberlist` ) o en un valor mayor en uno que el de inmediatamente anterior `member` .

La expresión proporcionada en cada `initializer` puede ser cualquier combinación de literales, otras constantes que ya están definidas y miembros de enumeración que ya están definidos, incluido un miembro anterior de esta enumeración. Puede usar operadores aritméticos y lógicos para combinar estos elementos.

No se pueden usar variables ni funciones en `initializer` . Sin embargo, puede usar palabras clave de conversión como `CByte` y `CShort` . También puede usar `AscW` si lo llama con una constante o un `String` `Char` argumento, ya que se puede evaluar en tiempo de compilación.

Las enumeraciones no pueden tener valores de punto flotante. Si a un miembro se le asigna un valor de punto flotante y `Option Strict` se establece en ON, se produce un error del compilador. Si `Option Strict` es OFF, el valor se convierte automáticamente al `Enum` tipo.

Si el valor de un miembro supera el intervalo permitido para el tipo de datos subyacente, o si se inicializa un miembro con el valor máximo permitido por el tipo de datos subyacente, el compilador informa de un error.

## <a name="modifiers"></a>Modificadores

Las enumeraciones de clase, estructura, módulo y miembro de interfaz tienen como valor predeterminado el acceso público. Los niveles de acceso se pueden ajustar con los modificadores de acceso. Las enumeraciones de miembros de espacio de nombres tienen acceso de confianza de forma predeterminada. Puede ajustar sus niveles de acceso a público, pero no a privado o protegido. Para obtener más información, consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

Todos los miembros de enumeración tienen acceso público y no se pueden usar modificadores de acceso en ellos. Sin embargo, si la propia enumeración tiene un nivel de acceso más restringido, tiene prioridad el nivel de acceso de enumeración especificado.

De forma predeterminada, todas las enumeraciones son tipos y sus campos son constantes. Por lo tanto `Shared` , las `Static` palabras clave, y `ReadOnly` no se pueden usar al declarar una enumeración o sus miembros.

## <a name="assigning-multiple-values"></a>Asignar varios valores

Las enumeraciones suelen representar valores mutuamente excluyentes. Al incluir el <xref:System.FlagsAttribute> atributo en la `Enum` declaración, en su lugar puede asignar varios valores a una instancia de la enumeración. El <xref:System.FlagsAttribute> atributo especifica que la enumeración se tratará como un campo de bits, es decir, un conjunto de marcas. Se denominan enumeraciones *bit a bit* .

Cuando se declara una enumeración mediante el <xref:System.FlagsAttribute> atributo, se recomienda usar las potencias de 2, es decir, 1, 2, 4, 8, 16, etc., para los valores. También se recomienda que "none" sea el nombre de un miembro cuyo valor sea 0. Para obtener instrucciones adicionales, vea <xref:System.FlagsAttribute> y <xref:System.Enum> .

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo usar la instrucción `Enum`. Tenga en cuenta que el miembro se conoce como `EggSizeEnum.Medium` y no como `Medium` .

[!code-vb[VbEnumsTask#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#41)]

## <a name="example"></a>Ejemplo

El método del ejemplo siguiente está fuera de la `Egg` clase. Por lo tanto, `EggSizeEnum` está completo como `Egg.EggSizeEnum` .

[!code-vb[VbEnumsTask#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#42)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se usa la `Enum` instrucción para definir un conjunto relacionado de valores constantes con nombre. En este caso, los valores son colores que se pueden elegir para diseñar formularios de entrada de datos para una base de datos.

[!code-vb[VbEnumsTask#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#30)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestran valores que incluyen números positivos y negativos.

[!code-vb[VbEnumsTask#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#31)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente, `As` se utiliza una cláusula para especificar el `datatype` de una enumeración.

[!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo usar una enumeración bit a bit. Se pueden asignar varios valores a una instancia de una enumeración bit a bit. La `Enum` Declaración incluye el <xref:System.FlagsAttribute> atributo, que indica que la enumeración se puede tratar como un conjunto de marcas.

[!code-vb[VbEnumsTask#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#61)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se recorre en iteración una enumeración. Utiliza el <xref:System.Enum.GetNames%2A> método para recuperar una matriz de nombres de miembro de la enumeración y <xref:System.Enum.GetValues%2A> para recuperar una matriz de valores de miembro.

[!code-vb[VbEnumsTask#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#51)]

## <a name="see-also"></a>Vea también

- <xref:System.Enum>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [Instrucción Const](const-statement.md)
- [Instrucción Dim](dim-statement.md)
- [Conversiones implícitas y explícitas](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Constantes y enumeraciones](../constants-and-enumerations.md)
