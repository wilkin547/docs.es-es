---
title: "Cómo: Crear una colección usada por un inicializador de colección (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: collection initializers [Visual Basic]
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cff862f16530bc268628d9406ae81d23f2761926
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="689fc-102">Cómo: Crear una colección usada por un inicializador de colección (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="689fc-102">How to: Create a Collection Used by a Collection Initializer (Visual Basic)</span></span>
<span data-ttu-id="689fc-103">Cuando se usa un inicializador de colección para crear una colección, el compilador de Visual Basic busca un `Add` método del tipo de colección para el que los parámetros para el `Add` método coincidan con los tipos de los valores en el inicializador de colección.</span><span class="sxs-lookup"><span data-stu-id="689fc-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="689fc-104">Esto `Add` método se usa para rellenar la colección con los valores desde el inicializador de colección.</span><span class="sxs-lookup"><span data-stu-id="689fc-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="689fc-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="689fc-105">Example</span></span>  
 <span data-ttu-id="689fc-106">El ejemplo siguiente muestra un `OrderCollection` colección que contiene un complemento público `Add` método que puede usar un inicializador de colección para agregar objetos de tipo `Order`.</span><span class="sxs-lookup"><span data-stu-id="689fc-106">The following example shows an `OrderCollection` collection that contains a public `Add` method that a collection initializer can use to add objects of type `Order`.</span></span> <span data-ttu-id="689fc-107">El `Add` método le permite usar la sintaxis de inicializador de colección abreviada.</span><span class="sxs-lookup"><span data-stu-id="689fc-107">The `Add` method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_3.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="689fc-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="689fc-108">See Also</span></span>  
 [<span data-ttu-id="689fc-109">Inicializadores de colección</span><span class="sxs-lookup"><span data-stu-id="689fc-109">Collection Initializers</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
 [<span data-ttu-id="689fc-110">Crear un método de extensión Add usado por un inicializador de colección</span><span class="sxs-lookup"><span data-stu-id="689fc-110">How to: Create an Add Extension Method Used by a Collection Initializer</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
