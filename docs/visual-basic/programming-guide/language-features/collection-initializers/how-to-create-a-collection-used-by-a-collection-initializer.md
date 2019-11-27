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
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="baa99-102">Cómo: Crear una colección usada por un inicializador de colección (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="baa99-102">How to: Create a Collection Used by a Collection Initializer (Visual Basic)</span></span>
<span data-ttu-id="baa99-103">Cuando se usa un inicializador de colección para crear una colección, el compilador Visual Basic busca un método `Add` del tipo de colección para el que los parámetros del método `Add` coinciden con los tipos de los valores del inicializador de colección.</span><span class="sxs-lookup"><span data-stu-id="baa99-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="baa99-104">Este método `Add` se usa para rellenar la colección con los valores del inicializador de colección.</span><span class="sxs-lookup"><span data-stu-id="baa99-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="baa99-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="baa99-105">Example</span></span>  
 <span data-ttu-id="baa99-106">En el ejemplo siguiente se muestra una colección `OrderCollection` que contiene un método de `Add` público que un inicializador de colección puede usar para agregar objetos de tipo `Order`.</span><span class="sxs-lookup"><span data-stu-id="baa99-106">The following example shows an `OrderCollection` collection that contains a public `Add` method that a collection initializer can use to add objects of type `Order`.</span></span> <span data-ttu-id="baa99-107">El método `Add` permite utilizar la sintaxis de inicializador de colección abreviada.</span><span class="sxs-lookup"><span data-stu-id="baa99-107">The `Add` method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#4)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="baa99-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="baa99-108">See also</span></span>

- [<span data-ttu-id="baa99-109">Inicializadores de colección</span><span class="sxs-lookup"><span data-stu-id="baa99-109">Collection Initializers</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [<span data-ttu-id="baa99-110">Crear un método de extensión Add usado por un inicializador de colección</span><span class="sxs-lookup"><span data-stu-id="baa99-110">How to: Create an Add Extension Method Used by a Collection Initializer</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
