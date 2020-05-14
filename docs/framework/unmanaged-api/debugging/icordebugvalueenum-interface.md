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
ms.openlocfilehash: 5f95202bd0c8c5045c10378068ae83cad3d93fdd
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396467"
---
# <a name="icordebugvalueenum-interface"></a><span data-ttu-id="a2fbf-102">Interfaz ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="a2fbf-102">ICorDebugValueEnum Interface</span></span>
<span data-ttu-id="a2fbf-103">Implementa los métodos "ICorDebugEnum" y enumera las matrices "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="a2fbf-103">Implements "ICorDebugEnum" methods and enumerates "ICorDebugValue" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a2fbf-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a2fbf-104">Methods</span></span>  
  
|<span data-ttu-id="a2fbf-105">Método</span><span class="sxs-lookup"><span data-stu-id="a2fbf-105">Method</span></span>|<span data-ttu-id="a2fbf-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a2fbf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a2fbf-107">Next (Método)</span><span class="sxs-lookup"><span data-stu-id="a2fbf-107">Next Method</span></span>](icordebugvalueenum-next-method.md)|<span data-ttu-id="a2fbf-108">Obtiene el número especificado de `ICorDebugValue` instancias de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="a2fbf-108">Gets the specified number of `ICorDebugValue` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2fbf-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a2fbf-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a2fbf-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="a2fbf-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2fbf-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a2fbf-111">Requirements</span></span>  
 <span data-ttu-id="a2fbf-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2fbf-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2fbf-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2fbf-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2fbf-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2fbf-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2fbf-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2fbf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2fbf-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2fbf-116">See also</span></span>

- [<span data-ttu-id="a2fbf-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a2fbf-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
