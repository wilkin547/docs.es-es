---
title: Permiso de seguridad para la redirección de enlaces de ensamblados
description: Obtenga información sobre el permiso de seguridad requerido para la redirección de enlace de ensamblados explícita en un archivo de configuración de la aplicación en .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
ms.openlocfilehash: 2de2c50f5adb9e9fa36ea015ef498e9953c83005
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165226"
---
# <a name="assembly-binding-redirection-security-permission"></a><span data-ttu-id="3e67d-103">Permiso de seguridad para la redirección de enlaces de ensamblados</span><span class="sxs-lookup"><span data-stu-id="3e67d-103">Assembly Binding Redirection Security Permission</span></span>

<span data-ttu-id="3e67d-104">Para realizar una redirección de enlaces de ensamblado de forma explícita en un archivo de configuración, se precisa permiso de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3e67d-104">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="3e67d-105">Esto se aplica a la redirección de los ensamblados de .NET Framework y de los ensamblados de otros proveedores.</span><span class="sxs-lookup"><span data-stu-id="3e67d-105">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="3e67d-106">El permiso se concede estableciendo la <xref:System.Security.Permissions.SecurityPermissionFlag> marca en <xref:System.Security.Permissions.SecurityPermission> .</span><span class="sxs-lookup"><span data-stu-id="3e67d-106">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="3e67d-107">De forma predeterminada, los ensamblados administrados no tienen permisos.</span><span class="sxs-lookup"><span data-stu-id="3e67d-107">Managed assemblies have no permissions by default.</span></span>  
  
 <span data-ttu-id="3e67d-108">El permiso de seguridad se concede a las aplicaciones que se ejecutan en la zona de confianza (equipo local) y en la zona de intranet.</span><span class="sxs-lookup"><span data-stu-id="3e67d-108">The security permission is granted to applications running in the Trusted Zone (local machine) and Intranet Zone.</span></span> <span data-ttu-id="3e67d-109">Las aplicaciones que se ejecutan en la zona de Internet están estrictamente prohibidas para realizar la redirección de enlace de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3e67d-109">Applications running in the Internet Zone are strictly prohibited from performing assembly binding redirection.</span></span>  
  
 <span data-ttu-id="3e67d-110">El permiso no es necesario si la redirección de ensamblados se realiza en un archivo de directiva de edición que está controlado por el publicador de componentes o en el archivo de configuración del equipo controlado por el administrador.</span><span class="sxs-lookup"><span data-stu-id="3e67d-110">The permission is not required if assembly redirection is performed in a publisher policy file that is controlled by the component publisher, or in the machine configuration file that is controlled by the administrator.</span></span> <span data-ttu-id="3e67d-111">Sin embargo, el permiso es necesario para que una aplicación ignore explícitamente la Directiva de editor mediante el [\<publisherPolicy apply="no"/>](./file-schema/runtime/publisherpolicy-element.md) elemento del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3e67d-111">However, the permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](./file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span>  
  
 <span data-ttu-id="3e67d-112">En la tabla siguiente se muestra la configuración de seguridad predeterminada para la marca **BindingRedirects** .</span><span class="sxs-lookup"><span data-stu-id="3e67d-112">The following table shows the default security settings for the **BindingRedirects** flag.</span></span>  
  
|<span data-ttu-id="3e67d-113">Zona</span><span class="sxs-lookup"><span data-stu-id="3e67d-113">Zone</span></span>|<span data-ttu-id="3e67d-114">Valor de la marca BindingRedirects</span><span class="sxs-lookup"><span data-stu-id="3e67d-114">BindingRedirects flag setting</span></span>|  
|----------|-----------------------------------|  
|<span data-ttu-id="3e67d-115">Zona de confianza (equipo local)</span><span class="sxs-lookup"><span data-stu-id="3e67d-115">Trusted Zone (local machine)</span></span>|<span data-ttu-id="3e67d-116">**ON**</span><span class="sxs-lookup"><span data-stu-id="3e67d-116">**ON**</span></span>|  
|<span data-ttu-id="3e67d-117">Zona Intranet</span><span class="sxs-lookup"><span data-stu-id="3e67d-117">Intranet Zone</span></span>|<span data-ttu-id="3e67d-118">**ON**</span><span class="sxs-lookup"><span data-stu-id="3e67d-118">**ON**</span></span>|  
|<span data-ttu-id="3e67d-119">Zona de Internet</span><span class="sxs-lookup"><span data-stu-id="3e67d-119">Internet Zone</span></span>|<span data-ttu-id="3e67d-120">**OFF**</span><span class="sxs-lookup"><span data-stu-id="3e67d-120">**OFF**</span></span>|  
|<span data-ttu-id="3e67d-121">Zonas que no son de confianza</span><span class="sxs-lookup"><span data-stu-id="3e67d-121">Untrusted zones</span></span>|<span data-ttu-id="3e67d-122">**OFF**</span><span class="sxs-lookup"><span data-stu-id="3e67d-122">**OFF**</span></span>|  
  
 <span data-ttu-id="3e67d-123">Un administrador puede cambiar esta configuración de seguridad para admitir o restringir escenarios específicos en un equipo determinado.</span><span class="sxs-lookup"><span data-stu-id="3e67d-123">An administrator can change these security settings to support or restrict specific scenarios on a given computer.</span></span> <span data-ttu-id="3e67d-124">No hay ninguna herramienta para cambiar la configuración de la marca **BindingRedirects** del valor predeterminado; un administrador debe editar manualmente el archivo de Security.config en el equipo de un usuario.</span><span class="sxs-lookup"><span data-stu-id="3e67d-124">There are no tools for changing the **BindingRedirects** flag setting from the default; an administrator must manually edit the Security.config file on a user's computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e67d-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3e67d-125">See also</span></span>

- <span data-ttu-id="3e67d-126">[Archivos de directivas de edición y ejecución en paralelo](/previous-versions/dotnet/netframework-4.0/06d2bae3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3e67d-126">[Publisher Policy Files and Side-by-Side Execution](/previous-versions/dotnet/netframework-4.0/06d2bae3(v=vs.100))</span></span>
- [<span data-ttu-id="3e67d-127">Cómo: Habilitar y deshabilitar redireccionamiento de enlaces automático</span><span class="sxs-lookup"><span data-stu-id="3e67d-127">How to: Enable and Disable Automatic Binding Redirection</span></span>](how-to-enable-and-disable-automatic-binding-redirection.md)
- [<span data-ttu-id="3e67d-128">Ejecución en paralelo</span><span class="sxs-lookup"><span data-stu-id="3e67d-128">Side-by-Side Execution</span></span>](../deployment/side-by-side-execution.md)
