---
title: "Enumeración CorDebugCodeInvokeKind"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugCodeInvokeKind
api_location: mscordbi.dll
api_type: COM
ms.assetid: e795e6a2-1008-4a81-af88-d777888e942e
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d46a47c7c655a960224bb836be0ea37cd07c8038
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugcodeinvokekind-enumeration"></a><span data-ttu-id="9ac76-102">Enumeración CorDebugCodeInvokeKind</span><span class="sxs-lookup"><span data-stu-id="9ac76-102">CorDebugCodeInvokeKind Enumeration</span></span>
<span data-ttu-id="9ac76-103">Describe cómo una función exportada invoca a código administrado.</span><span class="sxs-lookup"><span data-stu-id="9ac76-103">Describes how an exported function invokes managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ac76-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9ac76-104">Syntax</span></span>  
  
```  
typedef enum CorDebugCodeInvokeKind  
{  
    CODE_INVOKE_KIND_NONE,       
    CODE_INVOKE_KIND_RETURN,     
    CODE_INVOKE_KIND_TAILCALL,   
} CorDebugCodeInvokeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="9ac76-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="9ac76-105">Members</span></span>  
  
|<span data-ttu-id="9ac76-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="9ac76-106">Member</span></span>|<span data-ttu-id="9ac76-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ac76-107">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_KIND_NONE`|<span data-ttu-id="9ac76-108">Si algún código administrado se invoca mediante este método, tendrá que encontrarse más adelante mediante eventos explícitos o puntos de interrupción.</span><span class="sxs-lookup"><span data-stu-id="9ac76-108">If any managed code is invoked by this method, it will have to be located by explicit events or breakpoints later.</span></span><br /><br /> <span data-ttu-id="9ac76-109">O bien</span><span class="sxs-lookup"><span data-stu-id="9ac76-109">--or--</span></span><br /><br /> <span data-ttu-id="9ac76-110">Puede que falte parte del código administrado al que este método llama porque no hay forma fácil de detenerse en él.</span><span class="sxs-lookup"><span data-stu-id="9ac76-110">We may just miss some of the managed code this method calls because there is no easy way to stop on it.</span></span><br /><br /> <span data-ttu-id="9ac76-111">O bien</span><span class="sxs-lookup"><span data-stu-id="9ac76-111">--or--</span></span><br /><br /> <span data-ttu-id="9ac76-112">El método no puede invocar nunca código administrado.</span><span class="sxs-lookup"><span data-stu-id="9ac76-112">The method may never invoke managed code.</span></span>|  
|`CODE_INVOKE_KIND_RETURN`|<span data-ttu-id="9ac76-113">Este método llamará a código administrado mediante una instrucción de devolución.</span><span class="sxs-lookup"><span data-stu-id="9ac76-113">This method will invoke managed code via a return instruction.</span></span> <span data-ttu-id="9ac76-114">El paso a paso para salir debe llegar en el siguiente código administrado.</span><span class="sxs-lookup"><span data-stu-id="9ac76-114">Stepping out should arrive at the next managed code.</span></span>|  
|`CODE_INVOKE_KIND_TAILCALL`|<span data-ttu-id="9ac76-115">Este método invocará código administrado mediante una llamada de cola.</span><span class="sxs-lookup"><span data-stu-id="9ac76-115">This method will invoke managed code via a tail-call.</span></span> <span data-ttu-id="9ac76-116">El paso a paso y el paso a paso por procedimientos sobre instrucciones de llamada deben llegar en el código administrado.</span><span class="sxs-lookup"><span data-stu-id="9ac76-116">Single-stepping and stepping over any call instructions should arrive at managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ac76-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9ac76-117">Remarks</span></span>  
 <span data-ttu-id="9ac76-118">Esta enumeración se usa en la [icordebugprocess6:: Getexportstepinfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) método para proporcionar información acerca de la ejecución paso a paso el código administrado.</span><span class="sxs-lookup"><span data-stu-id="9ac76-118">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ac76-119">Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9ac76-119">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ac76-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9ac76-120">Requirements</span></span>  
 <span data-ttu-id="9ac76-121">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ac76-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ac76-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ac76-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ac76-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ac76-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ac76-124">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ac76-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ac76-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ac76-125">See Also</span></span>  
 [<span data-ttu-id="9ac76-126">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="9ac76-126">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="9ac76-127">Depuración</span><span class="sxs-lookup"><span data-stu-id="9ac76-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
