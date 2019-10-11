---
title: Serialización y deserialización de C# JSON mediante .net
author: tdykstra
ms.author: tdykstra
ms.date: 09/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: 5ce98a7908470a402779436db43333d46f5101fc
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2019
ms.locfileid: "72180153"
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
* [Código fuente](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json)
* [Referencia de API](xref:System.Text.Json)
* [Guía básica](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/roadmap/README.md)
* Problemas de GitHub en el repositorio dotnet/corefx
  * [Debate sobre el desarrollo de System. Text. JSON](https://github.com/dotnet/corefx/issues/33115)
  * [Todos los problemas de System. Text. JSON](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json)
  * [Problemas de System. Text. JSON con la etiqueta JSON-funcionalidad-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc)
