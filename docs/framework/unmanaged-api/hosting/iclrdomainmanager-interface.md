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
ms.openlocfilehash: 797b6031449672e8b610b2a53e77497e5835ea6a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54657433"
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="260f9-102">ICLRDomainManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="260f9-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="260f9-103">Permite que el host especificar el Administrador de dominio de aplicación que se utilizará para inicializar el dominio de aplicación predeterminado y para especificar las propiedades de inicialización.</span><span class="sxs-lookup"><span data-stu-id="260f9-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="260f9-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="260f9-104">Methods</span></span>  
  
|<span data-ttu-id="260f9-105">Método</span><span class="sxs-lookup"><span data-stu-id="260f9-105">Method</span></span>|<span data-ttu-id="260f9-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="260f9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="260f9-107">SetAppDomainManagerType (método)</span><span class="sxs-lookup"><span data-stu-id="260f9-107">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="260f9-108">Especifica el tipo, derivado de la <xref:System.AppDomainManager?displayProperty=nameWithType> (clase), del administrador del dominio de aplicación que se utilizará para inicializar el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="260f9-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="260f9-109">SetPropertiesForDefaultAppDomain (método)</span><span class="sxs-lookup"><span data-stu-id="260f9-109">SetPropertiesForDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="260f9-110">Establece las propiedades que se utilizará para inicializar el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="260f9-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="260f9-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="260f9-111">Remarks</span></span>  
 <span data-ttu-id="260f9-112">Para obtener una instancia de esta interfaz, llame a la [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) método con el tipo de administrador IID `IID_ICLRDomainManager`.</span><span class="sxs-lookup"><span data-stu-id="260f9-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="260f9-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="260f9-113">Requirements</span></span>  
 <span data-ttu-id="260f9-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="260f9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="260f9-115">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="260f9-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="260f9-116">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="260f9-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="260f9-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="260f9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="260f9-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="260f9-118">See also</span></span>
- [<span data-ttu-id="260f9-119">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="260f9-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="260f9-120">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="260f9-120">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
