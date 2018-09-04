---
title: Permiso de seguridad para la redirección de enlaces de ensamblados
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b9b9ac5c4e8ce08b9f926b0cdf7149dbdd9ac2da
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43501438"
---
# <a name="assembly-binding-redirection-security-permission"></a><span data-ttu-id="26175-102">Permiso de seguridad para la redirección de enlaces de ensamblados</span><span class="sxs-lookup"><span data-stu-id="26175-102">Assembly Binding Redirection Security Permission</span></span>
<span data-ttu-id="26175-103">Para realizar una redirección de enlaces de ensamblado de forma explícita en un archivo de configuración, se precisa permiso de seguridad.</span><span class="sxs-lookup"><span data-stu-id="26175-103">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="26175-104">Esto se aplica a la redirección de los ensamblados de .NET Framework y de los ensamblados de otros proveedores.</span><span class="sxs-lookup"><span data-stu-id="26175-104">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="26175-105">El permiso se otorga estableciendo el <xref:System.Security.Permissions.SecurityPermissionFlag> marca en el <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="26175-105">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="26175-106">Los ensamblados administrados no tienen permisos de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="26175-106">Managed assemblies have no permissions by default.</span></span>  
  
 <span data-ttu-id="26175-107">Se concede el permiso de seguridad para aplicaciones que se ejecutan en la zona de confianza (equipo local) y la zona de Intranet.</span><span class="sxs-lookup"><span data-stu-id="26175-107">The security permission is granted to applications running in the Trusted Zone (local machine) and Intranet Zone.</span></span> <span data-ttu-id="26175-108">Aplicaciones que se ejecutan en la zona de Internet se prohíbe estrictamente realiza la redirección de enlace de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="26175-108">Applications running in the Internet Zone are strictly prohibited from performing assembly binding redirection.</span></span>  
  
 <span data-ttu-id="26175-109">El permiso no es necesario si se realiza la redirección de ensamblado en un archivo de directiva de edición que se controla mediante el Editor de componentes, o en el archivo de configuración de máquina que esté controlado por el administrador.</span><span class="sxs-lookup"><span data-stu-id="26175-109">The permission is not required if assembly redirection is performed in a publisher policy file that is controlled by the component publisher, or in the machine configuration file that is controlled by the administrator.</span></span> <span data-ttu-id="26175-110">Sin embargo, el permiso es necesario para una aplicación omitir explícitamente la directiva de publicador con el [ \<publisherPolicy aplicar = "no" / >](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) elemento en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="26175-110">However, the permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span>  
  
 <span data-ttu-id="26175-111">En la tabla siguiente se muestra el valor predeterminado de configuración de seguridad para el **BindingRedirects** marca.</span><span class="sxs-lookup"><span data-stu-id="26175-111">The following table shows the default security settings for the **BindingRedirects** flag.</span></span>  
  
|<span data-ttu-id="26175-112">Zona</span><span class="sxs-lookup"><span data-stu-id="26175-112">Zone</span></span>|<span data-ttu-id="26175-113">Indicador BindingRedirects</span><span class="sxs-lookup"><span data-stu-id="26175-113">BindingRedirects flag setting</span></span>|  
|----------|-----------------------------------|  
|<span data-ttu-id="26175-114">Zona de confianza (equipo local)</span><span class="sxs-lookup"><span data-stu-id="26175-114">Trusted Zone (local machine)</span></span>|<span data-ttu-id="26175-115">**ON**</span><span class="sxs-lookup"><span data-stu-id="26175-115">**ON**</span></span>|  
|<span data-ttu-id="26175-116">Zona de intranet</span><span class="sxs-lookup"><span data-stu-id="26175-116">Intranet Zone</span></span>|<span data-ttu-id="26175-117">**ON**</span><span class="sxs-lookup"><span data-stu-id="26175-117">**ON**</span></span>|  
|<span data-ttu-id="26175-118">Zona de Internet</span><span class="sxs-lookup"><span data-stu-id="26175-118">Internet Zone</span></span>|<span data-ttu-id="26175-119">**DESACTIVAR**</span><span class="sxs-lookup"><span data-stu-id="26175-119">**OFF**</span></span>|  
|<span data-ttu-id="26175-120">Zonas de confianza</span><span class="sxs-lookup"><span data-stu-id="26175-120">Untrusted zones</span></span>|<span data-ttu-id="26175-121">**DESACTIVAR**</span><span class="sxs-lookup"><span data-stu-id="26175-121">**OFF**</span></span>|  
  
 <span data-ttu-id="26175-122">Un administrador puede cambiar esta configuración de seguridad para admitir o rechazar escenarios específicos en un equipo determinado.</span><span class="sxs-lookup"><span data-stu-id="26175-122">An administrator can change these security settings to support or restrict specific scenarios on a given computer.</span></span> <span data-ttu-id="26175-123">No hay ninguna herramienta para cambiar la **BindingRedirects** marca predeterminado; un administrador debe editar manualmente el archivo Security.config en el equipo del usuario.</span><span class="sxs-lookup"><span data-stu-id="26175-123">There are no tools for changing the **BindingRedirects** flag setting from the default; an administrator must manually edit the Security.config file on a user's computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26175-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="26175-124">See Also</span></span>  
 [<span data-ttu-id="26175-125">Archivos de directivas de publicador y ejecución en paralelo</span><span class="sxs-lookup"><span data-stu-id="26175-125">Publisher Policy Files and Side-by-Side Execution</span></span>](https://msdn.microsoft.com/library/97a042be-4d72-40c3-91c0-76fd36bdf133)  
 [<span data-ttu-id="26175-126">Cómo: Habilitar y deshabilitar redireccionamiento de enlaces automático</span><span class="sxs-lookup"><span data-stu-id="26175-126">How to: Enable and Disable Automatic Binding Redirection</span></span>](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)  
 [<span data-ttu-id="26175-127">Ejecución en paralelo</span><span class="sxs-lookup"><span data-stu-id="26175-127">Side-by-Side Execution</span></span>](../../../docs/framework/deployment/side-by-side-execution.md)
