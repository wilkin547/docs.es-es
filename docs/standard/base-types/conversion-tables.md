---
title: "Tablas de conversi&#243;n de tipos en .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "conversiones de ampliación"
  - "conversiones de restricción"
  - "conversión de tipos, tabla"
  - "tipos de conversión, conversiones de restricción"
  - "tipos de conversión, conversiones de ampliación"
  - "tipos base, conversión"
  - "tablas [.NET Framework], conversiones de tipos"
  - "tipos de datos [.NET Framework], convertir"
ms.assetid: 0ea65c59-85eb-4a52-94ca-c36d3bd13058
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Tablas de conversi&#243;n de tipos en .NET Framework
La conversión de ampliación se produce cuando un valor de un tipo se convierte en otro tipo de tamaño igual o mayor.  La conversión de restricción se produce cuando un valor de un tipo se convierte en un valor de otro tipo de tamaño menor.  Las tablas de este tema ilustran el comportamiento que presentan los dos tipos de conversión.  
  
## Conversiones de ampliación  
 En la tabla siguiente se describen las conversiones de ampliación que se pueden realizar sin pérdida de información.  
  
|Tipo|Puede convertirse sin pérdida de datos en|  
|----------|-----------------------------------------------|  
|<xref:System.Byte>|<xref:System.UInt16>, <xref:System.Int16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.SByte>|<xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.Int16>|<xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.UInt16>|<xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.Char>|<xref:System.UInt16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.Int32>|<xref:System.Int64>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.UInt32>|<xref:System.Int64>, <xref:System.UInt64>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.Int64>|<xref:System.Decimal>|  
|<xref:System.UInt64>|<xref:System.Decimal>|  
|<xref:System.Single>|<xref:System.Double>|  
  
 Ciertas conversiones de ampliación a <xref:System.Single> o <xref:System.Double> pueden producir una pérdida de precisión.  En la tabla siguiente se describen las conversiones de ampliación que pueden, en ocasiones, provocar una pérdida de información.  
  
|Tipo|Se puede convertir en|  
|----------|---------------------------|  
|<xref:System.Int32>|<xref:System.Single>|  
|<xref:System.UInt32>|<xref:System.Single>|  
|<xref:System.Int64>|<xref:System.Single>, <xref:System.Double>|  
|<xref:System.UInt64>|<xref:System.Single>, <xref:System.Double>|  
|<xref:System.Decimal>|<xref:System.Single>, <xref:System.Double>|  
  
## Conversiones de restricción  
 Una conversión de restricción a <xref:System.Single> o <xref:System.Double> puede producir una pérdida de información.  Si el tipo de destino no puede expresar correctamente la magnitud del origen, el tipo resultante se establece en la constante `PositiveInfinity` o `NegativeInfinity`.  `PositiveInfinity` es el resultado de dividir un número positivo por cero y también se obtiene cuando el valor de <xref:System.Single> o <xref:System.Double> supera el valor del campo `MaxValue`.  `NegativeInfinity` es el resultado de dividir un número negativo por cero y también se obtiene cuando el valor de <xref:System.Single> o <xref:System.Double> es menor que el valor del campo `MinValue`.  Una conversión de un tipo <xref:System.Double> a un tipo <xref:System.Single> podría producir `PositiveInfinity` o `NegativeInfinity`.  
  
 Una conversión de restricción también puede producir una pérdida de información con otros tipos de datos.  Sin embargo, se produce <xref:System.OverflowException> si el valor de un tipo que se está convirtiendo está fuera del intervalo especificado por los campos `MaxValue` y `MinValue` del tipo de destino, y el tiempo de ejecución comprueba la conversión para garantizar que el valor del tipo de destino no supera su `MaxValue` o `MinValue`.  Las conversiones que se realizan con la clase <xref:System.Convert?displayProperty=fullName> siempre se comprueban de esta forma.  
  
 En la tabla siguiente se enumeran las conversiones que producen una <xref:System.OverflowException> al usar <xref:System.Convert?displayProperty=fullName> o alguna de las conversiones comprobadas si el valor del tipo que se va a convertir está fuera del intervalo definido del tipo resultante.  
  
|Tipo|Se puede convertir en|  
|----------|---------------------------|  
|<xref:System.Byte>|<xref:System.SByte>|  
|<xref:System.SByte>|<xref:System.Byte>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64>|  
|<xref:System.Int16>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.UInt16>|  
|<xref:System.UInt16>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>|  
|<xref:System.Int32>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>,<xref:System.UInt32>|  
|<xref:System.UInt32>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>|  
|<xref:System.Int64>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>,<xref:System.UInt32>,<xref:System.UInt64>|  
|<xref:System.UInt64>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>|  
|<xref:System.Decimal>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64>|  
|<xref:System.Single>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64>|  
|<xref:System.Double>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64>|  
  
## Vea también  
 <xref:System.Convert?displayProperty=fullName>   
 [Conversión de tipos en .NET Framework](../../../docs/standard/base-types/type-conversion.md)