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
ms.openlocfilehash: 3a771100ad4d63173fdb3b1ddea5ae3d67fbbc7c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960672"
---
# <a name="icordebugcodeenum-interface"></a><span data-ttu-id="2879b-102">Interfaz ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="2879b-102">ICorDebugCodeEnum Interface</span></span>

<span data-ttu-id="2879b-103">Implementa los métodos "ICorDebugEnum" y enumera las matrices "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="2879b-103">Implements "ICorDebugEnum" methods, and enumerates "ICorDebugCode" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2879b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="2879b-104">Methods</span></span>  
  
|<span data-ttu-id="2879b-105">Método</span><span class="sxs-lookup"><span data-stu-id="2879b-105">Method</span></span>|<span data-ttu-id="2879b-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2879b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2879b-107">Next (método)</span><span class="sxs-lookup"><span data-stu-id="2879b-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcodeenum-next-method.md)|<span data-ttu-id="2879b-108">Obtiene el número especificado de `ICorDebugCode` instancias de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="2879b-108">Gets the specified number of `ICorDebugCode` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2879b-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2879b-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2879b-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="2879b-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2879b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2879b-111">Requirements</span></span>  
 <span data-ttu-id="2879b-112">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2879b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2879b-113">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="2879b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2879b-114">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2879b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2879b-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2879b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2879b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="2879b-116">See also</span></span>

- [<span data-ttu-id="2879b-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="2879b-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
