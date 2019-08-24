---
title: Interfaz ICorDebugAssemblyEnum
ms.date: 03/30/2017
api_name:
- ICorDebugAssemblyEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssemblyEnum
helpviewer_keywords:
- ICorDebugAssemblyEnum interface [.NET Framework debugging]
ms.assetid: 891ceb43-5161-421e-a0bf-299962fd7efd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c557df3c69b9d18b95ebf33815b92dcb9097f4e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69987538"
---
# <a name="icordebugassemblyenum-interface"></a><span data-ttu-id="145cc-102">Interfaz ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="145cc-102">ICorDebugAssemblyEnum Interface</span></span>

<span data-ttu-id="145cc-103">Implementa los métodos ICorDebugEnum y enumera las matrices ICorDebugAssembly.</span><span class="sxs-lookup"><span data-stu-id="145cc-103">Implements ICorDebugEnum methods and enumerates ICorDebugAssembly arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="145cc-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="145cc-104">Methods</span></span>  
  
|<span data-ttu-id="145cc-105">Método</span><span class="sxs-lookup"><span data-stu-id="145cc-105">Method</span></span>|<span data-ttu-id="145cc-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="145cc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="145cc-107">Next (método)</span><span class="sxs-lookup"><span data-stu-id="145cc-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassemblyenum-next-method.md)|<span data-ttu-id="145cc-108">Obtiene el número especificado de `ICorDebugAssembly` instancias en la enumeración, a partir de la posición actual.</span><span class="sxs-lookup"><span data-stu-id="145cc-108">Gets the specified number of `ICorDebugAssembly` instances in the enumeration, starting from the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="145cc-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="145cc-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="145cc-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="145cc-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="145cc-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="145cc-111">Requirements</span></span>  
 <span data-ttu-id="145cc-112">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="145cc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="145cc-113">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="145cc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="145cc-114">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="145cc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="145cc-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="145cc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="145cc-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="145cc-116">See also</span></span>

- [<span data-ttu-id="145cc-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="145cc-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
