---
title: Type List
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
ms.openlocfilehash: 3f2aaa65293ed2bcc6c8eeb4bd77e49907d93425
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352773"
---
# <a name="type-list-visual-basic"></a>Lista de tipos (Visual Basic)

Especifica los *parámetros de tipo* para un elemento de programación *genérico* . Varios parámetros se separan mediante comas. A continuación se encuentra la sintaxis de un parámetro de tipo.

## <a name="syntax"></a>Sintaxis

```vb
[genericmodifier] typename [ As constraintlist ]
```

## <a name="parts"></a>Elementos

|Término|Definición|
|---|---|
|`genericmodifier`|Opcional. Solo se puede usar en interfaces y delegados genéricos. Puede declarar un tipo covariante mediante la palabra clave [out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) o contravariante mediante la palabra clave [in](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) . Vea [Covarianza y contravarianza](../../programming-guide/concepts/covariance-contravariance/index.md).|
|`typename`|Obligatorio. Nombre del parámetro de tipo. Se trata de un marcador de posición que se reemplazará por un tipo definido proporcionado por el argumento de tipo correspondiente.|
|`constraintlist`|Opcional. Lista de requisitos que restringen el tipo de datos que se puede proporcionar para `typename`. Si tiene varias restricciones, enciérrelos entre llaves (`{ }`) y sepárelas con comas. Debe introducir la lista de restricciones con la palabra clave [as](../../../visual-basic/language-reference/statements/as-clause.md) . Solo se usa `As` una vez, al principio de la lista.|

## <a name="remarks"></a>Comentarios

Cada elemento de programación genérico debe tomar al menos un parámetro de tipo. Un parámetro de tipo es un marcador de posición para un tipo específico (un *elemento construido*) que el código de cliente especifica cuando crea una instancia del tipo genérico. Puede definir una clase, una estructura, una interfaz, un procedimiento o un delegado genéricos.

Para obtener más información sobre cuándo definir un tipo genérico, vea [tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md). Para obtener más información sobre los nombres de parámetros de tipo, vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).

## <a name="rules"></a>Reglas

- **Paréntesis.** Si proporciona una lista de parámetros de tipo, debe encerrarla entre paréntesis y debe introducir la lista con [la palabra clave](../../../visual-basic/language-reference/statements/of-clause.md) . Solo se usa `Of` una vez, al principio de la lista.

- **Restricciones.** Una lista de *restricciones* en un parámetro de tipo puede incluir los elementos siguientes en cualquier combinación:

  - Cualquier número de interfaces. El tipo proporcionado debe implementar cada interfaz en esta lista.

  - A lo sumo una clase. El tipo proporcionado debe heredar de esa clase.

  - Palabra clave `New`. El tipo proporcionado debe exponer un constructor sin parámetros al que pueda tener acceso el tipo genérico. Esto resulta útil si se restringe un parámetro de tipo mediante una o más interfaces. Un tipo que implementa interfaces no expone necesariamente un constructor y, en función del nivel de acceso de un constructor, el código dentro del tipo genérico podría no tener acceso a él.

  - La palabra clave `Class` o la palabra clave `Structure`. La palabra clave `Class` restringe un parámetro de tipo genérico para exigir que cualquier argumento de tipo pasado a él sea un tipo de referencia, por ejemplo una cadena, una matriz o un delegado, o un objeto creado a partir de una clase. La palabra clave `Structure` restringe un parámetro de tipo genérico para exigir que cualquier argumento de tipo pasado a él sea un tipo de valor, por ejemplo, una estructura, una enumeración o un tipo de datos elemental. No puede incluir `Class` y `Structure` en el mismo `constraintlist`.

  El tipo proporcionado debe cumplir todos los requisitos que se incluyen en `constraintlist`.

  Las restricciones de cada parámetro de tipo son independientes de las restricciones en otros parámetros de tipo.

## <a name="behavior"></a>Comportamiento

- **Sustitución en tiempo de compilación.** Cuando se crea un tipo construido a partir de un elemento de programación genérico, se proporciona un tipo definido para cada parámetro de tipo. El compilador de Visual Basic sustituye el tipo proporcionado por cada aparición de `typename` dentro del elemento genérico.

- **Ausencia de restricciones.** Si no especifica ninguna restricción en un parámetro de tipo, el código se limita a las operaciones y miembros admitidos por el tipo de [datos Object](../../../visual-basic/language-reference/data-types/object-data-type.md) para ese parámetro de tipo.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra una definición de esqueleto de una clase de diccionario genérico, incluida una función esqueleto para agregar una nueva entrada al diccionario.

[!code-vb[VbVbalrStatements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#3)]

## <a name="example"></a>Ejemplo

Dado que `dictionary` es genérico, el código que lo usa puede crear una variedad de objetos a partir de él, cada uno con la misma funcionalidad pero actuando en un tipo de datos diferente. En el ejemplo siguiente se muestra una línea de código que crea un objeto `dictionary` con `String` entradas y `Integer` claves.

[!code-vb[VbVbalrStatements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#4)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra la definición de esqueleto equivalente generada por el ejemplo anterior.

[!code-vb[VbVbalrStatements#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#5)]

## <a name="see-also"></a>Vea también

- [Of](../../../visual-basic/language-reference/statements/of-clause.md)
- [New (operador)](../../../visual-basic/language-reference/operators/new-operator.md)
- [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)
- [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Utilizar una clase genérica](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Covarianza y contravarianza](../../programming-guide/concepts/covariance-contravariance/index.md)
- [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
