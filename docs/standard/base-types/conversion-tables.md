---
title: Tablas de conversión de tipos en .NET
ms.date: 03/30/2017
helpviewer_keywords:
- widening conversions
- narrowing conversions
- type conversion, table
- converting types, narrowing conversions
- converting types, widening conversions
- base types, converting
- tables [.NET], type conversions
- data types [.NET], converting
ms.assetid: 0ea65c59-85eb-4a52-94ca-c36d3bd13058
ms.openlocfilehash: dc98a326155273805e3157d99755de2e97f83a46
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730219"
---
# <a name="type-conversion-tables-in-net"></a>Tablas de conversión de tipos en .NET

Una conversión de ampliación se produce cuando se convierte un valor de un tipo a otro tipo que es de igual o mayor tamaño. Una conversión de restricción se produce cuando se convierte un valor de un tipo a otro tipo que es de un tamaño menor. En las tablas de este tema se muestran los comportamientos de ambos tipos de conversiones.  
  
## <a name="widening-conversions"></a>Conversiones de ampliación  

 En la tabla siguiente se describen las conversiones de ampliación que pueden realizarse sin pérdida de información.  
  
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
  
 Algunas conversiones de ampliación a <xref:System.Single> o <xref:System.Double> pueden provocar una pérdida de precisión. En la tabla siguiente se describen las conversiones de ampliación que a veces se traducen en una pérdida de información.  
  
|Tipo|Se puede convertir a|  
|----------|-------------------------|  
|<xref:System.Int32>|<xref:System.Single>|  
|<xref:System.UInt32>|<xref:System.Single>|  
|<xref:System.Int64>|<xref:System.Single>, <xref:System.Double>|  
|<xref:System.UInt64>|<xref:System.Single>, <xref:System.Double>|  
|<xref:System.Decimal>|<xref:System.Single>, <xref:System.Double>|  
  
## <a name="narrowing-conversions"></a>Conversiones de restricción  

 Una conversión de restricción a <xref:System.Single> o <xref:System.Double> puede provocar una pérdida de información. Si el tipo de destino no puede expresar correctamente la magnitud del origen, el tipo resultante se establece en la constante `PositiveInfinity` o `NegativeInfinity`. `PositiveInfinity` resulta al dividir un número positivo por cero y también se devuelve cuando el valor de <xref:System.Single> o <xref:System.Double> supera el valor del campo `MaxValue`. `NegativeInfinity` resulta al dividir un número negativo por cero y también se devuelve cuando el valor de <xref:System.Single> o <xref:System.Double> cae por debajo del valor del campo `MinValue`. Una conversión de <xref:System.Double> a <xref:System.Single> podría dar lugar a `PositiveInfinity` o `NegativeInfinity`.  
  
 Una conversión de restricción también puede traducirse en una pérdida de información para otros tipos de datos. Pero se inicia <xref:System.OverflowException> si el valor de un tipo que se va a convertir está fuera del intervalo especificado por los campos `MaxValue` y `MinValue` del tipo de destino y el tiempo de ejecución comprueba la conversión para asegurarse de que el valor del tipo de destino no supera su `MaxValue` o `MinValue`. Las conversiones que se realizan con la clase <xref:System.Convert?displayProperty=nameWithType> siempre se comprueban de esta manera.  
  
 En la tabla siguiente se enumeran las conversiones que inician <xref:System.OverflowException> con <xref:System.Convert?displayProperty=nameWithType> o cualquier conversión comprobada si el valor del tipo que se va a convertir está fuera del intervalo definido del tipo resultante.  
  
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

- <xref:System.Convert?displayProperty=nameWithType>
- [Conversión de tipos en .NET](type-conversion.md)
