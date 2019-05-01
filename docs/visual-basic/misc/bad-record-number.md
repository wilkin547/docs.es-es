---
title: Número de registro incorrecto
ms.date: 07/20/2015
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
ms.openlocfilehash: abd0a1467c0991a40b93e74a1d7a7889367fb8ca
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61977033"
---
# <a name="bad-record-number"></a><span data-ttu-id="3adbb-102">Número de registro incorrecto</span><span class="sxs-lookup"><span data-stu-id="3adbb-102">Bad record number</span></span>
<span data-ttu-id="3adbb-103">El número de registro de la instrucción `a FileGet`, `FilePut`, `FileGetObject`o `FilePutObject` es menor o igual que cero.</span><span class="sxs-lookup"><span data-stu-id="3adbb-103">The record number in `a FileGet`, `FilePut`, `FileGetObject`, or `FilePutObject` statement is less than or equal to zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3adbb-104">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="3adbb-104">To correct this error</span></span>  
  
1. <span data-ttu-id="3adbb-105">Compruebe los cálculos usados para generar el número de registro.</span><span class="sxs-lookup"><span data-stu-id="3adbb-105">Check the calculations used in generating the record number.</span></span> <span data-ttu-id="3adbb-106">Compruebe la ortografía de las variables que contienen el número de registro o usadas para calcular números de registro.</span><span class="sxs-lookup"><span data-stu-id="3adbb-106">Verify spelling of the variables containing the record number or used in calculating record numbers.</span></span> <span data-ttu-id="3adbb-107">Un nombre de variable mal escrito se declara implícitamente y se inicializa en cero, a menos que use `Option Explicit On` en el módulo.</span><span class="sxs-lookup"><span data-stu-id="3adbb-107">A misspelled variable name is implicitly declared and initialized to zero, unless you used `Option Explicit On` in the module.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3adbb-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="3adbb-108">See also</span></span>

- [<span data-ttu-id="3adbb-109">Option Explicit (instrucción)</span><span class="sxs-lookup"><span data-stu-id="3adbb-109">Option Explicit Statement</span></span>](../../visual-basic/language-reference/statements/option-explicit-statement.md)
