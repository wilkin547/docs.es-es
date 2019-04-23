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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59128685"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="e33ff-102">ICorDebugUnmanagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e33ff-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="e33ff-103">Proporciona notificación de eventos nativos que no están directamente relacionadas con common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="e33ff-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e33ff-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e33ff-104">Methods</span></span>  
  
|<span data-ttu-id="e33ff-105">Método</span><span class="sxs-lookup"><span data-stu-id="e33ff-105">Method</span></span>|<span data-ttu-id="e33ff-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e33ff-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e33ff-107">DebugEvent (método)</span><span class="sxs-lookup"><span data-stu-id="e33ff-107">DebugEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="e33ff-108">Notifica al depurador que se ha desencadenado un evento nativo.</span><span class="sxs-lookup"><span data-stu-id="e33ff-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e33ff-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e33ff-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e33ff-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="e33ff-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e33ff-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e33ff-111">Requirements</span></span>  
 <span data-ttu-id="e33ff-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e33ff-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e33ff-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e33ff-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e33ff-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e33ff-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e33ff-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e33ff-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e33ff-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e33ff-116">See also</span></span>

- [<span data-ttu-id="e33ff-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="e33ff-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
