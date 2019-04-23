---
title: Número de registro incorrecto
ms.date: 07/20/2015
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
ms.openlocfilehash: abd0a1467c0991a40b93e74a1d7a7889367fb8ca
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59340807"
---
# <a name="bad-record-number"></a><span data-ttu-id="ff097-102">Número de registro incorrecto</span><span class="sxs-lookup"><span data-stu-id="ff097-102">Bad record number</span></span>
<span data-ttu-id="ff097-103">El número de registro de la instrucción `a FileGet`, `FilePut`, `FileGetObject`o `FilePutObject` es menor o igual que cero.</span><span class="sxs-lookup"><span data-stu-id="ff097-103">The record number in `a FileGet`, `FilePut`, `FileGetObject`, or `FilePutObject` statement is less than or equal to zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ff097-104">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="ff097-104">To correct this error</span></span>  
  
1. <span data-ttu-id="ff097-105">Compruebe los cálculos usados para generar el número de registro.</span><span class="sxs-lookup"><span data-stu-id="ff097-105">Check the calculations used in generating the record number.</span></span> <span data-ttu-id="ff097-106">Compruebe la ortografía de las variables que contienen el número de registro o usadas para calcular números de registro.</span><span class="sxs-lookup"><span data-stu-id="ff097-106">Verify spelling of the variables containing the record number or used in calculating record numbers.</span></span> <span data-ttu-id="ff097-107">Un nombre de variable mal escrito se declara implícitamente y se inicializa en cero, a menos que use `Option Explicit On` en el módulo.</span><span class="sxs-lookup"><span data-stu-id="ff097-107">A misspelled variable name is implicitly declared and initialized to zero, unless you used `Option Explicit On` in the module.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff097-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff097-108">See also</span></span>

- [<span data-ttu-id="ff097-109">Option Explicit (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ff097-109">Option Explicit Statement</span></span>](../../visual-basic/language-reference/statements/option-explicit-statement.md)
