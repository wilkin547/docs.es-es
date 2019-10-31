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
ms.openlocfilehash: aa874205cf14232e7a69ed2215086e33c0beab4d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129340"
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="dfd35-102">ICLRDomainManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dfd35-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="dfd35-103">Permite al host especificar el administrador del dominio de aplicación que se utilizará para inicializar el dominio de aplicación predeterminado y para especificar las propiedades de inicialización.</span><span class="sxs-lookup"><span data-stu-id="dfd35-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dfd35-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="dfd35-104">Methods</span></span>  
  
|<span data-ttu-id="dfd35-105">Método</span><span class="sxs-lookup"><span data-stu-id="dfd35-105">Method</span></span>|<span data-ttu-id="dfd35-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="dfd35-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dfd35-107">SetAppDomainManagerType (método)</span><span class="sxs-lookup"><span data-stu-id="dfd35-107">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="dfd35-108">Especifica el tipo, derivado de la clase <xref:System.AppDomainManager?displayProperty=nameWithType>, del administrador del dominio de aplicación que se utilizará para inicializar el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="dfd35-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="dfd35-109">SetPropertiesForDefaultAppDomain (método)</span><span class="sxs-lookup"><span data-stu-id="dfd35-109">SetPropertiesForDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="dfd35-110">Establece las propiedades que se usarán para inicializar el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="dfd35-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dfd35-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dfd35-111">Remarks</span></span>  
 <span data-ttu-id="dfd35-112">Para obtener una instancia de esta interfaz, llame al método [ICLRControl:: GetCLRManager (](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) con el IID de tipo de administrador `IID_ICLRDomainManager`.</span><span class="sxs-lookup"><span data-stu-id="dfd35-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfd35-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dfd35-113">Requirements</span></span>  
 <span data-ttu-id="dfd35-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfd35-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfd35-115">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="dfd35-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="dfd35-116">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="dfd35-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dfd35-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfd35-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfd35-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="dfd35-118">See also</span></span>

- [<span data-ttu-id="dfd35-119">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="dfd35-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="dfd35-120">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="dfd35-120">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
