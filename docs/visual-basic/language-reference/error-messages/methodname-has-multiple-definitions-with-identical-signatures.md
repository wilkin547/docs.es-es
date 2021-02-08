---
description: "Más información sobre: BC30269: ' <methodname> ' tiene varias definiciones con firmas idénticas"
title: "'<methodname>' tiene varias definiciones con firmas idénticas"
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: 7364ee7a308fab96afce268ff0c92cd45717f1bd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795812"
---
# <a name="bc30269-methodname-has-multiple-definitions-with-identical-signatures"></a><span data-ttu-id="4984f-103">BC30269: ' \<methodname> ' tiene varias definiciones con firmas idénticas</span><span class="sxs-lookup"><span data-stu-id="4984f-103">BC30269: '\<methodname>' has multiple definitions with identical signatures</span></span>

<span data-ttu-id="4984f-104">Una `Function` `Sub` declaración de procedimiento o usa el nombre de procedimiento idéntico y la lista de argumentos como una declaración anterior.</span><span class="sxs-lookup"><span data-stu-id="4984f-104">A `Function` or `Sub` procedure declaration uses the identical procedure name and argument list as a previous declaration.</span></span> <span data-ttu-id="4984f-105">Una posible causa es un intento de sobrecargar el procedimiento original.</span><span class="sxs-lookup"><span data-stu-id="4984f-105">One possible cause is an attempt to overload the original procedure.</span></span> <span data-ttu-id="4984f-106">Los procedimientos sobrecargados deben tener listas de argumentos diferentes.</span><span class="sxs-lookup"><span data-stu-id="4984f-106">Overloaded procedures must have different argument lists.</span></span>

 <span data-ttu-id="4984f-107">**Identificador de error:** BC30269</span><span class="sxs-lookup"><span data-stu-id="4984f-107">**Error ID:** BC30269</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="4984f-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="4984f-108">To correct this error</span></span>

- <span data-ttu-id="4984f-109">Cambie el nombre del procedimiento o la lista de argumentos, o bien Quite la declaración duplicada.</span><span class="sxs-lookup"><span data-stu-id="4984f-109">Change the procedure name or the argument list, or remove the duplicate declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="4984f-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="4984f-110">See also</span></span>

- [<span data-ttu-id="4984f-111">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="4984f-111">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="4984f-112">Consideraciones sobre la sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="4984f-112">Considerations in Overloading Procedures</span></span>](../../programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
