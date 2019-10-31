---
title: 'Cómo: obtener acceso a los objetos de zona horaria local y UTC predefinidos'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], local
- predefined time zones
- UTC times, predefined
- local time zone access
- time zones [.NET Framework], retrieving
- time zones [.NET Framework], UTC
ms.assetid: 961fb70b-83f0-4dab-a042-cb5fcd817cf5
ms.openlocfilehash: ef22753d9934a52d955412a4493b608f265519aa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132607"
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a>Cómo: obtener acceso a los objetos de zona horaria local y UTC predefinidos

La clase <xref:System.TimeZoneInfo> proporciona dos propiedades, <xref:System.TimeZoneInfo.Utc%2A> y <xref:System.TimeZoneInfo.Local%2A>, que proporcionan al código acceso a los objetos de zona horaria predefinidos. En este tema, se describe cómo obtener acceso a los objetos <xref:System.TimeZoneInfo> que devuelven esas propiedades.

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a>Para obtener acceso al objeto TimeZoneInfo de la hora universal coordinada (UTC)

1. Use la propiedad `static` (`Shared` en Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> para obtener acceso a la hora universal coordinada.

2. En lugar de asignar el objeto <xref:System.TimeZoneInfo> devuelto por la propiedad a una variable de objeto, siga accediendo a la hora universal coordinada a través de la propiedad <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType>.

### <a name="to-access-the-local-time-zone"></a>Para obtener acceso a la zona horaria local

1. Use la propiedad `static` (`Shared` en Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> para tener acceso a la zona horaria del sistema local.

2. En lugar de asignar el objeto <xref:System.TimeZoneInfo> devuelto por la propiedad a una variable de objeto, siga accediendo a la zona horaria local a través de la propiedad <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>.

## <a name="example"></a>Ejemplo

En el código siguiente se usan las propiedades <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> y <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> para convertir una hora de la zona horaria estándar del este de EE. UU. y Canadá, así como para mostrar el nombre de la zona horaria en la consola.

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

Siempre debe tener acceso a la zona horaria local a través de la propiedad <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> en lugar de asignar la zona horaria local a una variable de objeto <xref:System.TimeZoneInfo>. Del mismo modo, siempre debe obtener acceso a la hora universal coordinada a través de la propiedad <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> en lugar de asignar la zona UTC a una variable de objeto <xref:System.TimeZoneInfo>. Esto evita que la variable de objeto <xref:System.TimeZoneInfo> se invalide mediante una llamada al método <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType>.

## <a name="compiling-the-code"></a>Compilación del código

Para este ejemplo se necesita:

- Que el espacio de nombres <xref:System> se importe con la instrucción `using` ( C# necesaria en el código).

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
- [Búsqueda de las zonas horarias definidas en un sistema local](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
- [Crear instancias de un objeto TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md)
