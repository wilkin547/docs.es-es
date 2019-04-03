---
title: Filtrar Crear una extensión método Add usado por un inicializador de colección (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: a5af41e25b8f82aa173e2df28cc41b313c8d68dd
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825409"
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a>Filtrar Crear una extensión método Add usado por un inicializador de colección (Visual Basic)
Cuando se usa un inicializador de colección para crear una colección, el compilador de Visual Basic busca un `Add` método del tipo de colección para el que los parámetros para el `Add` método coinciden con los tipos de los valores del inicializador de colección. Esto `Add` método se usa para rellenar la colección con los valores del inicializador de colección.  
  
 Si no hay coincidencia `Add` método existe y no se puede modificar el código de la colección, puede agregar un método de extensión denominado `Add` que toma los parámetros requeridos por el inicializador de colección. Normalmente, esto es lo que necesita hacer al usar inicializadores de colección para las colecciones genéricas.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo agregar un método de extensión para el tipo genérico <xref:System.Collections.Generic.List%601> escriba por lo que puede utilizarse un inicializador de colección para agregar objetos de tipo `Employee`. El método de extensión le permite usar la sintaxis de inicializador de colección abreviada.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#3)]  
  
## <a name="see-also"></a>Vea también

- [Inicializadores de colección](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Cómo: Crear una colección usada por un inicializador de colección](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
