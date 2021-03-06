---
title: Comparar ASP.NET Identity y ASP.NET Core identidad
description: En esta sección se examinan las diferencias entre ASP.NET Identity y ASP.NET Core identidad, que son especialmente importantes al planear una migración de .NET Framework a .NET Core.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 184c0e7c872b7676530b917727f380d6735ba10a
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401761"
---
# <a name="compare-aspnet-identity-and-aspnet-core-identity"></a>Comparar ASP.NET Identity y ASP.NET Core identidad

En ASP.NET MVC, las características de identidad se configuran normalmente en *IdentityConfig.CS* en la carpeta *App_Start* . Revise cómo se configura en la aplicación existente y compárelo con la [configuración necesaria para ASP.net Core identidad](/aspnet/core/security/authentication/identity-configuration) en *Startup.CS*.

ASP.NET Identity es una API que admite la funcionalidad de inicio de sesión de la interfaz de usuario y administra usuarios, contraseñas, datos de perfil, roles, notificaciones, tokens, confirmaciones de correo electrónico y mucho más. Admite proveedores de inicio de sesión externos como Facebook, Google, Microsoft y Twitter.

Si su aplicación ASP.NET MVC usa la pertenencia a ASP.NET, encontrará una guía para [migrar desde ASP.net la autenticación de pertenencia a ASP.net Core identidad 2,0](/aspnet/core/migration/proper-to-2x/membership-to-core-identity). Se trata principalmente de un ejercicio de migración de datos, a la finalización de la que debería poder usar ASP.NET Core identidad con los registros de usuario migrados.

Si migra sus usuarios de ASP.NET Identity a ASP.NET Core identidad, es posible que tenga que actualizar sus hashes de contraseña o hacer un seguimiento de las contraseñas con el nuevo enfoque de identidad de ASP.NET Core o el enfoque de ASP.NET Identity anterior. [Este enfoque descrito en Stack Overflow](https://stackoverflow.com/a/57074910/13729) proporciona algunas opciones para migrar los hash de contraseña de usuario a lo largo del tiempo, en lugar de todos a la vez.

Una de las mayores diferencias cuando se trata de ASP.NET Core identidad en comparación con ASP.NET Identity es el poco código que se debe incluir en el proyecto. ASP.NET Core identidad ahora se distribuye como una biblioteca de clases de Razor, lo que significa que la interfaz de usuario y la lógica están disponibles desde un paquete NuGet. Puede invalidar la interfaz de usuario y la lógica existentes mediante [la técnica scaffolding de los archivos de identidad de ASP.net Core](/aspnet/core/security/authentication/scaffold-identity) pero, incluso en este caso, solo necesita scaffolding las páginas que desea modificar, no todas ellas.

## <a name="migrate-from-owin--katana"></a>Migración desde OWIN/Katana

Los siguientes recursos ofrecen algunas instrucciones para la migración desde OWIN/Katana:

- [Migración](/aspnet/core/migration/proper-to-2x/#globalasax-file-replacement)
- [Katana a ASPNET 5](https://devblogs.microsoft.com/aspnet/katana-asp-net-5-and-bridging-the-gap/)

## <a name="references"></a>Referencias

- [Migración de la autenticación y la identidad a ASP.NET Core](/aspnet/core/migration/identity)
- [Introducción a la identidad en ASP.NET Core](/aspnet/core/security/authorization/introduction)
- [Configuración de la identidad de ASP.NET Core](/aspnet/core/security/authentication/identity-configuration)
- [Identidad de scaffolding en proyectos de ASP.NET Core](/aspnet/core/security/authentication/scaffold-identity)

>[!div class="step-by-step"]
>[Anterior](authentication-differences.md)
>[Siguiente](controller-differences.md)
