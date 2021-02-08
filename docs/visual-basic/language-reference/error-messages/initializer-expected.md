---
description: 'Más información acerca de: BC30996: se esperaba un inicializador'
title: Se esperaba un inicializador
ms.date: 07/20/2015
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
ms.openlocfilehash: a9859dc319ec53cb42785d71b21447a097ce30f6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796059"
---
# <a name="bc30996-initializer-expected"></a><span data-ttu-id="b34b8-103">BC30996: se esperaba un inicializador</span><span class="sxs-lookup"><span data-stu-id="b34b8-103">BC30996: Initializer expected</span></span>

<span data-ttu-id="b34b8-104">Ha intentado declarar una instancia de una clase usando un inicializador de objeto en el que la lista de inicialización está vacía, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b34b8-104">You have tried to declare an instance of a class by using an object initializer in which the initialization list is empty, as shown in the following example.</span></span>

 `' Not valid.`

 `' Dim aStudent As New Student With {}`

 <span data-ttu-id="b34b8-105">Debe inicializarse al menos un campo o una propiedad en la lista de inicializadores, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b34b8-105">At least one field or property must be initialized in the initializer list, as shown in the following example.</span></span>

 `Dim aStudent As New Student With {.year = "Senior"}`

 <span data-ttu-id="b34b8-106">**Identificador de error:** BC30996</span><span class="sxs-lookup"><span data-stu-id="b34b8-106">**Error ID:** BC30996</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="b34b8-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="b34b8-107">To correct this error</span></span>

- <span data-ttu-id="b34b8-108">Inicialice al menos un campo o propiedad en el inicializador o no use un inicializador de objeto.</span><span class="sxs-lookup"><span data-stu-id="b34b8-108">Initialize at least one field or property in the initializer, or do not use an object initializer.</span></span>

## <a name="see-also"></a><span data-ttu-id="b34b8-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="b34b8-109">See also</span></span>

- [<span data-ttu-id="b34b8-110">Inicializadores de objeto: tipos con nombre y anónimos</span><span class="sxs-lookup"><span data-stu-id="b34b8-110">Object Initializers: Named and Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="b34b8-111">Procedimiento para declarar un objeto mediante un inicializador de objeto</span><span class="sxs-lookup"><span data-stu-id="b34b8-111">How to: Declare an Object by Using an Object Initializer</span></span>](../../programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
