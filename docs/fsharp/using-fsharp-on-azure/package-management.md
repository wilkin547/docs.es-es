---
title: 'Uso de Administración de paquetes con F # para Azure'
description: 'Uso de Paket o Nuget para administrar las dependencias de Azure de F #'
author: sylvanc
ms.date: 09/20/2016
ms.custom: devx-track-fsharp
ms.openlocfilehash: 011a363b264079599e8b7d402fe9896045b1fe04
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91100118"
---
# <a name="package-management-for-f-azure-dependencies"></a>Administración de paquetes para las dependencias de Azure de F #

La obtención de paquetes para el desarrollo de Azure es fácil cuando se usa un administrador de paquetes. Las dos opciones son [Paket](https://fsprojects.github.io/Paket/) y [NuGet](https://www.nuget.org/).

## <a name="using-paket"></a>Usar Paket

Si usa [Paket](https://fsprojects.github.io/Paket/) como administrador de dependencias, puede usar la `paket.exe` herramienta para agregar dependencias de Azure. Por ejemplo:

```console
> paket add nuget WindowsAzure.Storage
```

O bien, si usa [mono](https://www.mono-project.com/) para el desarrollo .net multiplataforma:

```console
> mono paket.exe add nuget WindowsAzure.Storage
```

Esto agregará `WindowsAzure.Storage` al conjunto de dependencias de paquete del proyecto en el directorio actual, modificará el `paket.dependencies` archivo y descargará el paquete. Si ha configurado previamente las dependencias o está trabajando con un proyecto en el que otro desarrollador ha configurado las dependencias, puede resolver e instalar las dependencias localmente de la siguiente manera:

```console
> paket install
```

O para el desarrollo en mono:

```console
> mono paket.exe install
```

Puede actualizar todas las dependencias del paquete a la versión más reciente de la siguiente manera:

```console
> paket update
```

O para el desarrollo en mono:

```console
> mono paket.exe update
```

## <a name="using-nuget"></a>Uso de Nuget

Si usa [NuGet](https://www.nuget.org/) como administrador de dependencias, puede usar la `nuget.exe` herramienta para agregar dependencias de Azure. Por ejemplo:

```console
> nuget install WindowsAzure.Storage -ExcludeVersion
```

O para el desarrollo en mono:

```console
> mono nuget.exe install WindowsAzure.Storage -ExcludeVersion
```

Esto agregará `WindowsAzure.Storage` al conjunto de dependencias de paquete del proyecto en el directorio actual y descargará el paquete. Si ha configurado previamente las dependencias o está trabajando con un proyecto en el que otro desarrollador ha configurado las dependencias, puede resolver e instalar las dependencias localmente de la siguiente manera:

```console
> nuget restore
```

O para el desarrollo en mono:

```console
> mono nuget.exe restore
```

Puede actualizar todas las dependencias del paquete a la versión más reciente de la siguiente manera:

```console
> nuget update
```

O para el desarrollo en mono:

```console
> mono nuget.exe update
```

## <a name="referencing-assemblies"></a>Referencia a ensamblados

Para usar los paquetes en el script de F #, debe hacer referencia a los ensamblados incluidos en los paquetes mediante una `#r` Directiva. Por ejemplo:

```fsharp
> #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"
```

Como puede ver, debe especificar la ruta de acceso relativa a la DLL y el nombre completo de la DLL, que puede no ser exactamente igual que el nombre del paquete. La ruta de acceso incluirá una versión de .NET Framework y, posiblemente, un número de versión del paquete. Para encontrar todos los ensamblados instalados, puede usar algo parecido a esto en una línea de comandos de Windows:

```console
> cd packages/WindowsAzure.Storage
> dir /s/b *.dll
```

O en un shell de UNIX, algo parecido a esto:

```console
> find packages/WindowsAzure.Storage -name "*.dll"
```

Esto le proporcionará las rutas de acceso a los ensamblados instalados. Desde allí, puede seleccionar la ruta de acceso correcta para la versión de .NET Framework.
