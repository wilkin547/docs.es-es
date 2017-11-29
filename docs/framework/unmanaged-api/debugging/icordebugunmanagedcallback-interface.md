---
title: ICorDebugUnmanagedCallback (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugUnmanagedCallback
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugUnmanagedCallback
helpviewer_keywords: ICorDebugUnmanagedCallback interface [.NET Framework debugging]
ms.assetid: bc71cbca-7d73-40e5-84dd-2109fade3c2a
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: aa104bee5171b3b28731cf18a4d26e32f49169ed
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="74075-102">ICorDebugUnmanagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="74075-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="74075-103">Proporciona notificación de eventos nativos que no están directamente relacionadas con common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="74075-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="74075-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="74075-104">Methods</span></span>  
  
|<span data-ttu-id="74075-105">Método</span><span class="sxs-lookup"><span data-stu-id="74075-105">Method</span></span>|<span data-ttu-id="74075-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="74075-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="74075-107">DebugEvent (método)</span><span class="sxs-lookup"><span data-stu-id="74075-107">DebugEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="74075-108">Notifica al depurador que se ha desencadenado un evento nativo.</span><span class="sxs-lookup"><span data-stu-id="74075-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74075-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="74075-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="74075-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="74075-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74075-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74075-111">Requirements</span></span>  
 <span data-ttu-id="74075-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74075-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74075-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="74075-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74075-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74075-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74075-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74075-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74075-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="74075-116">See Also</span></span>  
 [<span data-ttu-id="74075-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="74075-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
