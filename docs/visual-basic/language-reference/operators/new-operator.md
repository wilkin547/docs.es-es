---
title: New (Operador)
ms.date: 07/20/2015
f1_keywords:
- vb.new
- vb.NewConstraint
helpviewer_keywords:
- constraints, Visual Basic generic types
- generics [Visual Basic], constraints
- constraints, New keyword [Visual Basic]
- New constraint
- New keyword [Visual Basic]
ms.assetid: d7d566d7-fe0e-4336-91f7-641a542de4d0
ms.openlocfilehash: 27b5b4516ef729045036c36fedc24b6c576a4f61
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348320"
---
# <a name="new-operator-visual-basic"></a>New (Operador, Visual Basic)

Presenta una cláusula `New` para crear una nueva instancia de objeto, especifica una restricción de constructor en un parámetro de tipo o identifica un procedimiento `Sub` como un constructor de clase.

## <a name="remarks"></a>Comentarios

En una declaración o una instrucción de asignación, una cláusula `New` debe especificar una clase definida a partir de la cual se pueda crear la instancia. Esto significa que la clase debe exponer uno o más constructores a los que puede tener acceso el código de llamada.

Puede usar una cláusula `New` en una instrucción de declaración o una instrucción de asignación. Cuando se ejecuta la instrucción, llama al constructor adecuado de la clase especificada, pasando los argumentos que ha proporcionado. En el siguiente ejemplo se muestra la creación de instancias de una clase `Customer` que tiene dos constructores, uno que no toma parámetros y otro que toma un parámetro de cadena:

[!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]

Dado que las matrices son clases, `New` puede crear una nueva instancia de la matriz, como se muestra en el ejemplo siguiente:

[!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]

El Common Language Runtime (CLR) produce un error de <xref:System.OutOfMemoryException> si no hay suficiente memoria para crear la nueva instancia.

> [!NOTE]
> La palabra clave `New` también se usa en las listas de parámetros de tipo para especificar que el tipo proporcionado debe exponer un constructor sin parámetros accesible. Para obtener más información sobre los parámetros de tipo y las restricciones, vea [Type List](../statements/type-list.md).

Para crear un procedimiento de constructor para una clase, establezca el nombre de una `Sub` procedimiento en la palabra clave `New`. Para obtener más información, vea [duración del objeto: cómo se crean y destruyen los objetos](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).

La palabra clave `New` se puede usar en los siguientes contextos:

- [Dim (instrucción)](../statements/dim-statement.md)
- [Of](../statements/of-clause.md)
- [Sub (instrucción)](../statements/sub-statement.md)

## <a name="see-also"></a>Vea también

- <xref:System.OutOfMemoryException>
- [Palabras clave](../keywords/index.md)
- [Lista de tipos](../statements/type-list.md)
- [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Duración de los objetos: cómo se crean y destruyen](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
