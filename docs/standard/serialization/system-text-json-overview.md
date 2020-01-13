---
title: Serialización y deserialización de C# JSON mediante .net
ms.date: 01/10/2020
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: c05783963ba521109fb542f247ec9e62fdb5c2d9
ms.sourcegitcommit: dfad244ba549702b649bfef3bb057e33f24a8fb2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2020
ms.locfileid: "75904644"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a>Serialización y deserialización de JSON (cálculo de referencias y desserialización) en .NET: información general

El espacio de nombres `System.Text.Json` proporciona funcionalidad para serializar y deserializar a partir de notación de objetos JavaScript (JSON).

El diseño de biblioteca enfatiza el alto rendimiento y la asignación de memoria baja en un conjunto de características amplio. La compatibilidad integrada con UTF-8 optimiza el proceso de lectura y escritura de texto JSON codificado como UTF-8, que es la codificación más frecuente de los datos en la web y los archivos en disco.

La biblioteca también proporciona clases para trabajar con un modelo de objetos de documento (DOM) en memoria. Esta característica permite el acceso aleatorio de solo lectura de los elementos de una cadena o un archivo JSON. 

## <a name="how-to-get-the-library"></a>Cómo obtener la biblioteca

* La biblioteca está integrada como parte del marco de trabajo compartido de [.net Core 3,0](https://aka.ms/netcore3download) .
* En el caso de otras plataformas de destino, instale el paquete NuGet [System. Text. JSON](https://www.nuget.org/packages/System.Text.Json) . El paquete admite:
  * .NET Standard 2,0 y versiones posteriores
  * .NET Framework 4.7.2 y versiones posteriores
  * .NET Core 2,0, 2,1 y 2,2

## <a name="additional-resources"></a>Recursos adicionales

* [Cómo usar la biblioteca](system-text-json-how-to.md)
* [Cómo migrar desde Newtonsoft. JSON](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Cómo escribir convertidores](system-text-json-converters-how-to.md)
* [Código fuente de System. Text. JSON](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)
* [Referencia de la API System. Text. JSON](xref:System.Text.Json)
* [Referencia de API de System. Text. JSON. Serialization](xref:System.Text.Json.Serialization)
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
