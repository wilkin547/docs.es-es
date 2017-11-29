---
title: Guardar y restaurar zonas horarias
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- restoring time zones
- deserialization [.NET Framework], time zones
- serialization [.NET Framework], time zones
- time zone objects [.NET Framework], restoring
- saving time zones
- time zone objects [.NET Framework], deserializing
- time zones [.NET Framework], saving
- time zones [.NET Framework], restoring
- time zone objects [.NET Framework], serializing
- time zone objects [.NET Framework], saving
ms.assetid: 4028b310-e7ce-49d4-a646-1e83bfaf6f9d
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d4e04de61ed5636d0102af694220dce06c256751
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="saving-and-restoring-time-zones"></a>Guardar y restaurar zonas horarias

La <xref:System.TimeZoneInfo> clase se basa en el registro para recuperar los datos de zona horaria predefinidos. Sin embargo, el registro es una estructura dinámica. Además, se utiliza la información de zona horaria que el registro contiene el sistema operativo principalmente para realizar los ajustes de hora y las conversiones para el año actual. Esto tiene dos implicaciones importantes para las aplicaciones que dependen de datos de zona horaria precisos:

* No se puede definir una zona horaria que se requiere una aplicación en el registro, o haya cambiado el nombre o quita del registro.

* Una zona horaria que se define en el registro puede carecer de información sobre las reglas de ajuste especial que son necesarios para las conversiones de histórica de zonas horarias.

La <xref:System.TimeZoneInfo> clase soluciona estas limitaciones a través de su compatibilidad para la serialización (Guardar) y deserialización (restaurar) de datos de zona horaria.

## <a name="time-zone-serialization-and-deserialization"></a>Zona horaria serialización y deserialización

Guardar y restaurar una zona horaria al serializar y deserializar los datos de zona horaria implica dos llamadas al método:

* Puede serializar un <xref:System.TimeZoneInfo> objeto mediante una llamada a ese objeto <xref:System.TimeZoneInfo.ToSerializedString%2A> método. El método no toma ningún parámetro y devuelve una cadena que contiene información de zona horaria.

* Puede deserializar un <xref:System.TimeZoneInfo> objeto a partir de una cadena serializada pasando esa cadena a la `static` (`Shared` en Visual Basic) <xref:System.TimeZoneInfo.FromSerializedString%2A?displayProperty=nameWithType> método.

## <a name="serialization-and-deserialization-scenarios"></a>Escenarios de serialización y deserialización

La capacidad de guardar (o serializar) un <xref:System.TimeZoneInfo> objeto en una cadena y restaurarlo (o deserializarlo) para su uso posterior aumenta la utilidad y la flexibilidad de la <xref:System.TimeZoneInfo> clase. Esta sección examinan algunas de las situaciones en que la serialización y deserialización son muy útiles.

### <a name="serializing-and-deserializing-time-zone-data-in-an-application"></a>Serializar y deserializar los datos de zona horaria en una aplicación

Una zona horaria serializada se puede restaurar desde una cadena cuando sea necesario. Una aplicación podría hacer esto si la zona horaria recuperada del registro es no se puede convertir correctamente una fecha y hora en un intervalo de fechas determinado. Por ejemplo, datos de zona horaria en el registro de Windows XP es compatible con una única regla de ajuste, mientras que las zonas horarias definidas en el registro de Windows Vista normalmente ofrecen información acerca de las dos reglas de ajuste. Esto significa que las conversiones horarias históricas no sea correcta. Serialización y deserialización de datos de zona horaria pueden tratar esta limitación.

En el ejemplo siguiente, un personalizado <xref:System.TimeZoneInfo> se define la clase que no tiene ninguna regla de ajuste para representar los Estados Unidos Hora estándar del este zona desde 1883 hasta 1917, antes de la introducción del horario de verano en Estados Unidos. La zona horaria personalizada se serializa en una variable que tiene ámbito global. El método de conversión de zona horaria, `ConvertUtcTime`, se pasa a veces de hora Universal coordinada (UTC) para convertir. Si la fecha y hora se produce en 1917 o versiones anteriores, la zona horaria estándar del este personalizada restaurados a partir de una cadena serializada y reemplaza la zona horaria recuperada del registro.

[!code-csharp[System.TimeZone2.Serialization.1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/cs/Serialization.cs#1)]
[!code-vb[System.TimeZone2.Serialization.1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/vb/Serialization.vb#1)]

### <a name="handling-time-zone-exceptions"></a>Control de excepciones de zona horaria

Dado que el registro es una estructura dinámica, su contenido está sujetos a modificación accidental o deliberada. Esto significa que una zona horaria que debe definirse en el registro y que es necesario para una aplicación se ejecute correctamente puede que falte. Sin compatibilidad para la zona horaria serialización y deserialización, tiene muchas más opciones pero a manipular resultante <xref:System.TimeZoneNotFoundException> si finaliza la aplicación. Sin embargo, si usa la zona horaria serialización y deserialización, se puede controlar inesperado <xref:System.TimeZoneNotFoundException> mediante la restauración de la zona horaria necesaria de una cadena serializada y la aplicación continuará ejecutándose.

En el ejemplo siguiente se crea y serializa una zona horaria estándar Central personalizada. A continuación, intenta recuperar la zona horaria estándar Central del registro. Si inicia la operación de recuperación ya sea un <xref:System.TimeZoneNotFoundException> o <xref:System.InvalidTimeZoneException>, el controlador de excepciones deserializa la zona horaria.

[!code-csharp[System.TimeZone2.Serialization.2#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/cs/Serialization2.cs#1)]
[!code-vb[System.TimeZone2.Serialization.2#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/vb/Serialization2.vb#1)]

### <a name="storing-a-serialized-string-and-restoring-it-when-needed"></a>Almacenar una cadena serializada y restaurarla cuando sea necesario

Los ejemplos anteriores se almacenan información de zona horaria a una variable de cadena y la restaura cuando sea necesario. Sin embargo, la cadena que contiene información de la zona puede propio almacenarse en algún medio de almacenamiento, como un archivo externo, un archivo de recursos de tiempo serializado se incrusta en la aplicación o el registro. (Tenga en cuenta que se debe almacenar información sobre zonas horarias personalizadas además de claves de zona horaria del sistema en el registro).

Almacenar una cadena de zona horaria serializada de esta manera, también separa la rutina de creación de la zona horaria de la propia aplicación. Por ejemplo, una rutina de creación de zonas horarias puede ejecutar y crear un archivo de datos que contiene información histórica de zonas horarias que una aplicación puede utilizar. El archivo de datos puede ser, a continuación, puede instalar con la aplicación y se puede abrir y uno o varios de sus zonas horarias se pueden deserializar cuando la aplicación los necesita.

Para obtener un ejemplo que usa un recurso incrustado para almacenar datos de zona horaria serializada, consulte [Cómo: guardar zonas horarias en un recurso incrustado](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) y [Cómo: restaurar zonas horarias de un recurso incrustado](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).

## <a name="see-also"></a>Vea también

[Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
