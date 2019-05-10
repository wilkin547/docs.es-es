---
title: Lista de tipos (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- StructureConstraint
- vb.StructureConstraint
- ClassConstraint
- vb.ClassConstraint
helpviewer_keywords:
- class constraint
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- generics [Visual Basic], type list
- structure constraint
- constraints, in type parameters
- generics [Visual Basic], generic types
- parameters [Visual Basic], type
- constraints, Structure keyword
- type parameters [Visual Basic], constraints
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], type parameters
- type parameters
- constraints, Class keyword
ms.assetid: 56db947a-2ae8-40f2-a70a-960764e9d0db
ms.openlocfilehash: aae9135207bbd3f9d0cc7c072e423a50902c372a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64751507"
---
# <a name="type-list-visual-basic"></a>Lista de tipos (Visual Basic)

Especifica el *parámetros de tipo* para un *genérico* elemento de programación. Varios parámetros están separados por comas. Siguiente es la sintaxis para un parámetro de tipo.

## <a name="syntax"></a>Sintaxis

```
[genericmodifier] typename [ As constraintlist ]
```

## <a name="parts"></a>Elementos

|Término|Definición|
|---|---|
|`genericmodifier`|Opcional. Puede usarse solo en interfaces y delegados genéricos. Puede declarar un tipo covariante mediante el [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) palabra clave o contravariante mediante la [en](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) palabra clave. Vea [Covarianza y contravarianza](../../programming-guide/concepts/covariance-contravariance/index.md).|
|`typename`|Obligatorio. Nombre del parámetro de tipo. Se trata de un marcador de posición, reemplazarse por un tipo definido proporcionado por el argumento de tipo correspondiente.|
|`constraintlist`|Opcional. Lista de requisitos que restringe el tipo de datos que se puede proporcionar para `typename`. Si tiene varias restricciones, encierre entre llaves (`{ }`) y sepárelas con comas. Debe introducir la lista de restricciones con el [como](../../../visual-basic/language-reference/statements/as-clause.md) palabra clave. Usa `As` una sola vez, al principio de la lista.|

## <a name="remarks"></a>Comentarios

Cada elemento de programación genérica debe tener al menos un parámetro de tipo. Un parámetro de tipo es un marcador de posición para un tipo específico (un *elemento construido*) que el código de cliente especifica cuando crea una instancia del tipo genérico. Puede definir una clase genérica, estructura, interfaz, procedimiento o delegado.

Para obtener más información sobre cuándo se debe definir un tipo genérico, vea [tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md). Para obtener más información sobre los nombres de parámetro de tipo, consulte [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).

## <a name="rules"></a>Reglas

- **Paréntesis.** Si se proporciona una lista de parámetros de tipo, debe encerrarlo entre paréntesis y debe introducir la lista con el [de](../../../visual-basic/language-reference/statements/of-clause.md) palabra clave. Usa `Of` una sola vez, al principio de la lista.

- **Restricciones.** Una lista de *restricciones* en un tipo de parámetro puede incluir los siguientes elementos en cualquier combinación:

  - Cualquier número de interfaces. El tipo proporcionado debe implementar todas las interfaces en esta lista.

  - A lo sumo una clase. El tipo proporcionado debe heredar de esa clase.

  - Palabra clave `New`. El tipo proporcionado debe exponer un constructor sin parámetros que puede tener acceso su tipo genérico. Esto es útil si restringe un parámetro de tipo por una o varias interfaces. Un tipo que implementa las interfaces no necesariamente exponer un constructor, y según el nivel de acceso de un constructor, el código dentro del tipo genérico es posible que no pueda obtener acceso a él.

  - Ya sea el `Class` palabra clave o el `Structure` palabra clave. El `Class` palabra clave restringe un parámetro de tipo genérico para exigir que cualquier argumento de tipo pasado a la ser un tipo de referencia, por ejemplo una cadena, matriz o delegado, o crea un objeto de una clase. El `Structure` palabra clave restringe un parámetro de tipo genérico para exigir que cualquier argumento de tipo pasado a la sea un tipo de valor, por ejemplo, una estructura, enumeración o datos elementales escriba. No se puede incluir tanto `Class` y `Structure` en el mismo `constraintlist`.

  El tipo proporcionado debe cumplir cada requisito que se incluya en `constraintlist`.

  Las restricciones de cada parámetro de tipo son independientes de las restricciones de otros tipos de parámetros.

## <a name="behavior"></a>Comportamiento

- **Sustitución de tiempo de compilación.** Cuando se crea un tipo construido desde un elemento de programación genérico, proporcione un tipo definido para cada parámetro de tipo. El compilador de Visual Basic sustituye el tipo proporcionado para todas las apariciones de `typename` dentro del elemento genérico.

- **Ausencia de restricciones.** Si no especifica ninguna restricción en un parámetro de tipo, el código se limita a las operaciones y miembros compatibles con el [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md) para ese parámetro de tipo.

## <a name="example"></a>Ejemplo

El ejemplo siguiente muestra un esquema de definición de una clase de diccionario genérico, incluida una función de esqueleto para agregar una nueva entrada al diccionario.

[!code-vb[VbVbalrStatements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#3)]

## <a name="example"></a>Ejemplo

Dado que `dictionary` es genérico, el código que lo usa puede crear una variedad de objetos, cada uno tiene la misma funcionalidad pero que actúan en un tipo de datos diferente. El ejemplo siguiente muestra una línea de código que crea un `dictionary` objeto con `String` entradas y `Integer` claves.

[!code-vb[VbVbalrStatements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#4)]

## <a name="example"></a>Ejemplo

El ejemplo siguiente muestra la definición de esqueleto equivalente generada por el ejemplo anterior.

[!code-vb[VbVbalrStatements#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#5)]

## <a name="see-also"></a>Vea también

- [Of](../../../visual-basic/language-reference/statements/of-clause.md)
- [New (operador)](../../../visual-basic/language-reference/operators/new-operator.md)
- [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Tipo de objeto de datos](../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)
- [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Cómo: Utilizar una clase genérica](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Covarianza y contravarianza](../../programming-guide/concepts/covariance-contravariance/index.md)
- [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
