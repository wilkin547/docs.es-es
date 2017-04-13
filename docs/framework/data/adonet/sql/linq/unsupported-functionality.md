---
title: "Funcionalidad incompatible | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Funcionalidad incompatible
En LINQ to SQL, la siguiente funcionalidad de SQL no se puede exponer a través de la conversión de las construcciones existentes de Common Language Runtime \(CLR\) y .NET Framework:  
  
-   `STDDEV`  
  
-   `LIKE`  
  
     Aunque `LIKE` no se admite a través de la conversión directa, existe una funcionalidad similar en la clase <xref:System.Data.Linq.SqlClient.SqlMethods>.  Para obtener más información, consulta [M:System.Data.Linq.SqlClient.SqlMethods.Like\(System.String,System.String](assetId:///M:System.Data.Linq.SqlClient.SqlMethods.Like(System.String,System.String?qualifyHint=True&autoUpgrade=True).  
  
-   `DATEDIFF`  
  
     LINQ to SQL proporciona compatibilidad limitada para `DATEDIFF`.  Existe una funcionalidad similar en la clase [SqlMethods](assetId:///T:System.Data.Linq.SqlClient.SqlMethods?qualifyHint=False&autoUpgrade=True).  
  
-   `ROUND`  
  
     LINQ to SQL proporciona compatibilidad limitada para `ROUND`.  Para obtener más información, consulta [System.Math \(Métodos\)](../Topic/System.Math%20Methods.md).  
  
## Vea también  
 [Funciones y tipos de datos](../Topic/Data%20Types%20and%20Functions.md)