---
title: Instalación de .NET Framework en Windows 7 SP1
description: Aprenda a instalar .NET Framework en Windows 7 SP1.
ms.date: 04/18/2019
ms.openlocfilehash: 900b38110626a93f37829045a8676ea87101d7e9
ms.sourcegitcommit: 8299abfbd5c49b596d61f1e4d09bc6b8ba055b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "98899092"
---
# <a name="install-the-net-framework-on-windows-7-sp1-and-windows-server-2008-r2"></a>Instalación de .NET Framework en Windows 7 SP1 y Windows Server 2008 R2

.NET Framework se requiere para ejecutar muchas aplicaciones en Windows. Puede usar las instrucciones siguientes para instalarlo. Es posible que haya llegado a esta página tras haber intentado ejecutar una aplicación y ver el cuadro de diálogo siguiente en el equipo.

![No se pudo iniciar esta aplicación.](./media/this-application-could-not-be-started.png)

Estas instrucciones ayudan a instalar las versiones necesarias de .NET Framework. [.NET Framework 4.8](https://github.com/Microsoft/dotnet/tree/master/releases/net48) es la última versión. Es compatible con Windows 7 SP1 y Windows Server 2008 R2, y está incluida en la [Actualización de mayo de 2019 de Windows 10](https://support.microsoft.com/help/4028685/windows-10-get-the-update).

## <a name="net-framework-48"></a>.NET Framework 4.8

> [!div class="button"]
> [Descarga de .NET Framework 4.8](https://dotnet.microsoft.com/download/dotnet-framework/net48)

[.NET Framework 4.8](https://github.com/Microsoft/dotnet/tree/master/releases/net48) se puede usar para ejecutar aplicaciones creadas para .NET Framework 4.0 o posterior.

### <a name="offline-installer"></a>instalador sin conexión

Al realizar una instalación sin conexión para .NET Framework en Windows 7, primero deberá asegurarse de que se ha instalado en la máquina de destino la versión más reciente de [Microsoft Root Certificate Authority 2011](https://www.microsoft.com/pkiops/Docs/Repository.htm).

La herramienta _certmgr.exe_ puede automatizar la instalación de un certificado y se obtiene de Visual Studio o Windows SDK. El siguiente comando se usa para instalar el certificado antes de ejecutar el instalador de .NET Framework:

```console
certmgr.exe /add MicRooCerAut2011_2011_03_22.crt /s /r localMachine root
```

## <a name="net-framework-35"></a>.NET Framework 3.5

[.NET Framework 3.5](https://dotnet.microsoft.com/download/dotnet-framework/net35-sp1) está incluido en Windows 7.

.NET Framework 3.5 es compatible con aplicaciones desarrolladas para .NET Framework de 1.0 a 3.5.

## <a name="help"></a>Ayuda

Si no puede instalar la versión correcta de .NET Framework, puede [ponerse en contacto con Microsoft para obtener ayuda](mailto:dotnet-install-help@service.microsoft.com?subject=Install-Help).

## <a name="see-also"></a>Vea también

- [Descarga de .NET Framework](https://dotnet.microsoft.com/download)
- [Solución de problemas en instalaciones y desinstalaciones bloqueadas de .NET Framework](troubleshoot-blocked-installations-and-uninstallations.md)
- [Instalación de .NET Framework para desarrolladores](guide-for-developers.md)
