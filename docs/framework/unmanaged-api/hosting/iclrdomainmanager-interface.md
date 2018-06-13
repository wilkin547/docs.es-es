---
title: ICLRDomainManager (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager
helpviewer_keywords:
- ICLRDomainManager interface [.NET Framework hosting]
ms.assetid: f08b2390-d872-4521-a815-e9c237c4c45d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3b8dd67cb7dff4bec5bab192a08461ef13fcbd9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436363"
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="39541-102">ICLRDomainManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="39541-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="39541-103">Permite que el host especificar el Administrador de dominio de aplicación que se utilizará para inicializar el dominio de aplicación predeterminado y para especificar las propiedades de inicialización.</span><span class="sxs-lookup"><span data-stu-id="39541-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="39541-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="39541-104">Methods</span></span>  
  
|<span data-ttu-id="39541-105">Método</span><span class="sxs-lookup"><span data-stu-id="39541-105">Method</span></span>|<span data-ttu-id="39541-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="39541-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="39541-107">SetAppDomainManagerType (método)</span><span class="sxs-lookup"><span data-stu-id="39541-107">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="39541-108">Especifica el tipo, derivado de la <xref:System.AppDomainManager?displayProperty=nameWithType> (clase), del Administrador de dominio de aplicación que se usarán para inicializar el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="39541-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="39541-109">SetPropertiesForDefaultAppDomain (método)</span><span class="sxs-lookup"><span data-stu-id="39541-109">SetPropertiesForDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="39541-110">Establece las propiedades que se usarán para inicializar el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="39541-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39541-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="39541-111">Remarks</span></span>  
 <span data-ttu-id="39541-112">Para obtener una instancia de esta interfaz, llame a la [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) método con el tipo de administrador IID `IID_ICLRDomainManager`.</span><span class="sxs-lookup"><span data-stu-id="39541-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39541-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="39541-113">Requirements</span></span>  
 <span data-ttu-id="39541-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39541-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39541-115">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="39541-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="39541-116">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="39541-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="39541-117">**Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39541-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39541-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="39541-118">See Also</span></span>  
 [<span data-ttu-id="39541-119">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="39541-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="39541-120">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="39541-120">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
