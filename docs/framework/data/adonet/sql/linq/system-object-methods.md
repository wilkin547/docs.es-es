---
title: System.Object (Métodos)
ms.date: 03/30/2017
ms.assetid: 5397fca0-689e-443e-802f-e1cbdc866427
ms.openlocfilehash: 3a52f081f1c0c6e6c5218550009c736d0ed60514
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59097673"
---
# <a name="systemobject-methods"></a><span data-ttu-id="4b95e-102">System.Object (Métodos)</span><span class="sxs-lookup"><span data-stu-id="4b95e-102">System.Object Methods</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="4b95e-103">admite las siguientes <xref:System.Object> métodos.</span><span class="sxs-lookup"><span data-stu-id="4b95e-103">supports the following <xref:System.Object> methods.</span></span>  
  
|||  
|-|-|  
|<xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType>|<xref:System.Object.Equals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType>||  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="4b95e-104">no admite los métodos <xref:System.Object> siguientes.</span><span class="sxs-lookup"><span data-stu-id="4b95e-104">does not support the following <xref:System.Object> methods.</span></span>  
  
|||  
|-|-|  
|<xref:System.Object.GetHashCode?displayProperty=nameWithType>|<xref:System.Object.ReferenceEquals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.MemberwiseClone?displayProperty=nameWithType>|<xref:System.Object.GetType?displayProperty=nameWithType>|  
|<span data-ttu-id="4b95e-105"><xref:System.Object.ToString?displayProperty=nameWithType> para los tipos binarios, como `BINARY`, `VARBINARY`, `IMAGE` y `TIMESTAMP`.</span><span class="sxs-lookup"><span data-stu-id="4b95e-105"><xref:System.Object.ToString?displayProperty=nameWithType> for binary types such as `BINARY`, `VARBINARY`, `IMAGE`, and `TIMESTAMP`.</span></span>||  
  
## <a name="differences-from-net"></a><span data-ttu-id="4b95e-106">Diferencias respecto a .NET</span><span class="sxs-lookup"><span data-stu-id="4b95e-106">Differences from .NET</span></span>  
 <span data-ttu-id="4b95e-107">La salida de <xref:System.Object.ToString?displayProperty=nameWithType> para double utiliza SQL `CONVERT`(nvarchar (30), @x, 2) en SQL.</span><span class="sxs-lookup"><span data-stu-id="4b95e-107">The output of <xref:System.Object.ToString?displayProperty=nameWithType> for double uses SQL `CONVERT`(NVARCHAR(30), @x, 2) on SQL.</span></span> <span data-ttu-id="4b95e-108">SQL siempre utiliza 16 dígitos y notación científica (por ejemplo, "0.000000000000000e+000" para 0).</span><span class="sxs-lookup"><span data-stu-id="4b95e-108">SQL always uses 16 digits and scientific notation in this case (for example, "0.000000000000000e+000" for 0).</span></span> <span data-ttu-id="4b95e-109">En consecuencia, la conversión del método <xref:System.Object.ToString?displayProperty=nameWithType> no produce la misma cadena que <xref:System.Convert.ToString%2A?displayProperty=nameWithType> de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4b95e-109">As a result, <xref:System.Object.ToString?displayProperty=nameWithType> conversion does not produce the same string as <xref:System.Convert.ToString%2A?displayProperty=nameWithType> in the .NET Framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b95e-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b95e-110">See also</span></span>

- [<span data-ttu-id="4b95e-111">Tipos de datos y funciones</span><span class="sxs-lookup"><span data-stu-id="4b95e-111">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
