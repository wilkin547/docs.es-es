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
ms.openlocfilehash: dda23ef3ff49bd32474f39f5ae1807e57bdc2a62
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980469"
---
# <a name="new-operator-visual-basic"></a>New (Operador, Visual Basic)
Presenta un `New` cláusula para crear una nueva instancia de objeto, especifica una restricción de constructor en un parámetro de tipo, o identifica una `Sub` procedimiento como un constructor de clase.  
  
## <a name="remarks"></a>Comentarios  
 En una declaración o instrucción de asignación, un `New` cláusula debe especificar una clase definida desde la que se puede crear la instancia. Esto significa que la clase debe exponer uno o más constructores que puede tener acceso el código de llamada.  
  
 Puede usar un `New` cláusula en una instrucción de declaración o en una instrucción de asignación. Cuando se ejecuta la instrucción, llama al constructor apropiado de la clase especificada, pasando los argumentos que hayan proporcionado. El ejemplo siguiente muestra mediante la creación de instancias de un `Customer` clase que tiene dos constructores, uno que no toma ningún parámetro y otro que toma un parámetro de cadena.  
  
 [!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]  
  
 Dado que las matrices son clases, `New` puede crear una nueva instancia de matriz, como se muestra en los ejemplos siguientes.  
  
 [!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]  
  
 Common language runtime (CLR) produce una <xref:System.OutOfMemoryException> error si no hay memoria suficiente para crear la nueva instancia.  
  
> [!NOTE]
>  El `New` palabra clave también se usa en las listas de parámetros de tipo para especificar que el tipo proporcionado debe exponer un constructor sin parámetros accesible. Para obtener más información sobre los parámetros de tipo y restricciones, vea [lista tipo](../../../visual-basic/language-reference/statements/type-list.md).  
  
 Para crear un procedimiento de constructor para una clase, establezca el nombre de un `Sub` procedimiento a la `New` palabra clave. Para obtener más información, consulte [duración del objeto: ¿Cómo se crean y destruyen objetos](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
 La palabra clave `New` se puede usar en los siguientes contextos:  
  
 [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vea también
- <xref:System.OutOfMemoryException>
- [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
- [Lista de tipos](../../../visual-basic/language-reference/statements/type-list.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Duración del objeto: ¿Cómo se crean y destruyen objetos](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
