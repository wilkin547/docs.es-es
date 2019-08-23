---
title: Interfaz ICorDebugBreakpointEnum
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpointEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpointEnum
helpviewer_keywords:
- ICorDebugBreakpointEnum interface [.NET Framework debugging]
ms.assetid: 4c6f4f6e-52cc-402e-881b-7b8526544c90
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e8192bd7ccaebab78158f11adb79509031132ecd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937015"
---
# <a name="icordebugbreakpointenum-interface"></a><span data-ttu-id="da5fd-102">Interfaz ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="da5fd-102">ICorDebugBreakpointEnum Interface</span></span>

<span data-ttu-id="da5fd-103">Implementa los métodos de ICorDebugEnum y enumera las matrices de ICorDebugBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="da5fd-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="da5fd-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="da5fd-104">Methods</span></span>  
  
|<span data-ttu-id="da5fd-105">Método</span><span class="sxs-lookup"><span data-stu-id="da5fd-105">Method</span></span>|<span data-ttu-id="da5fd-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="da5fd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="da5fd-107">Next (método)</span><span class="sxs-lookup"><span data-stu-id="da5fd-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-next-method.md)|<span data-ttu-id="da5fd-108">Obtiene el número especificado de `ICorDebugBreakpoint` instancias de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="da5fd-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da5fd-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="da5fd-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="da5fd-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="da5fd-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da5fd-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="da5fd-111">Requirements</span></span>  
 <span data-ttu-id="da5fd-112">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da5fd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da5fd-113">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="da5fd-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da5fd-114">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da5fd-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da5fd-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da5fd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da5fd-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="da5fd-116">See also</span></span>

- [<span data-ttu-id="da5fd-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="da5fd-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
