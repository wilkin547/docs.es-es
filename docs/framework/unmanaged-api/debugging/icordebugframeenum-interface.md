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
ms.openlocfilehash: 4277a552d217ad7f601bfe72cae32a1f25dd6be4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696237"
---
# <a name="icordebugframeenum-interface"></a><span data-ttu-id="33c5c-102">Interfaz ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="33c5c-102">ICorDebugFrameEnum Interface</span></span>

<span data-ttu-id="33c5c-103">Implementa los métodos ICorDebugEnum y enumera las matrices ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="33c5c-103">Implements ICorDebugEnum methods, and enumerates ICorDebugFrame arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="33c5c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="33c5c-104">Methods</span></span>  
  
|<span data-ttu-id="33c5c-105">Método</span><span class="sxs-lookup"><span data-stu-id="33c5c-105">Method</span></span>|<span data-ttu-id="33c5c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="33c5c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="33c5c-107">Next (Método)</span><span class="sxs-lookup"><span data-stu-id="33c5c-107">Next Method</span></span>](icordebugframeenum-next-method.md)|<span data-ttu-id="33c5c-108">Obtiene el número especificado de `ICorDebugFrame` instancias de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="33c5c-108">Gets the specified number of `ICorDebugFrame` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33c5c-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="33c5c-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="33c5c-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="33c5c-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33c5c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33c5c-111">Requirements</span></span>  

 <span data-ttu-id="33c5c-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33c5c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33c5c-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="33c5c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33c5c-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33c5c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33c5c-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33c5c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33c5c-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="33c5c-116">See also</span></span>

- [<span data-ttu-id="33c5c-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="33c5c-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
