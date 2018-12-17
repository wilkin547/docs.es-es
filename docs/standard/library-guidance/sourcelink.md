---
title: SourceLink y bibliotecas de .NET
description: Prácticas recomendadas para el uso de SourceLink para mejorar la depuración de las bibliotecas de .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 3bc72e158a5773b656095f9ce58b442469f91e67
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128937"
---
# <a name="sourcelink"></a>SourceLink

SourceLink es una tecnología que permite a los desarrolladores depurar el código fuente de los ensamblados de .NET de NuGet. SourceLink se ejecuta al crear el paquete NuGet e inserta metadatos de control de código fuente dentro de los ensamblados y el paquete. Los desarrolladores que descarguen el paquete y tengan SourceLink habilitado en Visual Studio pueden entrar en su código fuente. SourceLink proporciona metadatos de control de origen para crear una excelente experiencia de depuración.

## <a name="sourcelink-demo"></a>Demostración de SourceLink

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-sourcelink"></a>Uso de SourceLink

Puede encontrar instrucciones para el uso de SourceLink en el repositorio de GitHub [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md).

Puede usar [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) para confirmar que los metadatos de SourceLink se han insertado correctamente en el paquete. Compruebe que los metadatos de `Repository` están presentes con un identificador de comentarios y que los archivos .pdb se encuentran con los .dll de cada destino.

![SourceLink en NuGet Package Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink in NuGet Package Explorer")

**✔️ ES RECOMENDABLE** usar SourceLink para agregar metadatos de control de código fuente a los ensamblados y los paquetes NuGet.

> [!TIP]
> Puede mejorar aún más la experiencia de depuración de los desarrolladores mediante la adición de atributos del depurador a los tipos.
> * <xref:System.Diagnostics.DebuggerDisplayAttribute> puede personalizar cómo se muestra una clase o un campo en las ventanas de variables del depurador.
> * <xref:System.Diagnostics.DebuggerStepThroughAttribute> indica al depurador que recorra el código en lugar de ejecutarlo paso a paso.
> * <xref:System.Diagnostics.DebuggerBrowsableAttribute> controla si se muestra un miembro en las ventanas de variables del depurador.

**✔️ ES RECOMENDABLE** incluir los archivos de símbolos (`*.pdb`) en el paquete NuGet.

> Normalmente, publicaría los archivos de símbolos en un [paquete de símbolos](./nuget.md#symbol-packages). Actualmente el host público principal para paquetes de símbolos no es compatible con los archivos de símbolos portátiles (`*.pdb`) creados por los proyectos estilo de SDK, y los paquetes de símbolos no son útiles.

>[!div class="step-by-step"]
>[Anterior](dependencies.md)
>[Siguiente](publish-nuget-package.md)