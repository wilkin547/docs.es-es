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
ms.openlocfilehash: 05900f55885f8f3a4c470d6842c42d0fc3e0171e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957454"
---
# <a name="icordebugprocess3-interface"></a><span data-ttu-id="64028-102">ICorDebugProcess3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="64028-102">ICorDebugProcess3 Interface</span></span>
<span data-ttu-id="64028-103">Controla las notificaciones del depurador personalizadas.</span><span class="sxs-lookup"><span data-stu-id="64028-103">Controls custom debugger notifications.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="64028-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="64028-104">Methods</span></span>  
  
|<span data-ttu-id="64028-105">Método</span><span class="sxs-lookup"><span data-stu-id="64028-105">Method</span></span>|<span data-ttu-id="64028-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="64028-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="64028-107">SetEnableCustomNotification (método)</span><span class="sxs-lookup"><span data-stu-id="64028-107">SetEnableCustomNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md)|<span data-ttu-id="64028-108">Habilita y deshabilita las notificaciones del depurador personalizado del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="64028-108">Enables and disables custom debugger notifications of the specified type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64028-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="64028-109">Remarks</span></span>  
 <span data-ttu-id="64028-110">Esta interfaz extiende lógicamente las interfaces ICorDebugProcess e ICorDebugProcess2.</span><span class="sxs-lookup"><span data-stu-id="64028-110">This interface logically extends the ICorDebugProcess and ICorDebugProcess2 interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="64028-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="64028-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64028-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="64028-112">Requirements</span></span>  
 <span data-ttu-id="64028-113">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64028-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64028-114">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="64028-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="64028-115">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64028-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64028-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64028-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64028-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="64028-117">See also</span></span>

- [<span data-ttu-id="64028-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="64028-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="64028-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="64028-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
