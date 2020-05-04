---
title: 'Serialización y deserialización de JSON con C#: .NET'
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 660a2831aa6a807486fc47eae880bcd11347c547
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159551"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a>Serialización y deserialización de JSON en .NET: información general

El espacio de nombres `System.Text.Json` proporciona funcionalidad para serializar y deserializar desde JSON (notaciones de objetos JavaScript).

El diseño de biblioteca resalta el rendimiento elevado y la asignación de memoria baja en un amplio conjunto de características. La compatibilidad integrada con UTF-8 optimiza el proceso de lectura y escritura de texto JSON codificado como UTF-8, que es la codificación más frecuente de los datos en Internet y los archivos en disco.

La biblioteca también proporciona clases para trabajar con un Document Object Model (DOM) en memoria. Esta característica permite el acceso de solo lectura aleatorio de los elementos de una cadena o archivo JSON.

## <a name="how-to-get-the-library"></a>Cómo obtener la biblioteca

* La biblioteca está integrada como parte del marco compartido de [.NET Core 3.0](https://aka.ms/netcore3download).
* En cuanto a otros marcos de destino, instale el paquete NuGet [System.Text.Json](https://www.nuget.org/packages/System.Text.Json), que admite lo siguiente:
  * .NET Standard 2.0 y versiones posteriores
  * .NET Framework 4.7.2 y versiones posteriores
  * .NET Core 2.0, 2.1 y 2.2

## <a name="additional-resources"></a>Recursos adicionales

* [Cómo usar la biblioteca](system-text-json-how-to.md)
* [Procedimiento para migrar desde Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Procedimiento para escribir convertidores](system-text-json-converters-how-to.md)
* [Código fuente System.Text.Json](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)
* [Referencia de API System.Text.Json](xref:System.Text.Json)
* [System.Text.JsonReferencia de API .Serialization](xref:System.Text.Json.Serialization)
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
