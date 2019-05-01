---
title: Procedimiento Crear una colección usada por un inicializador de colección (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
ms.openlocfilehash: 75c280b57df03bde173c740123cccda278536dc1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053631"
---
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a>Procedimiento Crear una colección usada por un inicializador de colección (Visual Basic)
Cuando se usa un inicializador de colección para crear una colección, el compilador de Visual Basic busca un `Add` método del tipo de colección para el que los parámetros para el `Add` método coinciden con los tipos de los valores del inicializador de colección. Esto `Add` método se usa para rellenar la colección con los valores del inicializador de colección.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se muestra un `OrderCollection` colección que contiene una pública `Add` método que puede usar un inicializador de colección para agregar objetos de tipo `Order`. El `Add` método le permite usar la sintaxis de inicializador de colección abreviada.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#4)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#3)]  
  
## <a name="see-also"></a>Vea también

- [Inicializadores de colección](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Cómo: Crear un método de extensión utilizado por un inicializador de colección Add](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
