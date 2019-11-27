---
title: 'Cómo: Crear una colección usada por un inicializador de colección'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
ms.openlocfilehash: 5eaf9e828455bf2accda86ab52a1ce645f10b9ee
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349060"
---
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a>Cómo: Crear una colección usada por un inicializador de colección (Visual Basic)
Cuando se usa un inicializador de colección para crear una colección, el compilador Visual Basic busca un método `Add` del tipo de colección para el que los parámetros del método `Add` coinciden con los tipos de los valores del inicializador de colección. Este método `Add` se usa para rellenar la colección con los valores del inicializador de colección.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra una colección `OrderCollection` que contiene un método de `Add` público que un inicializador de colección puede usar para agregar objetos de tipo `Order`. El método `Add` permite utilizar la sintaxis de inicializador de colección abreviada.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#4)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#3)]  
  
## <a name="see-also"></a>Vea también

- [Inicializadores de colección](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Crear un método de extensión Add usado por un inicializador de colección](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
