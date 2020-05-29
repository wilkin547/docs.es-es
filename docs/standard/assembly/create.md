---
title: Creación de ensamblados
description: Aprenda a crear ensamblados de uno o varios archivos mediante un IDE, como Visual Studio, o los compiladores y las herramientas que proporciona Windows SDK.
ms.date: 08/19/2019
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- single-file assemblies
- assemblies [.NET Framework], creating
- multifile assemblies
ms.assetid: 54832ee9-dca8-4c8b-913c-c0b9d265e9a4
ms.openlocfilehash: 3e17d6a066d937a161135b8b03c3f9258f3586b0
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378519"
---
# <a name="create-assemblies"></a>Creación de ensamblados

Para crear ensamblados de un solo archivo o de varios archivos, se puede usar un IDE, como Visual Studio, o los compiladores y las herramientas que proporciona Windows SDK. El ensamblado más sencillo es un solo archivo que tiene un nombre simple y se carga en un solo dominio de aplicación. Este ensamblado no se somete a la comprobación de versión y no pueden hacer referencia a él otros ensamblados fuera del directorio de la aplicación. Para desinstalar la aplicación que se compone del ensamblado, basta con eliminar el directorio en el que reside. Muchos desarrolladores solo necesitan un ensamblado de estas características para implementar una aplicación.

Puede crear un ensamblado de varios archivos a partir de varios módulos de código y archivos de recursos. También puede crear un ensamblado que compartan varias aplicaciones. Un ensamblado compartido debe tener un nombre seguro y puede implementarse en la caché global de ensamblados.

Existen varias opciones al agrupar módulos de código y recursos en ensamblados, en función de los factores siguientes:

- Control de versiones

     Agrupar módulos con la misma información de versión.

- Implementación

     Agrupar módulos de código y recursos compatibles con el modelo de implementación.

- Reutilización

     Agrupar módulos si se pueden usar juntos lógicamente con el mismo fin. Por ejemplo, un ensamblado formado por tipos y clases que se usan con poca frecuencia para el mantenimiento de programas puede colocarse en el mismo ensamblado. Además, los tipos que está previsto compartir con varias aplicaciones deben agruparse en un ensamblado y el ensamblado debe firmarse con un nombre seguro.

- Seguridad

     Agrupar módulos que contienen tipos que requieren los mismos permisos de seguridad.

- Ámbito

     Agrupar módulos que contienen tipos cuya visibilidad se debe restringir al mismo ensamblado.

Se deben tener en cuenta consideraciones especiales a la hora de poner los ensamblados de Common Language Runtime a disposición de aplicaciones COM no administradas. Para obtener más información sobre cómo trabajar con código no administrado, vea [Exposición de los componentes de .NET a COM](../../framework/interop/exposing-dotnet-components-to-com.md).

## <a name="see-also"></a>Vea también

- [Control de versiones de los ensamblados](versioning.md)
- [Cómo: Compilar un ensamblado de un solo archivo](../../framework/app-domains/build-single-file-assembly.md)
- [Cómo: Compilar un ensamblado de varios archivos](../../framework/app-domains/build-multifile-assembly.md)
- [Cómo el motor en tiempo de ejecución ubica ensamblados](../../framework/deployment/how-the-runtime-locates-assemblies.md)
- [Ensamblados de varios archivos](../../framework/app-domains/multifile-assemblies.md)
