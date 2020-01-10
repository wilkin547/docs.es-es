---
title: Serialización y deserialización de C# JSON mediante .net
ms.date: 09/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 6561d5e1580e1170369622ebc7bb330ff4e0964f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705787"
---
# <a name="json-serialization-in-net---overview"></a>Serialización de JSON en .NET: información general

El espacio de nombres `System.Text.Json` proporciona funcionalidad para serializar y deserializar a partir de notación de objetos JavaScript (JSON).

El diseño de biblioteca enfatiza el alto rendimiento y la asignación de memoria baja en un conjunto de características amplio. La compatibilidad integrada con UTF-8 optimiza el proceso de lectura y escritura de texto JSON codificado como UTF-8, que es la codificación más frecuente de los datos en la web y los archivos en disco.

La biblioteca también proporciona clases para trabajar con un modelo de objetos de documento (DOM) en memoria. Esta característica permite el acceso aleatorio de solo lectura de los elementos de una cadena o un archivo JSON. 

## <a name="how-to-get-the-library"></a>Cómo obtener la biblioteca

* La biblioteca está integrada como parte del marco de trabajo compartido de [.net Core 3,0](https://aka.ms/netcore3download) .
* En el caso de otras plataformas de destino, instale el paquete NuGet [System. Text. JSON](https://www.nuget.org/packages/System.Text.Json) . El paquete admite:
  * .NET Standard 2,0 y versiones posteriores
  * .NET Framework 4.6.1 y versiones posteriores
  * .NET Core 2,0, 2,1 y 2,2

## <a name="additional-resources"></a>Recursos adicionales

* [Cómo usar la biblioteca](system-text-json-how-to.md)
* [Código fuente](https://github.com/dotnet/runtime/tree/master/src/libraries/System.Text.Json)
* [Referencia de API](xref:System.Text.Json)
* [Guía básica](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Text.Json/roadmap/README.md)
* Problemas de GitHub en el repositorio dotnet/corefx
  * [Debate sobre el desarrollo de System. Text. JSON](https://github.com/dotnet/corefx/issues/33115) <!-- TODO: Issues are still not moved to the new repo-->
  * [Todos los problemas de System. Text. JSON](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json)
  * [Problemas de System. Text. JSON con la etiqueta JSON-funcionalidad-doc](https://github.com/dotnet/runtime/labels/json-functionality-doc)
