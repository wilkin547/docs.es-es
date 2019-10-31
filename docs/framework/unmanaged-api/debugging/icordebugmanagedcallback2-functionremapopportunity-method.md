---
title: ICorDebugManagedCallback2::FunctionRemapOpportunity (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapOpportunity
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapOpportunity
helpviewer_keywords:
- FunctionRemapOpportunity method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapOpportunity method [.NET Framework debugging]
ms.assetid: 0d6471bc-ad9b-4b1d-a307-c10443918863
topic_type:
- apiref
ms.openlocfilehash: c6c361113a441df050a8e7cd5219819cc8332581
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131488"
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a><span data-ttu-id="7b057-102">ICorDebugManagedCallback2::FunctionRemapOpportunity (Método)</span><span class="sxs-lookup"><span data-stu-id="7b057-102">ICorDebugManagedCallback2::FunctionRemapOpportunity Method</span></span>
<span data-ttu-id="7b057-103">Notifica al depurador que la ejecución del código ha alcanzado un punto de secuencia en una versión anterior de una función editada.</span><span class="sxs-lookup"><span data-stu-id="7b057-103">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b057-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b057-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b057-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7b057-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="7b057-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene la función editada.</span><span class="sxs-lookup"><span data-stu-id="7b057-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="7b057-107">de Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se encontró el punto de interrupción de reasignación.</span><span class="sxs-lookup"><span data-stu-id="7b057-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pOldFunction`  
 <span data-ttu-id="7b057-108">de Un puntero a un objeto ICorDebugFunction que representa la versión de la función que se está ejecutando actualmente en el subproceso.</span><span class="sxs-lookup"><span data-stu-id="7b057-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function that is currently running on the thread.</span></span>  
  
 `pNewFunction`  
 <span data-ttu-id="7b057-109">de Un puntero a un objeto ICorDebugFunction que representa la versión más reciente de la función.</span><span class="sxs-lookup"><span data-stu-id="7b057-109">[in] A pointer to an ICorDebugFunction object that represents the latest version of the function.</span></span>  
  
 `oldILOffset`  
 <span data-ttu-id="7b057-110">de Desplazamiento del lenguaje intermedio de Microsoft (MSIL) del puntero de instrucción en la versión anterior de la función.</span><span class="sxs-lookup"><span data-stu-id="7b057-110">[in] The Microsoft intermediate language (MSIL) offset of the instruction pointer in the old version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b057-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7b057-111">Remarks</span></span>  
 <span data-ttu-id="7b057-112">Esta devolución de llamada proporciona al depurador una oportunidad para reasignar el puntero de instrucción a su lugar adecuado en la nueva versión de la función especificada llamando al método [ICorDebugILFrame2:: remapfunction (](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7b057-112">This callback gives the debugger an opportunity to remap the instruction pointer to its proper place in the new version of the specified function by calling the [ICorDebugILFrame2::RemapFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md) method.</span></span> <span data-ttu-id="7b057-113">Si el depurador no llama a `RemapFunction` antes de llamar al método [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) , el motor en tiempo de ejecución seguirá ejecutando el código anterior y activará otra devolución de llamada `FunctionRemapOpportunity` en el siguiente punto de secuencia.</span><span class="sxs-lookup"><span data-stu-id="7b057-113">If the debugger does not call `RemapFunction` before calling the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method, the runtime will continue to execute the old code and will fire another `FunctionRemapOpportunity` callback at the next sequence point.</span></span>  
  
 <span data-ttu-id="7b057-114">Esta devolución de llamada se invocará para cada fotograma que ejecute una versión anterior de la función especificada hasta que el depurador devuelva S_OK.</span><span class="sxs-lookup"><span data-stu-id="7b057-114">This callback will be invoked for every frame that is executing an older version of the given function until the debugger returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b057-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b057-115">Requirements</span></span>  
 <span data-ttu-id="7b057-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b057-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b057-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b057-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b057-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b057-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b057-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b057-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b057-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b057-120">See also</span></span>

- [<span data-ttu-id="7b057-121">ICorDebugManagedCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b057-121">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="7b057-122">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b057-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
