---
title: Enumeración CorDebugCodeInvokeKind
ms.date: 03/30/2017
api_name:
- CorDebugCodeInvokeKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: e795e6a2-1008-4a81-af88-d777888e942e
topic_type:
- apiref
ms.openlocfilehash: ece5bd5373fed1a10e6592ff884e98b614e7991d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715997"
---
# <a name="cordebugcodeinvokekind-enumeration"></a><span data-ttu-id="7a5e4-102">Enumeración CorDebugCodeInvokeKind</span><span class="sxs-lookup"><span data-stu-id="7a5e4-102">CorDebugCodeInvokeKind Enumeration</span></span>

<span data-ttu-id="7a5e4-103">Describe cómo una función exportada invoca a código administrado.</span><span class="sxs-lookup"><span data-stu-id="7a5e4-103">Describes how an exported function invokes managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a5e4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7a5e4-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugCodeInvokeKind  
{  
    CODE_INVOKE_KIND_NONE,
    CODE_INVOKE_KIND_RETURN,
    CODE_INVOKE_KIND_TAILCALL,
} CorDebugCodeInvokeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="7a5e4-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="7a5e4-105">Members</span></span>  
  
|<span data-ttu-id="7a5e4-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="7a5e4-106">Member</span></span>|<span data-ttu-id="7a5e4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a5e4-107">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_KIND_NONE`|<span data-ttu-id="7a5e4-108">Si algún código administrado se invoca mediante este método, tendrá que encontrarse más adelante mediante eventos explícitos o puntos de interrupción.</span><span class="sxs-lookup"><span data-stu-id="7a5e4-108">If any managed code is invoked by this method, it will have to be located by explicit events or breakpoints later.</span></span><br /><br /> <span data-ttu-id="7a5e4-109">O bien</span><span class="sxs-lookup"><span data-stu-id="7a5e4-109">--or--</span></span><br /><br /> <span data-ttu-id="7a5e4-110">Puede que falte parte del código administrado al que este método llama porque no hay forma fácil de detenerse en él.</span><span class="sxs-lookup"><span data-stu-id="7a5e4-110">We may just miss some of the managed code this method calls because there is no easy way to stop on it.</span></span><br /><br /> <span data-ttu-id="7a5e4-111">O bien</span><span class="sxs-lookup"><span data-stu-id="7a5e4-111">--or--</span></span><br /><br /> <span data-ttu-id="7a5e4-112">El método no puede invocar nunca código administrado.</span><span class="sxs-lookup"><span data-stu-id="7a5e4-112">The method may never invoke managed code.</span></span>|  
|`CODE_INVOKE_KIND_RETURN`|<span data-ttu-id="7a5e4-113">Este método llamará a código administrado mediante una instrucción de devolución.</span><span class="sxs-lookup"><span data-stu-id="7a5e4-113">This method will invoke managed code via a return instruction.</span></span> <span data-ttu-id="7a5e4-114">El paso a paso para salir debe llegar en el siguiente código administrado.</span><span class="sxs-lookup"><span data-stu-id="7a5e4-114">Stepping out should arrive at the next managed code.</span></span>|  
|`CODE_INVOKE_KIND_TAILCALL`|<span data-ttu-id="7a5e4-115">Este método invocará código administrado mediante una llamada de cola.</span><span class="sxs-lookup"><span data-stu-id="7a5e4-115">This method will invoke managed code via a tail-call.</span></span> <span data-ttu-id="7a5e4-116">El paso a paso y el paso a paso por procedimientos sobre instrucciones de llamada deben llegar en el código administrado.</span><span class="sxs-lookup"><span data-stu-id="7a5e4-116">Single-stepping and stepping over any call instructions should arrive at managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a5e4-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7a5e4-117">Remarks</span></span>  

 <span data-ttu-id="7a5e4-118">El método [método icordebugprocess6:: GetExportStepInfo](icordebugprocess6-getexportstepinfo-method.md) usa esta enumeración para proporcionar información sobre la ejecución paso a paso a través del código administrado.</span><span class="sxs-lookup"><span data-stu-id="7a5e4-118">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7a5e4-119">Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7a5e4-119">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a5e4-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7a5e4-120">Requirements</span></span>  

 <span data-ttu-id="7a5e4-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a5e4-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a5e4-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7a5e4-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7a5e4-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a5e4-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a5e4-124">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a5e4-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a5e4-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7a5e4-125">See also</span></span>

- [<span data-ttu-id="7a5e4-126">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="7a5e4-126">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="7a5e4-127">Depuración</span><span class="sxs-lookup"><span data-stu-id="7a5e4-127">Debugging</span></span>](index.md)
