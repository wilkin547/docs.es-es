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
ms.openlocfilehash: a34454e7e007b4eba557c712cb824362aa5047c3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952977"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="97541-102">ICorDebugUnmanagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="97541-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="97541-103">Proporciona la notificación de eventos nativos que no están directamente relacionados con el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="97541-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="97541-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="97541-104">Methods</span></span>  
  
|<span data-ttu-id="97541-105">Método</span><span class="sxs-lookup"><span data-stu-id="97541-105">Method</span></span>|<span data-ttu-id="97541-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="97541-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="97541-107">DebugEvent (método)</span><span class="sxs-lookup"><span data-stu-id="97541-107">DebugEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="97541-108">Notifica al depurador que se ha desencadenado un evento nativo.</span><span class="sxs-lookup"><span data-stu-id="97541-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97541-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="97541-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="97541-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="97541-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97541-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="97541-111">Requirements</span></span>  
 <span data-ttu-id="97541-112">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97541-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97541-113">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="97541-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97541-114">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97541-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97541-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97541-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97541-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="97541-116">See also</span></span>

- [<span data-ttu-id="97541-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="97541-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
