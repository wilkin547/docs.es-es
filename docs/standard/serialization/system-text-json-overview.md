---
title: 'Serialización y deserialización de JSON con C#: .NET'
description: En esta introducción se describe la funcionalidad del espacio de nombres System.Text.Json para serializar y deserializar con JSON en .NET.
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: cb5c15c2a5c336e2d5b4a3754fa7a02a370602f3
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009890"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a>Serialización y deserialización de JSON en .NET: información general

El espacio de nombres `System.Text.Json` proporciona funcionalidad para serializar y deserializar desde JSON (notaciones de objetos JavaScript).

El diseño de biblioteca resalta el rendimiento elevado y la asignación de memoria baja en un amplio conjunto de características. La compatibilidad integrada con UTF-8 optimiza el proceso de lectura y escritura de texto JSON codificado como UTF-8, que es la codificación más frecuente de los datos en Internet y los archivos en disco.

La biblioteca también proporciona clases para trabajar con un Document Object Model (DOM) en memoria. Esta característica permite el acceso de solo lectura aleatorio de los elementos de una cadena o archivo JSON.

## <a name="how-to-get-the-library"></a>Cómo obtener la biblioteca

* La biblioteca está integrada como parte del marco compartido para .NET Core 3.0 y versiones posteriores.
* Para versiones anteriores del marco, instale el paquete [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) de NuGet, que admite lo siguiente:

  * .NET Standard 2.0 y versiones posteriores
  * .NET Framework 4.7.2 y versiones posteriores
  * .NET Core 2.0, 2.1 y 2.2

## <a name="additional-resources"></a>Recursos adicionales

* [Cómo usar la biblioteca](system-text-json-how-to.md)
* [Creación de instancias de JsonSerializerOptions](system-text-json-configure-options.md)
* [Habilitación de la coincidencia sin distinción entre mayúsculas y minúsculas](system-text-json-character-casing.md)
* [Personalización de los nombres y valores de propiedad](system-text-json-customize-properties.md)
* [Omisión de propiedades](system-text-json-ignore-properties.md)
* [Permiso del formato JSON no válido](system-text-json-invalid-json.md)
* [JSON de desbordamiento de control](system-text-json-handle-overflow.md)
* [Conservación de las referencias](system-text-json-preserve-references.md)
* [Tipos inmutables y descriptores de acceso no públicos](system-text-json-immutability.md)
* [Serialización polimórfica](system-text-json-polymorphism.md)
* [Migración desde Newtonsoft.Json a System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Personalización de la codificación de caracteres](system-text-json-character-encoding.md)
* [Escritura de serializadores y deserializadores personalizados](write-custom-serializer-deserializer.md)
* [Escritura de convertidores personalizados para la serialización de JSON](system-text-json-converters-how-to.md)
* [Compatibilidad con DateTime y DateTimeOffset](../datetime/system-text-json-support.md)
* [Referencia de API de System.Text.Json](xref:System.Text.Json)
* [Referencia de API de System.Text.Json.Serialization](xref:System.Text.Json.Serialization)
