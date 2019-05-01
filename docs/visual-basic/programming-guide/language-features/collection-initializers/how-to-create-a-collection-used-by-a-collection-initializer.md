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
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="33246-102">Procedimiento Crear una colección usada por un inicializador de colección (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="33246-102">How to: Create a Collection Used by a Collection Initializer (Visual Basic)</span></span>
<span data-ttu-id="33246-103">Cuando se usa un inicializador de colección para crear una colección, el compilador de Visual Basic busca un `Add` método del tipo de colección para el que los parámetros para el `Add` método coinciden con los tipos de los valores del inicializador de colección.</span><span class="sxs-lookup"><span data-stu-id="33246-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="33246-104">Esto `Add` método se usa para rellenar la colección con los valores del inicializador de colección.</span><span class="sxs-lookup"><span data-stu-id="33246-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33246-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="33246-105">Example</span></span>  
 <span data-ttu-id="33246-106">El ejemplo siguiente se muestra un `OrderCollection` colección que contiene una pública `Add` método que puede usar un inicializador de colección para agregar objetos de tipo `Order`.</span><span class="sxs-lookup"><span data-stu-id="33246-106">The following example shows an `OrderCollection` collection that contains a public `Add` method that a collection initializer can use to add objects of type `Order`.</span></span> <span data-ttu-id="33246-107">El `Add` método le permite usar la sintaxis de inicializador de colección abreviada.</span><span class="sxs-lookup"><span data-stu-id="33246-107">The `Add` method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#4)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="33246-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="33246-108">See also</span></span>

- [<span data-ttu-id="33246-109">Inicializadores de colección</span><span class="sxs-lookup"><span data-stu-id="33246-109">Collection Initializers</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [<span data-ttu-id="33246-110">Cómo: Crear un método de extensión utilizado por un inicializador de colección Add</span><span class="sxs-lookup"><span data-stu-id="33246-110">How to: Create an Add Extension Method Used by a Collection Initializer</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
