---
title: Instrucción Const
ms.date: 05/12/2018
f1_keywords:
- vb.Const
helpviewer_keywords:
- Const statement [Visual Basic]
ms.assetid: 495b318d-b7c5-4198-94f8-0790a541b07a
ms.openlocfilehash: 3b05d4067ef99e03df07d2c316c982051180d961
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84382112"
---
# <a name="const-statement-visual-basic"></a>Instrucción Const (Visual Basic)

Declara y define una o más constantes.

## <a name="syntax"></a>Sintaxis

```vb
[ <attributelist> ] [ accessmodifier ] [ Shadows ]
Const constantlist
```

## <a name="parts"></a>Partes

`attributelist`  
Opcional. Lista de atributos que se aplican a todas las constantes declaradas en esta instrucción. Vea [lista de atributos](attribute-list.md) entre corchetes angulares (" `<` " y " `>` ").

`accessmodifier`  
Opcional. Úselo para especificar qué código puede tener acceso a estas constantes. Puede ser [Public](../modifiers/public.md), [Protected](../modifiers/protected.md), [Friend](../modifiers/friend.md), [Protected Friend](../modifiers/protected-friend.md), [Private](../modifiers/private.md)o [Private Protected](../modifiers/private-protected.md).

`Shadows`  
Opcional. Use esto para volver a declarar y ocultar un elemento de programación en una clase base. Vea [Shadows](../modifiers/shadows.md).

`constantlist`  
Necesario. Lista de constantes que se declaran en esta instrucción.

`constant` `[ ,` `constant` `... ]`

Cada `constant` tiene la sintaxis y las partes siguientes:

`constantname` `[ As` `datatype` `] =` `initializer`

|Parte|Descripción|
|----------|-----------------|
|`constantname`|Necesario. Nombre de la constante. Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).|
|`datatype`|Obligatorio si `Option Strict` es `On` . Tipo de datos de la constante.|
|`initializer`|Necesario. Expresión que se evalúa en tiempo de compilación y se asigna a la constante.|

## <a name="remarks"></a>Observaciones

Si tiene un valor que nunca cambia en la aplicación, puede definir una constante con nombre y utilizarla en lugar de un valor literal. Un nombre es más fácil de recordar que un valor. Puede definir la constante una sola vez y usarla en muchos lugares del código. Si en una versión posterior necesita volver a definir el valor, la `Const` instrucción es el único lugar que necesita para realizar un cambio.

Solo se puede usar `Const` en el nivel de módulo o de procedimiento. Esto significa que el contexto de la *declaración* de una variable debe ser una clase, una estructura, un módulo, un procedimiento o un bloque, y no puede ser un archivo de código fuente, un espacio de nombres o una interfaz. Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).

Las constantes locales (dentro de un procedimiento) tienen como valor predeterminado el acceso público y no se pueden usar modificadores de acceso en ellas. Las constantes de miembro de clase y módulo (fuera de cualquier procedimiento) tienen como valor predeterminado el acceso privado y las constantes de miembro de estructura tienen como valor predeterminado el acceso público. Los niveles de acceso se pueden ajustar con los modificadores de acceso.

## <a name="rules"></a>Reglas

- **Contexto de declaración.** Una constante declarada en el nivel de módulo, fuera de cualquier procedimiento, es una *constante de miembro*; es miembro de la clase, estructura o módulo que lo declara.

  Una constante declarada en el nivel de procedimiento es una *constante local*; es local para el procedimiento o bloque que lo declara.

- **Sus.** Solo puede aplicar atributos a constantes de miembro, no a constantes locales. Un atributo contribuye a la información en los metadatos del ensamblado, lo que no es significativo para el almacenamiento temporal, como las constantes locales.

- **Modificadores.** De forma predeterminada, todas las constantes son `Shared` , `Static` y `ReadOnly` . No se puede usar ninguna de estas palabras clave al declarar una constante.

  En el nivel de procedimiento, no se puede usar `Shadows` o cualquier modificador de acceso para declarar constantes locales.

- **Varias constantes.** Puede declarar varias constantes en la misma instrucción de declaración, especificando la `constantname` parte para cada una de ellas. Varias constantes se separan mediante comas.

## <a name="data-type-rules"></a>Reglas de tipo de datos

- **Tipos de datos.** La `Const` instrucción puede declarar el tipo de datos de una variable. Puede especificar cualquier tipo de datos o el nombre de una enumeración.

- **Tipo predeterminado.** Si no especifica `datatype` , la constante toma el tipo de datos de `initializer` . Si especifica `datatype` y `initializer` , el tipo de datos de `initializer` debe ser convertible a `datatype` . Si ni `datatype` ni `initializer` están presentes, el tipo de datos tiene como valor predeterminado `Object` .

- **Tipos diferentes.** Puede especificar tipos de datos diferentes para las diferentes constantes mediante el uso de una `As` cláusula independiente para cada variable que declare. Sin embargo, no se pueden declarar varias constantes para que sean del mismo tipo mediante el uso de una `As` cláusula común.

- **Inicial.** Debe inicializar el valor de cada constante en `constantlist` . Se usa `initializer` para proporcionar una expresión que se va a asignar a la constante. La expresión puede ser cualquier combinación de literales, otras constantes que ya están definidas y miembros de enumeración que ya están definidos. Puede usar operadores aritméticos y lógicos para combinar estos elementos.

  No se pueden usar variables ni funciones en `initializer` . Sin embargo, puede usar palabras clave de conversión como `CByte` y `CShort` . También puede usar `AscW` si lo llama con una constante o un `String` `Char` argumento, ya que se puede evaluar en tiempo de compilación.

## <a name="behavior"></a>Comportamiento

- **Ámbito.** Solo se puede tener acceso a las constantes locales desde el procedimiento o el bloque. Las constantes de miembro son accesibles desde cualquier lugar dentro de su clase, estructura o módulo.

- **Evaluación.** El código fuera de una clase, estructura o módulo debe calificar el nombre de una constante de miembro con el nombre de esa clase, estructura o módulo. El código fuera de un procedimiento o bloque no puede hacer referencia a ninguna constante local dentro de ese procedimiento o bloque.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se usa la `Const` instrucción para declarar constantes que se usan en lugar de los valores literales.

[!code-vb[VbVbalrStatements#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#13)]

## <a name="example"></a>Ejemplo

Si define una constante con el tipo `Object` de datos, el compilador Visual Basic le asigna el tipo de `initializer` , en lugar de `Object` . En el ejemplo siguiente, la constante `naturalLogBase` tiene el tipo en tiempo de ejecución `Decimal` .

[!code-vb[VbVbalrStatements#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#87)]

En el ejemplo anterior se usa el <xref:System.Type.ToString%2A> método en el <xref:System.Type> objeto devuelto por el [operador GetType](../operators/gettype-operator.md), porque <xref:System.Type> no se puede convertir en `String` mediante `CStr` .

## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [Instrucción Enum](enum-statement.md)
- [#Const (directiva)](../directives/const-directive.md)
- [Instrucción Dim](dim-statement.md)
- [Instrucción ReDim](redim-statement.md)
- [Conversiones implícitas y explícitas](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Constantes y enumeraciones](../../programming-guide/language-features/constants-enums/index.md)
- [Constantes y enumeraciones](../constants-and-enumerations.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
