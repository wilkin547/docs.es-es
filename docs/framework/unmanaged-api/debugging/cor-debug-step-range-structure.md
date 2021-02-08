---
description: 'Más información acerca de: estructura de COR_DEBUG_STEP_RANGE'
title: COR_DEBUG_STEP_RANGE (Estructura)
ms.date: 03/30/2017
api_name:
- COR_DEBUG_STEP_RANGE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_DEBUG_STEP_RANGE
helpviewer_keywords:
- COR_DEBUG_STEP_RANGE structure [.NET Framework debugging]
ms.assetid: 8809d00e-beaa-4dcf-b4e8-e89d0a5406b7
topic_type:
- apiref
ms.openlocfilehash: 40462be4b165351b3265fa0833d19f18e0fa3a37
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801844"
---
# <a name="cor_debug_step_range-structure"></a><span data-ttu-id="40bd5-103">COR_DEBUG_STEP_RANGE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="40bd5-103">COR_DEBUG_STEP_RANGE Structure</span></span>

<span data-ttu-id="40bd5-104">Contiene información de desplazamiento para un intervalo de código.</span><span class="sxs-lookup"><span data-stu-id="40bd5-104">Contains the offset information for a range of code.</span></span>  
  
 <span data-ttu-id="40bd5-105">Esta estructura la usa el método [ICorDebugStepper:: steprange (](icordebugstepper-steprange-method.md) .</span><span class="sxs-lookup"><span data-stu-id="40bd5-105">This structure is used by the [ICorDebugStepper::StepRange](icordebugstepper-steprange-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40bd5-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40bd5-106">Syntax</span></span>  
  
```cpp  
typedef struct {  
    ULONG32 startOffset;  
    ULONG32 endOffset;  
} COR_DEBUG_STEP_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="40bd5-107">Members</span><span class="sxs-lookup"><span data-stu-id="40bd5-107">Members</span></span>  
  
|<span data-ttu-id="40bd5-108">Miembro</span><span class="sxs-lookup"><span data-stu-id="40bd5-108">Member</span></span>|<span data-ttu-id="40bd5-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="40bd5-109">Description</span></span>|  
|------------|-----------------|  
|`startOffset`|<span data-ttu-id="40bd5-110">Desplazamiento del principio del intervalo.</span><span class="sxs-lookup"><span data-stu-id="40bd5-110">The offset of the beginning of the range.</span></span>|  
|`endOffset`|<span data-ttu-id="40bd5-111">Desplazamiento del final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="40bd5-111">The offset of the end of the range.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="40bd5-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="40bd5-112">Requirements</span></span>  

 <span data-ttu-id="40bd5-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40bd5-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40bd5-114">**Encabezado:** Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="40bd5-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="40bd5-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40bd5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40bd5-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40bd5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40bd5-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="40bd5-117">See also</span></span>

- [<span data-ttu-id="40bd5-118">Método StepRange</span><span class="sxs-lookup"><span data-stu-id="40bd5-118">StepRange Method</span></span>](icordebugstepper-steprange-method.md)
- [<span data-ttu-id="40bd5-119">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="40bd5-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="40bd5-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="40bd5-120">Debugging</span></span>](index.md)
