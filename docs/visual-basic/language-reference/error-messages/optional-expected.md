---
title: Se esperaba 'Optional'
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: e212939cf814a9ac632571b2203f2f256dea61ae
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873600"
---
# <a name="optional-expected"></a><span data-ttu-id="b63e4-102">Se esperaba 'Optional'</span><span class="sxs-lookup"><span data-stu-id="b63e4-102">'Optional' expected</span></span>

<span data-ttu-id="b63e4-103">Un argumento opcional en una declaración de procedimiento va seguido de un argumento necesario.</span><span class="sxs-lookup"><span data-stu-id="b63e4-103">An optional argument in a procedure declaration is followed by a required argument.</span></span> <span data-ttu-id="b63e4-104">Cada argumento que siga a un argumento opcional también debe ser opcional.</span><span class="sxs-lookup"><span data-stu-id="b63e4-104">Every argument following an optional argument must also be optional.</span></span>  
  
 <span data-ttu-id="b63e4-105">**Identificador de error:** BC30202</span><span class="sxs-lookup"><span data-stu-id="b63e4-105">**Error ID:** BC30202</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b63e4-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="b63e4-106">To correct this error</span></span>  
  
1. <span data-ttu-id="b63e4-107">Si el argumento está pensado para ser necesario, muévalo para que preceda al primer argumento opcional de la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="b63e4-107">If the argument is intended to be required, move it to precede the first optional argument in the argument list.</span></span>  
  
2. <span data-ttu-id="b63e4-108">Si el argumento está pensado para ser opcional, use la `Optional` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="b63e4-108">If the argument is intended to be optional, use the `Optional` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b63e4-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b63e4-109">See also</span></span>

- [<span data-ttu-id="b63e4-110">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="b63e4-110">Optional Parameters</span></span>](../../programming-guide/language-features/procedures/optional-parameters.md)
