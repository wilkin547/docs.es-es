---
title: Ejecución de aplicaciones de .NET Framework 1.1 en Windows 8, Windows 8.1 o Windows 10
description: Describe cómo alojar aplicaciones que requieren .NET Framework 1.1, que ya no se admiten en muchas versiones del sistema operativo Windows.
ms.date: 05/26/2017
helpviewer_keywords:
- Windows 8, running .NET Framework 1.1 apps
- .NET Framework 1.1, running on Windows 8
ms.assetid: fb14e195-fea5-4561-b9a8-60a67283edb9
ms.openlocfilehash: 6d1cb2f9251bba96d0a378bf4dbab9f7da267037
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111795"
---
# <a name="run-net-framework-11-apps-on-windows-8-windows-81-or-windows-10"></a>Ejecución de aplicaciones de .NET Framework 1.1 en Windows 8, Windows 8.1 o Windows 10

.NET Framework 1.1 no se admite en los sistemas operativos Windows 8, Windows 8.1, Windows Server 2012, Windows Server 2012 R2 o Windows 10. En algunos casos, se requiere .NET Framework 1.1 para que se ejecute una aplicación. En esos casos, póngase en contacto con el fabricante de software independiente (ISV) para que la aplicación actualizada se ejecute en .NET Framework 3.5 SP1 o una versión posterior. Para más información, consulte [Migración desde .NET Framework 1.1](../migration-guide/migrating-from-the-net-framework-1-1.md).

## <a name="install-net-framework-11-from-a-cd-or-download-center"></a>Instalación de .NET Framework 1.1 desde un CD o el Centro de descarga

No es posible instalar manualmente .NET Framework 1.1 en Windows 8, Windows 8.1, Windows Server 2012, Windows Server 2012 R2 o Windows 10 mediante un CD o el Centro de descarga. Ya no se admite. Si intenta instalar el paquete, se muestra el mensaje de error siguiente: "El programa de instalación no puede continuar porque esta versión de .NET Framework no es compatible con una instalada previamente". Para solucionar este problema, instale [.NET Framework 3.5 SP1](https://www.microsoft.com/download/details.aspx?id=22). Esta versión incluye .NET Framework 2.0 (la versión siguiente a .NET Framework 1.1), que es compatible con Windows 8, Windows 8.1 y Windows 10. Intente siempre instalar primero la aplicación para determinar si se va a actualizar automáticamente a una versión posterior de .NET Framework. De no ser así, póngase en contacto con el ISV para obtener una actualización de la aplicación.

## <a name="see-also"></a>Vea también

- [Migración desde .NET Framework 1.1](../migration-guide/migrating-from-the-net-framework-1-1.md)
- [Instalación de .NET Framework 3.5 en Windows 10, Windows 8.1 y Windows 8](dotnet-35-windows-10.md)
