---
title: 'Cómo: resolver horas ambiguas'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
ms.openlocfilehash: 0b5b28c588237fb2f7f069aaef06f3f73d5268bf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122249"
---
# <a name="how-to-resolve-ambiguous-times"></a>Cómo: resolver horas ambiguas

Una hora ambigua es aquella que se asigna a más de una hora universal coordinada (UTC). Esto sucede cuando la hora del reloj se atrasa, como durante la transición del horario de verano de una zona horaria al horario estándar. Cuando se enfrente a una hora ambigua, puede realizar una de las siguientes acciones:

- Piense cómo se corresponde esa hora con la hora UTC. Por ejemplo, puede dar por supuesto que una hora ambigua siempre se expresa en la hora estándar de la zona horaria.

- Si la hora ambigua es un dato introducido por el usuario, puede dejar que el usuario resuelva la ambigüedad.

En este tema se muestra cómo resolver una hora ambigua suponiendo que representa la hora estándar de la zona horaria.

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a>Para asignar una hora ambigua a la hora estándar de una zona horaria

1. Llame al método <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> para determinar si la hora es ambigua.

2. Si la hora es ambigua, reste el tiempo del objeto <xref:System.TimeSpan> devuelto por la propiedad <xref:System.TimeZoneInfo.BaseUtcOffset%2A> de la zona horaria.

3. Llame al método de <xref:System.DateTime.SpecifyKind%2A> `static` (`Shared` en Visual Basic .NET) para establecer la propiedad <xref:System.DateTime.Kind%2A> del valor de fecha y hora UTC en <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo convertir una hora ambigua a la hora UTC suponiendo que representa la hora estándar de la zona horaria local.

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

El ejemplo consta de un método denominado `ResolveAmbiguousTime` que determina si el valor de <xref:System.DateTime> pasado es ambiguo. Si el valor es ambiguo, el método devuelve un valor <xref:System.DateTime> que representa la hora UTC correspondiente. El método controla esta conversión restando el valor de la propiedad <xref:System.TimeZoneInfo.BaseUtcOffset%2A> de la zona horaria local a la hora local.

Normalmente, se controla una hora ambigua llamando al método <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> para recuperar una matriz de objetos <xref:System.TimeSpan> que contengan los desplazamientos UTC posibles de la hora ambigua. Pero en este ejemplo se supone arbitrariamente que una hora ambigua siempre debe estar asignada a la hora estándar de la zona horaria. La propiedad <xref:System.TimeZoneInfo.BaseUtcOffset%2A> devuelve el desplazamiento entre la hora UTC y la hora estándar de una zona horaria.

En este ejemplo, todas las referencias a la zona horaria local se realizan a través de la propiedad <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>; la zona horaria local nunca se asigna a una variable de objeto. Se trata de una práctica recomendada, ya que una llamada al método <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> invalida los objetos a los que está asignada la zona horaria local.

## <a name="compiling-the-code"></a>Compilación del código

Para este ejemplo se necesita:

- Que el espacio de nombres <xref:System> se importe con la instrucción `using` ( C# necesaria en el código).

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
- [Permitir que los usuarios resuelvan horas ambiguas](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)
