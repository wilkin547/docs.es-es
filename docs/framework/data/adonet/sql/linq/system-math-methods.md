---
description: 'Más información sobre: métodos System. Math'
title: System.Math (Métodos)
ms.date: 03/30/2017
ms.assetid: 0f299521-6f41-4720-bd70-67c93fc50948
ms.openlocfilehash: e97e0a16b6eafdb57f4aaf72d62788e6657afbdc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681349"
---
# <a name="systemmath-methods"></a><span data-ttu-id="ac5ba-103">System.Math (Métodos)</span><span class="sxs-lookup"><span data-stu-id="ac5ba-103">System.Math Methods</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="ac5ba-104">no admite los métodos <xref:System.Math> siguientes.</span><span class="sxs-lookup"><span data-stu-id="ac5ba-104">does not support the following <xref:System.Math> methods.</span></span>  
  
- <xref:System.Math.DivRem%28System.Int32%2CSystem.Int32%2CSystem.Int32%40%29?displayProperty=nameWithType>  
  
- <xref:System.Math.DivRem%28System.Int64%2CSystem.Int64%2CSystem.Int64%40%29?displayProperty=nameWithType>  
  
- <xref:System.Math.IEEERemainder%28System.Double%2CSystem.Double%29?displayProperty=nameWithType>  
  
## <a name="differences-from-net"></a><span data-ttu-id="ac5ba-105">Diferencias respecto a .NET</span><span class="sxs-lookup"><span data-stu-id="ac5ba-105">Differences from .NET</span></span>  

 <span data-ttu-id="ac5ba-106">.NET Framework tiene una semántica de redondeo diferente a la de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ac5ba-106">The .NET Framework has different rounding semantics from SQL Server.</span></span> <span data-ttu-id="ac5ba-107">El <xref:System.Math.Round%2A> método en el .NET Framework realiza el *redondeo bancario*, donde los números que terminan en 0,5 se redondean al dígito par más cercano en lugar de al siguiente dígito más alto.</span><span class="sxs-lookup"><span data-stu-id="ac5ba-107">The <xref:System.Math.Round%2A> method in the .NET Framework performs *Banker's rounding*, where numbers that ends in .5 round to the nearest even digit instead of to the next higher digit.</span></span> <span data-ttu-id="ac5ba-108">Por ejemplo, 2,5 se redondea a 2, mientras que 3,5 se redondea a 4.</span><span class="sxs-lookup"><span data-stu-id="ac5ba-108">For example, 2.5 rounds to 2, while 3.5 rounds to 4.</span></span> <span data-ttu-id="ac5ba-109">(Esta técnica ayuda a evitar la desviación sistemática hacia los valores más altos en transacciones de datos grandes.)</span><span class="sxs-lookup"><span data-stu-id="ac5ba-109">(This technique helps avoid systematic bias toward higher values in large data transactions.)</span></span>  
  
 <span data-ttu-id="ac5ba-110">En SQL, la función `ROUND` siempre aplica un redondeo desde 0.</span><span class="sxs-lookup"><span data-stu-id="ac5ba-110">In SQL, the `ROUND` function instead always rounds away from 0.</span></span> <span data-ttu-id="ac5ba-111">Por consiguiente, 2,5 se redondea a 3, mientras que en .NET Framework se redondea a 2.</span><span class="sxs-lookup"><span data-stu-id="ac5ba-111">Therefore 2.5 rounds to 3, contrasted with its rounding to 2 in the .NET Framework.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="ac5ba-112">admite directamente la semántica de `ROUND` en SQL y no intenta implementar el redondeo bancario.</span><span class="sxs-lookup"><span data-stu-id="ac5ba-112">passes through to the SQL `ROUND` semantics and does not try to implement Banker's rounding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac5ba-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac5ba-113">See also</span></span>

- [<span data-ttu-id="ac5ba-114">Tipos de datos y funciones</span><span class="sxs-lookup"><span data-stu-id="ac5ba-114">Data Types and Functions</span></span>](data-types-and-functions.md)
