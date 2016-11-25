---
title: Comando dotnet-nuget-delete| SDK de .NET Core
description: El comando dotnet-nuget-delete elimina o quita de la lista un paquete del servidor.
keywords: dotnet-nuget-delete, CLI, comando de la CLI, .NET Core
author: karann-msft
ms.author: mairaw
manager: wpickett
ms.date: 11/11/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 6ddffde4-c789-4e90-990e-d35f6a6565d4
translationtype: Human Translation
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: a338f91d33347d48eefe572ea61da5d58d5c639a

---

#<a name="dotnet-nuget-delete"></a>dotnet-nuget-delete

[!INCLUDE[preview-warning](../../../includes/warning.md)]

## <a name="name"></a>Nombre 
`dotnet-nuget-delete`: elimina o quita de la lista un paquete del servidor. 

## <a name="synopsis"></a>Sinopsis

`dotnet nuget delete [<package_name> <package_version>] 
    [--help] [--source] [--non-interactive] 
    [--api-key] [--force-english-output] [--verbosity] [--config-file]`

## <a name="description"></a>Descripción

El comando `dotnet nuget delete` elimina o quita de la lista un paquete del servidor. Para NuGet.org, la acción es quitar de la lista el paquete.

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.  

`-s|--source <SOURCE>`

Especifica la dirección URL del servidor. Las direcciones URL admitidas para nuget.org incluyen `http://www.nuget.org`, `http://www.nuget.org/api/v3` y `http://www.nuget.org/api/v2/package`. Para fuentes privadas, sustituya el nombre de host (por ejemplo, `%hostname%/api/v3`).

`--non-interactive`

No pide confirmaciones o intervención del usuario.

`-k|--api-key <API_KEY>`

La clave de API para el servidor.

`--force-english-output`

Fuerza a que la salida de la línea de comandos esté en inglés.

`--verbosity <LEVEL>`

Muestra esta cantidad de detalles en la salida. El nivel puede ser `normal`, `quiet` o `detailed`.

`--config-file <FILE>`

Un archivo de configuración de NuGet usado específicamente para este comando, que sustituye los demás archivos de configuración que se encuentran durante la detección de archivos de configuración estándar y el proceso de encadenamiento. La ruta de acceso puede ser absoluta o relativa.
Para más información sobre los archivos de configuración, consulte [Configuring NuGet Behavior](https://docs.nuget.org/ndocs/consume-packages/configuring-nuget-behavior) (Configuración del comportamiento de NuGet). 

## <a name="examples"></a>Ejemplos

Elimina la versión 1.0 del paquete MyPackage:

`dotnet nuget delete MyPackage 1.0` 

Elimina la versión 1.0 del paquete MyPackage, sin pedir al usuario credenciales u otra información:

`dotnet nuget delete MyPackage 1.0 --non-interactive`

Elimina la versión 1.0 del paquete MyPackage y especifica un archivo de configuración personalizado *./config/My.Config*:

`dotnet nuget delete MyPackage 1.0 --config-file ./config/My.Config`

Elimina la versión 1.0 del paquete MyPackage, con el máximo nivel de detalle:

`dotnet nuget delete MyPackage 1.0 --verbosity detailed`



<!--HONumber=Nov16_HO3-->


