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
ms.openlocfilehash: 3a820381f1c4605d620d74a5915c3e08de69d9fb
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210129"
---
# <a name="icordebugprocessenum-interface"></a><span data-ttu-id="f96c6-102">Interfaz ICorDebugProcessEnum</span><span class="sxs-lookup"><span data-stu-id="f96c6-102">ICorDebugProcessEnum Interface</span></span>
<span data-ttu-id="f96c6-103">Implementa los métodos ICorDebugEnum y enumera las matrices ICorDebugProcess.</span><span class="sxs-lookup"><span data-stu-id="f96c6-103">Implements ICorDebugEnum methods and enumerates ICorDebugProcess arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f96c6-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f96c6-104">Methods</span></span>  
  
|<span data-ttu-id="f96c6-105">Método</span><span class="sxs-lookup"><span data-stu-id="f96c6-105">Method</span></span>|<span data-ttu-id="f96c6-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f96c6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f96c6-107">Next (Método)</span><span class="sxs-lookup"><span data-stu-id="f96c6-107">Next Method</span></span>](icordebugprocessenum-next-method.md)|<span data-ttu-id="f96c6-108">Obtiene el número especificado de `ICorDebugProcess` instancias de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="f96c6-108">Gets the specified number of `ICorDebugProcess` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f96c6-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f96c6-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f96c6-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="f96c6-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f96c6-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f96c6-111">Requirements</span></span>  
 <span data-ttu-id="f96c6-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f96c6-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f96c6-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f96c6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f96c6-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f96c6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f96c6-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f96c6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f96c6-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f96c6-116">See also</span></span>

- [<span data-ttu-id="f96c6-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f96c6-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
