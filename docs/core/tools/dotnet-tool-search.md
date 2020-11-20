---
title: Comando dotnet tool search
description: El comando dotnet tool search busca las herramientas de .NET publicadas en NuGet.org.
ms.date: 11/11/2020
ms.openlocfilehash: e0289e651ec4a439c791c8c948bef2d85d9c3794
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634147"
---
# <a name="dotnet-tool-search"></a>dotnet tool search

**Este artículo se aplica a:** ✔️ SDK de .NET 5.0 y versiones posteriores

## <a name="name"></a>Name

`dotnet tool search`: busca todas las [herramientas de .NET](global-tools.md) publicadas en NuGet.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet tool search [--detail]  [--prerelease]
    [--skip <NUMBER>] [--take <NUMBER>] <SEARCH TERM>

dotnet tool search -h|--help
```

## <a name="description"></a>Descripción

El comando `dotnet tool search` proporciona una manera de buscar en NuGet las herramientas que se pueden usar como herramientas globales, de ruta de acceso de herramientas o locales de .NET. El comando busca en los nombres de herramienta y los metadatos, como títulos, descripciones y etiquetas.

El comando usa la [API Search de NuGet](/nuget/api/search-query-service-resource#search-for-packages). Filtra por `packageType=dotnettool` para seleccionar solo los paquetes de herramientas de .NET.

## <a name="options"></a>Opciones

- **`--detail`**

  Muestra los resultados detallados de la consulta.

- **`--prerelease`**

  Incluye paquetes en versión preliminar.

- **`--skip <NUMBER>`**

  Especifica el número de resultados de la consulta que se omiten. Se usa para la paginación.

- **`--take <NUMBER>`**

  Especifica el número de resultados de la consulta que se muestran. Se usa para la paginación.

- **`-h|--help`**

  Muestra la ayuda de la línea de comandos.

## <a name="examples"></a>Ejemplos

- Busque herramientas de .NET en NuGet.org que incluyan "formato" en el nombre o la descripción del paquete:

  ```dotnetcli
  dotnet tool search format
  ```

  La salida se parece al ejemplo siguiente:

  ```output
  Package ID                              Latest Version      Authors                                                                     Downloads      Verified
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------
  dotnet-format                           4.1.131201          Microsoft                                                                   496746
  bsoa.generator                          1.0.0               Microsoft                                                                   533
  ```

- Busque herramientas de .NET en NuGet.org que incluyan "formato" en el nombre o los metadatos del paquete, muestre solo el primer resultado y muestre una vista detallada.

  ```dotnetcli
  dotnet tool search format --take 1 --detail
  ```

  La salida se parece al ejemplo siguiente:

  ```output
  ----------------
  dotnet-format
  Latest Version: 4.1.131201
  Authors: Microsoft
  Tags:
  Downloads: 496746
  Verified: False
  Description: Command line tool for formatting C# and Visual Basic code files based on .editorconfig settings.
  Versions:
          3.0.2 Downloads: 1973
          3.0.4 Downloads: 9064
          3.1.37601 Downloads: 114730
          3.2.107702 Downloads: 13423
          3.3.111304 Downloads: 131195
          4.0.130203 Downloads: 78610
          4.1.131201 Downloads: 145927
  ```

## <a name="see-also"></a>Consulte también

- [Herramientas de .NET](global-tools.md)
- [Tutorial: Instalación y uso de una herramienta global de .NET mediante la CLI de .NET](global-tools-how-to-use.md)
- [Tutorial: Instalación y uso de una herramienta local de .NET mediante la CLI de .NET](local-tools-how-to-use.md)
