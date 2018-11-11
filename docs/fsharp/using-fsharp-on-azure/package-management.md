---
title: Uso de administración de paquetes con F# para Azure
description: Usar Paket o Nuget para administrar F# dependencias de Azure
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: fd9c4a15ab0741d44d6d5cf909b7219d310affb0
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "33566981"
---
# <a name="package-management-for-f-azure-dependencies"></a>Administración de paquetes para las dependencias de Azure de F#

Obtención de paquetes para el desarrollo de Azure es fácil cuando se usa un administrador de paquetes. Las dos opciones son [Paket](https://fsprojects.github.io/Paket/) y [NuGet](https://www.nuget.org/).

## <a name="using-paket"></a>Uso de Paket

Si usas [Paket](https://fsprojects.github.io/Paket/) como su administrador de dependencias, puede usar el `paket.exe` herramienta para agregar dependencias de Azure. Por ejemplo:

    > paket add nuget WindowsAzure.Storage

O bien, si usas [Mono](https://www.mono-project.com/) para el desarrollo de .NET multiplataforma:

    > mono paket.exe add nuget WindowsAzure.Storage

Esto agregará `WindowsAzure.Storage` en el conjunto de dependencias de paquete para el proyecto en el directorio actual, modifique la `paket.dependencies` de archivos y descargar el paquete. Si ha configurado previamente las dependencias, o está trabajando con un proyecto donde se han configurado las dependencias por otro desarrollador, puede resolver e instalar las dependencias localmente como esto:

    > paket install

O bien, para el desarrollo de Mono:

    > mono paket.exe install

Puede actualizar todas las dependencias de paquete a la versión más reciente similar al siguiente:

    > paket update

O bien, para el desarrollo de Mono:

    > mono paket.exe update

## <a name="using-nuget"></a>Uso de Nuget

Si usas [NuGet](https://www.nuget.org/) como su administrador de dependencias, puede usar el `nuget.exe` herramienta para agregar dependencias de Azure. Por ejemplo:

    > nuget install WindowsAzure.Storage -ExcludeVersion

O bien, para el desarrollo de Mono:

    > mono nuget.exe install WindowsAzure.Storage -ExcludeVersion

Esto agregará `WindowsAzure.Storage` al conjunto de dependencias de paquete para el proyecto en el directorio actual y el paquete de descarga. Si ha configurado previamente las dependencias, o está trabajando con un proyecto donde se han configurado las dependencias por otro desarrollador, puede resolver e instalar las dependencias localmente como esto:

    > nuget restore 

O bien, para el desarrollo de Mono:

    > mono nuget.exe restore

Puede actualizar todas las dependencias de paquete a la versión más reciente similar al siguiente:

    > nuget update

O bien, para el desarrollo de Mono:

    > mono nuget.exe update

## <a name="referencing-assemblies"></a>Referencia a ensamblados

Para poder usar los paquetes en su F# secuencia de comandos, deberá hacer referencia a los ensamblados incluidos en los paquetes mediante un `#r` directiva. Por ejemplo:

    > #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"

Como puede ver, deberá especificar la ruta de acceso relativa del archivo DLL y el nombre de archivo DLL completo, que es posible que no sea exactamente el mismo que el nombre del paquete. La ruta de acceso incluirá una versión de .NET framework y, posiblemente, un número de versión del paquete. Para buscar todos los ensamblados instalados, puede usar algo parecido a esto en una línea de comandos de Windows:

    > cd packages/WindowsAzure.Storage
    > dir /s/b *.dll

O bien, en un shell de Unix, algo como esto:

    > find packages/WindowsAzure.Storage -name "*.dll"

Esto le dará las rutas de acceso a los ensamblados instalados. Desde allí, puede seleccionar la ruta de acceso correcta para su versión de framework.
