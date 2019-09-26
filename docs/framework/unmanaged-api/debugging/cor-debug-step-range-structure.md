---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 11d5e2eb5e2743fca4876ed09add79be3eba514f
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274203"
---
# <a name="cor_debug_step_range-structure"></a><span data-ttu-id="bd33b-102">COR_DEBUG_STEP_RANGE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="bd33b-102">COR_DEBUG_STEP_RANGE Structure</span></span>
<span data-ttu-id="bd33b-103">Contiene información de desplazamiento para un intervalo de código.</span><span class="sxs-lookup"><span data-stu-id="bd33b-103">Contains the offset information for a range of code.</span></span>  
  
 <span data-ttu-id="bd33b-104">Esta estructura la usa el método [ICorDebugStepper:: steprange (](icordebugstepper-steprange-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bd33b-104">This structure is used by the [ICorDebugStepper::StepRange](icordebugstepper-steprange-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd33b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd33b-105">Syntax</span></span>  
  
```cpp  
typedef struct {  
    ULONG32 startOffset;  
    ULONG32 endOffset;  
} COR_DEBUG_STEP_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="bd33b-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="bd33b-106">Members</span></span>  
  
|<span data-ttu-id="bd33b-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="bd33b-107">Member</span></span>|<span data-ttu-id="bd33b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="bd33b-108">Description</span></span>|  
|------------|-----------------|  
|`startOffset`|<span data-ttu-id="bd33b-109">Desplazamiento del principio del intervalo.</span><span class="sxs-lookup"><span data-stu-id="bd33b-109">The offset of the beginning of the range.</span></span>|  
|`endOffset`|<span data-ttu-id="bd33b-110">Desplazamiento del final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="bd33b-110">The offset of the end of the range.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bd33b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bd33b-111">Requirements</span></span>  
 <span data-ttu-id="bd33b-112">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd33b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd33b-113">**Encabezado**: CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="bd33b-113">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="bd33b-114">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd33b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd33b-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd33b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd33b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd33b-116">See also</span></span>

- [<span data-ttu-id="bd33b-117">StepRange (método)</span><span class="sxs-lookup"><span data-stu-id="bd33b-117">StepRange Method</span></span>](icordebugstepper-steprange-method.md)
- [<span data-ttu-id="bd33b-118">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="bd33b-118">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="bd33b-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="bd33b-119">Debugging</span></span>](index.md)
