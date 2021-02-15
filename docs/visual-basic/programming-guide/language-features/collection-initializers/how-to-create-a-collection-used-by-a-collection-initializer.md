---
description: 'Más información acerca de cómo: crear una colección usada por un inicializador de colección (Visual Basic)'
title: Procedimiento para crear una colección usada por un inicializador de colección
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
ms.openlocfilehash: 09928cb0fbeb0346fd0e1148ffcd6ddce54279c0
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100460025"
---
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a>Cómo: Crear una colección usada por un inicializador de colección (Visual Basic)

Cuando se usa un inicializador de colección para crear una colección, el compilador Visual Basic busca un `Add` método del tipo de colección para el que los parámetros del `Add` método coinciden con los tipos de los valores del inicializador de colección. Este `Add` método se usa para rellenar la colección con los valores del inicializador de colección.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra una `OrderCollection` colección que contiene un `Add` método público que un inicializador de colección puede usar para agregar objetos de tipo `Order` . El `Add` método le permite usar la sintaxis de inicializador de colección abreviada.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#4)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#3)]  
  
## <a name="see-also"></a>Consulte también

- [Inicializadores de colección](index.md)
- [Procedimiento para crear un método de extensión de adiciones usado por un inicializador de colección](how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
