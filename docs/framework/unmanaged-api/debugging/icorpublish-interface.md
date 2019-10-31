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
ms.openlocfilehash: 70cf2d76c7c5d1c3431506685f8506e44ab9ec4a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121766"
---
# <a name="icorpublish-interface"></a><span data-ttu-id="c3180-102">ICorPublish (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c3180-102">ICorPublish Interface</span></span>
<span data-ttu-id="c3180-103">Actúa como la interfaz general para publicar información sobre procesos e información sobre los dominios de aplicación en esos procesos.</span><span class="sxs-lookup"><span data-stu-id="c3180-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c3180-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c3180-104">Methods</span></span>  
  
|<span data-ttu-id="c3180-105">Método</span><span class="sxs-lookup"><span data-stu-id="c3180-105">Method</span></span>|<span data-ttu-id="c3180-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c3180-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c3180-107">EnumProcesses (método)</span><span class="sxs-lookup"><span data-stu-id="c3180-107">EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md)|<span data-ttu-id="c3180-108">Obtiene una instancia de [ICorPublishProcessEnum (](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) que contiene los procesos administrados que se ejecutan en este equipo.</span><span class="sxs-lookup"><span data-stu-id="c3180-108">Gets an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="c3180-109">GetProcess (método)</span><span class="sxs-lookup"><span data-stu-id="c3180-109">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-getprocess-method.md)|<span data-ttu-id="c3180-110">Obtiene una instancia de [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) que representa el proceso con el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="c3180-110">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c3180-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c3180-111">Requirements</span></span>  
 <span data-ttu-id="c3180-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3180-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3180-113">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="c3180-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="c3180-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3180-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3180-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3180-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3180-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3180-116">See also</span></span>

- [<span data-ttu-id="c3180-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c3180-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="c3180-118">CorpubPublish (coclase)</span><span class="sxs-lookup"><span data-stu-id="c3180-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
