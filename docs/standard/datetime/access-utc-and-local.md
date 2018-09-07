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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f074e6f6d9b11cc7d7405adced3a4523a31676fa
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44086918"
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a>Cómo: obtener acceso a los objetos de zona horaria local y UTC predefinidos

El <xref:System.TimeZoneInfo> clase proporciona dos propiedades, <xref:System.TimeZoneInfo.Utc%2A> y <xref:System.TimeZoneInfo.Local%2A>, que dan al código acceso a los objetos de zona horaria predefinidos. En este tema, se describe cómo obtener acceso a los objetos <xref:System.TimeZoneInfo> que devuelven esas propiedades.

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a>Para obtener acceso al objeto TimeZoneInfo de la hora universal coordinada (UTC)

1. Use la `static` (`Shared` en Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> propiedad para tener acceso a la hora Universal coordinada.

2. En lugar de asignar la <xref:System.TimeZoneInfo> objeto devuelto por la propiedad a una variable de objeto, seguir teniendo acceso a la hora de Universal coordinada a través de la <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> propiedad.

### <a name="to-access-the-local-time-zone"></a>Para obtener acceso a la zona horaria local

1. Use la `static` (`Shared` en Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> propiedad para tener acceso a la zona horaria local.

2. En lugar de asignar la <xref:System.TimeZoneInfo> objeto devuelto por la propiedad a una variable de objeto, seguir teniendo acceso a la zona horaria local a través de la <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> propiedad.

## <a name="example"></a>Ejemplo

El siguiente código utiliza el <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> y <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> propiedades para convertir una hora de la zona horaria de Estados Unidos y Canadá, así como para mostrar el nombre de zona horaria en la consola.

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

Siempre debe tener acceso a la zona horaria local a través de la <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> propiedad en lugar de asignar la hora local de la zona a un <xref:System.TimeZoneInfo> variable de objeto. De forma similar, siempre debería acceder en hora Universal a través de la <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> propiedad en lugar de asignar la hora UTC de la zona a un <xref:System.TimeZoneInfo> variable de objeto. Esto evita la <xref:System.TimeZoneInfo> variable de objeto del que se invalida mediante una llamada a la <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> método.

## <a name="compiling-the-code"></a>Compilación del código

Para este ejemplo se necesita:

* Que se agregarán al proyecto una referencia a System.Core.dll.

* Que el <xref:System> se importan el espacio de nombres con el `using` instrucción (obligatorio en el código de C#).

## <a name="see-also"></a>Vea también

* [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
* [Búsqueda de las zonas horarias definidas en un sistema local](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
* [Crear instancias de un objeto TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md)
