---
description: 'Más información acerca de: número de registro incorrecto'
title: Número de registro incorrecto
ms.date: 07/20/2015
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
ms.openlocfilehash: a250419c131f75381426705d52563732322631cb
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100461000"
---
# <a name="bad-record-number"></a><span data-ttu-id="1fbd6-103">Número de registro incorrecto</span><span class="sxs-lookup"><span data-stu-id="1fbd6-103">Bad record number</span></span>

<span data-ttu-id="1fbd6-104">El número de registro de la instrucción `a FileGet`, `FilePut`, `FileGetObject`o `FilePutObject` es menor o igual que cero.</span><span class="sxs-lookup"><span data-stu-id="1fbd6-104">The record number in `a FileGet`, `FilePut`, `FileGetObject`, or `FilePutObject` statement is less than or equal to zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1fbd6-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="1fbd6-105">To correct this error</span></span>  
  
1. <span data-ttu-id="1fbd6-106">Compruebe los cálculos usados para generar el número de registro.</span><span class="sxs-lookup"><span data-stu-id="1fbd6-106">Check the calculations used in generating the record number.</span></span> <span data-ttu-id="1fbd6-107">Compruebe la ortografía de las variables que contienen el número de registro o usadas para calcular números de registro.</span><span class="sxs-lookup"><span data-stu-id="1fbd6-107">Verify spelling of the variables containing the record number or used in calculating record numbers.</span></span> <span data-ttu-id="1fbd6-108">Un nombre de variable mal escrito se declara implícitamente y se inicializa en cero, a menos que use `Option Explicit On` en el módulo.</span><span class="sxs-lookup"><span data-stu-id="1fbd6-108">A misspelled variable name is implicitly declared and initialized to zero, unless you used `Option Explicit On` in the module.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fbd6-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1fbd6-109">See also</span></span>

- [<span data-ttu-id="1fbd6-110">Option Explicit (instrucción)</span><span class="sxs-lookup"><span data-stu-id="1fbd6-110">Option Explicit Statement</span></span>](../language-reference/statements/option-explicit-statement.md)
