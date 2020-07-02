---
ms.openlocfilehash: e4d9efe7d2a06a1e501b070c23184dcd913dba71
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621410"
---
### <a name="persian-calendar-now-uses-the-hijri-solar-algorithm"></a>En el calendario persa ahora se usa el algoritmo Hijri solar

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.6, en la clase <xref:System.Globalization.PersianCalendar?displayProperty=fullName> se usa el algoritmo Hijri solar. La conversión de fechas entre <xref:System.Globalization.PersianCalendar?displayProperty=fullName> y otros calendarios puede producir un resultado ligeramente diferente a partir de .NET Framework 4.6 para las fechas anteriores a 1800 o posteriores a 2023 (del calendario gregoriano). Además, <xref:System.Globalization.PersianCalendar.MinSupportedDateTime?displayProperty=nameWithType> ahora es <code>March 22, 0622</code> en lugar de <code>March 21, 0622</code>.

#### <a name="suggestion"></a>Sugerencia

Tenga en cuenta que algunas fechas tempranas o tardías pueden ser ligeramente diferentes cuando se usa PersianCalendar en .NET Framework 4.6. Además, al serializar fechas entre procesos que puedan ejecutarse en diferentes versiones de .NET Framework, no las guarde como cadenas de fecha de PersianCalendar (ya que estos valores pueden ser diferentes).

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.6|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Globalization.PersianCalendar?displayProperty=nameWithType></li></ul>|
