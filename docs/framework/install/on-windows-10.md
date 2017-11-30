---
title: "Instalación de .NET Framework en Windows 10"
description: "Obtenga información acerca de cómo instalar .NET Framework en Windows 10 o Windows Server 2016."
author: rlander
ms.author: mairaw
keywords: .NET Framework, Instalar
ms.date: 11/17/2017
ms.topic: article
ms.custom: updateeachrelease
ms.prod: .net-framework
ms.openlocfilehash: d7f8dd4c6ee9f7eeda389a955f806a5765876ea7
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2017
---
# <a name="install-the-net-framework-on-windows-10-and-windows-server-2016"></a>Instalar .NET Framework en Windows 10 y Windows Server 2016

Se requiere .NET Framework para ejecutar muchas aplicaciones en Windows. Las instrucciones de este artículo puede ayudarle a instalar las versiones de .NET Framework que necesita. El [.NET Framework 4.7.1](https://www.microsoft.com/download/details.aspx?id=56115&desc=dotnet47) es la última versión disponible.

Puede haber llegado a esta página después de intentar ejecutar una aplicación y ver un cuadro de diálogo en la máquina de forma similar a la siguiente:

![No se puede iniciar esta aplicación](./media/this-application-could-not-be-started.png)

## <a name="net-framework-471"></a>.NET framework 4.7.1

Se incluye con .NET Framework 4.7.1:

* [Actualización de creadores de otoño de Windows 10 (versión 1709)](https://www.microsoft.com/software-download/windows10)
* [Windows Server 2016 (versión 1709)](https://docs.microsoft.com/windows-server/get-started/get-started-with-1709)

> [!div class="button"]
[Descargar .NET Framework 4.7.1](https://www.microsoft.com/net/download/thank-you/net471?utm_source=ms-docs&utm_medium=referral)

El [.NET Framework 4.7.1](https://www.microsoft.com/download/details.aspx?id=56115&desc=dotnet47) puede usarse para ejecutar aplicaciones creadas para .NET Framework 4.0 a través de 4.7.1.

Puede instalar el [.NET Framework 4.7.1](https://www.microsoft.com/en-us/download/details.aspx?id=56115&desc=dotnet47) en:

* Actualización de los creadores de Windows 10 (versión 1703)
* Actualización de aniversario de Windows 10 (versión 1607)
* Windows Server 2016

.NET Framework 4.7.1 no es compatible con:

* Windows 10 1507
* Windows 10 1511

Si está usando Windows 10 1507 o 1511 y desea instalar .NET Framework 4.7.1, primero debe actualizar a una versión posterior de Windows 10.

## <a name="net-framework-461"></a>.NET Framework 4.6.1

El [.NET Framework 4.6.1](https://www.microsoft.com/download/details.aspx?id=49981) es la más reciente .NET Framework versión admitida de Windows 10 1507 y 1511.

.NET Framework 4.6.1 es compatible con aplicaciones basadas en .NET Framework 4.0 a través de 4.6.1.

## <a name="net-framework-35"></a>.NET Framework 3,5

Siga las instrucciones para instalar [.NET Framework 3.5 en Windows 10](dotnet-35-windows-10.md).

.NET Framework 3.5 es compatible con aplicaciones desarrolladas para .NET Framework 1.0 a través de 3.5.

## <a name="additional-information"></a>Información adicional

Versiones de .NET framework 4.x son actualizaciones en contexto a versiones anteriores. Esto significa lo siguiente:

- Solo puede tener una versión de .NET Framework 4.x instalados en su equipo.

- No se puede instalar una versión anterior de .NET Framework en su equipo si ya hay instalada una versión posterior.

- las versiones de .NET Framework 4.x pueden utilizarse para ejecutar aplicaciones creadas para .NET Framework 4.0 a través de esa versión. Por ejemplo, .NET Framework 4.7 puede usarse para ejecutar las aplicaciones creadas para .NET Framework 4.0 a través de 4.7. La versión más reciente (.NET Framework 4.7.1) puede utilizarse para las aplicaciones compiladas ejecutar todas las versiones de .NET Framework a partir de 4.0.

Para obtener una lista de todas las versiones de .NET Framework disponible para su descarga, vea el [.NET descarga](https://www.microsoft.com/net/download?utm_source=ms-docs&utm_medium=referral) página.

## <a name="help"></a>Ayuda

Si no se puede obtener la versión correcta de .NET Framework instalado, puede [póngase en contacto con Microsoft para obtener ayuda](mailto:dotnet-install-help@service.microsoft.com?subject=Install-Help).

## <a name="see-also"></a>Vea también

[Descargas de .NET](https://www.microsoft.com/net/download?utm_source=ms-docs&utm_medium=referral)   
[Solución de problemas en instalaciones y desinstalaciones bloqueadas de .NET Framework](troubleshoot-blocked-installations-and-uninstallations.md)   
[Instalar .NET Framework para desarrolladores](guide-for-developers.md)