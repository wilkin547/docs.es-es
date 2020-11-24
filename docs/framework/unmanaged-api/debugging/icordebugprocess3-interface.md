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
ms.openlocfilehash: ef8dbd5253c02355f85fba626fa7e68ed62df4bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686462"
---
# <a name="icordebugprocess3-interface"></a><span data-ttu-id="cc920-102">ICorDebugProcess3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cc920-102">ICorDebugProcess3 Interface</span></span>

<span data-ttu-id="cc920-103">Controla las notificaciones del depurador personalizadas.</span><span class="sxs-lookup"><span data-stu-id="cc920-103">Controls custom debugger notifications.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cc920-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="cc920-104">Methods</span></span>  
  
|<span data-ttu-id="cc920-105">Método</span><span class="sxs-lookup"><span data-stu-id="cc920-105">Method</span></span>|<span data-ttu-id="cc920-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc920-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cc920-107">Método SetEnableCustomNotification</span><span class="sxs-lookup"><span data-stu-id="cc920-107">SetEnableCustomNotification Method</span></span>](icordebugprocess3-setenablecustomnotification-method.md)|<span data-ttu-id="cc920-108">Habilita y deshabilita las notificaciones del depurador personalizado del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="cc920-108">Enables and disables custom debugger notifications of the specified type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc920-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cc920-109">Remarks</span></span>  

 <span data-ttu-id="cc920-110">Esta interfaz extiende lógicamente las interfaces ICorDebugProcess e ICorDebugProcess2.</span><span class="sxs-lookup"><span data-stu-id="cc920-110">This interface logically extends the ICorDebugProcess and ICorDebugProcess2 interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cc920-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="cc920-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc920-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cc920-112">Requirements</span></span>  

 <span data-ttu-id="cc920-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc920-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc920-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc920-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc920-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc920-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc920-116">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc920-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc920-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cc920-117">See also</span></span>

- [<span data-ttu-id="cc920-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="cc920-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="cc920-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="cc920-119">Debugging</span></span>](index.md)
