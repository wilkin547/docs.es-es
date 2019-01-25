---
title: System.Math (Métodos)
ms.date: 03/30/2017
ms.assetid: 0f299521-6f41-4720-bd70-67c93fc50948
ms.openlocfilehash: 45a674c86fc2f19f3e273834b8cb9d6adee5b3ab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576868"
---
# <a name="systemmath-methods"></a>System.Math (Métodos)
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no admite los métodos <xref:System.Math> siguientes.  
  
-   <xref:System.Math.DivRem%28System.Int32%2CSystem.Int32%2CSystem.Int32%40%29?displayProperty=nameWithType>  
  
-   <xref:System.Math.DivRem%28System.Int64%2CSystem.Int64%2CSystem.Int64%40%29?displayProperty=nameWithType>  
  
-   <xref:System.Math.IEEERemainder%28System.Double%2CSystem.Double%29?displayProperty=nameWithType>  
  
## <a name="differences-from-net"></a>Diferencias respecto a .NET  
 .NET Framework tiene una semántica de redondeo diferente a la de SQL Server. El <xref:System.Math.Round%2A> método en .NET Framework realiza *redondeo bancario*, donde los números que terminan en.5 redondean el dígito par en lugar de a la siguiente dígito superior más cercano. Por ejemplo, 2,5 se redondea a 2, mientras que 3,5 se redondea a 4. (Esta técnica ayuda a evitar la desviación sistemática hacia los valores más altos en transacciones de datos grandes.)  
  
 En SQL, la función `ROUND` siempre aplica un redondeo desde 0. Por consiguiente, 2,5 se redondea a 3, mientras que en .NET Framework se redondea a 2.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite directamente la semántica de `ROUND` en SQL y no intenta implementar el redondeo bancario.  
  
## <a name="see-also"></a>Vea también
- [Tipos de datos y funciones](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
