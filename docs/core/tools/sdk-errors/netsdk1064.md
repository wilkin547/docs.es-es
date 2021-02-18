---
title: 'NETSDK1064: paquete no encontrado'
description: Obtenga información sobre el error NETSDK1064 del SDK de .NET, que se produce cuando no se encuentra un paquete.
ms.topic: error-reference
ms.date: 02/10/2021
f1_keywords:
- NETSDK1064
ms.openlocfilehash: 1a155db1aacbceb9878401dbcac61ece5f1f9824
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100488252"
---
# <a name="netsdk1064-package-not-found"></a>NETSDK1064: paquete no encontrado

**Este artículo se aplica a: ✔️** SDK de .NET Core 2.1.100 y versiones posteriores

Este error se produce cuando las herramientas de compilación no pueden encontrar un paquete NuGet necesario para compilar un proyecto. Esto suele deberse a un problema de restauración de paquetes. El mensaje de error es similar al ejemplo siguiente:

> NETSDK1064: No se ha encontrado el paquete "NombreDelPaquete", versión x.x.x. Es posible que se haya eliminado desde la restauración de NuGet. De lo contrario, es posible que la restauración de NuGet solo se haya completado parcialmente, lo que podría deberse a restricciones de longitud máxima de la ruta de acceso.

Estas son algunas acciones que puede realizar para resolver este error:

* Agregue la opción `/restore` al comando *MSBuild.exe*. No utilice `/t:Restore;Build`, ya que esto puede provocar errores sutiles. Una alternativa consiste en usar el comando `dotnet build`, ya que realiza automáticamente una restauración de paquetes.
* Si va a ejecutar la restauración de paquetes con Visual Studio 2019 o *MSBuild.exe*, el error puede deberse a restricciones de longitud máxima de la ruta de acceso. Para obtener más información, vea [Compatibilidad con rutas largas (CLI de NuGet)](/nuget/reference/cli-reference/cli-ref-long-path) y la [incidencia de NuGet/Home n.º 3324](https://github.com/NuGet/Home/issues/3324).
* Si va a realizar la restauración con *nuget.exe* x86 y la compilación con *MSBuild.exe* x64, el valor de bits no coincidente podría generar este error. La compilación no puede encontrar los paquetes que la restauración notifica que ha adquirido porque la ruta de acceso en *project.assets.json* no funciona en un proceso con otro valor de bits. Para resolver el error, use herramientas del mismo valor de bits para la restauración y compilación, o bien configure NuGet para restaurar los paquetes en una carpeta que no se pueda virtualizar entre x86 y x64. Para obtener más información, vea la [incidencia n.º 4332 (dotnet/core)](https://github.com/dotnet/core/issues/4332).
* Si va a compilar una imagen de Docker, asegúrese de que el archivo *.dockerignore* omite los directorios *bin* y *obj*. Para obtener más información, vea [NETSDK1064: No se ha encontrado el paquete DnsClient, 1.2.0](https://stackoverflow.com/questions/61167032/error-netsdk1064-package-dnsclient-1-2-0-was-not-found).
