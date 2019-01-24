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
ms.openlocfilehash: 128e47d356369a75e98a62a85c1dfe8fb6108516
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54519741"
---
# <a name="ihostcontrol-interface"></a><span data-ttu-id="b8a98-102">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b8a98-102">IHostControl Interface</span></span>
<span data-ttu-id="b8a98-103">Proporciona métodos para configurar la carga de ensamblados y para determinar qué interfaces de hospedaje admite el host.</span><span class="sxs-lookup"><span data-stu-id="b8a98-103">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b8a98-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="b8a98-104">Methods</span></span>  
  
|<span data-ttu-id="b8a98-105">Método</span><span class="sxs-lookup"><span data-stu-id="b8a98-105">Method</span></span>|<span data-ttu-id="b8a98-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8a98-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b8a98-107">GetHostManager (método)</span><span class="sxs-lookup"><span data-stu-id="b8a98-107">GetHostManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)|<span data-ttu-id="b8a98-108">Obtiene un puntero de interfaz a la implementación del host de la interfaz con los valores especificados `IID`.</span><span class="sxs-lookup"><span data-stu-id="b8a98-108">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>|  
|[<span data-ttu-id="b8a98-109">SetAppDomainManager (método)</span><span class="sxs-lookup"><span data-stu-id="b8a98-109">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)|<span data-ttu-id="b8a98-110">Notifica al host que se ha creado un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b8a98-110">Notifies the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b8a98-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b8a98-111">Requirements</span></span>  
 <span data-ttu-id="b8a98-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8a98-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8a98-113">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b8a98-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b8a98-114">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b8a98-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b8a98-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8a98-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8a98-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8a98-116">See also</span></span>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="b8a98-117">ICLRRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b8a98-117">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="b8a98-118">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b8a98-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="b8a98-119">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="b8a98-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
