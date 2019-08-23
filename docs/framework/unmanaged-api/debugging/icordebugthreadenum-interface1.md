---
title: Interfaz ICorDebugThreadEnum
ms.date: 03/30/2017
api_name:
- ICorDebugThreadEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum
helpviewer_keywords:
- ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: 796de687-7dd4-4b7b-a10b-8bf22dc7779f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b7e5b0a9f4166923a559eb3886aa0f9cabbcd72
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962945"
---
# <a name="icordebugthreadenum-interface"></a><span data-ttu-id="6c927-102">Interfaz ICorDebugThreadEnum</span><span class="sxs-lookup"><span data-stu-id="6c927-102">ICorDebugThreadEnum Interface</span></span>
<span data-ttu-id="6c927-103">Implementa los métodos ICorDebugEnum y enumera las matrices ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="6c927-103">Implements ICorDebugEnum methods and enumerates ICorDebugThread arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6c927-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="6c927-104">Methods</span></span>  
  
|<span data-ttu-id="6c927-105">Método</span><span class="sxs-lookup"><span data-stu-id="6c927-105">Method</span></span>|<span data-ttu-id="6c927-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6c927-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6c927-107">Next (método)</span><span class="sxs-lookup"><span data-stu-id="6c927-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-next-method.md)|<span data-ttu-id="6c927-108">Obtiene el número especificado de `ICorDebugThread` instancias de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="6c927-108">Gets the specified number of `ICorDebugThread` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c927-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6c927-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6c927-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="6c927-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c927-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6c927-111">Requirements</span></span>  
 <span data-ttu-id="6c927-112">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c927-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c927-113">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="6c927-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6c927-114">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c927-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c927-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c927-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c927-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c927-116">See also</span></span>

- [<span data-ttu-id="6c927-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="6c927-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
