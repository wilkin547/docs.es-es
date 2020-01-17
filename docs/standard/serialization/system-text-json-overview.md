---
title: Serialización y deserialización de C# JSON mediante .net
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: acb83be9b20a155b6b6a9fb5ade38e099f54e71d
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163597"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a>Serialización y deserialización de JSON (cálculo de referencias y desserialización) en .NET: información general

El espacio de nombres `System.Text.Json` proporciona funcionalidad para serializar y deserializar a partir de notación de objetos JavaScript (JSON).

El diseño de biblioteca enfatiza el alto rendimiento y la asignación de memoria baja en un conjunto de características amplio. La compatibilidad integrada con UTF-8 optimiza el proceso de lectura y escritura de texto JSON codificado como UTF-8, que es la codificación más frecuente de los datos en la web y los archivos en disco.

La biblioteca también proporciona clases para trabajar con un modelo de objetos de documento (DOM) en memoria. Esta característica permite el acceso aleatorio de solo lectura de los elementos de una cadena o un archivo JSON. 

## <a name="how-to-get-the-library"></a>Cómo obtener la biblioteca

* La biblioteca está integrada como parte del marco de trabajo compartido de [.net Core 3,0](https://aka.ms/netcore3download) .
* En el caso de otras plataformas de destino, instale el paquete NuGet [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) . El paquete admite:
  * .NET Standard 2,0 y versiones posteriores
  * .NET Framework 4.7.2 y versiones posteriores
  * .NET Core 2,0, 2,1 y 2,2

## <a name="additional-resources"></a>Recursos adicionales

* [Cómo usar la biblioteca](system-text-json-how-to.md)
* [Cómo migrar desde Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Cómo escribir convertidores](system-text-json-converters-how-to.md)
* [código fuente de System.Text.Json](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)
* [referencia de API de System.Text.Json](xref:System.Text.Json)
* [System.Text.Json. Referencia de API de serialización](xref:System.Text.Json.Serialization)
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
