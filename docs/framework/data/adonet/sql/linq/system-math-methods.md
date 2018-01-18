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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: cfcbf915703c72211fc9d958abfda7ffac8aafdc
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
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
 [Tipos de datos y funciones](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
