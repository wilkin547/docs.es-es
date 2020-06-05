---
title: Procedimiento Inclusión de más de un valor en una variable
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- arrays [Visual Basic], compilation errors
- types [Visual Basic], composite
ms.assetid: 5fe0e558-aac2-4a40-b7f2-7cfea7336917
ms.openlocfilehash: 399c5909ee6988f96bcc85260b0401f3bd18a0f2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393901"
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a>Cómo: Contener más de un valor en una variable (Visual Basic)

Una variable contiene más de un valor si se declara como un *tipo de datos compuesto*.

Los [tipos de datos compuestos](composite-data-types.md) incluyen estructuras, matrices y clases. Una variable de un tipo de datos compuesto puede contener una combinación de tipos de datos básicos y otros tipos compuestos. Las estructuras y las clases pueden contener código y datos.

## <a name="to-hold-more-than-one-value-in-a-variable"></a>Para contener más de un valor en una variable

1. Determine qué tipo de datos compuesto desea usar para la variable.

2. Si el tipo de datos compuesto todavía no está definido, debe definirlo para que la variable pueda usarlo.

    - Defina una estructura con una [instrucción Structure](../../../language-reference/statements/structure-statement.md).

    - Defina una matriz con una [instrucción Dim](../../../language-reference/statements/dim-statement.md).

    - Defina una clase con una [instrucción de clase](../../../language-reference/statements/class-statement.md).

3. Declare la variable con una `Dim` instrucción.

4. Siga el nombre de la variable con una `As` cláusula.

5. Siga la `As` palabra clave con el nombre del tipo de datos compuesto adecuado.

## <a name="see-also"></a>Consulte también

- [Tipos de datos](../../../language-reference/data-types/index.md)
- [Caracteres de tipo](type-characters.md)
- [Tipos de datos compuestos](composite-data-types.md)
- [Estructuras](structures.md)
- [Matrices](../arrays/index.md)
- [Objetos y clases](../objects-and-classes/index.md)
- [Tipos de valor y tipos de referencia](value-types-and-reference-types.md)
