---
title: "'<methodname>' tiene varias definiciones con firmas idénticas"
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: 663b22421d1a0e401cfb3c135c99bd097163a78b
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160371"
---
# <a name="bc30269-methodname-has-multiple-definitions-with-identical-signatures"></a><span data-ttu-id="c7874-102">BC30269: ' \<methodname> ' tiene varias definiciones con firmas idénticas</span><span class="sxs-lookup"><span data-stu-id="c7874-102">BC30269: '\<methodname>' has multiple definitions with identical signatures</span></span>

<span data-ttu-id="c7874-103">Una `Function` `Sub` declaración de procedimiento o usa el nombre de procedimiento idéntico y la lista de argumentos como una declaración anterior.</span><span class="sxs-lookup"><span data-stu-id="c7874-103">A `Function` or `Sub` procedure declaration uses the identical procedure name and argument list as a previous declaration.</span></span> <span data-ttu-id="c7874-104">Una posible causa es un intento de sobrecargar el procedimiento original.</span><span class="sxs-lookup"><span data-stu-id="c7874-104">One possible cause is an attempt to overload the original procedure.</span></span> <span data-ttu-id="c7874-105">Los procedimientos sobrecargados deben tener listas de argumentos diferentes.</span><span class="sxs-lookup"><span data-stu-id="c7874-105">Overloaded procedures must have different argument lists.</span></span>

 <span data-ttu-id="c7874-106">**Identificador de error:** BC30269</span><span class="sxs-lookup"><span data-stu-id="c7874-106">**Error ID:** BC30269</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="c7874-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="c7874-107">To correct this error</span></span>

- <span data-ttu-id="c7874-108">Cambie el nombre del procedimiento o la lista de argumentos, o bien Quite la declaración duplicada.</span><span class="sxs-lookup"><span data-stu-id="c7874-108">Change the procedure name or the argument list, or remove the duplicate declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7874-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7874-109">See also</span></span>

- [<span data-ttu-id="c7874-110">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="c7874-110">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="c7874-111">Consideraciones sobre la sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="c7874-111">Considerations in Overloading Procedures</span></span>](../../programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
