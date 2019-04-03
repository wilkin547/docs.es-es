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
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="474b5-102">Filtrar Crear una extensión método Add usado por un inicializador de colección (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="474b5-102">How to: Create an Add Extension Method Used by a Collection Initializer (Visual Basic)</span></span>
<span data-ttu-id="474b5-103">Cuando se usa un inicializador de colección para crear una colección, el compilador de Visual Basic busca un `Add` método del tipo de colección para el que los parámetros para el `Add` método coinciden con los tipos de los valores del inicializador de colección.</span><span class="sxs-lookup"><span data-stu-id="474b5-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="474b5-104">Esto `Add` método se usa para rellenar la colección con los valores del inicializador de colección.</span><span class="sxs-lookup"><span data-stu-id="474b5-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
 <span data-ttu-id="474b5-105">Si no hay coincidencia `Add` método existe y no se puede modificar el código de la colección, puede agregar un método de extensión denominado `Add` que toma los parámetros requeridos por el inicializador de colección.</span><span class="sxs-lookup"><span data-stu-id="474b5-105">If no matching `Add` method exists and you cannot modify the code for the collection, you can add an extension method called `Add` that takes the parameters that are required by the collection initializer.</span></span> <span data-ttu-id="474b5-106">Normalmente, esto es lo que necesita hacer al usar inicializadores de colección para las colecciones genéricas.</span><span class="sxs-lookup"><span data-stu-id="474b5-106">This is typically what you need to do when you use collection initializers for generic collections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="474b5-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="474b5-107">Example</span></span>  
 <span data-ttu-id="474b5-108">El ejemplo siguiente muestra cómo agregar un método de extensión para el tipo genérico <xref:System.Collections.Generic.List%601> escriba por lo que puede utilizarse un inicializador de colección para agregar objetos de tipo `Employee`.</span><span class="sxs-lookup"><span data-stu-id="474b5-108">The following example shows how to add an extension method to the generic <xref:System.Collections.Generic.List%601> type so that a collection initializer can be used to add objects of type `Employee`.</span></span> <span data-ttu-id="474b5-109">El método de extensión le permite usar la sintaxis de inicializador de colección abreviada.</span><span class="sxs-lookup"><span data-stu-id="474b5-109">The extension method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="474b5-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="474b5-110">See also</span></span>

- [<span data-ttu-id="474b5-111">Inicializadores de colección</span><span class="sxs-lookup"><span data-stu-id="474b5-111">Collection Initializers</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [<span data-ttu-id="474b5-112">Cómo: Crear una colección usada por un inicializador de colección</span><span class="sxs-lookup"><span data-stu-id="474b5-112">How to: Create a Collection Used by a Collection Initializer</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
