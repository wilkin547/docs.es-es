---
title: ICorDebugUnmanagedCallback (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugUnmanagedCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback
helpviewer_keywords:
- ICorDebugUnmanagedCallback interface [.NET Framework debugging]
ms.assetid: bc71cbca-7d73-40e5-84dd-2109fade3c2a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd61c8133d9f155ae8e15bbc6aa90b2b9de1aadd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54647677"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="437c2-102">ICorDebugUnmanagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="437c2-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="437c2-103">Proporciona notificación de eventos nativos que no están directamente relacionadas con common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="437c2-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="437c2-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="437c2-104">Methods</span></span>  
  
|<span data-ttu-id="437c2-105">Método</span><span class="sxs-lookup"><span data-stu-id="437c2-105">Method</span></span>|<span data-ttu-id="437c2-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="437c2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="437c2-107">DebugEvent (método)</span><span class="sxs-lookup"><span data-stu-id="437c2-107">DebugEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="437c2-108">Notifica al depurador que se ha desencadenado un evento nativo.</span><span class="sxs-lookup"><span data-stu-id="437c2-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="437c2-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="437c2-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="437c2-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="437c2-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="437c2-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="437c2-111">Requirements</span></span>  
 <span data-ttu-id="437c2-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="437c2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="437c2-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="437c2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="437c2-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="437c2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="437c2-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="437c2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="437c2-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="437c2-116">See also</span></span>
- [<span data-ttu-id="437c2-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="437c2-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
