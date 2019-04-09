---
title: System.Object (Métodos)
ms.date: 03/30/2017
ms.assetid: 5397fca0-689e-443e-802f-e1cbdc866427
ms.openlocfilehash: 3a52f081f1c0c6e6c5218550009c736d0ed60514
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097673"
---
# <a name="systemobject-methods"></a>System.Object (Métodos)
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite las siguientes <xref:System.Object> métodos.  
  
|||  
|-|-|  
|<xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType>|<xref:System.Object.Equals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType>||  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no admite los siguientes <xref:System.Object> métodos.  
  
|||  
|-|-|  
|<xref:System.Object.GetHashCode?displayProperty=nameWithType>|<xref:System.Object.ReferenceEquals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.MemberwiseClone?displayProperty=nameWithType>|<xref:System.Object.GetType?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType> para los tipos binarios como `BINARY`, `VARBINARY`, `IMAGE`, y `TIMESTAMP`.||  
  
## <a name="differences-from-net"></a>Diferencias respecto a .NET  
 La salida de <xref:System.Object.ToString?displayProperty=nameWithType> para double utiliza SQL `CONVERT`(nvarchar (30), @x, 2) en SQL. SQL siempre utiliza 16 dígitos y notación científica (por ejemplo, "0.000000000000000e+000" para 0). En consecuencia, la conversión del método <xref:System.Object.ToString?displayProperty=nameWithType> no produce la misma cadena que <xref:System.Convert.ToString%2A?displayProperty=nameWithType> de .NET Framework.  
  
## <a name="see-also"></a>Vea también

- [Tipos de datos y funciones](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
