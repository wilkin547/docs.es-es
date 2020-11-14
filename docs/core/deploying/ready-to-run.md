---
title: Información general sobre la implementación de ReadyToRun
description: Obtenga información sobre qué son las implementaciones de ReadyToRun y por qué debe considerar su uso en el marco de la publicación de la aplicación con .NET 5 y .NET Core 3.0 y versiones posteriores.
author: davidwr
ms.author: davidwr
ms.date: 09/21/2020
ms.openlocfilehash: cd8eaebd05d79b11e90e255e702a52220fffda76
ms.sourcegitcommit: ffd4d5e824db6c5f0c3521c0e802fd9e8f0edcbe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2020
ms.locfileid: "93342636"
---
# <a name="readytorun-compilation"></a>Compilación ReadyToRun

La latencia y el tiempo de inicio de la aplicación .NET se pueden mejorar si se compilan los ensamblados de aplicación como formato ReadyToRun (R2R). R2R es una forma de compilación Ahead Of Time (AOT).

Los binarios de R2R mejoran el rendimiento de inicio reduciendo la cantidad de trabajo que el compilador Just-In-Time (JIT) debe llevar a cabo cuando se carga la aplicación. Los binarios contienen código nativo similar en comparación con lo que generaría el compilador JIT. Sin embargo, los binarios de R2R son más grandes porque contienen tanto el código de lenguaje intermedio (IL), que sigue siendo necesario para algunos escenarios, como la versión nativa del mismo código. R2R solo está disponible cuando publica una aplicación que tenga como destino entornos de tiempo de ejecución específicos (RID), como Linux x64 o Windows x64.

Para compilar el proyecto como ReadyToRun, la aplicación debe publicarse con la propiedad PublishReadyToRun establecida en true.

Hay dos maneras de publicar la aplicación como ReadyToRun:

01. Especifique la marca PublishReadyToRun directamente en el comando dotnet publish. Consulte [dotnet publish](../tools/dotnet-publish.md) para obtener más información.

    ```dotnetcli
    dotnet publish -c Release -r win-x64 -p:PublishReadyToRun=true
    ```

02. Especificación de la propiedad en el proyecto

    - Agregue el valor `<PublishReadyToRun>` al proyecto.

    ```xml
    <PropertyGroup>
      <PublishReadyToRun>true</PublishReadyToRun>
    </PropertyGroup>
    ```

    - Publique la aplicación sin ningún parámetro especial.

    ```dotnetcli
    dotnet publish -c Release -r win-x64
    ```

## <a name="impact-of-using-the-readytorun-feature"></a>Impacto del uso de la característica ReadyToRun

La compilación anticipada tiene un impacto complejo en el rendimiento de la aplicación, que puede ser difícil de predecir. En general, el tamaño de un ensamblado aumentará entre dos y tres veces. Este aumento en el tamaño físico del archivo puede reducir el rendimiento de la carga del ensamblado desde el disco y aumentar el espacio de trabajo del proceso. Sin embargo, a cambio, el número de métodos compilados en el entorno de ejecución suele reducirse considerablemente. El resultado es que la mayoría de las aplicaciones que tienen grandes cantidades de código obtienen beneficios de rendimiento elevados de la habilitación de ReadyToRun. Las aplicaciones con pequeñas cantidades de código probablemente no experimentarán una mejora significativa en la habilitación de ReadyToRun, ya que las bibliotecas del entorno de ejecución de .NET ya se han precompilado con ReadyToRun.

La mejora de inicio que se describe aquí no solo se aplica al inicio de la aplicación, sino también al primer uso de cualquier código de la aplicación. Por ejemplo, ReadyToRun se puede usar para reducir la latencia de respuesta del primer uso de la API web en una aplicación de ASP.NET.

### <a name="interaction-with-tiered-compilation"></a>Interacción con la compilación en capas

La compilación anticipada generada no está tan optimizada como el código generado por JIT. Para solucionar este problema, la compilación en capas reemplazará los métodos de ReadyToRun usados comúnmente con métodos generados por JIT.

## <a name="how-is-the-set-of-precompiled-assemblies-chosen"></a>¿Cómo se elige el conjunto de ensamblados precompilados?

El SDK precompilará los ensamblados que se distribuyen con la aplicación. En el caso de las aplicaciones independientes, este conjunto de ensamblados incluirá el marco. Los archivos binarios de C++/CLI no son válidos para la compilación de ReadyToRun.

## <a name="how-is-the-set-of-methods-to-precompile-chosen"></a>¿Cómo se elige el conjunto de métodos para la precompilación?

El compilador intentará precompilar todos los métodos que pueda. Sin embargo, por varias razones, no se espera que el uso de la característica ReadyToRun impida la ejecución de JIT.

Estos motivos pueden incluir, entre otros, los siguientes:

- Uso de tipos genéricos definidos en ensamblados independientes
- Interoperabilidad con código nativo
- Uso de elementos intrínsecos de hardware que el compilador no puede probar que sean seguros de usar en una máquina de destino
- Ciertos patrones de IL inusuales
- Creación de métodos dinámicos mediante reflexión o LINQ

## <a name="cross-platformarchitecture-restrictions"></a>Restricciones multiplataforma y de arquitectura

Para algunas plataformas SDK, el compilador ReadyToRun es capaz de realizar una compilación cruzada para otras plataformas de destino. Los destinos de compilación admitidos se describen en la tabla siguiente.

| Plataforma de SDK | Plataformas de destino compatibles |
| ------------ | --------------------------- |
| Windows X64  | Windows X86, Windows X64, Windows ARM32, Windows ARM64 |
| Windows X86  | Windows X86, Windows ARM32 |
| Linux X64    | Linux X86, Linux X64, Linux ARM32, Linux ARM64 |
| Linux ARM32  | Linux ARM32 |
| Linux ARM64  | Linux ARM64 |
| macOS X64    | macOS X64 |
