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
# <a name="compare-aspnet-identity-and-aspnet-core-identity"></a><span data-ttu-id="9647e-103">Comparar ASP.NET Identity y ASP.NET Core identidad</span><span class="sxs-lookup"><span data-stu-id="9647e-103">Compare ASP.NET Identity and ASP.NET Core Identity</span></span>

<span data-ttu-id="9647e-104">En ASP.NET MVC, las características de identidad se configuran normalmente en *IdentityConfig.CS* en la carpeta *App_Start* .</span><span class="sxs-lookup"><span data-stu-id="9647e-104">In ASP.NET MVC, identity features are typically configured in *IdentityConfig.cs* in the *App_Start* folder.</span></span> <span data-ttu-id="9647e-105">Revise cómo se configura en la aplicación existente y compárelo con la [configuración necesaria para ASP.net Core identidad](/aspnet/core/security/authentication/identity-configuration) en *Startup.CS*.</span><span class="sxs-lookup"><span data-stu-id="9647e-105">Review how this is configured in the existing app, and compare it to the [configuration required for ASP.NET Core Identity](/aspnet/core/security/authentication/identity-configuration) in *Startup.cs*.</span></span>

<span data-ttu-id="9647e-106">ASP.NET Identity es una API que admite la funcionalidad de inicio de sesión de la interfaz de usuario y administra usuarios, contraseñas, datos de perfil, roles, notificaciones, tokens, confirmaciones de correo electrónico y mucho más.</span><span class="sxs-lookup"><span data-stu-id="9647e-106">ASP.NET Identity is an API that supports user interface login functionality and manages users, passwords, profile data, roles, claims, tokens, email confirmations, and more.</span></span> <span data-ttu-id="9647e-107">Admite proveedores de inicio de sesión externos como Facebook, Google, Microsoft y Twitter.</span><span class="sxs-lookup"><span data-stu-id="9647e-107">It supports external login providers like Facebook, Google, Microsoft, and Twitter.</span></span>

<span data-ttu-id="9647e-108">Si su aplicación ASP.NET MVC usa la pertenencia a ASP.NET, encontrará una guía para [migrar desde ASP.net la autenticación de pertenencia a ASP.net Core identidad 2,0](/aspnet/core/migration/proper-to-2x/membership-to-core-identity).</span><span class="sxs-lookup"><span data-stu-id="9647e-108">If your ASP.NET MVC app is using ASP.NET Membership, you'll find a guide to [migrate from ASP.NET Membership authentication to ASP.NET Core 2.0 Identity](/aspnet/core/migration/proper-to-2x/membership-to-core-identity).</span></span> <span data-ttu-id="9647e-109">Se trata principalmente de un ejercicio de migración de datos, a la finalización de la que debería poder usar ASP.NET Core identidad con los registros de usuario migrados.</span><span class="sxs-lookup"><span data-stu-id="9647e-109">This is mainly a data migration exercise, at the completion of which you should be able to use ASP.NET Core Identity with your migrated user records.</span></span>

<span data-ttu-id="9647e-110">Si migra sus usuarios de ASP.NET Identity a ASP.NET Core identidad, es posible que tenga que actualizar sus hashes de contraseña o hacer un seguimiento de las contraseñas con el nuevo enfoque de identidad de ASP.NET Core o el enfoque de ASP.NET Identity anterior.</span><span class="sxs-lookup"><span data-stu-id="9647e-110">If you migrate your ASP.NET Identity users to ASP.NET Core Identity, you may need to update their password hashes, or track which passwords are hashed with the new ASP.NET Core Identity approach or the older ASP.NET Identity approach.</span></span> <span data-ttu-id="9647e-111">[Este enfoque descrito en Stack Overflow](https://stackoverflow.com/a/57074910/13729) proporciona algunas opciones para migrar los hash de contraseña de usuario a lo largo del tiempo, en lugar de todos a la vez.</span><span class="sxs-lookup"><span data-stu-id="9647e-111">[This approach described on Stack Overflow](https://stackoverflow.com/a/57074910/13729) provides some options for migrating user password hashes over time, rather than all at once.</span></span>

<span data-ttu-id="9647e-112">Una de las mayores diferencias cuando se trata de ASP.NET Core identidad en comparación con ASP.NET Identity es el poco código que se debe incluir en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="9647e-112">One of the biggest differences when it comes to ASP.NET Core Identity compared to ASP.NET Identity is how little code you need to include in your project.</span></span> <span data-ttu-id="9647e-113">ASP.NET Core identidad ahora se distribuye como una biblioteca de clases de Razor, lo que significa que la interfaz de usuario y la lógica están disponibles desde un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="9647e-113">ASP.NET Core Identity now ships as a Razor Class Library, meaning its UI and logic are all available from a NuGet package.</span></span> <span data-ttu-id="9647e-114">Puede invalidar la interfaz de usuario y la lógica existentes mediante [la técnica scaffolding de los archivos de identidad de ASP.net Core](/aspnet/core/security/authentication/scaffold-identity) pero, incluso en este caso, solo necesita scaffolding las páginas que desea modificar, no todas ellas.</span><span class="sxs-lookup"><span data-stu-id="9647e-114">You can override the existing UI and logic by [scaffolding the ASP.NET Core Identity files](/aspnet/core/security/authentication/scaffold-identity) but even in this case you need only scaffold the pages you want to modify, not every one that exists.</span></span>

## <a name="migrate-from-owin--katana"></a><span data-ttu-id="9647e-115">Migración desde OWIN/Katana</span><span class="sxs-lookup"><span data-stu-id="9647e-115">Migrate from OWIN / Katana</span></span>

<span data-ttu-id="9647e-116">Los siguientes recursos ofrecen algunas instrucciones para la migración desde OWIN/Katana:</span><span class="sxs-lookup"><span data-stu-id="9647e-116">The following resources offer some guidance for migrating from OWIN / Katana:</span></span>

- [<span data-ttu-id="9647e-117">Migración</span><span class="sxs-lookup"><span data-stu-id="9647e-117">Migration</span></span>](/aspnet/core/migration/proper-to-2x/#globalasax-file-replacement)
- [<span data-ttu-id="9647e-118">Katana a ASPNET 5</span><span class="sxs-lookup"><span data-stu-id="9647e-118">Katana to ASPNET 5</span></span>](https://devblogs.microsoft.com/aspnet/katana-asp-net-5-and-bridging-the-gap/)

## <a name="references"></a><span data-ttu-id="9647e-119">Referencias</span><span class="sxs-lookup"><span data-stu-id="9647e-119">References</span></span>

- [<span data-ttu-id="9647e-120">Migración de la autenticación y la identidad a ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9647e-120">Migrate Authentication and Identity to ASP.NET Core</span></span>](/aspnet/core/migration/identity)
- [<span data-ttu-id="9647e-121">Introducción a la identidad en ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9647e-121">Introduction to Identity on ASP.NET Core</span></span>](/aspnet/core/security/authorization/introduction)
- [<span data-ttu-id="9647e-122">Configuración de la identidad de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9647e-122">Configure ASP.NET Core Identity</span></span>](/aspnet/core/security/authentication/identity-configuration)
- [<span data-ttu-id="9647e-123">Identidad de scaffolding en proyectos de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9647e-123">Scaffold Identity in ASP.NET Core projects</span></span>](/aspnet/core/security/authentication/scaffold-identity)

>[!div class="step-by-step"]
><span data-ttu-id="9647e-124">[Anterior](authentication-differences.md)
>[Siguiente](controller-differences.md)</span><span class="sxs-lookup"><span data-stu-id="9647e-124">[Previous](authentication-differences.md)
[Next](controller-differences.md)</span></span>
