---
title: IGCHost2 (Interfaz)
ms.date: 03/30/2017
api_name:
- IGCHost2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2
helpviewer_keywords:
- IGCHost2 interface [.NET Framework hosting]
ms.assetid: e5323fa4-18ac-424d-859d-a65a550d08d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75bef91eb70c8109653741452362cd2e85f625ce
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946112"
---
# <a name="igchost2-interface"></a><span data-ttu-id="13355-102">IGCHost2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="13355-102">IGCHost2 Interface</span></span>
<span data-ttu-id="13355-103">Proporciona métodos para obtener información sobre el sistema de recopilación de elementos no utilizados y para controlar algunos aspectos de la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="13355-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13355-104">Para el desarrollo nuevo, se recomienda que use el [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) interfaz en su lugar.</span><span class="sxs-lookup"><span data-stu-id="13355-104">For new development, we recommend that you use the [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="13355-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="13355-105">Methods</span></span>  
  
|<span data-ttu-id="13355-106">Método</span><span class="sxs-lookup"><span data-stu-id="13355-106">Method</span></span>|<span data-ttu-id="13355-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="13355-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="13355-108">SetGCStartupLimitsEx (método)</span><span class="sxs-lookup"><span data-stu-id="13355-108">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="13355-109">Establece el tamaño del segmento y el tamaño máximo para la generación 0.</span><span class="sxs-lookup"><span data-stu-id="13355-109">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="13355-110">Habilita la generación 0 y el tamaño de segmento mayor que `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="13355-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="13355-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="13355-111">Requirements</span></span>  
 <span data-ttu-id="13355-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13355-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13355-113">**Encabezado**: GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="13355-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="13355-114">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="13355-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13355-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13355-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13355-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="13355-116">See also</span></span>

- [<span data-ttu-id="13355-117">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="13355-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="13355-118">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="13355-118">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="13355-119">CorRuntimeHost (coclase)</span><span class="sxs-lookup"><span data-stu-id="13355-119">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
