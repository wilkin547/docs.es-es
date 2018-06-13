---
title: ICorDebugProcess3 (Interfaz)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95c2218aadd62902ff9bc7f2e6a190aa2ce241ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418852"
---
# <a name="icordebugprocess3-interface"></a><span data-ttu-id="f53e6-102">ICorDebugProcess3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f53e6-102">ICorDebugProcess3 Interface</span></span>
<span data-ttu-id="f53e6-103">Controla las notificaciones del depurador personalizadas.</span><span class="sxs-lookup"><span data-stu-id="f53e6-103">Controls custom debugger notifications.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f53e6-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f53e6-104">Methods</span></span>  
  
|<span data-ttu-id="f53e6-105">Método</span><span class="sxs-lookup"><span data-stu-id="f53e6-105">Method</span></span>|<span data-ttu-id="f53e6-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f53e6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f53e6-107">SetEnableCustomNotification (método)</span><span class="sxs-lookup"><span data-stu-id="f53e6-107">SetEnableCustomNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md)|<span data-ttu-id="f53e6-108">Habilita y deshabilita notificaciones del depurador personalizadas del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="f53e6-108">Enables and disables custom debugger notifications of the specified type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f53e6-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f53e6-109">Remarks</span></span>  
 <span data-ttu-id="f53e6-110">Esta interfaz extiende lógicamente las interfaces ICorDebugProcess y ICorDebugProcess2.</span><span class="sxs-lookup"><span data-stu-id="f53e6-110">This interface logically extends the ICorDebugProcess and ICorDebugProcess2 interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f53e6-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="f53e6-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f53e6-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f53e6-112">Requirements</span></span>  
 <span data-ttu-id="f53e6-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f53e6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f53e6-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f53e6-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f53e6-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f53e6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f53e6-116">**Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f53e6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f53e6-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f53e6-117">See Also</span></span>  
 [<span data-ttu-id="f53e6-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f53e6-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="f53e6-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="f53e6-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
