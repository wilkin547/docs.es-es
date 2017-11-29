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
# <a name="systemmath-methods"></a>System.Math (Métodos)
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no admite los métodos <xref:System.Math> siguientes.  
  
-   <xref:System.Math.DivRem%28System.Int32%2CSystem.Int32%2CSystem.Int32%40%29?displayProperty=nameWithType>  
  
-   <xref:System.Math.DivRem%28System.Int64%2CSystem.Int64%2CSystem.Int64%40%29?displayProperty=nameWithType>  
  
-   <xref:System.Math.IEEERemainder%28System.Double%2CSystem.Double%29?displayProperty=nameWithType>  
  
## <a name="differences-from-net"></a>Diferencias respecto a .NET  
 .NET Framework tiene una semántica de redondeo diferente a la de SQL Server. El <xref:System.Math.Round%2A> método en .NET Framework realiza *el redondeo bancario*, donde los números que terminan en, 5 de ida y vuelta para el dígito par en lugar de con el siguiente dígito superior más cercano. Por ejemplo, 2,5 se redondea a 2, mientras que 3,5 se redondea a 4. (Esta técnica ayuda a evitar la desviación sistemática hacia los valores más altos en transacciones de datos grandes.)  
  
 En SQL, la función `ROUND` siempre aplica un redondeo desde 0. Por consiguiente, 2,5 se redondea a 3, mientras que en .NET Framework se redondea a 2.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite directamente la semántica de `ROUND` en SQL y no intenta implementar el redondeo bancario.  
  
## <a name="see-also"></a>Vea también  
 [Funciones y tipos de datos](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
