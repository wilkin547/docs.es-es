---
title: New (Operador, Visual Basic)
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
ms.openlocfilehash: 36cf71529b1f81c27881638d788117222c37171d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955877"
---
# <a name="new-operator-visual-basic"></a>New (Operador, Visual Basic)
Introduce una `New` cláusula para crear una nueva instancia de objeto, especifica una restricción de constructor en un parámetro de tipo o `Sub` identifica un procedimiento como un constructor de clase.  
  
## <a name="remarks"></a>Comentarios  
 En una declaración o una instrucción de asignación `New` , una cláusula debe especificar una clase definida a partir de la cual se pueda crear la instancia. Esto significa que la clase debe exponer uno o más constructores a los que puede tener acceso el código de llamada.  
  
 Puede utilizar una `New` cláusula en una instrucción de declaración o una instrucción de asignación. Cuando se ejecuta la instrucción, llama al constructor adecuado de la clase especificada, pasando los argumentos que ha proporcionado. En el siguiente ejemplo se muestra la creación de instancias `Customer` de una clase que tiene dos constructores, uno que no toma parámetros y otro que toma un parámetro de cadena.  
  
 [!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]  
  
 Puesto que las matrices son clases `New` , pueden crear una nueva instancia de la matriz, como se muestra en los ejemplos siguientes.  
  
 [!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]  
  
 El Common Language Runtime (CLR) produce un <xref:System.OutOfMemoryException> error si no hay memoria suficiente para crear la nueva instancia.  
  
> [!NOTE]
> La `New` palabra clave también se usa en las listas de parámetros de tipo para especificar que el tipo proporcionado debe exponer un constructor sin parámetros accesible. Para obtener más información sobre los parámetros de tipo y las restricciones, vea [Type List](../../../visual-basic/language-reference/statements/type-list.md).  
  
 Para crear un procedimiento de constructor para una clase, establezca el nombre de `Sub` un procedimiento en `New` la palabra clave. Para obtener más información, [consulte duración de los objetos: Cómo se crean y destruyen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)los objetos.  
  
 La palabra clave `New` se puede usar en los siguientes contextos:  
  
 [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vea también

- <xref:System.OutOfMemoryException>
- [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
- [Lista de tipos](../../../visual-basic/language-reference/statements/type-list.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Duración del objeto: Cómo se crean y destruyen los objetos](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
