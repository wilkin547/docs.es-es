---
description: 'Más información sobre: ICorDebugManagedCallback2:: Functionremapopportunity ((método)'
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
ms.openlocfilehash: 901a9432ddf17efabd96153581b816f653ff501d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790872"
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a><span data-ttu-id="5fe9e-103">ICorDebugManagedCallback2::FunctionRemapOpportunity (Método)</span><span class="sxs-lookup"><span data-stu-id="5fe9e-103">ICorDebugManagedCallback2::FunctionRemapOpportunity Method</span></span>

<span data-ttu-id="5fe9e-104">Notifica al depurador que la ejecución del código ha alcanzado un punto de secuencia en una versión anterior de una función editada.</span><span class="sxs-lookup"><span data-stu-id="5fe9e-104">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fe9e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5fe9e-105">Syntax</span></span>  
  
```cpp  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fe9e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5fe9e-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="5fe9e-107">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene la función editada.</span><span class="sxs-lookup"><span data-stu-id="5fe9e-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="5fe9e-108">de Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se encontró el punto de interrupción de reasignación.</span><span class="sxs-lookup"><span data-stu-id="5fe9e-108">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pOldFunction`  
 <span data-ttu-id="5fe9e-109">de Un puntero a un objeto ICorDebugFunction que representa la versión de la función que se está ejecutando actualmente en el subproceso.</span><span class="sxs-lookup"><span data-stu-id="5fe9e-109">[in] A pointer to an ICorDebugFunction object that represents the version of the function that is currently running on the thread.</span></span>  
  
 `pNewFunction`  
 <span data-ttu-id="5fe9e-110">de Un puntero a un objeto ICorDebugFunction que representa la versión más reciente de la función.</span><span class="sxs-lookup"><span data-stu-id="5fe9e-110">[in] A pointer to an ICorDebugFunction object that represents the latest version of the function.</span></span>  
  
 `oldILOffset`  
 <span data-ttu-id="5fe9e-111">de Desplazamiento del lenguaje intermedio de Microsoft (MSIL) del puntero de instrucción en la versión anterior de la función.</span><span class="sxs-lookup"><span data-stu-id="5fe9e-111">[in] The Microsoft intermediate language (MSIL) offset of the instruction pointer in the old version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fe9e-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5fe9e-112">Remarks</span></span>  

 <span data-ttu-id="5fe9e-113">Esta devolución de llamada proporciona al depurador una oportunidad para reasignar el puntero de instrucción a su lugar adecuado en la nueva versión de la función especificada llamando al método [ICorDebugILFrame2:: remapfunction (](icordebugilframe2-remapfunction-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5fe9e-113">This callback gives the debugger an opportunity to remap the instruction pointer to its proper place in the new version of the specified function by calling the [ICorDebugILFrame2::RemapFunction](icordebugilframe2-remapfunction-method.md) method.</span></span> <span data-ttu-id="5fe9e-114">Si el depurador no llama a `RemapFunction` antes de llamar al método [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) , el tiempo de ejecución continuará ejecutando el código antiguo y activará otra `FunctionRemapOpportunity` devolución de llamada en el siguiente punto de secuencia.</span><span class="sxs-lookup"><span data-stu-id="5fe9e-114">If the debugger does not call `RemapFunction` before calling the [ICorDebugController::Continue](icordebugcontroller-continue-method.md) method, the runtime will continue to execute the old code and will fire another `FunctionRemapOpportunity` callback at the next sequence point.</span></span>  
  
 <span data-ttu-id="5fe9e-115">Esta devolución de llamada se invocará para cada fotograma que ejecute una versión anterior de la función especificada hasta que el depurador devuelva S_OK.</span><span class="sxs-lookup"><span data-stu-id="5fe9e-115">This callback will be invoked for every frame that is executing an older version of the given function until the debugger returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fe9e-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5fe9e-116">Requirements</span></span>  

 <span data-ttu-id="5fe9e-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fe9e-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fe9e-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5fe9e-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5fe9e-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fe9e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5fe9e-120">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fe9e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fe9e-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="5fe9e-121">See also</span></span>

- [<span data-ttu-id="5fe9e-122">ICorDebugManagedCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5fe9e-122">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="5fe9e-123">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5fe9e-123">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
