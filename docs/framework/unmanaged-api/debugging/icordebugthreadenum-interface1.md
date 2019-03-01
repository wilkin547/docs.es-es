---
title: ICorDebugThreadEnum (Interfaz)
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
ms.openlocfilehash: b620357967d5d22148f64a3258fbb8dc52361d86
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981730"
---
# <a name="icordebugthreadenum-interface"></a><span data-ttu-id="727d3-102">ICorDebugThreadEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="727d3-102">ICorDebugThreadEnum Interface</span></span>
<span data-ttu-id="727d3-103">Implementa métodos ICorDebugEnum y enumera las matrices de ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="727d3-103">Implements ICorDebugEnum methods and enumerates ICorDebugThread arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="727d3-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="727d3-104">Methods</span></span>  
  
|<span data-ttu-id="727d3-105">Método</span><span class="sxs-lookup"><span data-stu-id="727d3-105">Method</span></span>|<span data-ttu-id="727d3-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="727d3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="727d3-107">Next (método)</span><span class="sxs-lookup"><span data-stu-id="727d3-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-next-method.md)|<span data-ttu-id="727d3-108">Obtiene el número especificado de `ICorDebugThread` instancias de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="727d3-108">Gets the specified number of `ICorDebugThread` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="727d3-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="727d3-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="727d3-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="727d3-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="727d3-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="727d3-111">Requirements</span></span>  
 <span data-ttu-id="727d3-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="727d3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="727d3-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="727d3-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="727d3-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="727d3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="727d3-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="727d3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="727d3-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="727d3-116">See also</span></span>
- [<span data-ttu-id="727d3-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="727d3-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
