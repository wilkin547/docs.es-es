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
ms.openlocfilehash: 31f26a40294857701b151cd2fce35b061da28238
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732533"
---
# <a name="icordebugprocessenum-interface"></a><span data-ttu-id="41eac-102">Interfaz ICorDebugProcessEnum</span><span class="sxs-lookup"><span data-stu-id="41eac-102">ICorDebugProcessEnum Interface</span></span>

<span data-ttu-id="41eac-103">Implementa los métodos ICorDebugEnum y enumera las matrices ICorDebugProcess.</span><span class="sxs-lookup"><span data-stu-id="41eac-103">Implements ICorDebugEnum methods and enumerates ICorDebugProcess arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="41eac-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="41eac-104">Methods</span></span>  
  
|<span data-ttu-id="41eac-105">Método</span><span class="sxs-lookup"><span data-stu-id="41eac-105">Method</span></span>|<span data-ttu-id="41eac-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="41eac-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="41eac-107">Next (Método)</span><span class="sxs-lookup"><span data-stu-id="41eac-107">Next Method</span></span>](icordebugprocessenum-next-method.md)|<span data-ttu-id="41eac-108">Obtiene el número especificado de `ICorDebugProcess` instancias de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="41eac-108">Gets the specified number of `ICorDebugProcess` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41eac-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="41eac-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="41eac-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="41eac-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41eac-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="41eac-111">Requirements</span></span>  

 <span data-ttu-id="41eac-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41eac-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41eac-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41eac-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41eac-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41eac-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41eac-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41eac-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41eac-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="41eac-116">See also</span></span>

- [<span data-ttu-id="41eac-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="41eac-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
