---
title: ICorPublish (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublish
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublish
helpviewer_keywords: ICorPublish interface [.NET Framework debugging]
ms.assetid: 87c4fcb2-7703-4a2e-afb6-42973381b960
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8eb3bd2da9529a681f7f3a09ef7eb78c776cc302
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorpublish-interface"></a><span data-ttu-id="73c9a-102">ICorPublish (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="73c9a-102">ICorPublish Interface</span></span>
<span data-ttu-id="73c9a-103">Actúa como interfaz general para publicar información acerca de los procesos e información sobre los dominios de aplicación en esos procesos.</span><span class="sxs-lookup"><span data-stu-id="73c9a-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="73c9a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="73c9a-104">Methods</span></span>  
  
|<span data-ttu-id="73c9a-105">Método</span><span class="sxs-lookup"><span data-stu-id="73c9a-105">Method</span></span>|<span data-ttu-id="73c9a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="73c9a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="73c9a-107">EnumProcesses (método)</span><span class="sxs-lookup"><span data-stu-id="73c9a-107">EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md)|<span data-ttu-id="73c9a-108">Obtiene un [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instancia que contiene los procesos administrados que se ejecutan en este equipo.</span><span class="sxs-lookup"><span data-stu-id="73c9a-108">Gets an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="73c9a-109">GetProcess (método)</span><span class="sxs-lookup"><span data-stu-id="73c9a-109">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-getprocess-method.md)|<span data-ttu-id="73c9a-110">Obtiene un [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instancia que representa el proceso con el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="73c9a-110">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="73c9a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="73c9a-111">Requirements</span></span>  
 <span data-ttu-id="73c9a-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73c9a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73c9a-113">**Encabezado:** Cordebug.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="73c9a-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="73c9a-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73c9a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73c9a-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73c9a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73c9a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="73c9a-116">See Also</span></span>  
 [<span data-ttu-id="73c9a-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="73c9a-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="73c9a-118">CorpubPublish (Coclase)</span><span class="sxs-lookup"><span data-stu-id="73c9a-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
