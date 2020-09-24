---
title: System.Object (Métodos)
ms.date: 03/30/2017
ms.assetid: 5397fca0-689e-443e-802f-e1cbdc866427
ms.openlocfilehash: d2b96ca9e7bedd0e0438b47698d4b963844c92f3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155645"
---
# <a name="systemobject-methods"></a>System.Object (Métodos)

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite los <xref:System.Object> métodos siguientes.  
  
|||  
|-|-|  
|<xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType>|<xref:System.Object.Equals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType>||  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no admite los métodos <xref:System.Object> siguientes.  
  
|||  
|-|-|  
|<xref:System.Object.GetHashCode?displayProperty=nameWithType>|<xref:System.Object.ReferenceEquals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.MemberwiseClone?displayProperty=nameWithType>|<xref:System.Object.GetType?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType> para los tipos binarios, como `BINARY`, `VARBINARY`, `IMAGE` y `TIMESTAMP`.||  
  
## <a name="differences-from-net"></a>Diferencias respecto a .NET  

 La salida de <xref:System.Object.ToString?displayProperty=nameWithType> para Double usa SQL `CONVERT` (nvarchar (30), @x , 2) en SQL. SQL siempre utiliza 16 dígitos y notación científica (por ejemplo, "0.000000000000000e+000" para 0). En consecuencia, la conversión del método <xref:System.Object.ToString?displayProperty=nameWithType> no produce la misma cadena que <xref:System.Convert.ToString%2A?displayProperty=nameWithType> de .NET Framework.  
  
## <a name="see-also"></a>Vea también

- [Tipos de datos y funciones](data-types-and-functions.md)
