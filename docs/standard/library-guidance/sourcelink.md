---
title: SourceLink y bibliotecas de .NET
description: Prácticas recomendadas para el uso de SourceLink para mejorar la depuración de las bibliotecas de .NET.
ms.date: 01/15/2019
ms.openlocfilehash: 0ebc7601f1ad92b0fc6ab4c7599b010cb42feb5d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706444"
---
# <a name="source-link"></a>SourceLink

SourceLink es una tecnología que permite a los desarrolladores depurar el código fuente de los ensamblados de .NET de NuGet. SourceLink se ejecuta al crear el paquete NuGet e inserta metadatos de control de código fuente dentro de los ensamblados y el paquete. Los desarrolladores que descarguen el paquete y tengan SourceLink habilitado en Visual Studio pueden entrar en su código fuente. SourceLink proporciona metadatos de control de origen para crear una excelente experiencia de depuración.

## <a name="source-link-demo"></a>Demostración de SourceLink

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-source-link"></a>Uso de SourceLink

Puede encontrar instrucciones para el uso de SourceLink en el repositorio de GitHub [dotnet/sourcelink](https://github.com/dotnet/sourcelink/blob/master/README.md).

Puede usar el [Explorador de paquetes NuGet](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) para confirmar que los metadatos de SourceLink se han insertado correctamente en el paquete. Compruebe que los metadatos de `Repository` están presentes con un identificador de la confirmación y que los archivos .pdb se encuentran con los .dll de cada destino.

![SourceLink en el explorador de paquetes NuGet](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink en el explorador de paquetes NuGet")

**✔️ ES RECOMENDABLE** usar SourceLink para agregar metadatos de control de código fuente a los ensamblados y los paquetes NuGet.

> [!TIP]
> Puede mejorar aún más la experiencia de depuración de los desarrolladores mediante la adición de atributos del depurador a los tipos.
>
> * <xref:System.Diagnostics.DebuggerDisplayAttribute> puede personalizar cómo se muestra una clase o un campo en las ventanas de variables del depurador.
> * <xref:System.Diagnostics.DebuggerStepThroughAttribute> indica al depurador que recorra el código en lugar de ejecutarlo paso a paso.
> * <xref:System.Diagnostics.DebuggerBrowsableAttribute> controla si se muestra un miembro en las ventanas de variables del depurador.

**✔️ CONSIDERE LA POSIBILIDAD DE** publicar archivos de símbolos (`*.pdb`).

> Para obtener la mejor experiencia de depuración, la biblioteca debe publicar archivos de símbolos, además de usar SourceLink. Para más información sobre los archivos de símbolos y los paquetes de símbolos, consulte [Paquetes de símbolos](./nuget.md#symbol-packages).

>[!div class="step-by-step"]
>[Anterior](dependencies.md)
>[Siguiente](publish-nuget-package.md)
