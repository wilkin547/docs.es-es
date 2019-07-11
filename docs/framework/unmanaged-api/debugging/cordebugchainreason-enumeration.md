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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e46118e97a4b888a16f12cf6705d2b7e67bbf7ec
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740361"
---
# <a name="cordebugchainreason-enumeration"></a><span data-ttu-id="0b0a7-102">CorDebugChainReason (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="0b0a7-102">CorDebugChainReason Enumeration</span></span>
<span data-ttu-id="0b0a7-103">Indica el motivo o los motivos para que se inicie una cadena de llamadas.</span><span class="sxs-lookup"><span data-stu-id="0b0a7-103">Indicates the reason or reasons for the initiation of a call chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b0a7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0b0a7-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="0b0a7-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="0b0a7-105">Members</span></span>  
  
|<span data-ttu-id="0b0a7-106">Member</span><span class="sxs-lookup"><span data-stu-id="0b0a7-106">Member</span></span>|<span data-ttu-id="0b0a7-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0b0a7-107">Description</span></span>|  
|------------|-----------------|  
|`CHAIN_NONE`|<span data-ttu-id="0b0a7-108">No se inició ninguna cadena de llamadas.</span><span class="sxs-lookup"><span data-stu-id="0b0a7-108">No call chain has been initiated.</span></span>|  
|`CHAIN_CLASS_INIT`|<span data-ttu-id="0b0a7-109">Un constructor inició la cadena.</span><span class="sxs-lookup"><span data-stu-id="0b0a7-109">The chain was initiated by a constructor.</span></span>|  
|`CHAIN_EXCEPTION_FILTER`|<span data-ttu-id="0b0a7-110">Un constructor inició la cadena.</span><span class="sxs-lookup"><span data-stu-id="0b0a7-110">The chain was initiated by an exception filter.</span></span>|  
|`CHAIN_SECURITY`|<span data-ttu-id="0b0a7-111">El código que exige la seguridad inició la cadena.</span><span class="sxs-lookup"><span data-stu-id="0b0a7-111">The chain was initiated by code that enforces security.</span></span>|  
|`CHAIN_CONTEXT_POLICY`|<span data-ttu-id="0b0a7-112">Una directiva de contexto inició la cadena.</span><span class="sxs-lookup"><span data-stu-id="0b0a7-112">The chain was initiated by a context policy.</span></span>|  
|`CHAIN_INTERCEPTION`|<span data-ttu-id="0b0a7-113">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="0b0a7-113">Not used.</span></span>|  
|`CHAIN_PROCESS_START`|<span data-ttu-id="0b0a7-114">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="0b0a7-114">Not used.</span></span>|  
|`CHAIN_THREAD_START`|<span data-ttu-id="0b0a7-115">El inicio de la ejecución de un subproceso inició la cadena.</span><span class="sxs-lookup"><span data-stu-id="0b0a7-115">The chain was initiated by the start of a thread execution.</span></span>|  
|`CHAIN_ENTER_MANAGED`|<span data-ttu-id="0b0a7-116">Una entrada en código administrado inició la cadena.</span><span class="sxs-lookup"><span data-stu-id="0b0a7-116">The chain was initiated by entry into managed code.</span></span>|  
|`CHAIN_ENTER_UNMANAGED`|<span data-ttu-id="0b0a7-117">Una entrada en código no administrado inició la cadena.</span><span class="sxs-lookup"><span data-stu-id="0b0a7-117">The chain was initiated by entry into unmanaged code.</span></span>|  
|`CHAIN_DEBUGGER_EVAL`|<span data-ttu-id="0b0a7-118">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="0b0a7-118">Not used.</span></span>|  
|`CHAIN_CONTEXT_SWITCH`|<span data-ttu-id="0b0a7-119">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="0b0a7-119">Not used.</span></span>|  
|`CHAIN_FUNC_EVAL`|<span data-ttu-id="0b0a7-120">Una evaluación de función inició la cadena.</span><span class="sxs-lookup"><span data-stu-id="0b0a7-120">The chain was initiated by a function evaluation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b0a7-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0b0a7-121">Remarks</span></span>  
 <span data-ttu-id="0b0a7-122">Use la [ICorDebugChain:: GetReason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md) método para determinar las razones para la iniciación de una cadena de llamadas.</span><span class="sxs-lookup"><span data-stu-id="0b0a7-122">Use the [ICorDebugChain::GetReason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md) method to ascertain the reasons for the initiation of a call chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b0a7-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0b0a7-123">Requirements</span></span>  
 <span data-ttu-id="0b0a7-124">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b0a7-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b0a7-125">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0b0a7-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0b0a7-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b0a7-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b0a7-127">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b0a7-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b0a7-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b0a7-128">See also</span></span>

- [<span data-ttu-id="0b0a7-129">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="0b0a7-129">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
