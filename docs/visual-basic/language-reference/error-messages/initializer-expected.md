---
title: Se esperaba un inicializador
ms.date: 07/20/2015
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
ms.openlocfilehash: cbe77bab3e4f8bf2094c70c1c16d95ee897c729e
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163017"
---
# <a name="bc30996-initializer-expected"></a><span data-ttu-id="42dd8-102">BC30996: se esperaba un inicializador</span><span class="sxs-lookup"><span data-stu-id="42dd8-102">BC30996: Initializer expected</span></span>

<span data-ttu-id="42dd8-103">Ha intentado declarar una instancia de una clase usando un inicializador de objeto en el que la lista de inicialización está vacía, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="42dd8-103">You have tried to declare an instance of a class by using an object initializer in which the initialization list is empty, as shown in the following example.</span></span>

 `' Not valid.`

 `' Dim aStudent As New Student With {}`

 <span data-ttu-id="42dd8-104">Debe inicializarse al menos un campo o una propiedad en la lista de inicializadores, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="42dd8-104">At least one field or property must be initialized in the initializer list, as shown in the following example.</span></span>

 `Dim aStudent As New Student With {.year = "Senior"}`

 <span data-ttu-id="42dd8-105">**Identificador de error:** BC30996</span><span class="sxs-lookup"><span data-stu-id="42dd8-105">**Error ID:** BC30996</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="42dd8-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="42dd8-106">To correct this error</span></span>

- <span data-ttu-id="42dd8-107">Inicialice al menos un campo o propiedad en el inicializador o no use un inicializador de objeto.</span><span class="sxs-lookup"><span data-stu-id="42dd8-107">Initialize at least one field or property in the initializer, or do not use an object initializer.</span></span>

## <a name="see-also"></a><span data-ttu-id="42dd8-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="42dd8-108">See also</span></span>

- [<span data-ttu-id="42dd8-109">Inicializadores de objeto: tipos con nombre y anónimos</span><span class="sxs-lookup"><span data-stu-id="42dd8-109">Object Initializers: Named and Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="42dd8-110">Procedimiento para declarar un objeto mediante un inicializador de objeto</span><span class="sxs-lookup"><span data-stu-id="42dd8-110">How to: Declare an Object by Using an Object Initializer</span></span>](../../programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
