---
title: CorDebugChainReason (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugChainReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugChainReason
helpviewer_keywords:
- CorDebugChainReason enumeration [.NET Framework debugging]
ms.assetid: c915da51-50b2-41df-841a-2b971f4d0975
topic_type:
- apiref
ms.openlocfilehash: 6185c5dda69a0cf7e9847ddc021448612a426b19
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716062"
---
# <a name="cordebugchainreason-enumeration"></a><span data-ttu-id="93116-102">CorDebugChainReason (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="93116-102">CorDebugChainReason Enumeration</span></span>

<span data-ttu-id="93116-103">Indica el motivo o los motivos para que se inicie una cadena de llamadas.</span><span class="sxs-lookup"><span data-stu-id="93116-103">Indicates the reason or reasons for the initiation of a call chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93116-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="93116-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugChainReason {  
    CHAIN_NONE              = 0x000,  
    CHAIN_CLASS_INIT        = 0x001,  
    CHAIN_EXCEPTION_FILTER  = 0x002,  
    CHAIN_SECURITY          = 0x004,  
    CHAIN_CONTEXT_POLICY    = 0x008,  
    CHAIN_INTERCEPTION      = 0x010,  
    CHAIN_PROCESS_START     = 0x020,  
    CHAIN_THREAD_START      = 0x040,  
    CHAIN_ENTER_MANAGED     = 0x080,  
    CHAIN_ENTER_UNMANAGED   = 0x100,  
    CHAIN_DEBUGGER_EVAL     = 0x200,  
    CHAIN_CONTEXT_SWITCH    = 0x400,  
    CHAIN_FUNC_EVAL         = 0x800  
} CorDebugChainReason;  
```  
  
## <a name="members"></a><span data-ttu-id="93116-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="93116-105">Members</span></span>  
  
|<span data-ttu-id="93116-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="93116-106">Member</span></span>|<span data-ttu-id="93116-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="93116-107">Description</span></span>|  
|------------|-----------------|  
|`CHAIN_NONE`|<span data-ttu-id="93116-108">No se inició ninguna cadena de llamadas.</span><span class="sxs-lookup"><span data-stu-id="93116-108">No call chain has been initiated.</span></span>|  
|`CHAIN_CLASS_INIT`|<span data-ttu-id="93116-109">Un constructor inició la cadena.</span><span class="sxs-lookup"><span data-stu-id="93116-109">The chain was initiated by a constructor.</span></span>|  
|`CHAIN_EXCEPTION_FILTER`|<span data-ttu-id="93116-110">Un constructor inició la cadena.</span><span class="sxs-lookup"><span data-stu-id="93116-110">The chain was initiated by an exception filter.</span></span>|  
|`CHAIN_SECURITY`|<span data-ttu-id="93116-111">El código que exige la seguridad inició la cadena.</span><span class="sxs-lookup"><span data-stu-id="93116-111">The chain was initiated by code that enforces security.</span></span>|  
|`CHAIN_CONTEXT_POLICY`|<span data-ttu-id="93116-112">Una directiva de contexto inició la cadena.</span><span class="sxs-lookup"><span data-stu-id="93116-112">The chain was initiated by a context policy.</span></span>|  
|`CHAIN_INTERCEPTION`|<span data-ttu-id="93116-113">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="93116-113">Not used.</span></span>|  
|`CHAIN_PROCESS_START`|<span data-ttu-id="93116-114">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="93116-114">Not used.</span></span>|  
|`CHAIN_THREAD_START`|<span data-ttu-id="93116-115">El inicio de la ejecución de un subproceso inició la cadena.</span><span class="sxs-lookup"><span data-stu-id="93116-115">The chain was initiated by the start of a thread execution.</span></span>|  
|`CHAIN_ENTER_MANAGED`|<span data-ttu-id="93116-116">Una entrada en código administrado inició la cadena.</span><span class="sxs-lookup"><span data-stu-id="93116-116">The chain was initiated by entry into managed code.</span></span>|  
|`CHAIN_ENTER_UNMANAGED`|<span data-ttu-id="93116-117">Una entrada en código no administrado inició la cadena.</span><span class="sxs-lookup"><span data-stu-id="93116-117">The chain was initiated by entry into unmanaged code.</span></span>|  
|`CHAIN_DEBUGGER_EVAL`|<span data-ttu-id="93116-118">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="93116-118">Not used.</span></span>|  
|`CHAIN_CONTEXT_SWITCH`|<span data-ttu-id="93116-119">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="93116-119">Not used.</span></span>|  
|`CHAIN_FUNC_EVAL`|<span data-ttu-id="93116-120">Una evaluación de función inició la cadena.</span><span class="sxs-lookup"><span data-stu-id="93116-120">The chain was initiated by a function evaluation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93116-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="93116-121">Remarks</span></span>  

 <span data-ttu-id="93116-122">Use el método [ICorDebugChain:: GetReason (](icordebugchain-getreason-method.md) para averiguar los motivos de inicio de una cadena de llamadas.</span><span class="sxs-lookup"><span data-stu-id="93116-122">Use the [ICorDebugChain::GetReason](icordebugchain-getreason-method.md) method to ascertain the reasons for the initiation of a call chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93116-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="93116-123">Requirements</span></span>  

 <span data-ttu-id="93116-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93116-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93116-125">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="93116-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93116-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93116-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93116-127">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93116-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93116-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="93116-128">See also</span></span>

- [<span data-ttu-id="93116-129">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="93116-129">Debugging Enumerations</span></span>](debugging-enumerations.md)
