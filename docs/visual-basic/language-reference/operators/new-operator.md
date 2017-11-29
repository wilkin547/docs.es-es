---
title: New (Operador, Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 74f0352379e861ad135ea23d31ea07d638f9e6c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="new-operator-visual-basic"></a>New (Operador, Visual Basic)
Presenta un `New` cláusula para crear una nueva instancia de objeto, especifica una restricción de constructor en un parámetro de tipo o identifica un `Sub` procedimiento como un constructor de clase.  
  
## <a name="remarks"></a>Comentarios  
 En una declaración o instrucción de asignación, una `New` cláusula debe especificar una clase definida desde el que se puede crear la instancia. Esto significa que la clase debe exponer uno o más constructores que pueda tener acceso el código que realiza la llamada.  
  
 Puede usar un `New` cláusula en una instrucción de declaración o una instrucción de asignación. Cuando se ejecuta la instrucción, llama al constructor adecuado de la clase especificada, pasa los argumentos que ha proporcionado. En el ejemplo siguiente se muestra cómo hacerlo mediante la creación de instancias de un `Customer` clase que tiene dos constructores, uno que no toma ningún parámetro y otro que toma un parámetro de cadena.  
  
 [!code-vb[VbVbalrKeywords#11](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_1.vb)]  
  
 Puesto que las matrices son clases, `New` puede crear una nueva instancia de matriz, como se muestra en los ejemplos siguientes.  
  
 [!code-vb[VbVbalrKeywords#12](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_2.vb)]  
  
 Common language runtime (CLR) produce un <xref:System.OutOfMemoryException> error si no hay memoria suficiente para crear la nueva instancia.  
  
> [!NOTE]
>  El `New` palabra clave también se utiliza en las listas de parámetros de tipo para especificar que el tipo proporcionado debe exponer un constructor sin parámetros accesible. Para obtener más información sobre los parámetros de tipo y restricciones, consulte [lista de tipo](../../../visual-basic/language-reference/statements/type-list.md).  
  
 Para crear un procedimiento de constructor para una clase, establezca el nombre de un `Sub` procedimiento para la `New` palabra clave. Para obtener más información, consulte [duración de los objetos: cómo los objetos son crean y destruyen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
 La palabra clave `New` se puede usar en los siguientes contextos:  
  
 [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vea también  
 <xref:System.OutOfMemoryException>  
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)  
 [Lista de tipos](../../../visual-basic/language-reference/statements/type-list.md)  
 [Tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Duración de los objetos: cómo se crean y destruyen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
