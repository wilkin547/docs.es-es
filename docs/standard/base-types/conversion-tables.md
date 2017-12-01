---
title: "Tablas de conversión de tipos en .NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- widening conversions
- narrowing conversions
- type conversion, table
- converting types, narrowing conversions
- converting types, widening conversions
- base types, converting
- tables [.NET Framework], type conversions
- data types [.NET Framework], converting
ms.assetid: 0ea65c59-85eb-4a52-94ca-c36d3bd13058
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 327469f9a151b6ef7e1c42f6669c0a9dae7016fd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="type-conversion-tables-in-net"></a>Tablas de conversión de tipos en .NET
Una conversión de ampliación se produce cuando se convierte un valor de un tipo a otro tipo que es de igual o mayor tamaño. Una conversión de restricción se produce cuando se convierte un valor de un tipo a otro tipo que es de un tamaño menor. En las tablas de este tema se muestran los comportamientos de ambos tipos de conversiones.  
  
## <a name="widening-conversions"></a>conversiones de ampliación  
 La tabla siguiente describen las conversiones de ampliación que se pueden realizar sin pérdida de información.  
  
|Tipo|Se puede convertir sin pérdida de datos a|  
|----------|-------------------------------------------|  
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
  
 Algunas conversiones a de ampliación <xref:System.Single> o <xref:System.Double> puede provocar una pérdida de precisión. En la tabla siguiente se describen las conversiones de ampliación que a veces se traducen en una pérdida de información.  
  
|Tipo|Se puede convertir a|  
|----------|-------------------------|  
|<xref:System.Int32>|<xref:System.Single>|  
|<xref:System.UInt32>|<xref:System.Single>|  
|<xref:System.Int64>|<xref:System.Single>, <xref:System.Double>|  
|<xref:System.UInt64>|<xref:System.Single>, <xref:System.Double>|  
|<xref:System.Decimal>|<xref:System.Single>, <xref:System.Double>|  
  
## <a name="narrowing-conversions"></a>conversiones de restricción  
 Una conversión de restricción a <xref:System.Single> o <xref:System.Double> puede provocar una pérdida de información. Si el tipo de destino no puede expresar correctamente la magnitud del origen, el tipo resultante se establece en la constante `PositiveInfinity` o `NegativeInfinity`. `PositiveInfinity`el resultado de dividir un número positivo por cero y también se devuelve cuando el valor de un <xref:System.Single> o <xref:System.Double> supera el valor de la `MaxValue` campo. `NegativeInfinity`el resultado de dividir un número negativo por cero y también se devuelve cuando el valor de un <xref:System.Single> o <xref:System.Double> cae por debajo del valor de la `MinValue` campo. Una conversión de un <xref:System.Double> a una <xref:System.Single> puede dar lugar a `PositiveInfinity` o `NegativeInfinity`.  
  
 Una conversión de restricción también puede traducirse en una pérdida de información para otros tipos de datos. Sin embargo, un <xref:System.OverflowException> se produce si el valor de un tipo que se va a convertir está fuera del intervalo especificado por el tipo de destino `MaxValue` y `MinValue` campos y la conversión se comprueba el tiempo de ejecución para asegurarse de que el valor de destino tipo no supere su `MaxValue` o `MinValue`. Las conversiones que se realizan con la <xref:System.Convert?displayProperty=nameWithType> clase siempre se protegen de esta manera.  
  
 En la tabla siguiente se enumera las conversiones que inician una <xref:System.OverflowException> con <xref:System.Convert?displayProperty=nameWithType> o cualquier comprobada conversión si el valor del tipo que se va a convertir está fuera del intervalo definido del tipo resultante.  
  
|Tipo|Se puede convertir a|  
|----------|-------------------------|  
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
  
## <a name="see-also"></a>Vea también  
 <xref:System.Convert?displayProperty=nameWithType>  
 [Conversión de tipos en .NET](../../../docs/standard/base-types/type-conversion.md)
