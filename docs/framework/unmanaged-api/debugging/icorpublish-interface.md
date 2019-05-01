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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993591"
---
# <a name="icorpublish-interface"></a><span data-ttu-id="d219a-102">ICorPublish (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d219a-102">ICorPublish Interface</span></span>
<span data-ttu-id="d219a-103">Actúa como interfaz general para publicar información acerca de los procesos e información sobre los dominios de aplicación en esos procesos.</span><span class="sxs-lookup"><span data-stu-id="d219a-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d219a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="d219a-104">Methods</span></span>  
  
|<span data-ttu-id="d219a-105">Método</span><span class="sxs-lookup"><span data-stu-id="d219a-105">Method</span></span>|<span data-ttu-id="d219a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="d219a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d219a-107">EnumProcesses (método)</span><span class="sxs-lookup"><span data-stu-id="d219a-107">EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md)|<span data-ttu-id="d219a-108">Obtiene un [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instancia que contiene los procesos administrados que se ejecutan en este equipo.</span><span class="sxs-lookup"><span data-stu-id="d219a-108">Gets an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="d219a-109">GetProcess (método)</span><span class="sxs-lookup"><span data-stu-id="d219a-109">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-getprocess-method.md)|<span data-ttu-id="d219a-110">Obtiene un [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instancia que representa el proceso con el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="d219a-110">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d219a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d219a-111">Requirements</span></span>  
 <span data-ttu-id="d219a-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d219a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d219a-113">**Encabezado**: CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="d219a-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="d219a-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d219a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d219a-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d219a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d219a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d219a-116">See also</span></span>

- [<span data-ttu-id="d219a-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="d219a-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="d219a-118">CorpubPublish (coclase)</span><span class="sxs-lookup"><span data-stu-id="d219a-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
