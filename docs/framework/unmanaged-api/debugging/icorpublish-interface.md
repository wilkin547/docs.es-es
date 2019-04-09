---
title: ICorPublish (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorPublish
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish
helpviewer_keywords:
- ICorPublish interface [.NET Framework debugging]
ms.assetid: 87c4fcb2-7703-4a2e-afb6-42973381b960
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7581d68f5c2b575403ddc84d06147f012e7ab39e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076346"
---
# <a name="icorpublish-interface"></a><span data-ttu-id="e4797-102">ICorPublish (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e4797-102">ICorPublish Interface</span></span>
<span data-ttu-id="e4797-103">Actúa como interfaz general para publicar información acerca de los procesos e información sobre los dominios de aplicación en esos procesos.</span><span class="sxs-lookup"><span data-stu-id="e4797-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e4797-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e4797-104">Methods</span></span>  
  
|<span data-ttu-id="e4797-105">Método</span><span class="sxs-lookup"><span data-stu-id="e4797-105">Method</span></span>|<span data-ttu-id="e4797-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4797-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e4797-107">Método EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="e4797-107">EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md)|<span data-ttu-id="e4797-108">Obtiene un [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instancia que contiene los procesos administrados que se ejecutan en este equipo.</span><span class="sxs-lookup"><span data-stu-id="e4797-108">Gets an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="e4797-109">Método GetProcess</span><span class="sxs-lookup"><span data-stu-id="e4797-109">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-getprocess-method.md)|<span data-ttu-id="e4797-110">Obtiene un [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instancia que representa el proceso con el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="e4797-110">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e4797-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e4797-111">Requirements</span></span>  
 <span data-ttu-id="e4797-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4797-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4797-113">**Encabezado**: CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="e4797-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="e4797-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4797-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e4797-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e4797-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e4797-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4797-116">See also</span></span>

- [<span data-ttu-id="e4797-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="e4797-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="e4797-118">CorpubPublish (coclase)</span><span class="sxs-lookup"><span data-stu-id="e4797-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
