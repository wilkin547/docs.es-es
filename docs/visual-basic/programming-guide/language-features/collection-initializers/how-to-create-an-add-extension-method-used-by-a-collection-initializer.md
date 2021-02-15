---
description: 'Más información sobre: Cómo: crear un método de extensión Add usado por un inicializador de colección (Visual Basic)'
title: Procedimiento para crear un método de extensión de adiciones usado por un inicializador de colección
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: 1fbe6f438c4761ae668a6bd6a0a2c38c8efdb439
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475479"
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="0ff36-103">Cómo: Crear un método de extensión Add usado por un inicializador de colección (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0ff36-103">How to: Create an Add Extension Method Used by a Collection Initializer (Visual Basic)</span></span>

<span data-ttu-id="0ff36-104">Cuando se usa un inicializador de colección para crear una colección, el compilador Visual Basic busca un `Add` método del tipo de colección para el que los parámetros del `Add` método coinciden con los tipos de los valores del inicializador de colección.</span><span class="sxs-lookup"><span data-stu-id="0ff36-104">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="0ff36-105">Este `Add` método se usa para rellenar la colección con los valores del inicializador de colección.</span><span class="sxs-lookup"><span data-stu-id="0ff36-105">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
 <span data-ttu-id="0ff36-106">Si no `Add` existe ningún método coincidente y no se puede modificar el código de la colección, puede Agregar un método de extensión denominado `Add` que toma los parámetros necesarios para el inicializador de colección.</span><span class="sxs-lookup"><span data-stu-id="0ff36-106">If no matching `Add` method exists and you cannot modify the code for the collection, you can add an extension method called `Add` that takes the parameters that are required by the collection initializer.</span></span> <span data-ttu-id="0ff36-107">Normalmente, esto es lo que debe hacer cuando se usan inicializadores de colección para colecciones genéricas.</span><span class="sxs-lookup"><span data-stu-id="0ff36-107">This is typically what you need to do when you use collection initializers for generic collections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ff36-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ff36-108">Example</span></span>  

 <span data-ttu-id="0ff36-109">En el ejemplo siguiente se muestra cómo agregar un método de extensión al <xref:System.Collections.Generic.List%601> tipo genérico para que se pueda utilizar un inicializador de colección para agregar objetos de tipo `Employee` .</span><span class="sxs-lookup"><span data-stu-id="0ff36-109">The following example shows how to add an extension method to the generic <xref:System.Collections.Generic.List%601> type so that a collection initializer can be used to add objects of type `Employee`.</span></span> <span data-ttu-id="0ff36-110">El método de extensión le permite usar la sintaxis de inicializador de colección abreviada.</span><span class="sxs-lookup"><span data-stu-id="0ff36-110">The extension method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="0ff36-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0ff36-111">See also</span></span>

- [<span data-ttu-id="0ff36-112">Inicializadores de colección</span><span class="sxs-lookup"><span data-stu-id="0ff36-112">Collection Initializers</span></span>](index.md)
- [<span data-ttu-id="0ff36-113">Procedimiento para crear una colección usada por un inicializador de colección</span><span class="sxs-lookup"><span data-stu-id="0ff36-113">How to: Create a Collection Used by a Collection Initializer</span></span>](how-to-create-a-collection-used-by-a-collection-initializer.md)
