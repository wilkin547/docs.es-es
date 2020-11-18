---
title: Procedimiento para obtener acceso a los objetos de zona horaria local y UTC predefinidos
ms.date: 04/10/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET], local
- predefined time zones
- UTC times, predefined
- local time zone access
- time zones [.NET], retrieving
- time zones [.NET], UTC
ms.assetid: 961fb70b-83f0-4dab-a042-cb5fcd817cf5
ms.openlocfilehash: b92ac812ed0bd0e80bb3a6ab03b52746eb15db97
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94818113"
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a>Procedimiento para obtener acceso a los objetos de zona horaria local y UTC predefinidos

La <xref:System.TimeZoneInfo> clase proporciona dos propiedades, <xref:System.TimeZoneInfo.Utc%2A> y <xref:System.TimeZoneInfo.Local%2A> , que dan al código acceso a los objetos de zona horaria predefinidos. En este tema, se describe cómo obtener acceso a los objetos <xref:System.TimeZoneInfo> que devuelven esas propiedades.

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a>Para obtener acceso al objeto TimeZoneInfo de la hora universal coordinada (UTC)

1. Utilice la `static` `Shared` propiedad (en el Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> para obtener acceso a la hora universal coordinada.

2. En lugar de asignar el <xref:System.TimeZoneInfo> objeto devuelto por la propiedad a una variable de objeto, siga accediendo a la hora universal coordinada a través de la <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> propiedad.

### <a name="to-access-the-local-time-zone"></a>Para obtener acceso a la zona horaria local

1. Utilice la `static` `Shared` propiedad (en el Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> para tener acceso a la zona horaria del sistema local.

2. En lugar de asignar el <xref:System.TimeZoneInfo> objeto devuelto por la propiedad a una variable de objeto, siga accediendo a la zona horaria local a través de la <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> propiedad.

## <a name="example"></a>Ejemplo

El código siguiente utiliza las <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> propiedades y para convertir una hora de la zona horaria estándar del este de EE. UU. y Canadá, así como para mostrar el nombre de la zona horaria en la consola.

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

Siempre debe tener acceso a la zona horaria local a través de la <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> propiedad en lugar de asignar la zona horaria local a una <xref:System.TimeZoneInfo> variable de objeto. Del mismo modo, siempre debe obtener acceso a la hora universal coordinada a través de la <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> propiedad en lugar de asignar la zona UTC a una <xref:System.TimeZoneInfo> variable de objeto. Esto evita que <xref:System.TimeZoneInfo> una llamada al método invalide la variable de objeto <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> .

## <a name="compiling-the-code"></a>Compilación del código

Para este ejemplo se necesita:

- Que el <xref:System> espacio de nombres se debe importar con la `using` instrucción (necesaria en el código de C#).

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](index.md)
- [Buscar las zonas horarias definidas en un sistema local](finding-the-time-zones-on-local-system.md)
- [Cómo: crear instancias de un objeto TimeZoneInfo](instantiate-time-zone-info.md)
