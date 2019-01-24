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
ms.openlocfilehash: e1dea8cc54c68db333c409e3bd7b3e4211bd52ac
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54713972"
---
# <a name="icorpublish-interface"></a><span data-ttu-id="33448-102">ICorPublish (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="33448-102">ICorPublish Interface</span></span>
<span data-ttu-id="33448-103">Actúa como interfaz general para publicar información acerca de los procesos e información sobre los dominios de aplicación en esos procesos.</span><span class="sxs-lookup"><span data-stu-id="33448-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="33448-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="33448-104">Methods</span></span>  
  
|<span data-ttu-id="33448-105">Método</span><span class="sxs-lookup"><span data-stu-id="33448-105">Method</span></span>|<span data-ttu-id="33448-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="33448-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="33448-107">EnumProcesses (método)</span><span class="sxs-lookup"><span data-stu-id="33448-107">EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md)|<span data-ttu-id="33448-108">Obtiene un [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instancia que contiene los procesos administrados que se ejecutan en este equipo.</span><span class="sxs-lookup"><span data-stu-id="33448-108">Gets an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="33448-109">GetProcess (método)</span><span class="sxs-lookup"><span data-stu-id="33448-109">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-getprocess-method.md)|<span data-ttu-id="33448-110">Obtiene un [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instancia que representa el proceso con el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="33448-110">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="33448-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33448-111">Requirements</span></span>  
 <span data-ttu-id="33448-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33448-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33448-113">**Encabezado**: CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="33448-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="33448-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33448-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33448-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33448-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33448-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="33448-116">See also</span></span>
- [<span data-ttu-id="33448-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="33448-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="33448-118">CorpubPublish (coclase)</span><span class="sxs-lookup"><span data-stu-id="33448-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
