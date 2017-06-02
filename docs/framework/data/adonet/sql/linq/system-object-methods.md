---
title: "System.Object (M&#233;todos) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5397fca0-689e-443e-802f-e1cbdc866427
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# System.Object (M&#233;todos)
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite los siguientes métodos <xref:System.Object>.  
  
|||  
|-|-|  
|<xref:System.Object.Equals%28System.Object%29?displayProperty=fullName>|<xref:System.Object.Equals%28System.Object%2CSystem.Object%29?displayProperty=fullName>|  
|<xref:System.Object.ToString?displayProperty=fullName>||  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no admite los métodos <xref:System.Object> siguientes.  
  
|||  
|-|-|  
|<xref:System.Object.GetHashCode?displayProperty=fullName>|<xref:System.Object.ReferenceEquals%28System.Object%2CSystem.Object%29?displayProperty=fullName>|  
|<xref:System.Object.MemberwiseClone?displayProperty=fullName>|<xref:System.Object.GetType?displayProperty=fullName>|  
|<xref:System.Object.ToString?displayProperty=fullName> para los tipos binarios, como `BINARY`, `VARBINARY`, `IMAGE` y `TIMESTAMP`.||  
  
## Diferencias respecto a .NET  
 El resultado de <xref:System.Object.ToString?displayProperty=fullName> para double utiliza SQL `CONVERT`\(NVARCHAR\(30\), @x, 2\) en SQL.  SQL siempre utiliza 16 dígitos y notación científica \(por ejemplo, "0.000000000000000e\+000" para 0\).  En consecuencia, la conversión del método <xref:System.Object.ToString?displayProperty=fullName> no produce la misma cadena que <xref:System.Convert.ToString%2A?displayProperty=fullName> de .NET Framework.  
  
## Vea también  
 [Funciones y tipos de datos](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)