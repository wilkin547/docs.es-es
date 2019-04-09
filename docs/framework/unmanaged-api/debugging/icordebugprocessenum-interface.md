---
title: Interfaz ICorDebugProcessEnum
ms.date: 03/30/2017
api_name:
- ICorDebugProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcessEnum
helpviewer_keywords:
- ICorDebugProcessEnum interface [.NET Framework debugging]
ms.assetid: b63a507a-ca97-4be0-8e4f-401cce2125f6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3651a4be94fa624d0dd6ab64b8c3f8169945de0d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175323"
---
# <a name="icordebugprocessenum-interface"></a><span data-ttu-id="baf16-102">Interfaz ICorDebugProcessEnum</span><span class="sxs-lookup"><span data-stu-id="baf16-102">ICorDebugProcessEnum Interface</span></span>
<span data-ttu-id="baf16-103">Implementa métodos ICorDebugEnum y enumera las matrices de ICorDebugProcess.</span><span class="sxs-lookup"><span data-stu-id="baf16-103">Implements ICorDebugEnum methods and enumerates ICorDebugProcess arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="baf16-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="baf16-104">Methods</span></span>  
  
|<span data-ttu-id="baf16-105">Método</span><span class="sxs-lookup"><span data-stu-id="baf16-105">Method</span></span>|<span data-ttu-id="baf16-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="baf16-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="baf16-107">Método Next</span><span class="sxs-lookup"><span data-stu-id="baf16-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocessenum-next-method.md)|<span data-ttu-id="baf16-108">Obtiene el número especificado de `ICorDebugProcess` instancias de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="baf16-108">Gets the specified number of `ICorDebugProcess` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="baf16-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="baf16-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="baf16-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="baf16-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="baf16-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="baf16-111">Requirements</span></span>  
 <span data-ttu-id="baf16-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="baf16-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="baf16-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="baf16-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="baf16-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="baf16-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="baf16-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="baf16-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="baf16-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="baf16-116">See also</span></span>

- [<span data-ttu-id="baf16-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="baf16-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
