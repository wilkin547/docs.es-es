---
title: Interfaz ICorDebugCodeEnum
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum
helpviewer_keywords:
- ICorDebugCodeEnum interface [.NET Framework debugging]
ms.assetid: b5589171-a4a0-4c00-bbdc-6e0a42233b75
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f36ce2fbf57c72102550069989c94b5cc19e58c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186659"
---
# <a name="icordebugcodeenum-interface"></a><span data-ttu-id="e32f2-102">Interfaz ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="e32f2-102">ICorDebugCodeEnum Interface</span></span>

<span data-ttu-id="e32f2-103">Implementa los métodos "ICorDebugEnum" y enumera las matrices de "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="e32f2-103">Implements "ICorDebugEnum" methods, and enumerates "ICorDebugCode" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e32f2-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e32f2-104">Methods</span></span>  
  
|<span data-ttu-id="e32f2-105">Método</span><span class="sxs-lookup"><span data-stu-id="e32f2-105">Method</span></span>|<span data-ttu-id="e32f2-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e32f2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e32f2-107">Next (método)</span><span class="sxs-lookup"><span data-stu-id="e32f2-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcodeenum-next-method.md)|<span data-ttu-id="e32f2-108">Obtiene el número especificado de `ICorDebugCode` instancias de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="e32f2-108">Gets the specified number of `ICorDebugCode` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e32f2-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e32f2-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e32f2-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="e32f2-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e32f2-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e32f2-111">Requirements</span></span>  
 <span data-ttu-id="e32f2-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e32f2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e32f2-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e32f2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e32f2-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e32f2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e32f2-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e32f2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e32f2-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e32f2-116">See also</span></span>

- [<span data-ttu-id="e32f2-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="e32f2-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
