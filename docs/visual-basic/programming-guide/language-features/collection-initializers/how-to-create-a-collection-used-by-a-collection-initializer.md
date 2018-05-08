---
title: 'Cómo: Crear una colección usada por un inicializador de colección (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
ms.openlocfilehash: 6158b6f02d95260e2955e77d732fae8b8d9d5e04
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a>Cómo: Crear una colección usada por un inicializador de colección (Visual Basic)
Cuando se usa un inicializador de colección para crear una colección, el compilador de Visual Basic busca un `Add` método del tipo de colección para el que los parámetros para el `Add` método coincidan con los tipos de los valores en el inicializador de colección. Esto `Add` método se usa para rellenar la colección con los valores desde el inicializador de colección.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra un `OrderCollection` colección que contiene un complemento público `Add` método que puede usar un inicializador de colección para agregar objetos de tipo `Order`. El `Add` método le permite usar la sintaxis de inicializador de colección abreviada.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_3.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_4.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Inicializadores de colección](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
 [Crear un método de extensión Add usado por un inicializador de colección](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
