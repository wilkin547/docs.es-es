---
title: IHostControl (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl
helpviewer_keywords:
- IHostControl interface [.NET Framework hosting]
ms.assetid: a4ae0d1f-ade9-4b0a-a122-93ed11a5e6b3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 014e5c9951091046ae07374794743e82affcd5ad
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122270"
---
# <a name="ihostcontrol-interface"></a><span data-ttu-id="29f4d-102">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="29f4d-102">IHostControl Interface</span></span>
<span data-ttu-id="29f4d-103">Proporciona métodos para configurar la carga de ensamblados y para determinar qué interfaces de hospedaje admite el host.</span><span class="sxs-lookup"><span data-stu-id="29f4d-103">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="29f4d-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="29f4d-104">Methods</span></span>  
  
|<span data-ttu-id="29f4d-105">Método</span><span class="sxs-lookup"><span data-stu-id="29f4d-105">Method</span></span>|<span data-ttu-id="29f4d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="29f4d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="29f4d-107">Método GetHostManager</span><span class="sxs-lookup"><span data-stu-id="29f4d-107">GetHostManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)|<span data-ttu-id="29f4d-108">Obtiene un puntero de interfaz a la implementación del host de la interfaz con los valores especificados `IID`.</span><span class="sxs-lookup"><span data-stu-id="29f4d-108">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>|  
|[<span data-ttu-id="29f4d-109">Método SetAppDomainManager</span><span class="sxs-lookup"><span data-stu-id="29f4d-109">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)|<span data-ttu-id="29f4d-110">Notifica al host que se ha creado un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="29f4d-110">Notifies the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="29f4d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="29f4d-111">Requirements</span></span>  
 <span data-ttu-id="29f4d-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29f4d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29f4d-113">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="29f4d-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="29f4d-114">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="29f4d-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="29f4d-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="29f4d-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="29f4d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="29f4d-116">See also</span></span>

- <xref:System.AppDomainManager>
- [<span data-ttu-id="29f4d-117">ICLRRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="29f4d-117">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="29f4d-118">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="29f4d-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="29f4d-119">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="29f4d-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
