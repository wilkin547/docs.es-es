---
description: 'Más información sobre: BC36599: el nombre de la variable de rango solo se puede inferir de un nombre simple o completo sin argumentos'
title: El nombre de una variable de rango sólo se puede inferir a partir de un nombre simple o completo sin argumentos
ms.date: 07/20/2015
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
ms.openlocfilehash: b729b6786f9b7803a794b9a4e786d94fa41a57ec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792068"
---
# <a name="bc36599-range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="40b9c-103">BC36599: el nombre de la variable de rango solo se puede inferir de un nombre simple o completo sin argumentos</span><span class="sxs-lookup"><span data-stu-id="40b9c-103">BC36599: Range variable name can be inferred only from a simple or qualified name with no arguments</span></span>

<span data-ttu-id="40b9c-104">Un elemento de programación que toma uno o más argumentos se incluye en una consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="40b9c-104">A programming element that takes one or more arguments is included in a LINQ query.</span></span> <span data-ttu-id="40b9c-105">El compilador no puede inferir una variable de rango de ese elemento de programación.</span><span class="sxs-lookup"><span data-stu-id="40b9c-105">The compiler is unable to infer a range variable from that programming element.</span></span>

<span data-ttu-id="40b9c-106">**Identificador de error:** BC36599</span><span class="sxs-lookup"><span data-stu-id="40b9c-106">**Error ID:** BC36599</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="40b9c-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="40b9c-107">To correct this error</span></span>

<span data-ttu-id="40b9c-108">Proporcione un nombre de variable explícito para el elemento de programación, tal y como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="40b9c-108">Supply an explicit variable name for the programming element, as shown in the following code:</span></span>

```vb
Dim query = From var1 In collection1
            Select VariableAlias= SampleFunction(var1), var1
```

## <a name="see-also"></a><span data-ttu-id="40b9c-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="40b9c-109">See also</span></span>

- [<span data-ttu-id="40b9c-110">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="40b9c-110">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="40b9c-111">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="40b9c-111">Select Clause</span></span>](../queries/select-clause.md)
