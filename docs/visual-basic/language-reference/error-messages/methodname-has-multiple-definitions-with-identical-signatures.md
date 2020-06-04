---
title: "'<methodname>' tiene varias definiciones con firmas idénticas"
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: 3b397711cc2fb1fd0c1dfd76899b162ab5fc1542
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397238"
---
# <a name="methodname-has-multiple-definitions-with-identical-signatures"></a><span data-ttu-id="7ff74-102">'\<methodname>' tiene varias definiciones con firmas idénticas</span><span class="sxs-lookup"><span data-stu-id="7ff74-102">'\<methodname>' has multiple definitions with identical signatures</span></span>
<span data-ttu-id="7ff74-103">Una `Function` `Sub` declaración de procedimiento o usa el nombre de procedimiento idéntico y la lista de argumentos como una declaración anterior.</span><span class="sxs-lookup"><span data-stu-id="7ff74-103">A `Function` or `Sub` procedure declaration uses the identical procedure name and argument list as a previous declaration.</span></span> <span data-ttu-id="7ff74-104">Una posible causa es un intento de sobrecargar el procedimiento original.</span><span class="sxs-lookup"><span data-stu-id="7ff74-104">One possible cause is an attempt to overload the original procedure.</span></span> <span data-ttu-id="7ff74-105">Los procedimientos sobrecargados deben tener listas de argumentos diferentes.</span><span class="sxs-lookup"><span data-stu-id="7ff74-105">Overloaded procedures must have different argument lists.</span></span>  
  
 <span data-ttu-id="7ff74-106">**Identificador de error:** BC30269</span><span class="sxs-lookup"><span data-stu-id="7ff74-106">**Error ID:** BC30269</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7ff74-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="7ff74-107">To correct this error</span></span>  
  
- <span data-ttu-id="7ff74-108">Cambie el nombre del procedimiento o la lista de argumentos, o bien Quite la declaración duplicada.</span><span class="sxs-lookup"><span data-stu-id="7ff74-108">Change the procedure name or the argument list, or remove the duplicate declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ff74-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7ff74-109">See also</span></span>

- [<span data-ttu-id="7ff74-110">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="7ff74-110">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="7ff74-111">Consideraciones sobre la sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="7ff74-111">Considerations in Overloading Procedures</span></span>](../../programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
