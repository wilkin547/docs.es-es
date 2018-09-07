---
title: Guardar y restaurar zonas horarias
ms.date: 04/10/2017
ms.technology: dotnet-standard
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1dc983f1f0b2405f207d69c62b800ee854fcd409
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44081773"
---
# <a name="saving-and-restoring-time-zones"></a>Guardar y restaurar zonas horarias

La <xref:System.TimeZoneInfo> clase se basa en el registro para recuperar los datos de zona horaria predefinidos. Sin embargo, el registro es una estructura dinámica. Además, se usa la información de zona horaria que el registro contiene el sistema operativo principalmente para controlar las conversiones y los ajustes de hora para el año actual. Esto tiene dos implicaciones importantes para las aplicaciones que dependen de datos de zona horaria precisos:

* No se puede definir una zona horaria que se requiere una aplicación en el registro, o es posible que se han cambiado o quitado del registro.

* Una zona horaria que se define en el registro puede carecer de información sobre las reglas de ajuste especial que son necesarios para las conversiones de zona horaria históricos.

La <xref:System.TimeZoneInfo> clase trata estas limitaciones a través de su compatibilidad para la serialización (Guardar) y deserialización (restaurar) de datos de zona horaria.

## <a name="time-zone-serialization-and-deserialization"></a>La zona horaria serialización y deserialización

Guardado y restauración de una zona horaria por serializar y deserializar los datos de zona horaria implica simplemente dos llamadas de método:

* Puede serializar un <xref:System.TimeZoneInfo> objeto mediante una llamada a ese objeto <xref:System.TimeZoneInfo.ToSerializedString%2A> método. El método no toma ningún parámetro y devuelve una cadena que contiene información de zona horaria.

* Puede deserializar un <xref:System.TimeZoneInfo> objeto a partir de una cadena serializada pasando esa cadena a la `static` (`Shared` en Visual Basic) <xref:System.TimeZoneInfo.FromSerializedString%2A?displayProperty=nameWithType> método.

## <a name="serialization-and-deserialization-scenarios"></a>Escenarios de serialización y deserialización

La capacidad de guardar (o serializar) un <xref:System.TimeZoneInfo> objeto en una cadena y a restaurar (o deserializar) para su uso posterior aumenta la utilidad y la flexibilidad de la <xref:System.TimeZoneInfo> clase. Esta sección examinan algunas de las situaciones en que la serialización y deserialización son más útiles.

### <a name="serializing-and-deserializing-time-zone-data-in-an-application"></a>Serializar y deserializar los datos de zona horaria en una aplicación

Una zona horaria serializada se puede restaurar desde una cadena cuando sea necesario. Una aplicación podría hacer esto si la zona horaria que se puede recuperada del registro no puede convertir correctamente una fecha y hora dentro de un intervalo de fechas determinado. Por ejemplo, los datos de zona horaria en el registro de Windows XP es compatible con una única regla de ajuste, mientras que las zonas horarias definidas en el registro de Windows Vista normalmente proporcionan información acerca de las dos reglas de ajuste. Esto significa que las conversiones de tiempo históricos pueden ser inexactos. Serialización y deserialización de datos de zona horaria pueden controlar esta limitación.

En el ejemplo siguiente, un personalizado <xref:System.TimeZoneInfo> se define la clase que no tiene ninguna regla de ajuste para representar los Estados Unidos. Zona de hora estándar de 1883 hasta 1917, antes de la introducción del horario de verano en Estados Unidos. La zona horaria personalizada se serializa en una variable que tiene ámbito global. El método de conversión de zona horaria, `ConvertUtcTime`, se pasa a veces de hora Universal coordinada (UTC) para convertir. Si la fecha y hora se produce en 1917 o versiones anteriores, la zona horaria estándar del este personalizada se restaura desde una cadena serializada y reemplaza la zona horaria que se puede recuperada del registro.

[!code-csharp[System.TimeZone2.Serialization.1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/cs/Serialization.cs#1)]
[!code-vb[System.TimeZone2.Serialization.1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/vb/Serialization.vb#1)]

### <a name="handling-time-zone-exceptions"></a>Control de excepciones de zona horaria

Dado que el registro es una estructura dinámica, su contenido está sujeto a modificación accidental o deliberada. Esto significa que una zona horaria que debe definirse en el registro y que es necesario para una aplicación se ejecute correctamente puede que falte. Sin compatibilidad para la zona horaria serialización y deserialización, tiene pocas opciones, sino para controlar el resultado <xref:System.TimeZoneNotFoundException> al finalizar la aplicación. Sin embargo, mediante el uso de zona horaria serialización y deserialización, puede controlar inesperado <xref:System.TimeZoneNotFoundException> mediante la restauración de la zona horaria necesaria de una cadena serializada y la aplicación seguirá ejecutándose.

El ejemplo siguiente se crea y serializa una zona horaria estándar Central personalizada. A continuación, intenta recuperar la zona horaria estándar Central en el registro. Si inicia la operación de recuperación ya sea un <xref:System.TimeZoneNotFoundException> o <xref:System.InvalidTimeZoneException>, el controlador de excepciones deserializa la zona horaria.

[!code-csharp[System.TimeZone2.Serialization.2#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/cs/Serialization2.cs#1)]
[!code-vb[System.TimeZone2.Serialization.2#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/vb/Serialization2.vb#1)]

### <a name="storing-a-serialized-string-and-restoring-it-when-needed"></a>Almacenar una cadena serializada y restaurarlo cuando sea necesario

Los ejemplos anteriores tiene almacenada información de zona horaria a una variable de cadena y restaurar cuando sea necesario. Sin embargo, la cadena que contiene información de zona sí se puede almacenar en algún medio de almacenamiento, como un archivo externo, un archivo de recursos de tiempo serializada se incrusta en la aplicación o el registro. (Tenga en cuenta que se debe almacenar información sobre zonas horarias personalizadas además de las claves de zona horaria del sistema en el registro.)

Almacenar una cadena de zona horaria serializada de esta manera, también separa la rutina de creación de la zona horaria desde la propia aplicación. Por ejemplo, puede ejecutar una rutina de creación de la zona horaria y se cree un archivo de datos que contiene información histórica de zonas horarias que puede usar una aplicación. El archivo de datos puede ser, a continuación, se puede instalar con la aplicación y se puede abrir y uno o varios de sus zonas horarias se pueden deserializar cuando la aplicación los necesita.

Para obtener un ejemplo que usa un recurso incrustado para almacenar los datos serializados de zona horaria, consulte [Cómo: guardar zonas horarias en un recurso incrustado](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) y [Cómo: restaurar zonas horarias de un recurso incrustado](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).

## <a name="see-also"></a>Vea también

* [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
