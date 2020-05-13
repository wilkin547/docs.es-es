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
ms.openlocfilehash: d2fc59621cbb6752830c7a8392ce4e0c476ef9e7
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210064"
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a><span data-ttu-id="84712-102">ICorDebugManagedCallback2::FunctionRemapOpportunity (Método)</span><span class="sxs-lookup"><span data-stu-id="84712-102">ICorDebugManagedCallback2::FunctionRemapOpportunity Method</span></span>
<span data-ttu-id="84712-103">Notifica al depurador que la ejecución del código ha alcanzado un punto de secuencia en una versión anterior de una función editada.</span><span class="sxs-lookup"><span data-stu-id="84712-103">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84712-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="84712-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84712-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="84712-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="84712-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene la función editada.</span><span class="sxs-lookup"><span data-stu-id="84712-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="84712-107">de Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se encontró el punto de interrupción de reasignación.</span><span class="sxs-lookup"><span data-stu-id="84712-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pOldFunction`  
 <span data-ttu-id="84712-108">de Un puntero a un objeto ICorDebugFunction que representa la versión de la función que se está ejecutando actualmente en el subproceso.</span><span class="sxs-lookup"><span data-stu-id="84712-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function that is currently running on the thread.</span></span>  
  
 `pNewFunction`  
 <span data-ttu-id="84712-109">de Un puntero a un objeto ICorDebugFunction que representa la versión más reciente de la función.</span><span class="sxs-lookup"><span data-stu-id="84712-109">[in] A pointer to an ICorDebugFunction object that represents the latest version of the function.</span></span>  
  
 `oldILOffset`  
 <span data-ttu-id="84712-110">de Desplazamiento del lenguaje intermedio de Microsoft (MSIL) del puntero de instrucción en la versión anterior de la función.</span><span class="sxs-lookup"><span data-stu-id="84712-110">[in] The Microsoft intermediate language (MSIL) offset of the instruction pointer in the old version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84712-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="84712-111">Remarks</span></span>  
 <span data-ttu-id="84712-112">Esta devolución de llamada proporciona al depurador una oportunidad para reasignar el puntero de instrucción a su lugar adecuado en la nueva versión de la función especificada llamando al método [ICorDebugILFrame2:: remapfunction (](icordebugilframe2-remapfunction-method.md) .</span><span class="sxs-lookup"><span data-stu-id="84712-112">This callback gives the debugger an opportunity to remap the instruction pointer to its proper place in the new version of the specified function by calling the [ICorDebugILFrame2::RemapFunction](icordebugilframe2-remapfunction-method.md) method.</span></span> <span data-ttu-id="84712-113">Si el depurador no llama a `RemapFunction` antes de llamar al método [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) , el tiempo de ejecución continuará ejecutando el código antiguo y activará otra `FunctionRemapOpportunity` devolución de llamada en el siguiente punto de secuencia.</span><span class="sxs-lookup"><span data-stu-id="84712-113">If the debugger does not call `RemapFunction` before calling the [ICorDebugController::Continue](icordebugcontroller-continue-method.md) method, the runtime will continue to execute the old code and will fire another `FunctionRemapOpportunity` callback at the next sequence point.</span></span>  
  
 <span data-ttu-id="84712-114">Esta devolución de llamada se invocará para cada fotograma que ejecute una versión anterior de la función especificada hasta que el depurador devuelva S_OK.</span><span class="sxs-lookup"><span data-stu-id="84712-114">This callback will be invoked for every frame that is executing an older version of the given function until the debugger returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84712-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="84712-115">Requirements</span></span>  
 <span data-ttu-id="84712-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84712-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84712-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84712-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84712-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84712-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84712-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84712-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84712-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="84712-120">See also</span></span>

- [<span data-ttu-id="84712-121">ICorDebugManagedCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="84712-121">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="84712-122">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="84712-122">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
