---
title: Procedimiento para resolver horas ambiguas
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e98d5d8240492ca30da2825b72277d7a35f97f6
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106782"
---
# <a name="how-to-resolve-ambiguous-times"></a>Procedimiento para resolver horas ambiguas

Una hora ambigua es aquella que se asigna a más de una hora universal coordinada (UTC). Esto sucede cuando la hora del reloj se atrasa, como durante la transición del horario de verano de una zona horaria al horario estándar. Cuando se enfrente a una hora ambigua, puede realizar una de las siguientes acciones:

- Piense cómo se corresponde esa hora con la hora UTC. Por ejemplo, puede dar por supuesto que una hora ambigua siempre se expresa en la hora estándar de la zona horaria.

- Si la hora ambigua es un dato introducido por el usuario, puede dejar que el usuario resuelva la ambigüedad.

En este tema se muestra cómo resolver una hora ambigua suponiendo que representa la hora estándar de la zona horaria.

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a>Para asignar una hora ambigua a la hora estándar de una zona horaria

1. Llame al <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> método para determinar si la hora es ambigua.

2. Si la hora es ambigua, reste la hora <xref:System.TimeSpan> del objeto devuelto por la propiedad de <xref:System.TimeZoneInfo.BaseUtcOffset%2A> la zona horaria.

3. `Shared` <xref:System.DateTime.SpecifyKind%2A> <xref:System.DateTime.Kind%2A> Llame al método <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>(en Visual Basic .net) para establecer la propiedad del valor de fecha y hora UTC en. `static`

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo convertir una hora ambigua a la hora UTC suponiendo que representa la hora estándar de la zona horaria local.

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

El ejemplo consta de un método denominado `ResolveAmbiguousTime` que determina si el <xref:System.DateTime> valor pasado a él es ambiguo. Si el valor es ambiguo, el método devuelve un <xref:System.DateTime> valor que representa la hora UTC correspondiente. El método controla esta conversión restando el valor de la <xref:System.TimeZoneInfo.BaseUtcOffset%2A> propiedad de la zona horaria local a la hora local.

Normalmente, se controla una hora ambigua llamando al <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> método para recuperar una matriz de <xref:System.TimeSpan> objetos que contienen los posibles desplazamientos de UTC de la hora ambigua. Pero en este ejemplo se supone arbitrariamente que una hora ambigua siempre debe estar asignada a la hora estándar de la zona horaria. La <xref:System.TimeZoneInfo.BaseUtcOffset%2A> propiedad devuelve el desplazamiento entre la hora UTC y la hora estándar de una zona horaria.

En este ejemplo, todas las referencias a la zona horaria local se realizan a <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> través de la propiedad; la zona horaria local nunca se asigna a una variable de objeto. Se trata de una práctica recomendada, ya que una <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> llamada al método invalida los objetos a los que está asignada la zona horaria local.

## <a name="compiling-the-code"></a>Compilación del código

Para este ejemplo se necesita:

- Que el <xref:System> espacio de nombres se debe `using` importar con la instrucción C# (necesario en el código).

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
- [Procedimientos: Permitir a los usuarios resolver horas ambiguas](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)
