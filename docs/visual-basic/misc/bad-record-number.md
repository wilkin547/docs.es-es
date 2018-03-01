---
title: "Número de registro incorrecto"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: be04987353498775ec7dcef50b6acc1e6b4ec149
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="bad-record-number"></a><span data-ttu-id="4cf90-102">Número de registro incorrecto</span><span class="sxs-lookup"><span data-stu-id="4cf90-102">Bad record number</span></span>
<span data-ttu-id="4cf90-103">El número de registro de la instrucción `a FileGet`, `FilePut`, `FileGetObject`o `FilePutObject` es menor o igual que cero.</span><span class="sxs-lookup"><span data-stu-id="4cf90-103">The record number in `a FileGet`, `FilePut`, `FileGetObject`, or `FilePutObject` statement is less than or equal to zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4cf90-104">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="4cf90-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="4cf90-105">Compruebe los cálculos usados para generar el número de registro.</span><span class="sxs-lookup"><span data-stu-id="4cf90-105">Check the calculations used in generating the record number.</span></span> <span data-ttu-id="4cf90-106">Compruebe la ortografía de las variables que contienen el número de registro o usadas para calcular números de registro.</span><span class="sxs-lookup"><span data-stu-id="4cf90-106">Verify spelling of the variables containing the record number or used in calculating record numbers.</span></span> <span data-ttu-id="4cf90-107">Un nombre de variable mal escrito se declara implícitamente y se inicializa en cero, a menos que use `Option Explicit On` en el módulo.</span><span class="sxs-lookup"><span data-stu-id="4cf90-107">A misspelled variable name is implicitly declared and initialized to zero, unless you used `Option Explicit On` in the module.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cf90-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="4cf90-108">See Also</span></span>  
 [<span data-ttu-id="4cf90-109">Option Explicit (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4cf90-109">Option Explicit Statement</span></span>](../../visual-basic/language-reference/statements/option-explicit-statement.md)
