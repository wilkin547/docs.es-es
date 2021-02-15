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
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="edbc3-103">Cómo: Crear una colección usada por un inicializador de colección (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="edbc3-103">How to: Create a Collection Used by a Collection Initializer (Visual Basic)</span></span>

<span data-ttu-id="edbc3-104">Cuando se usa un inicializador de colección para crear una colección, el compilador Visual Basic busca un `Add` método del tipo de colección para el que los parámetros del `Add` método coinciden con los tipos de los valores del inicializador de colección.</span><span class="sxs-lookup"><span data-stu-id="edbc3-104">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="edbc3-105">Este `Add` método se usa para rellenar la colección con los valores del inicializador de colección.</span><span class="sxs-lookup"><span data-stu-id="edbc3-105">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="edbc3-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="edbc3-106">Example</span></span>  

 <span data-ttu-id="edbc3-107">En el ejemplo siguiente se muestra una `OrderCollection` colección que contiene un `Add` método público que un inicializador de colección puede usar para agregar objetos de tipo `Order` .</span><span class="sxs-lookup"><span data-stu-id="edbc3-107">The following example shows an `OrderCollection` collection that contains a public `Add` method that a collection initializer can use to add objects of type `Order`.</span></span> <span data-ttu-id="edbc3-108">El `Add` método le permite usar la sintaxis de inicializador de colección abreviada.</span><span class="sxs-lookup"><span data-stu-id="edbc3-108">The `Add` method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#4)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="edbc3-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="edbc3-109">See also</span></span>

- [<span data-ttu-id="edbc3-110">Inicializadores de colección</span><span class="sxs-lookup"><span data-stu-id="edbc3-110">Collection Initializers</span></span>](index.md)
- [<span data-ttu-id="edbc3-111">Procedimiento para crear un método de extensión de adiciones usado por un inicializador de colección</span><span class="sxs-lookup"><span data-stu-id="edbc3-111">How to: Create an Add Extension Method Used by a Collection Initializer</span></span>](how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
