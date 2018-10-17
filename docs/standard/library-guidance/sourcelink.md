---
title: Bibliotecas de .NET y de SourceLink
description: Prácticas recomendadas para el uso de SourceLink para mejorar la depuración para bibliotecas de. NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: fa4af47eaa5dd1510640c2bf0ebb2187b56efae0
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2018
ms.locfileid: "49370316"
---
# <a name="sourcelink"></a>SourceLink

SourceLink es una tecnología que permite depurar el código fuente de los ensamblados de .NET de NuGet por desarrolladores. SourceLink ejecuta al crear el paquete de NuGet y las incrusta los metadatos de control de código fuente dentro de los ensamblados y el paquete. Los desarrolladores que descargue el paquete y dispondrá de SourceLink habilitado en Visual Studio pueden entrar en su código fuente. SourceLink proporciona los metadatos de control de origen para crear una excelente experiencia de depuración.

## <a name="sourcelink-demo"></a>Demostración de SourceLink

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-sourcelink"></a>Uso de SourceLink

Puede encontrar instrucciones para el uso de SourceLink en el [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md) repositorio de GitHub.

Puede usar [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) para confirmar que los metadatos de SourceLink se ha insertado correctamente en el paquete. Compruebe el `Repository` metadatos están presente con un identificador de comentario y que los archivos .pdb se encuentran con DLL de cada destino.

![SourceLink en el Explorador de paquetes de NuGet](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink en el Explorador de paquetes de NuGet")

**Considere la posibilidad de ✔️** con SourceLink para agregar metadatos de control de origen a los ensamblados y paquetes de NuGet.

**Considere la posibilidad de ✔️** incluyendo archivos PDB en el paquete NuGet.

>[!div class="step-by-step"]
[Anterior](./dependencies.md)
[Siguiente](./publish-nuget-package.md)
