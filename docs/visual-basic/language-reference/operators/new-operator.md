---
description: 'Más información acerca de: nuevo operador (Visual Basic)'
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
ms.openlocfilehash: f52dd7606127c7587173de8a78e618ceb3e4681d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665385"
---
# <a name="new-operator-visual-basic"></a>New (Operador, Visual Basic)

Introduce una `New` cláusula para crear una nueva instancia de objeto, especifica una restricción de constructor en un parámetro de tipo o identifica un `Sub` procedimiento como un constructor de clase.

## <a name="remarks"></a>Observaciones

En una declaración o una instrucción de asignación, una `New` cláusula debe especificar una clase definida a partir de la cual se pueda crear la instancia. Esto significa que la clase debe exponer uno o más constructores a los que puede tener acceso el código de llamada.

Puede utilizar una `New` cláusula en una instrucción de declaración o una instrucción de asignación. Cuando se ejecuta la instrucción, llama al constructor adecuado de la clase especificada, pasando los argumentos que ha proporcionado. En el siguiente ejemplo se muestra la creación de instancias de una `Customer` clase que tiene dos constructores, uno que no toma parámetros y otro que toma un parámetro de cadena:

[!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]

Puesto que las matrices son clases, `New` pueden crear una nueva instancia de la matriz, como se muestra en el ejemplo siguiente:

[!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]

El Common Language Runtime (CLR) produce un <xref:System.OutOfMemoryException> error si no hay memoria suficiente para crear la nueva instancia.

> [!NOTE]
> La `New` palabra clave también se usa en las listas de parámetros de tipo para especificar que el tipo proporcionado debe exponer un constructor sin parámetros accesible. Para obtener más información sobre los parámetros de tipo y las restricciones, vea [Type List](../statements/type-list.md).

Para crear un procedimiento de constructor para una clase, establezca el nombre de un `Sub` procedimiento en la `New` palabra clave. Para obtener más información, vea [duración del objeto: cómo se crean y destruyen los objetos](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).

La palabra clave `New` se puede usar en los siguientes contextos:

- [Instrucción Dim](../statements/dim-statement.md)
- [De](../statements/of-clause.md)
- [Instrucción Sub](../statements/sub-statement.md)

## <a name="see-also"></a>Vea también

- <xref:System.OutOfMemoryException>
- [Palabras clave](../keywords/index.md)
- [Type List](../statements/type-list.md)
- [Tipos genéricos en Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Duración de los objetos: cómo se crean y destruyen](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
