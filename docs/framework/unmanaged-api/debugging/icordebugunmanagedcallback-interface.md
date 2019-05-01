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
ms.openlocfilehash: 60a1546068ae6a8c8be1c0af1ef3c7d770c23d70
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993764"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="91291-102">ICorDebugUnmanagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="91291-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="91291-103">Proporciona notificación de eventos nativos que no están directamente relacionadas con common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="91291-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="91291-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="91291-104">Methods</span></span>  
  
|<span data-ttu-id="91291-105">Método</span><span class="sxs-lookup"><span data-stu-id="91291-105">Method</span></span>|<span data-ttu-id="91291-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="91291-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="91291-107">DebugEvent (método)</span><span class="sxs-lookup"><span data-stu-id="91291-107">DebugEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="91291-108">Notifica al depurador que se ha desencadenado un evento nativo.</span><span class="sxs-lookup"><span data-stu-id="91291-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91291-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="91291-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91291-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="91291-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91291-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="91291-111">Requirements</span></span>  
 <span data-ttu-id="91291-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91291-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91291-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91291-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91291-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91291-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91291-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91291-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91291-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="91291-116">See also</span></span>

- [<span data-ttu-id="91291-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="91291-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
