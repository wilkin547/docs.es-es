---
title: System.Math (Métodos)
ms.date: 03/30/2017
ms.assetid: 0f299521-6f41-4720-bd70-67c93fc50948
ms.openlocfilehash: e91c8ea95d21288ad2577f1550333febd448766d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158206"
---
# <a name="systemmath-methods"></a>System.Math (Métodos)

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no admite los métodos <xref:System.Math> siguientes.  
  
- <xref:System.Math.DivRem%28System.Int32%2CSystem.Int32%2CSystem.Int32%40%29?displayProperty=nameWithType>  
  
- <xref:System.Math.DivRem%28System.Int64%2CSystem.Int64%2CSystem.Int64%40%29?displayProperty=nameWithType>  
  
- <xref:System.Math.IEEERemainder%28System.Double%2CSystem.Double%29?displayProperty=nameWithType>  
  
## <a name="differences-from-net"></a>Diferencias respecto a .NET  

 .NET Framework tiene una semántica de redondeo diferente a la de SQL Server. El <xref:System.Math.Round%2A> método en el .NET Framework realiza el *redondeo bancario*, donde los números que terminan en 0,5 se redondean al dígito par más cercano en lugar de al siguiente dígito más alto. Por ejemplo, 2,5 se redondea a 2, mientras que 3,5 se redondea a 4. (Esta técnica ayuda a evitar la desviación sistemática hacia los valores más altos en transacciones de datos grandes.)  
  
 En SQL, la función `ROUND` siempre aplica un redondeo desde 0. Por consiguiente, 2,5 se redondea a 3, mientras que en .NET Framework se redondea a 2.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite directamente la semántica de `ROUND` en SQL y no intenta implementar el redondeo bancario.  
  
## <a name="see-also"></a>Consulte también

- [Tipos de datos y funciones](data-types-and-functions.md)
