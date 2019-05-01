---
title: Interfaz ICorDebugFrameEnum
ms.date: 03/30/2017
api_name:
- ICorDebugFrameEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrameEnum
helpviewer_keywords:
- ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: ee3f85d3-044e-46b8-945c-93ebfa5d9e91
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd24dfa6771ca450e79b4b932735968ecc51fc90
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995792"
---
# <a name="icordebugframeenum-interface"></a><span data-ttu-id="69327-102">Interfaz ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="69327-102">ICorDebugFrameEnum Interface</span></span>

<span data-ttu-id="69327-103">Implementa los métodos ICorDebugEnum y enumera las matrices ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="69327-103">Implements ICorDebugEnum methods, and enumerates ICorDebugFrame arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="69327-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="69327-104">Methods</span></span>  
  
|<span data-ttu-id="69327-105">Método</span><span class="sxs-lookup"><span data-stu-id="69327-105">Method</span></span>|<span data-ttu-id="69327-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="69327-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="69327-107">Next (método)</span><span class="sxs-lookup"><span data-stu-id="69327-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframeenum-next-method.md)|<span data-ttu-id="69327-108">Obtiene el número especificado de `ICorDebugFrame` instancias de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="69327-108">Gets the specified number of `ICorDebugFrame` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69327-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="69327-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69327-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="69327-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69327-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="69327-111">Requirements</span></span>  
 <span data-ttu-id="69327-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69327-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69327-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69327-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69327-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69327-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69327-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69327-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69327-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="69327-116">See also</span></span>

- [<span data-ttu-id="69327-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="69327-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
