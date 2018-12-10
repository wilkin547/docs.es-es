---
title: Instalación de .NET Framework en Windows 10
description: Aprenda a instalar .NET Framework en Windows 10 o Windows Server 2016.
author: rlander
ms.author: mairaw
ms.date: 04/10/2018
ms.custom: updateeachrelease
ms.openlocfilehash: 6db1a3f5fd2011a13a28551a38b319995039ab38
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53153620"
---
# <a name="install-the-net-framework-on-windows-10-and-windows-server-2016"></a>Instalación de .NET Framework en Windows 10 o Windows Server 2016

.NET Framework se requiere para ejecutar muchas aplicaciones en Windows. Las instrucciones de este artículo puede ayudarle a instalar las versiones de .NET Framework que necesite. [.NET Framework 4.7.2](https://go.microsoft.com/fwlink/?LinkID=863255) es la última versión disponible.

Es posible que haya llegado a esta página tras haber intentado ejecutar una aplicación y que haya aparecido un cuadro de diálogo en el equipo similar al siguiente:

![No se pudo iniciar esta aplicación.](./media/this-application-could-not-be-started.png)

## <a name="net-framework-472"></a>.NET Framework 4.7.2

.NET Framework 4.7.2 se incluye con:

* [Actualización de octubre de 2018 de Windows 10](https://support.microsoft.com/help/4028685/windows-10-get-the-update)

* [Actualización de abril de 2018 de Windows 10](https://www.microsoft.com/software-download/windows10)

> [!div class="button"]
> [Descargar .NET Framework 4.7.2](https://www.microsoft.com/net/download/thank-you/net472?utm_source=ms-docs&utm_medium=referral)

[.NET Framework 4.7.2](https://go.microsoft.com/fwlink/?LinkID=863255) se puede usar para ejecutar aplicaciones creadas para .NET Framework de 4.0 a 4.7.1.

[.NET Framework 4.7.2](https://go.microsoft.com/fwlink/?LinkID=863255) se puede instalar en:

* Windows 10 Fall Creators Update (versión 1709)
* Windows 10 Creators Update (versión 1703)
* Actualización de aniversario de Windows 10 (versión 1607)
* Windows Server, versión 1709
* Windows Server 2016

.NET Framework 4.7.2 no se admite en:

* Windows 10 1507
* Windows 10 1511

Si está usando Windows 10 1507 o 1511 y quiere instalar .NET Framework 4.7.2, primero debe actualizar a una versión posterior de Windows 10.

## <a name="net-framework-462"></a>.NET Framework 4.6.2

[.NET Framework 4.6.2](https://www.microsoft.com/en-us/download/details.aspx?id=53345) es la versión más reciente admitida de .NET Framework en Windows 10 1507 y 1511.

.NET Framework 4.6.2 es compatible con aplicaciones desarrolladas para .NET Framework de 4.0 a 4.6.2.

## <a name="net-framework-35"></a>.NET Framework 3,5

Siga las instrucciones para instalar [.NET Framework 3.5 en Windows 10](dotnet-35-windows-10.md).

.NET Framework 3.5 es compatible con aplicaciones desarrolladas para .NET Framework de 1.0 a 3.5.

## <a name="additional-information"></a>Información adicional

Las versiones de .NET Framework 4.x son actualizaciones locales de versiones anteriores. Esto significa lo siguiente:

- Solo puede tener una versión de .NET Framework 4.x instalada en su equipo.

- No puede instalar una versión anterior de .NET Framework en el equipo si ya hay instalada una versión posterior.

- Las versiones 4.x de .NET Framework se pueden usar para ejecutar aplicaciones creadas para un rango que va desde .NET Framework 4.0 hasta esa versión. Por ejemplo, .NET Framework 4.7 se puede usar para ejecutar aplicaciones creadas para .NET Framework de 4.0 a 4.7. La versión más reciente (.NET Framework 4.7.2) se puede usar para ejecutar aplicaciones desarrolladas con todas las versiones de .NET Framework a partir de 4.0.

Para obtener una lista de todas las versiones de .NET Framework disponibles para su descarga, vea la página [.NET Downloads](https://www.microsoft.com/net/download?utm_source=ms-docs&utm_medium=referral) (Descargas de .NET).

## <a name="help"></a>Ayuda

Si no puede obtener la versión correcta de la versión de .NET Framework instalada, puede [ponerse en contacto con Microsoft para obtener ayuda](mailto:dotnet-install-help@service.microsoft.com?subject=Install-Help).

## <a name="see-also"></a>Vea también

[.NET Downloads](https://www.microsoft.com/net/download?utm_source=ms-docs&utm_medium=referral)  (Descargas de .NET)  
[Solución de problemas en instalaciones y desinstalaciones bloqueadas de .NET Framework](troubleshoot-blocked-installations-and-uninstallations.md)   
[Instalación de .NET Framework para desarrolladores](guide-for-developers.md)
