---
title: Interfaz ICorDebugValueEnum
ms.date: 03/30/2017
api_name:
- ICorDebugValueEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueEnum
helpviewer_keywords:
- ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: 88989482-a09f-4bd0-9adb-16f47b0291fd
topic_type:
- apiref
ms.openlocfilehash: e3934cbce76df3997fa07d8fa3a99bd8ddab09a2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684348"
---
# <a name="icordebugvalueenum-interface"></a><span data-ttu-id="e1e34-102">Interfaz ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="e1e34-102">ICorDebugValueEnum Interface</span></span>

<span data-ttu-id="e1e34-103">Implementa los métodos "ICorDebugEnum" y enumera las matrices "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="e1e34-103">Implements "ICorDebugEnum" methods and enumerates "ICorDebugValue" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e1e34-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e1e34-104">Methods</span></span>  
  
|<span data-ttu-id="e1e34-105">Método</span><span class="sxs-lookup"><span data-stu-id="e1e34-105">Method</span></span>|<span data-ttu-id="e1e34-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1e34-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e1e34-107">Next (Método)</span><span class="sxs-lookup"><span data-stu-id="e1e34-107">Next Method</span></span>](icordebugvalueenum-next-method.md)|<span data-ttu-id="e1e34-108">Obtiene el número especificado de `ICorDebugValue` instancias de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="e1e34-108">Gets the specified number of `ICorDebugValue` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1e34-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e1e34-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e1e34-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="e1e34-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1e34-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e1e34-111">Requirements</span></span>  

 <span data-ttu-id="e1e34-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1e34-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1e34-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1e34-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1e34-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1e34-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1e34-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1e34-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1e34-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e1e34-116">See also</span></span>

- [<span data-ttu-id="e1e34-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="e1e34-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
