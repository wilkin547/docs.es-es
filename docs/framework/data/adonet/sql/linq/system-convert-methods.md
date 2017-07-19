---
title: "System.Convert (M&#233;todos) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3ca6c5b6-ea5d-4ab0-b675-f082135b342c
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# System.Convert (M&#233;todos)
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no admite los métodos <xref:System.Convert> siguientes.  
  
-   Versiones con un parámetro <xref:System.IFormatProvider>.  
  
-   Métodos que incluyen matrices de caracteres o matrices de bytes:  
  
    -   <xref:System.Convert.FromBase64CharArray%2A>  
  
    -   <xref:System.Convert.ToBase64CharArray%2A>  
  
    -   <xref:System.Convert.FromBase64String%2A>  
  
    -   <xref:System.Convert.ToBase64String%2A>  
  
-   Los métodos siguientes:  
  
    -   `public static <Type2> To<Type2>(<Type1> value);` donde  
  
         `Type1` y `Type2` son `sbyte`, `uint`, `ulong` o `ushort`.  
  
    -   C\#:  
  
         `int To<int type>(string value, int fromBase),`  
  
         `ToString(...  value, int toBase)`  
  
    -   Visual Basic:  
  
         `Function To(Of [Numeric])(value as String, fromBase As Integer)`  
  
         `As [Numeric], ToString( value As …, toBase As Integer)`  
  
    -   <xref:System.Convert.IsDBNull%2A>  
  
    -   <xref:System.Convert.GetTypeCode%2A>  
  
    -   <xref:System.Convert.ChangeType%2A>  
  
## Vea también  
 [Funciones y tipos de datos](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)