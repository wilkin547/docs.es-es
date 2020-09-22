---
title: Se esperaba un inicializador
ms.date: 07/20/2015
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
ms.openlocfilehash: 2c5a65443dc16a600e25fcf6dfd11c4597b3a086
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873954"
---
# <a name="initializer-expected"></a><span data-ttu-id="131cb-102">Se esperaba un inicializador</span><span class="sxs-lookup"><span data-stu-id="131cb-102">Initializer expected</span></span>

<span data-ttu-id="131cb-103">Ha intentado declarar una instancia de una clase usando un inicializador de objeto en el que la lista de inicialización está vacía, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="131cb-103">You have tried to declare an instance of a class by using an object initializer in which the initialization list is empty, as shown in the following example.</span></span>  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 <span data-ttu-id="131cb-104">Debe inicializarse al menos un campo o una propiedad en la lista de inicializadores, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="131cb-104">At least one field or property must be initialized in the initializer list, as shown in the following example.</span></span>  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 <span data-ttu-id="131cb-105">**Identificador de error:** BC30996</span><span class="sxs-lookup"><span data-stu-id="131cb-105">**Error ID:** BC30996</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="131cb-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="131cb-106">To correct this error</span></span>  
  
1. <span data-ttu-id="131cb-107">Inicialice al menos un campo o propiedad en el inicializador o no use un inicializador de objeto.</span><span class="sxs-lookup"><span data-stu-id="131cb-107">Initialize at least one field or property in the initializer, or do not use an object initializer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="131cb-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="131cb-108">See also</span></span>

- [<span data-ttu-id="131cb-109">Inicializadores de objeto: tipos con nombre y anónimos</span><span class="sxs-lookup"><span data-stu-id="131cb-109">Object Initializers: Named and Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="131cb-110">Procedimiento para declarar un objeto mediante un inicializador de objeto</span><span class="sxs-lookup"><span data-stu-id="131cb-110">How to: Declare an Object by Using an Object Initializer</span></span>](../../programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
