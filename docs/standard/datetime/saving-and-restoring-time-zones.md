---
description: Más información acerca de cómo guardar y restaurar zonas horarias
title: Guardado y restauración de zonas horarias
ms.date: 04/10/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- restoring time zones
- deserialization [.NET], time zones
- serialization [.NET], time zones
- time zone objects [.NET], restoring
- saving time zones
- time zone objects [.NET], deserializing
- time zones [.NET], saving
- time zones [.NET], restoring
- time zone objects [.NET], serializing
- time zone objects [.NET], saving
ms.assetid: 4028b310-e7ce-49d4-a646-1e83bfaf6f9d
ms.openlocfilehash: bd888c2d9a1f02fa05fd1abf9d984022be03e192
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99702449"
---
# <a name="saving-and-restoring-time-zones"></a>Guardado y restauración de zonas horarias

La <xref:System.TimeZoneInfo> clase se basa en el registro para recuperar los datos de zona horaria predefinidos. Sin embargo, el registro es una estructura dinámica. Además, el sistema operativo usa la información de zona horaria que el registro contiene principalmente para controlar los ajustes de tiempo y las conversiones del año actual. Esto tiene dos implicaciones importantes en las aplicaciones que se basan en datos de zona horaria precisos:

- Es posible que una zona horaria requerida por una aplicación no se defina en el registro o que se le haya cambiado el nombre o que se haya quitado del registro.

- Una zona horaria que se define en el registro puede carecer de información sobre las reglas de ajuste concretas que son necesarias para las conversiones de zona horaria históricas.

La <xref:System.TimeZoneInfo> clase aborda estas limitaciones a través de su compatibilidad con la serialización (almacenamiento) y la deserialización (restauración) de datos de zona horaria.

## <a name="time-zone-serialization-and-deserialization"></a>Serialización y deserialización de zona horaria

Guardar y restaurar una zona horaria mediante la serialización y deserialización de datos de zona horaria implica solo dos llamadas al método:

- Puede serializar un <xref:System.TimeZoneInfo> objeto llamando al método de ese objeto <xref:System.TimeZoneInfo.ToSerializedString%2A> . El método no toma ningún parámetro y devuelve una cadena que contiene información de zona horaria.

- Puede deserializar un <xref:System.TimeZoneInfo> objeto a partir de una cadena serializada pasando esa cadena al `static` método ( `Shared` en Visual Basic) <xref:System.TimeZoneInfo.FromSerializedString%2A?displayProperty=nameWithType> .

## <a name="serialization-and-deserialization-scenarios"></a>Escenarios de serialización y deserialización

La capacidad de guardar (o serializar) un <xref:System.TimeZoneInfo> objeto en una cadena y restaurar (o deserializar) para su uso posterior aumenta la utilidad y la flexibilidad de la <xref:System.TimeZoneInfo> clase. En esta sección se examinan algunas de las situaciones en las que la serialización y deserialización son más útiles.

### <a name="serializing-and-deserializing-time-zone-data-in-an-application"></a>Serialización y deserialización de datos de zona horaria en una aplicación

Una zona horaria serializada se puede restaurar a partir de una cadena cuando sea necesario. Una aplicación podría hacer esto si la zona horaria recuperada del registro no puede convertir correctamente una fecha y hora en un intervalo de fechas determinado. Por ejemplo, los datos de zona horaria en el registro de Windows XP admiten una única regla de ajuste, mientras que las zonas horarias definidas en el registro de Windows Vista normalmente proporcionan información sobre dos reglas de ajuste. Esto significa que las conversiones de hora históricas pueden ser inexactas. La serialización y deserialización de datos de zona horaria pueden controlar esta limitación.

En el ejemplo siguiente, <xref:System.TimeZoneInfo> se define una clase personalizada que no tiene reglas de ajuste para representar la zona horaria estándar del este de EE. UU. de 1883 a 1917, antes de la introducción del horario de verano en el Estados Unidos. La zona horaria personalizada se serializa en una variable que tiene ámbito global. El método de conversión de zona horaria, `ConvertUtcTime` , se pasa a la hora universal coordinada (UTC) horas que se va a convertir. Si la fecha y la hora se producen en 1917 o versiones anteriores, la zona horaria estándar del este se restaura a partir de una cadena serializada y reemplaza la zona horaria recuperada del registro.

[!code-csharp[System.TimeZone2.Serialization.1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/cs/Serialization.cs#1)]
[!code-vb[System.TimeZone2.Serialization.1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/vb/Serialization.vb#1)]

### <a name="handling-time-zone-exceptions"></a>Control de excepciones de zona horaria

Dado que el registro es una estructura dinámica, su contenido está sujeto a modificaciones accidentales o deliberadas. Esto significa que una zona horaria que debe definirse en el registro y que es necesaria para que una aplicación se ejecute correctamente puede que no esté presente. Sin compatibilidad con la serialización y deserialización de zona horaria, tiene poca elección pero controla el resultado <xref:System.TimeZoneNotFoundException> al finalizar la aplicación. Sin embargo, mediante la serialización y deserialización de zona horaria, puede controlar un inesperado <xref:System.TimeZoneNotFoundException> restaurando la zona horaria necesaria a partir de una cadena serializada y la aplicación continuará ejecutándose.

En el ejemplo siguiente se crea y serializa una zona horaria estándar central personalizada. A continuación, intenta recuperar la zona horaria estándar central del registro. Si la operación de recuperación inicia <xref:System.TimeZoneNotFoundException> o <xref:System.InvalidTimeZoneException> , el controlador de excepciones deserializa la zona horaria.

[!code-csharp[System.TimeZone2.Serialization.2#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/cs/Serialization2.cs#1)]
[!code-vb[System.TimeZone2.Serialization.2#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/vb/Serialization2.vb#1)]

### <a name="storing-a-serialized-string-and-restoring-it-when-needed"></a>Almacenar una cadena serializada y restaurarla cuando sea necesario

En los ejemplos anteriores se ha almacenado información de zona horaria en una variable de cadena y se ha restaurado cuando es necesario. Sin embargo, la cadena que contiene la información de zona horaria serializada se puede almacenar en un medio de almacenamiento, como un archivo externo, un archivo de recursos incrustado en la aplicación o el registro. (Tenga en cuenta que la información acerca de las zonas horarias personalizadas debe almacenarse además de las claves de zona horaria del sistema en el registro).

Almacenar una cadena de zona horaria serializada de esta manera también separa la rutina de creación de zona horaria de la propia aplicación. Por ejemplo, una rutina de creación de zona horaria puede ejecutar y crear un archivo de datos que contiene información histórica de zona horaria que una aplicación puede utilizar. El archivo de datos se puede instalar con la aplicación y se puede abrir y una o varias de sus zonas horarias se pueden deserializar cuando la aplicación los necesite.

Para obtener un ejemplo en el que se usa un recurso incrustado para almacenar datos de zona horaria serializados, consulte [Cómo: guardar zonas horarias en un recurso incrustado](save-time-zones-to-an-embedded-resource.md) y [Cómo: restaurar zonas horarias desde un recurso incrustado](restore-time-zones-from-an-embedded-resource.md).

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](index.md)
