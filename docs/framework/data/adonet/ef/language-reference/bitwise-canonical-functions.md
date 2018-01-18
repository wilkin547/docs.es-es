---
title: "Funciones canónicas bit a bit"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 993868ca-16e3-47b6-9915-c29cd63b0a21
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 1d703b2467d508324f3eb39b822c239484ac1c6e
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="bitwise-canonical-functions"></a><span data-ttu-id="122ab-102">Funciones canónicas bit a bit</span><span class="sxs-lookup"><span data-stu-id="122ab-102">Bitwise Canonical Functions</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="122ab-103"> incluye funciones canónicas bit a bit.</span><span class="sxs-lookup"><span data-stu-id="122ab-103"> includes bitwise canonical functions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="122ab-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="122ab-104">Remarks</span></span>  
 <span data-ttu-id="122ab-105">En la tabla siguiente se muestran las demás funciones canónicas de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] bit a bit.</span><span class="sxs-lookup"><span data-stu-id="122ab-105">The following table shows the bitwise [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span> <span data-ttu-id="122ab-106">Estas funciones devolverán `Null` si `Null` se proporciona la entrada.</span><span class="sxs-lookup"><span data-stu-id="122ab-106">These functions will return `Null` if `Null` input is provided.</span></span> <span data-ttu-id="122ab-107">El tipo de valor devuelto de las funciones es igual que los tipos de argumento.</span><span class="sxs-lookup"><span data-stu-id="122ab-107">The return type of the functions is the same as the argument type(s).</span></span> <span data-ttu-id="122ab-108">Los argumentos deben ser del mismo tipo, si la función toma más de uno.</span><span class="sxs-lookup"><span data-stu-id="122ab-108">Arguments must be of the same type, if the function takes more than one argument.</span></span> <span data-ttu-id="122ab-109">Para llevar a cabo operaciones bit a bit entre tipos diferentes, debe convertir explícitamente al mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="122ab-109">To perform bitwise operations across different types, you need to cast to the same type explicitly.</span></span>  
  
|<span data-ttu-id="122ab-110">Función</span><span class="sxs-lookup"><span data-stu-id="122ab-110">Function</span></span>|<span data-ttu-id="122ab-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="122ab-111">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="122ab-112">`BitWiseAnd (` `value1` `,`  `value2` `)`</span><span class="sxs-lookup"><span data-stu-id="122ab-112">`BitWiseAnd (` `value1` `,`  `value2` `)`</span></span>|<span data-ttu-id="122ab-113">Devuelve la conjunción bit a bit de `value1` y `value2` como el tipo de `value1` y `value2`.</span><span class="sxs-lookup"><span data-stu-id="122ab-113">Returns the bitwise conjunction of `value1` and `value2` as the type of `value1` and `value2`.</span></span><br /><br /> <span data-ttu-id="122ab-114">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="122ab-114">**Arguments**</span></span><br /><br /> <span data-ttu-id="122ab-115">A `Byte`, `Int16`, `Int32`, y `Int64`.</span><span class="sxs-lookup"><span data-stu-id="122ab-115">A `Byte`, `Int16`, `Int32`, and `Int64`.</span></span><br /><br /> <span data-ttu-id="122ab-116">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="122ab-116">**Example**</span></span><br /><br /> `-- The following example returns 1.`<br /><br /> `BitWiseAnd(1,3)`|  
|<span data-ttu-id="122ab-117">`BitWiseNot (` `value` `)`</span><span class="sxs-lookup"><span data-stu-id="122ab-117">`BitWiseNot (` `value` `)`</span></span>|<span data-ttu-id="122ab-118">Devuelve la negación bit a bit de `value`.</span><span class="sxs-lookup"><span data-stu-id="122ab-118">Returns the bitwise negation of `value`.</span></span><br /><br /> <span data-ttu-id="122ab-119">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="122ab-119">**Arguments**</span></span><br /><br /> <span data-ttu-id="122ab-120">A `Byte`, `Int16`, `Int32`, y `Int64`.</span><span class="sxs-lookup"><span data-stu-id="122ab-120">A `Byte`, `Int16`, `Int32`, and `Int64`.</span></span><br /><br /> <span data-ttu-id="122ab-121">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="122ab-121">**Example**</span></span><br /><br /> `-- The following example returns -4.`<br /><br /> `BitWiseNot(3)`|  
|<span data-ttu-id="122ab-122">`BitWiseOr (` `value1` `,`  `value2` `)`</span><span class="sxs-lookup"><span data-stu-id="122ab-122">`BitWiseOr (` `value1` `,`  `value2` `)`</span></span>|<span data-ttu-id="122ab-123">Devuelve la disyunción bit a bit de `value1` y `value2` como el tipo de `value1` y `value2`.</span><span class="sxs-lookup"><span data-stu-id="122ab-123">Returns the bitwise disjunction of `value1` and `value2` as the type of `value1` and `value2`.</span></span><br /><br /> <span data-ttu-id="122ab-124">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="122ab-124">**Arguments**</span></span><br /><br /> <span data-ttu-id="122ab-125">A `Byte`, `Int16`, `Int32` y `Int64`.</span><span class="sxs-lookup"><span data-stu-id="122ab-125">A `Byte`, `Int16`, `Int32` and `Int64`.</span></span><br /><br /> <span data-ttu-id="122ab-126">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="122ab-126">**Example**</span></span><br /><br /> `-- The following example returns 3.`<br /><br /> `BitWiseOr(1,3)`|  
|<span data-ttu-id="122ab-127">`BitWiseXor (` `value1` `,`  `value2` `)`</span><span class="sxs-lookup"><span data-stu-id="122ab-127">`BitWiseXor (` `value1` `,`  `value2` `)`</span></span>|<span data-ttu-id="122ab-128">Devuelve la disyunción exclusiva bit a bit de `value1` y `value2` como el tipo de `value1` y `value2`.</span><span class="sxs-lookup"><span data-stu-id="122ab-128">Returns the bitwise exclusive disjunction of `value1` and `value2` as the type of `value1` and `value2`.</span></span><br /><br /> <span data-ttu-id="122ab-129">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="122ab-129">**Arguments**</span></span><br /><br /> <span data-ttu-id="122ab-130">A `Byte`, `Int16`, `Int32` y `Int64`.</span><span class="sxs-lookup"><span data-stu-id="122ab-130">A `Byte`, `Int16`, `Int32` and `Int64`.</span></span><br /><br /> <span data-ttu-id="122ab-131">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="122ab-131">**Example**</span></span><br /><br /> `-- The following example returns 2.`<br /><br /> `BitWiseXor (1,3)`|  
  
## <a name="see-also"></a><span data-ttu-id="122ab-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="122ab-132">See Also</span></span>  
 [<span data-ttu-id="122ab-133">Funciones canónicas</span><span class="sxs-lookup"><span data-stu-id="122ab-133">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
