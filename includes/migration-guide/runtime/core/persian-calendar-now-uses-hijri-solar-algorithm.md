---
ms.openlocfilehash: bfe406161ac754124a2cc38c68a80c3b9fb2c7f6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858413"
---
### <a name="persian-calendar-now-uses-the-hijri-solar-algorithm"></a>En el calendario persa ahora se usa el algoritmo Hijri solar

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.6, en la clase <xref:System.Globalization.PersianCalendar?displayProperty=name> se usa el algoritmo Hijri solar. La conversión de fechas entre <xref:System.Globalization.PersianCalendar?displayProperty=name> y otros calendarios puede producir un resultado ligeramente diferente a partir de .NET Framework 4.6 para las fechas anteriores a 1800 o posteriores a 2023 (del calendario gregoriano). Además, <xref:System.Globalization.PersianCalendar.MinSupportedDateTime?displayProperty=nameWithType> ahora es <code>March 22, 0622</code> en lugar de <code>March 21, 0622</code>.|
|Sugerencia|Tenga en cuenta que algunas fechas tempranas o tardías pueden ser ligeramente diferentes cuando se usa PersianCalendar en .NET Framework 4.6. Además, al serializar fechas entre procesos que puedan ejecutarse en diferentes versiones de .NET Framework, no las guarde como cadenas de fecha de PersianCalendar (ya que estos valores pueden ser diferentes).|
|Ámbito|Secundaria|
|Versión|4.6|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Globalization.PersianCalendar?displayProperty=nameWithType></li></ul>|
