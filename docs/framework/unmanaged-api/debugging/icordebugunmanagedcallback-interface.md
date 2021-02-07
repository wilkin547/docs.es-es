---
description: 'Más información acerca de: interfaz ICorDebugUnmanagedCallback ('
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
ms.openlocfilehash: 6d8aa398ff7121e360c3da66671781cd169b6228
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690553"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="e1ffe-103">ICorDebugUnmanagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1ffe-103">ICorDebugUnmanagedCallback Interface</span></span>

<span data-ttu-id="e1ffe-104">Proporciona la notificación de eventos nativos que no están directamente relacionados con el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="e1ffe-104">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e1ffe-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="e1ffe-105">Methods</span></span>  
  
|<span data-ttu-id="e1ffe-106">Método</span><span class="sxs-lookup"><span data-stu-id="e1ffe-106">Method</span></span>|<span data-ttu-id="e1ffe-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1ffe-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e1ffe-108">Método DebugEvent</span><span class="sxs-lookup"><span data-stu-id="e1ffe-108">DebugEvent Method</span></span>](icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="e1ffe-109">Notifica al depurador que se ha desencadenado un evento nativo.</span><span class="sxs-lookup"><span data-stu-id="e1ffe-109">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1ffe-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e1ffe-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e1ffe-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="e1ffe-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1ffe-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e1ffe-112">Requirements</span></span>  

 <span data-ttu-id="e1ffe-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1ffe-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1ffe-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1ffe-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1ffe-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1ffe-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1ffe-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1ffe-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1ffe-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1ffe-117">See also</span></span>

- [<span data-ttu-id="e1ffe-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="e1ffe-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
