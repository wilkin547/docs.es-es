---
title: ICorDebugManagedCallback2::FunctionRemapComplete (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapComplete
helpviewer_keywords:
- FunctionRemapComplete method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapComplete method [.NET Framework debugging]
ms.assetid: 5396c4c3-4ec3-4e3a-a38d-d65b21f0a2fc
topic_type:
- apiref
ms.openlocfilehash: 7eb7fb55a5077d2914eb85a67ca62163a1aa8cc0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704609"
---
# <a name="icordebugmanagedcallback2functionremapcomplete-method"></a><span data-ttu-id="2744d-102">ICorDebugManagedCallback2::FunctionRemapComplete (Método)</span><span class="sxs-lookup"><span data-stu-id="2744d-102">ICorDebugManagedCallback2::FunctionRemapComplete Method</span></span>

<span data-ttu-id="2744d-103">Notifica al depurador que la ejecución del código ha cambiado a una nueva versión de una función editada.</span><span class="sxs-lookup"><span data-stu-id="2744d-103">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2744d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2744d-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionRemapComplete (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2744d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2744d-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="2744d-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene la función editada.</span><span class="sxs-lookup"><span data-stu-id="2744d-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="2744d-107">de Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se encontró el punto de interrupción de reasignación.</span><span class="sxs-lookup"><span data-stu-id="2744d-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pFunction`  
 <span data-ttu-id="2744d-108">de Un puntero a un objeto ICorDebugFunction que representa la versión de la función que se está ejecutando actualmente en el subproceso.</span><span class="sxs-lookup"><span data-stu-id="2744d-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function currently running on the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2744d-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2744d-109">Remarks</span></span>  

 <span data-ttu-id="2744d-110">Esta devolución de llamada proporciona al depurador una oportunidad para volver a crear los steppers que ya existían.</span><span class="sxs-lookup"><span data-stu-id="2744d-110">This callback gives the debugger an opportunity to recreate any steppers that previously existed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2744d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2744d-111">Requirements</span></span>  

 <span data-ttu-id="2744d-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2744d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2744d-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2744d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2744d-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2744d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2744d-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2744d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2744d-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2744d-116">See also</span></span>

- [<span data-ttu-id="2744d-117">ICorDebugManagedCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2744d-117">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="2744d-118">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2744d-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
