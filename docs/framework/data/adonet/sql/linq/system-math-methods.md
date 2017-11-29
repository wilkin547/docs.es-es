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
ms.openlocfilehash: af5e18b9c4334cfab26c9a84ac647bb433391ef1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="systemmath-methods"></a><span data-ttu-id="bf42c-102">System.Math (Métodos)</span><span class="sxs-lookup"><span data-stu-id="bf42c-102">System.Math Methods</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="bf42c-103"> no admite los métodos <xref:System.Math> siguientes.</span><span class="sxs-lookup"><span data-stu-id="bf42c-103"> does not support the following <xref:System.Math> methods.</span></span>  
  
-   <xref:System.Math.DivRem%28System.Int32%2CSystem.Int32%2CSystem.Int32%40%29?displayProperty=nameWithType>  
  
-   <xref:System.Math.DivRem%28System.Int64%2CSystem.Int64%2CSystem.Int64%40%29?displayProperty=nameWithType>  
  
-   <xref:System.Math.IEEERemainder%28System.Double%2CSystem.Double%29?displayProperty=nameWithType>  
  
## <a name="differences-from-net"></a><span data-ttu-id="bf42c-104">Diferencias respecto a .NET</span><span class="sxs-lookup"><span data-stu-id="bf42c-104">Differences from .NET</span></span>  
 <span data-ttu-id="bf42c-105">.NET Framework tiene una semántica de redondeo diferente a la de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bf42c-105">The .NET Framework has different rounding semantics from SQL Server.</span></span> <span data-ttu-id="bf42c-106">El <xref:System.Math.Round%2A> método en .NET Framework realiza *el redondeo bancario*, donde los números que terminan en, 5 de ida y vuelta para el dígito par en lugar de con el siguiente dígito superior más cercano.</span><span class="sxs-lookup"><span data-stu-id="bf42c-106">The <xref:System.Math.Round%2A> method in the .NET Framework performs *Banker's rounding*, where numbers that ends in .5 round to the nearest even digit instead of to the next higher digit.</span></span> <span data-ttu-id="bf42c-107">Por ejemplo, 2,5 se redondea a 2, mientras que 3,5 se redondea a 4.</span><span class="sxs-lookup"><span data-stu-id="bf42c-107">For example, 2.5 rounds to 2, while 3.5 rounds to 4.</span></span> <span data-ttu-id="bf42c-108">(Esta técnica ayuda a evitar la desviación sistemática hacia los valores más altos en transacciones de datos grandes.)</span><span class="sxs-lookup"><span data-stu-id="bf42c-108">(This technique helps avoid systematic bias toward higher values in large data transactions.)</span></span>  
  
 <span data-ttu-id="bf42c-109">En SQL, la función `ROUND` siempre aplica un redondeo desde 0.</span><span class="sxs-lookup"><span data-stu-id="bf42c-109">In SQL, the `ROUND` function instead always rounds away from 0.</span></span> <span data-ttu-id="bf42c-110">Por consiguiente, 2,5 se redondea a 3, mientras que en .NET Framework se redondea a 2.</span><span class="sxs-lookup"><span data-stu-id="bf42c-110">Therefore 2.5 rounds to 3, contrasted with its rounding to 2 in the .NET Framework.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="bf42c-111"> admite directamente la semántica de `ROUND` en SQL y no intenta implementar el redondeo bancario.</span><span class="sxs-lookup"><span data-stu-id="bf42c-111"> passes through to the SQL `ROUND` semantics and does not try to implement Banker's rounding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf42c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf42c-112">See Also</span></span>  
 [<span data-ttu-id="bf42c-113">Funciones y tipos de datos</span><span class="sxs-lookup"><span data-stu-id="bf42c-113">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
