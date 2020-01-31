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
ms.openlocfilehash: fdd2fee11e9353c3aa3faee2b137597e4ba47801
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791183"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="f5749-102">ICorDebugUnmanagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f5749-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="f5749-103">Proporciona la notificación de eventos nativos que no están directamente relacionados con el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="f5749-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f5749-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f5749-104">Methods</span></span>  
  
|<span data-ttu-id="f5749-105">Método</span><span class="sxs-lookup"><span data-stu-id="f5749-105">Method</span></span>|<span data-ttu-id="f5749-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5749-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f5749-107">DebugEvent (método)</span><span class="sxs-lookup"><span data-stu-id="f5749-107">DebugEvent Method</span></span>](icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="f5749-108">Notifica al depurador que se ha desencadenado un evento nativo.</span><span class="sxs-lookup"><span data-stu-id="f5749-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5749-109">Notas</span><span class="sxs-lookup"><span data-stu-id="f5749-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f5749-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="f5749-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5749-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="f5749-111">Requirements</span></span>  
 <span data-ttu-id="f5749-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5749-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5749-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5749-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5749-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5749-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5749-115">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5749-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5749-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5749-116">See also</span></span>

- [<span data-ttu-id="f5749-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f5749-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
