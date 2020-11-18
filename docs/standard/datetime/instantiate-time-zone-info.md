---
title: Procedimiento para crear una instancia de un objeto TimeZoneInfo
ms.date: 04/10/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- instantiating time zone objects
- time zone objects [.NET], instantiation
ms.assetid: 8cb620e5-c6a6-4267-a52e-beeb73cd1a34
ms.openlocfilehash: c4e441e793244dfe368fb86c3e77fcf67a685558
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94817827"
---
# <a name="how-to-instantiate-a-timezoneinfo-object"></a>Procedimiento para crear una instancia de un objeto TimeZoneInfo

La manera más común para crear una instancia de un objeto <xref:System.TimeZoneInfo> es recuperar información sobre él del registro. En este tema se describe cómo crear una instancia de un objeto <xref:System.TimeZoneInfo> desde el registro del sistema local.

### <a name="to-instantiate-a-timezoneinfo-object"></a>Cómo crear una instancia de un objeto TimeZoneInfo

1. Declare un objeto <xref:System.TimeZoneInfo> .

2. Llame al método `static` (`Shared` en Visual Basic) <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> .

3. Controle las excepciones que genere el método, especialmente la <xref:System.TimeZoneNotFoundException> que se produce si la zona horaria no está definida en el registro.

## <a name="example"></a>Ejemplo

El siguiente código recupera un objeto <xref:System.TimeZoneInfo> que representa la zona horaria estándar del Este y muestra la hora estándar del Este que corresponde a la hora local.

[!code-csharp[System.TimeZone2.Concepts#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#5)]
[!code-vb[System.TimeZone2.Concepts#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#5)]

El único parámetro del método <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> es el identificador de la zona horaria que quiere recuperar, que se corresponde con la propiedad <xref:System.TimeZoneInfo.Id%2A?displayProperty=nameWithType> del objeto. El identificador de zona horaria es un campo clave que identifica de forma única la zona horaria. Aunque la mayoría de las claves son relativamente cortas, el identificador de zona horaria es comparativamente largo. En la mayoría de los casos, su valor corresponde a la propiedad <xref:System.TimeZoneInfo.StandardName%2A> de un objeto <xref:System.TimeZoneInfo> , que se utiliza para proporcionar el nombre de la hora estándar de la zona horaria. Sin embargo, hay excepciones. La mejor manera de asegurarse de que se proporciona un identificador válido es enumerar las zonas horarias disponibles en el sistema y anotar los identificadores de las zonas horarias que figuran en ellas. Para obtener un ejemplo, vea [How to: Enumerate time zones present on a computer](enumerate-time-zones.md). El tema [Finding the time zones defined on a local system](finding-the-time-zones-on-local-system.md) también contiene una lista de identificadores de la zona horaria seleccionada.

Si se encuentra la zona horaria, el método devuelve su objeto <xref:System.TimeZoneInfo> . Si no se encuentra la zona horaria, el método produce una <xref:System.TimeZoneNotFoundException>. Si se encuentra la zona horaria, pero sus datos están dañados o incompletos, el método produce una <xref:System.InvalidTimeZoneException>.

Si la aplicación se basa en una zona horaria que debe estar presente, debe llamar primero al método <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> para recuperar la información de zona horaria del registro. Si se produce un error en la llamada al método, el controlador de excepciones debe crear una nueva instancia de la zona horaria o volver a crearla mediante la deserialización de un objeto <xref:System.TimeZoneInfo> serializado. Consulte [Cómo: restaurar zonas horarias de un recurso incrustado](restore-time-zones-from-an-embedded-resource.md) para obtener un ejemplo.

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](index.md)
- [Buscar las zonas horarias definidas en un sistema local](finding-the-time-zones-on-local-system.md)
- [Cómo: obtener acceso a los objetos de zona horaria local y UTC predefinidos](access-utc-and-local.md)
