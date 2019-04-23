---
title: Interfaz ICorDebugModuleEnum
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum
helpviewer_keywords:
- ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 2fb93cd6-6d47-4fdc-a9a0-047726fd03a1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 26efb3e43642b6d1fd10b084c2b321609c89d89b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59146515"
---
# <a name="icordebugmoduleenum-interface"></a><span data-ttu-id="f3e15-102">Interfaz ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="f3e15-102">ICorDebugModuleEnum Interface</span></span>

<span data-ttu-id="f3e15-103">Implementa los métodos ICorDebugEnum y enumera las matrices ICorDebugModule.</span><span class="sxs-lookup"><span data-stu-id="f3e15-103">Implements ICorDebugEnum methods, and enumerates ICorDebugModule arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f3e15-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f3e15-104">Methods</span></span>  
  
|<span data-ttu-id="f3e15-105">Método</span><span class="sxs-lookup"><span data-stu-id="f3e15-105">Method</span></span>|<span data-ttu-id="f3e15-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3e15-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f3e15-107">Next (método)</span><span class="sxs-lookup"><span data-stu-id="f3e15-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduleenum-next-method.md)|<span data-ttu-id="f3e15-108">Obtiene el número especificado de `ICorDebugModule` instancias de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="f3e15-108">Gets the specified number of `ICorDebugModule` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3e15-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f3e15-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3e15-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="f3e15-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3e15-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f3e15-111">Requirements</span></span>  
 <span data-ttu-id="f3e15-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3e15-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3e15-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3e15-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3e15-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3e15-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3e15-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3e15-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3e15-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3e15-116">See also</span></span>

- [<span data-ttu-id="f3e15-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f3e15-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
