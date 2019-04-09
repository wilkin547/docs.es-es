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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093831"
---
# <a name="icordebugframeenum-interface"></a><span data-ttu-id="582fc-102">Interfaz ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="582fc-102">ICorDebugFrameEnum Interface</span></span>

<span data-ttu-id="582fc-103">Implementa los métodos ICorDebugEnum y enumera las matrices ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="582fc-103">Implements ICorDebugEnum methods, and enumerates ICorDebugFrame arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="582fc-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="582fc-104">Methods</span></span>  
  
|<span data-ttu-id="582fc-105">Método</span><span class="sxs-lookup"><span data-stu-id="582fc-105">Method</span></span>|<span data-ttu-id="582fc-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="582fc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="582fc-107">Método Next</span><span class="sxs-lookup"><span data-stu-id="582fc-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframeenum-next-method.md)|<span data-ttu-id="582fc-108">Obtiene el número especificado de `ICorDebugFrame` instancias de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="582fc-108">Gets the specified number of `ICorDebugFrame` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="582fc-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="582fc-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="582fc-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="582fc-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="582fc-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="582fc-111">Requirements</span></span>  
 <span data-ttu-id="582fc-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="582fc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="582fc-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="582fc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="582fc-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="582fc-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="582fc-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="582fc-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="582fc-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="582fc-116">See also</span></span>

- [<span data-ttu-id="582fc-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="582fc-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
