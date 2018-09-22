---
title: 'Cómo: crear una instancia de un objeto TimeZoneInfo'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- instantiating time zone objects
- time zone objects [.NET Framework], instantiation
ms.assetid: 8cb620e5-c6a6-4267-a52e-beeb73cd1a34
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8c8ff38325e26dd1bc946f6f12c365b6dea3e228
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2018
ms.locfileid: "46576683"
---
# <a name="how-to-instantiate-a-timezoneinfo-object"></a>Cómo: crear una instancia de un objeto TimeZoneInfo

La manera más común para crear una instancia de un objeto <xref:System.TimeZoneInfo> es recuperar información sobre él del registro. En este tema se describe cómo crear una instancia de un objeto <xref:System.TimeZoneInfo> desde el registro del sistema local.

### <a name="to-instantiate-a-timezoneinfo-object"></a>Cómo crear una instancia de un objeto TimeZoneInfo

1. Declare un objeto <xref:System.TimeZoneInfo> .

2. Llame a la `static` (`Shared` en Visual Basic) <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> método.

3. Controle las excepciones que genere el método, especialmente la <xref:System.TimeZoneNotFoundException> que se produce si la zona horaria no está definida en el registro.

## <a name="example"></a>Ejemplo

El siguiente código recupera un objeto <xref:System.TimeZoneInfo> que representa la zona horaria estándar del Este y muestra la hora estándar del Este que corresponde a la hora local.

[!code-csharp[System.TimeZone2.Concepts#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#5)]
[!code-vb[System.TimeZone2.Concepts#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#5)]

El <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> único parámetro del método es el identificador de la zona horaria que desea recuperar, que se corresponde con el objeto <xref:System.TimeZoneInfo.Id%2A?displayProperty=nameWithType> propiedad. El identificador de zona horaria es un campo clave que identifica de forma única la zona horaria. Aunque la mayoría de las claves son relativamente cortas, el identificador de zona horaria es comparativamente largo. En la mayoría de los casos, su valor corresponde a la propiedad <xref:System.TimeZoneInfo.StandardName%2A> de un objeto <xref:System.TimeZoneInfo> , que se utiliza para proporcionar el nombre de la hora estándar de la zona horaria. Sin embargo, hay excepciones. La mejor manera de asegurarse de que se proporciona un identificador válido es enumerar las zonas horarias disponibles en el sistema y anotar los identificadores de las zonas horarias que figuran en ellas. Para obtener un ejemplo, vea [Cómo: Enumerar zonas horarias presentes en un equipo](../../../docs/standard/datetime/enumerate-time-zones.md). El tema [Buscar las zonas horarias definidas en un sistema local](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md) también contiene una lista de los identificadores de zona horaria seleccionada.

Si se encuentra la zona horaria, el método devuelve su objeto <xref:System.TimeZoneInfo> . Si no se encuentra la zona horaria, el método produce una <xref:System.TimeZoneNotFoundException>. Si se encuentra la zona horaria, pero sus datos están dañados o incompletos, el método produce una <xref:System.InvalidTimeZoneException>.

Si la aplicación se basa en una zona horaria que debe estar presente, debe llamar primero al método <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> para recuperar la información de zona horaria del registro. Si se produce un error en la llamada al método, el controlador de excepciones debe crear una nueva instancia de la zona horaria o volver a crearla mediante la deserialización de un objeto <xref:System.TimeZoneInfo> serializado. Consulte [Cómo: restaurar zonas horarias de un recurso incrustado](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) para obtener un ejemplo.

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
- [Búsqueda de las zonas horarias definidas en un sistema local](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
- [Acceso a los objetos de zona horaria local y UTC predefinidos](../../../docs/standard/datetime/access-utc-and-local.md)
