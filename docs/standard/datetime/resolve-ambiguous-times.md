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
ms.openlocfilehash: aae3e5145d2fa85cd55fc5b1288ef4aaa0fef48f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796414"
---
# <a name="how-to-resolve-ambiguous-times"></a>Procedimiento para resolver horas ambiguas

Una hora ambigua es aquella que se asigna a más de una hora universal coordinada (UTC). Esto sucede cuando la hora del reloj se atrasa, como durante la transición del horario de verano de una zona horaria al horario estándar. Cuando se enfrente a una hora ambigua, puede realizar una de las siguientes acciones:

* Piense cómo se corresponde esa hora con la hora UTC. Por ejemplo, puede dar por supuesto que una hora ambigua siempre se expresa en la hora estándar de la zona horaria.

* Si la hora ambigua es un dato introducido por el usuario, puede dejar que el usuario resuelva la ambigüedad.

En este tema se muestra cómo resolver una hora ambigua, por supuesto que representa la hora de la zona horaria estándar.

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a>Para asignar una hora ambigua a la hora estándar de una zona horaria

1. Llame a la <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> método para determinar si la hora es ambigua.

2. Si la hora es ambigua, reste la hora de la <xref:System.TimeSpan> objeto devuelto por la zona horaria <xref:System.TimeZoneInfo.BaseUtcOffset%2A> propiedad.

3. Llame a la `static` (`Shared` en Visual Basic. NET) <xref:System.DateTime.SpecifyKind%2A> método para establecer la hora UTC de fecha y hora del valor <xref:System.DateTime.Kind%2A> propiedad <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.

## <a name="example"></a>Ejemplo

El ejemplo siguiente muestra cómo convertir una hora ambigua a UTC dando por supuesto que representa la hora estándar de la zona horaria local.

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

El ejemplo consta de un método denominado `ResolveAmbiguousTime` que determina si el <xref:System.DateTime> valor pasado es ambiguo. Si el valor es ambiguo, el método devuelve un <xref:System.DateTime> valor que representa la hora UTC correspondiente. El método trata esta conversión restando el valor de la zona horaria local <xref:System.TimeZoneInfo.BaseUtcOffset%2A> propiedad de la hora local.

Normalmente, una hora ambigua se controla mediante una llamada a la <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> método para recuperar una matriz de <xref:System.TimeSpan> desplazamientos de los objetos que contienen posible UTC la hora ambigua. Pero en este ejemplo se supone arbitrariamente que una hora ambigua siempre debe estar asignada a la hora estándar de la zona horaria. El <xref:System.TimeZoneInfo.BaseUtcOffset%2A> propiedad devuelve la diferencia entre la hora UTC y la hora de una zona horaria estándar.

En este ejemplo, todas las referencias a la zona horaria local se realizan a través del <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> propiedad; la hora local zona nunca se asigna a una variable de objeto. Esto es una práctica recomendada porque una llamada a la <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> método invalida cualquier objeto asignado a la zona horaria local.

## <a name="compiling-the-code"></a>Compilación del código

Para este ejemplo se necesita:

* Que se agregarán al proyecto una referencia a System.Core.dll.

* Que el <xref:System> se importan el espacio de nombres con el `using` instrucción (obligatorio en el código de C#).

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
- [Cómo: Permitir que los usuarios resuelvan horas ambiguas](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)
