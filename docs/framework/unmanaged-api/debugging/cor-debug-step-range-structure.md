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
ms.openlocfilehash: d5809221f2f31bc725c6a62fa5f8f91822f1c157
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407245"
---
# <a name="cordebugsteprange-structure"></a><span data-ttu-id="e9811-102">COR_DEBUG_STEP_RANGE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="e9811-102">COR_DEBUG_STEP_RANGE Structure</span></span>
<span data-ttu-id="e9811-103">Contiene información de desplazamiento para un intervalo de código.</span><span class="sxs-lookup"><span data-stu-id="e9811-103">Contains the offset information for a range of code.</span></span>  
  
 <span data-ttu-id="e9811-104">Esta estructura se usa por la [ICorDebugStepper:: StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="e9811-104">This structure is used by the [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9811-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9811-105">Syntax</span></span>  
  
```  
typedef struct {  
    ULONG32 startOffset;  
    ULONG32 endOffset;  
} COR_DEBUG_STEP_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="e9811-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="e9811-106">Members</span></span>  
  
|<span data-ttu-id="e9811-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="e9811-107">Member</span></span>|<span data-ttu-id="e9811-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e9811-108">Description</span></span>|  
|------------|-----------------|  
|`startOffset`|<span data-ttu-id="e9811-109">El desplazamiento del principio del intervalo.</span><span class="sxs-lookup"><span data-stu-id="e9811-109">The offset of the beginning of the range.</span></span>|  
|`endOffset`|<span data-ttu-id="e9811-110">El desplazamiento del final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="e9811-110">The offset of the end of the range.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e9811-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9811-111">Requirements</span></span>  
 <span data-ttu-id="e9811-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9811-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9811-113">**Encabezado:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="e9811-113">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="e9811-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9811-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9811-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9811-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9811-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9811-116">See Also</span></span>  
 [<span data-ttu-id="e9811-117">StepRange (método)</span><span class="sxs-lookup"><span data-stu-id="e9811-117">StepRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)  
 [<span data-ttu-id="e9811-118">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="e9811-118">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="e9811-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="e9811-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
