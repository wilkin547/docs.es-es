---
title: ICorDebugProcess3 (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugProcess3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3
helpviewer_keywords:
- ICorDebugProcess3 interface [.NET Framework debugging]
ms.assetid: ced9c82e-d7b0-4806-a151-98b6611d3097
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 894d3295b83a1971792e6da845f276be486a4ea5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess3-interface"></a><span data-ttu-id="5c353-102">ICorDebugProcess3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5c353-102">ICorDebugProcess3 Interface</span></span>
<span data-ttu-id="5c353-103">Controla las notificaciones del depurador personalizadas.</span><span class="sxs-lookup"><span data-stu-id="5c353-103">Controls custom debugger notifications.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5c353-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="5c353-104">Methods</span></span>  
  
|<span data-ttu-id="5c353-105">Método</span><span class="sxs-lookup"><span data-stu-id="5c353-105">Method</span></span>|<span data-ttu-id="5c353-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c353-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5c353-107">SetEnableCustomNotification (método)</span><span class="sxs-lookup"><span data-stu-id="5c353-107">SetEnableCustomNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md)|<span data-ttu-id="5c353-108">Habilita y deshabilita notificaciones del depurador personalizadas del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="5c353-108">Enables and disables custom debugger notifications of the specified type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c353-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5c353-109">Remarks</span></span>  
 <span data-ttu-id="5c353-110">Esta interfaz extiende lógicamente las interfaces ICorDebugProcess y ICorDebugProcess2.</span><span class="sxs-lookup"><span data-stu-id="5c353-110">This interface logically extends the ICorDebugProcess and ICorDebugProcess2 interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c353-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="5c353-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c353-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c353-112">Requirements</span></span>  
 <span data-ttu-id="5c353-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c353-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c353-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c353-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c353-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c353-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c353-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c353-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c353-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c353-117">See Also</span></span>  
 [<span data-ttu-id="5c353-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="5c353-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="5c353-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="5c353-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
