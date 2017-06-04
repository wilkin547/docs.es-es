---
title: "System.Math (M&#233;todos) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0f299521-6f41-4720-bd70-67c93fc50948
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# System.Math (M&#233;todos)
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no admite los métodos <xref:System.Math> siguientes.  
  
-   <xref:System.Math.DivRem%28System.Int32%2CSystem.Int32%2CSystem.Int32%40%29?displayProperty=fullName>  
  
-   <xref:System.Math.DivRem%28System.Int64%2CSystem.Int64%2CSystem.Int64%40%29?displayProperty=fullName>  
  
-   <xref:System.Math.IEEERemainder%28System.Double%2CSystem.Double%29?displayProperty=fullName>  
  
## Diferencias respecto a .NET  
 .NET Framework tiene una semántica de redondeo diferente a la de SQL Server.  El método <xref:System.Math.Round%2A> de .NET Framework realiza un *redondeo bancario*, según el cual los números que terminan en ,5 se redondean al dígito par más cercano en lugar de al siguiente dígito superior.  Por ejemplo, 2,5 se redondea a 2, mientras que 3,5 se redondea a 4.  \(Esta técnica ayuda a evitar la desviación sistemática hacia los valores más altos en transacciones de datos grandes.\)  
  
 En SQL, la función `ROUND` siempre aplica un redondeo desde 0.  Por consiguiente, 2,5 se redondea a 3, mientras que en .NET Framework se redondea a 2.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite directamente la semántica de `ROUND` en SQL y no intenta implementar el redondeo bancario.  
  
## Vea también  
 [Funciones y tipos de datos](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)