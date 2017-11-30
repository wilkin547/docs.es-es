---
title: ICLRDomainManager (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDomainManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDomainManager
helpviewer_keywords: ICLRDomainManager interface [.NET Framework hosting]
ms.assetid: f08b2390-d872-4521-a815-e9c237c4c45d
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 75a7e93d26a5c77484d78ad4632bedf8def6a44b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="943fb-102">ICLRDomainManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="943fb-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="943fb-103">Permite que el host especificar el Administrador de dominio de aplicación que se utilizará para inicializar el dominio de aplicación predeterminado y para especificar las propiedades de inicialización.</span><span class="sxs-lookup"><span data-stu-id="943fb-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="943fb-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="943fb-104">Methods</span></span>  
  
|<span data-ttu-id="943fb-105">Método</span><span class="sxs-lookup"><span data-stu-id="943fb-105">Method</span></span>|<span data-ttu-id="943fb-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="943fb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="943fb-107">SetAppDomainManagerType (método)</span><span class="sxs-lookup"><span data-stu-id="943fb-107">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="943fb-108">Especifica el tipo, derivado de la <xref:System.AppDomainManager?displayProperty=nameWithType> (clase), del Administrador de dominio de aplicación que se usarán para inicializar el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="943fb-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="943fb-109">SetPropertiesForDefaultAppDomain (método)</span><span class="sxs-lookup"><span data-stu-id="943fb-109">SetPropertiesForDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="943fb-110">Establece las propiedades que se usarán para inicializar el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="943fb-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="943fb-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="943fb-111">Remarks</span></span>  
 <span data-ttu-id="943fb-112">Para obtener una instancia de esta interfaz, llame a la [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) método con el tipo de administrador IID `IID_ICLRDomainManager`.</span><span class="sxs-lookup"><span data-stu-id="943fb-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="943fb-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="943fb-113">Requirements</span></span>  
 <span data-ttu-id="943fb-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="943fb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="943fb-115">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="943fb-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="943fb-116">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="943fb-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="943fb-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="943fb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="943fb-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="943fb-118">See Also</span></span>  
 [<span data-ttu-id="943fb-119">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="943fb-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="943fb-120">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="943fb-120">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
