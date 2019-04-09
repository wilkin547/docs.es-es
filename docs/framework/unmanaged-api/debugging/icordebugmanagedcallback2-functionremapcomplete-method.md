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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 515d434e8d8f1c99cf5052ef9a2f1e098f6021b2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59140561"
---
# <a name="icordebugmanagedcallback2functionremapcomplete-method"></a><span data-ttu-id="85ef6-102">ICorDebugManagedCallback2::FunctionRemapComplete (Método)</span><span class="sxs-lookup"><span data-stu-id="85ef6-102">ICorDebugManagedCallback2::FunctionRemapComplete Method</span></span>
<span data-ttu-id="85ef6-103">Notifica al depurador que la ejecución de código ha cambiado a una nueva versión de una función modificada.</span><span class="sxs-lookup"><span data-stu-id="85ef6-103">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85ef6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85ef6-104">Syntax</span></span>  
  
```  
HRESULT FunctionRemapComplete (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85ef6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="85ef6-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="85ef6-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene la función modificada.</span><span class="sxs-lookup"><span data-stu-id="85ef6-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="85ef6-107">[in] Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se encontró el punto de interrupción de reasignación.</span><span class="sxs-lookup"><span data-stu-id="85ef6-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pFunction`  
 <span data-ttu-id="85ef6-108">[in] Un puntero a un objeto ICorDebugFunction que representa la versión de la función que se están ejecutando actualmente en el subproceso.</span><span class="sxs-lookup"><span data-stu-id="85ef6-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function currently running on the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85ef6-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="85ef6-109">Remarks</span></span>  
 <span data-ttu-id="85ef6-110">Esta devolución de llamada da la oportunidad para volver a crear los steppers que existían previamente el depurador.</span><span class="sxs-lookup"><span data-stu-id="85ef6-110">This callback gives the debugger an opportunity to recreate any steppers that previously existed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85ef6-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="85ef6-111">Requirements</span></span>  
 <span data-ttu-id="85ef6-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85ef6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85ef6-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85ef6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85ef6-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85ef6-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="85ef6-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="85ef6-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="85ef6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="85ef6-116">See also</span></span>

- [<span data-ttu-id="85ef6-117">ICorDebugManagedCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="85ef6-117">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="85ef6-118">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="85ef6-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
