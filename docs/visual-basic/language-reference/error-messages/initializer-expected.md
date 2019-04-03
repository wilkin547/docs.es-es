---
title: Se esperaba un inicializador
ms.date: 07/20/2015
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
ms.openlocfilehash: 77cfeb57bc313ded2d2c4d5a0c59041c5c19f515
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826085"
---
# <a name="initializer-expected"></a><span data-ttu-id="a7735-102">Se esperaba un inicializador</span><span class="sxs-lookup"><span data-stu-id="a7735-102">Initializer expected</span></span>
<span data-ttu-id="a7735-103">Ha intentado declarar una instancia de una clase con un inicializador de objeto en el que la lista de inicialización está vacía, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a7735-103">You have tried to declare an instance of a class by using an object initializer in which the initialization list is empty, as shown in the following example.</span></span>  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 <span data-ttu-id="a7735-104">Al menos un campo o propiedad se debe inicializar en la lista de inicializadores, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a7735-104">At least one field or property must be initialized in the initializer list, as shown in the following example.</span></span>  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 <span data-ttu-id="a7735-105">**Identificador de error:** BC30996</span><span class="sxs-lookup"><span data-stu-id="a7735-105">**Error ID:** BC30996</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a7735-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="a7735-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="a7735-107">Inicializar al menos un campo o propiedad en el inicializador o no use un inicializador de objeto.</span><span class="sxs-lookup"><span data-stu-id="a7735-107">Initialize at least one field or property in the initializer, or do not use an object initializer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7735-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7735-108">See also</span></span>

- [<span data-ttu-id="a7735-109">Inicializadores de objeto: Tipos con nombre y anónimos</span><span class="sxs-lookup"><span data-stu-id="a7735-109">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="a7735-110">Cómo: Declarar un objeto usando un inicializador de objeto</span><span class="sxs-lookup"><span data-stu-id="a7735-110">How to: Declare an Object by Using an Object Initializer</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
