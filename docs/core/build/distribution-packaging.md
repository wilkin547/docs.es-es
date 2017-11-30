---
title: "Empaquetado de distribución de .NET Core"
description: "Obtenga información sobre cómo empaquetar, nombrar y versionar .NET Core para su distribución."
keywords: .NET, .NET Core, source, build
author: bleroy
ms.author: mairaw
ms.date: 06/28/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 71b9d722-c5a8-4271-9ce1-d87e7ae2494d
ms.openlocfilehash: 7ff5ed127ad0d4f435c697a8f35b33c7ba3b56ff
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="net-core-distribution-packaging"></a>Empaquetado de distribución de .NET Core

Como .NET Core está disponible cada vez en más plataformas, resulta útil aprender cómo empaquetarlo, nombrarlo y versionarlo. De esta manera, los mantenedores de paquetes pueden ayudar a garantizar una experiencia coherente, independientemente de dónde los usuarios elijan ejecutar .NET.

## <a name="net-core-components"></a>Componentes de .NET Core

.NET Core consta de tres partes principales que deben empaquetarse:

1. **El host** (también conocido como "muxer") tiene dos roles diferentes: activar un runtime para iniciar una aplicación y activar un SDK para enviarle comandos. El host es un ejecutable nativo (`dotnet.exe`) y sus bibliotecas de directivas auxiliares (instaladas en `host/fxr`). Se crea a partir del código en el repositorio [`dotnet/core-setup`](https://github.com/dotnet/core-setup/). Normalmente hay solo un host en un equipo determinado, aunque no es un requisito estricto.
2. El **marco** consta de un runtime y de bibliotecas administradas auxiliares. El marco puede instalarse como parte de una aplicación, o bien como un marco compartido en una ubicación central que varias aplicaciones pueden reutilizar. Puede haber cualquier número de marcos compartidos instalados en un equipo determinado. Los marcos compartidos se encuentran en `shared/Microsoft.NETCore.App/<version>`. El host se pone al día entre las versiones de las revisiones. Si una aplicación está orientada a `Microsoft.NETCore.App` 1.0.0, y solo existe la versión 1.0.4, la aplicación se lanza en la 1.0.4.
3. **El SDK** (también conocido como "las herramientas") son un conjunto de herramientas administradas que pueden usarse para escribir y compilar aplicaciones y bibliotecas de .NET Core. El SDK incluye la CLI, MSBuild y tareas y destinos de compilación asociada, NuGet, nuevas plantillas de proyecto, etc. Es posible tener varios SDK en un equipo (por ejemplo, para compilar proyectos que necesitan de forma explícita una versión anterior), pero la recomendación es usar las últimas herramientas lanzadas.

## <a name="recommended-package-names"></a>Nombres de paquetes recomendados

En la guía siguiente se especifica la recomendación en relación con los nombres de paquetes. Un mantenedor de paquetes puede optar por no seguirla por varios motivos, como una tradición diferente para la distribución específica en la que se centra.

### <a name="minimum-package-set"></a>Conjunto de paquetes mínimo

* `dotnet-runtime-[major].[minor]`: un marco compartido con la versión especificada (solo la última versión de revisión para una combinación determinada principal+secundaria debe estar disponible en el administrador de paquetes). **dependencias**: `dotnet-host`
* `dotnet-sdk`: el último SDK. **dependencias**: el último `dotnet-sdk-[major].[minor]`.
* `dotnet-sdk-[major].[minor]`: el SDK con la versión especificada. La versión especificada es la versión incluida más alta de los marcos compartidos incluidos, para que los usuarios puedan relacionar con facilidad un SDK con un marco compartido. **dependencias**: `dotnet-host`, una o varias instancias de `dotnet-runtime-[major].[minor]` (uno de los runtime utilizado por el propio código del SDK; los demás están disponibles para que los usuarios realicen tareas de compilación y ejecución).
* `dotnet-host`: el último host.

#### <a name="preview-versions"></a>Versiones preliminares

Los mantenedores de paquetes pueden decidir incluir versiones preliminares del marco compartido y del SDK. Nunca se deben incluir en el paquete `dotnet-sdk` sin versión, pero se pueden lanzar como paquetes con versión con un marcador de versión preliminar adicional anexado a las secciones de versión principal y secundaria del nombre. Por ejemplo, puede haber un paquete `dotnet-sdk-2.0-preview-final`.

### <a name="optional-additional-packages"></a>Paquetes adicionales opcionales

Algunos mantenedores pueden elegir proporcionar paquetes adicionales, como:

* `dotnet-lts`: la última versión de soporte técnico a largo plazo (LTS) del marco compartido. Las [series de versiones actuales y de LTS](~/docs/core/versions/lts-current.md) corresponden a cadencias diferentes a aquellas con las que se lanza .NET Core. Los usuarios tienen la opción de adoptar una u otra serie, en función de la frecuencia con que deseen realizar actualizaciones. Se trata de un concepto que también está vinculado a los niveles de soporte técnico, por lo que puede tener sentido o no, según la distribución considerada.

## <a name="disk-layout"></a>Diseño de disco

Al instalar paquetes de .NET Core, es importante tener en cuenta la colocación relativa de sus destinos objetivo en el disco.
El host `dotnet.exe` debe colocarse junto a las carpetas `sdk` y `shared` que incluyen el contenido con versión de los paquetes del SDK `dotnet-sdk` y de los paquetes del marco compartido `dotnet-runtime`.

Se aplica el control de versiones al diseño del disco de archivos y directorios incluidos en los paquetes. Esto significa que la actualización a la última versión `dotnet-runtime` instala la nueva versión en paralelo con las versiones anteriores, de tal forma que se reduce la posibilidad de interrumpir las aplicaciones existentes mediante la actualización del paquete. Las actualizaciones del paquete no deben quitar las versiones anteriores.

## <a name="update-policies"></a>Directivas de actualización

Cuando se lleva a cabo una operación `update`, el comportamiento de cada paquete es el siguiente:

* `dotnet-runtime-[major].[minor]`: las nueva versiones de revisión actualizan el paquete, pero las nuevas versiones secundarias o principales son paquetes independientes.
* `dotnet-sdk`: `update` pone al día las versiones de revisión, las versiones principales y las secundarias.
* `dotnet-sdk-[major].[minor]`: las nueva versiones de revisión actualizan el paquete, pero las nuevas versiones secundarias o principales son paquetes independientes.
* `dotnet-lts`: `update` pone al día las versiones de revisión, las versiones principales y las secundarias.

En este tema se han presentado las recomendaciones para empaquetar .NET Core; sin embargo, cada distribución tiene la libertad de elegir qué versiones ofrecer y cuándo. Por ejemplo, una distribución que valora la estabilidad que el hecho de estar actualizada puede optar por publicar solo las versiones que se basan en la serie de versiones de LTS.