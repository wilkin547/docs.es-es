---
description: 'Más información sobre: enumeración CorDebugCodeInvokeKind'
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
ms.openlocfilehash: d3fc3fe6f7568adcb2d1bbbe18c98d9d84bac337
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747093"
---
# <a name="cordebugcodeinvokekind-enumeration"></a><span data-ttu-id="e31fb-103">Enumeración CorDebugCodeInvokeKind</span><span class="sxs-lookup"><span data-stu-id="e31fb-103">CorDebugCodeInvokeKind Enumeration</span></span>

<span data-ttu-id="e31fb-104">Describe cómo una función exportada invoca a código administrado.</span><span class="sxs-lookup"><span data-stu-id="e31fb-104">Describes how an exported function invokes managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e31fb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e31fb-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugCodeInvokeKind  
{  
    CODE_INVOKE_KIND_NONE,
    CODE_INVOKE_KIND_RETURN,
    CODE_INVOKE_KIND_TAILCALL,
} CorDebugCodeInvokeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="e31fb-106">Members</span><span class="sxs-lookup"><span data-stu-id="e31fb-106">Members</span></span>  
  
|<span data-ttu-id="e31fb-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="e31fb-107">Member</span></span>|<span data-ttu-id="e31fb-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e31fb-108">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_KIND_NONE`|<span data-ttu-id="e31fb-109">Si algún código administrado se invoca mediante este método, tendrá que encontrarse más adelante mediante eventos explícitos o puntos de interrupción.</span><span class="sxs-lookup"><span data-stu-id="e31fb-109">If any managed code is invoked by this method, it will have to be located by explicit events or breakpoints later.</span></span><br /><br /> <span data-ttu-id="e31fb-110">O bien</span><span class="sxs-lookup"><span data-stu-id="e31fb-110">--or--</span></span><br /><br /> <span data-ttu-id="e31fb-111">Puede que falte parte del código administrado al que este método llama porque no hay forma fácil de detenerse en él.</span><span class="sxs-lookup"><span data-stu-id="e31fb-111">We may just miss some of the managed code this method calls because there is no easy way to stop on it.</span></span><br /><br /> <span data-ttu-id="e31fb-112">O bien</span><span class="sxs-lookup"><span data-stu-id="e31fb-112">--or--</span></span><br /><br /> <span data-ttu-id="e31fb-113">El método no puede invocar nunca código administrado.</span><span class="sxs-lookup"><span data-stu-id="e31fb-113">The method may never invoke managed code.</span></span>|  
|`CODE_INVOKE_KIND_RETURN`|<span data-ttu-id="e31fb-114">Este método llamará a código administrado mediante una instrucción de devolución.</span><span class="sxs-lookup"><span data-stu-id="e31fb-114">This method will invoke managed code via a return instruction.</span></span> <span data-ttu-id="e31fb-115">El paso a paso para salir debe llegar en el siguiente código administrado.</span><span class="sxs-lookup"><span data-stu-id="e31fb-115">Stepping out should arrive at the next managed code.</span></span>|  
|`CODE_INVOKE_KIND_TAILCALL`|<span data-ttu-id="e31fb-116">Este método invocará código administrado mediante una llamada de cola.</span><span class="sxs-lookup"><span data-stu-id="e31fb-116">This method will invoke managed code via a tail-call.</span></span> <span data-ttu-id="e31fb-117">El paso a paso y el paso a paso por procedimientos sobre instrucciones de llamada deben llegar en el código administrado.</span><span class="sxs-lookup"><span data-stu-id="e31fb-117">Single-stepping and stepping over any call instructions should arrive at managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e31fb-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e31fb-118">Remarks</span></span>  

 <span data-ttu-id="e31fb-119">El método [método icordebugprocess6:: GetExportStepInfo](icordebugprocess6-getexportstepinfo-method.md) usa esta enumeración para proporcionar información sobre la ejecución paso a paso a través del código administrado.</span><span class="sxs-lookup"><span data-stu-id="e31fb-119">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e31fb-120">Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e31fb-120">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e31fb-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e31fb-121">Requirements</span></span>  

 <span data-ttu-id="e31fb-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e31fb-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e31fb-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e31fb-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e31fb-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e31fb-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e31fb-125">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e31fb-125">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e31fb-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="e31fb-126">See also</span></span>

- [<span data-ttu-id="e31fb-127">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="e31fb-127">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="e31fb-128">Depuración</span><span class="sxs-lookup"><span data-stu-id="e31fb-128">Debugging</span></span>](index.md)
