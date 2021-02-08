---
description: 'Más información sobre: ICorDebugManagedCallback2:: Functionremapcomplete ((método)'
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
ms.openlocfilehash: fcb4388185de17d602c1e3dbc725e104a0a48b3b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790859"
---
# <a name="icordebugmanagedcallback2functionremapcomplete-method"></a><span data-ttu-id="36301-103">ICorDebugManagedCallback2::FunctionRemapComplete (Método)</span><span class="sxs-lookup"><span data-stu-id="36301-103">ICorDebugManagedCallback2::FunctionRemapComplete Method</span></span>

<span data-ttu-id="36301-104">Notifica al depurador que la ejecución del código ha cambiado a una nueva versión de una función editada.</span><span class="sxs-lookup"><span data-stu-id="36301-104">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36301-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36301-105">Syntax</span></span>  
  
```cpp  
HRESULT FunctionRemapComplete (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36301-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="36301-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="36301-107">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene la función editada.</span><span class="sxs-lookup"><span data-stu-id="36301-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="36301-108">de Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se encontró el punto de interrupción de reasignación.</span><span class="sxs-lookup"><span data-stu-id="36301-108">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pFunction`  
 <span data-ttu-id="36301-109">de Un puntero a un objeto ICorDebugFunction que representa la versión de la función que se está ejecutando actualmente en el subproceso.</span><span class="sxs-lookup"><span data-stu-id="36301-109">[in] A pointer to an ICorDebugFunction object that represents the version of the function currently running on the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36301-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="36301-110">Remarks</span></span>  

 <span data-ttu-id="36301-111">Esta devolución de llamada proporciona al depurador una oportunidad para volver a crear los steppers que ya existían.</span><span class="sxs-lookup"><span data-stu-id="36301-111">This callback gives the debugger an opportunity to recreate any steppers that previously existed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36301-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="36301-112">Requirements</span></span>  

 <span data-ttu-id="36301-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36301-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36301-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="36301-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="36301-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36301-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36301-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36301-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36301-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="36301-117">See also</span></span>

- [<span data-ttu-id="36301-118">ICorDebugManagedCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="36301-118">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="36301-119">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="36301-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
