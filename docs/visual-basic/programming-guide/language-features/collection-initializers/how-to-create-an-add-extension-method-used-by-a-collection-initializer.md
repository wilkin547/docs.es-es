---
title: Procedimiento Crear una extensión método Add usado por un inicializador de colección (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: 3a1db8ede8162b329d546c0e712ef1c2df7d7883
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661677"
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a>Procedimiento Crear una extensión método Add usado por un inicializador de colección (Visual Basic)
Cuando se usa un inicializador de colección para crear una colección, el compilador de Visual Basic busca un `Add` método del tipo de colección para el que los parámetros para el `Add` método coinciden con los tipos de los valores del inicializador de colección. Esto `Add` método se usa para rellenar la colección con los valores del inicializador de colección.  
  
 Si no hay coincidencia `Add` método existe y no se puede modificar el código de la colección, puede agregar un método de extensión denominado `Add` que toma los parámetros requeridos por el inicializador de colección. Normalmente, esto es lo que necesita hacer al usar inicializadores de colección para las colecciones genéricas.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo agregar un método de extensión para el tipo genérico <xref:System.Collections.Generic.List%601> escriba por lo que puede utilizarse un inicializador de colección para agregar objetos de tipo `Employee`. El método de extensión le permite usar la sintaxis de inicializador de colección abreviada.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_3.vb)]  
  
## <a name="see-also"></a>Vea también
- [Inicializadores de colección](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Cómo: Crear una colección usada por un inicializador de colección](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
