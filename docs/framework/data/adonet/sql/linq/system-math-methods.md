---
title: "System.Math (Métodos)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f299521-6f41-4720-bd70-67c93fc50948
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 8c5f19918ca1c80daffab482436ab6ce018321f5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="systemmath-methods"></a><span data-ttu-id="babaa-102">System.Math (Métodos)</span><span class="sxs-lookup"><span data-stu-id="babaa-102">System.Math Methods</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="babaa-103"> no admite los métodos <xref:System.Math> siguientes.</span><span class="sxs-lookup"><span data-stu-id="babaa-103"> does not support the following <xref:System.Math> methods.</span></span>  
  
-   <xref:System.Math.DivRem%28System.Int32%2CSystem.Int32%2CSystem.Int32%40%29?displayProperty=nameWithType>  
  
-   <xref:System.Math.DivRem%28System.Int64%2CSystem.Int64%2CSystem.Int64%40%29?displayProperty=nameWithType>  
  
-   <xref:System.Math.IEEERemainder%28System.Double%2CSystem.Double%29?displayProperty=nameWithType>  
  
## <a name="differences-from-net"></a><span data-ttu-id="babaa-104">Diferencias respecto a .NET</span><span class="sxs-lookup"><span data-stu-id="babaa-104">Differences from .NET</span></span>  
 <span data-ttu-id="babaa-105">.NET Framework tiene una semántica de redondeo diferente a la de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="babaa-105">The .NET Framework has different rounding semantics from SQL Server.</span></span> <span data-ttu-id="babaa-106">El <xref:System.Math.Round%2A> método en .NET Framework realiza *el redondeo bancario*, donde los números que terminan en, 5 de ida y vuelta para el dígito par en lugar de con el siguiente dígito superior más cercano.</span><span class="sxs-lookup"><span data-stu-id="babaa-106">The <xref:System.Math.Round%2A> method in the .NET Framework performs *Banker's rounding*, where numbers that ends in .5 round to the nearest even digit instead of to the next higher digit.</span></span> <span data-ttu-id="babaa-107">Por ejemplo, 2,5 se redondea a 2, mientras que 3,5 se redondea a 4.</span><span class="sxs-lookup"><span data-stu-id="babaa-107">For example, 2.5 rounds to 2, while 3.5 rounds to 4.</span></span> <span data-ttu-id="babaa-108">(Esta técnica ayuda a evitar la desviación sistemática hacia los valores más altos en transacciones de datos grandes.)</span><span class="sxs-lookup"><span data-stu-id="babaa-108">(This technique helps avoid systematic bias toward higher values in large data transactions.)</span></span>  
  
 <span data-ttu-id="babaa-109">En SQL, la función `ROUND` siempre aplica un redondeo desde 0.</span><span class="sxs-lookup"><span data-stu-id="babaa-109">In SQL, the `ROUND` function instead always rounds away from 0.</span></span> <span data-ttu-id="babaa-110">Por consiguiente, 2,5 se redondea a 3, mientras que en .NET Framework se redondea a 2.</span><span class="sxs-lookup"><span data-stu-id="babaa-110">Therefore 2.5 rounds to 3, contrasted with its rounding to 2 in the .NET Framework.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="babaa-111"> admite directamente la semántica de `ROUND` en SQL y no intenta implementar el redondeo bancario.</span><span class="sxs-lookup"><span data-stu-id="babaa-111"> passes through to the SQL `ROUND` semantics and does not try to implement Banker's rounding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="babaa-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="babaa-112">See Also</span></span>  
 [<span data-ttu-id="babaa-113">Tipos de datos y funciones</span><span class="sxs-lookup"><span data-stu-id="babaa-113">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
