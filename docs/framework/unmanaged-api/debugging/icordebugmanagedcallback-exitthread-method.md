---
title: ICorDebugManagedCallback::ExitThread (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitThread
helpviewer_keywords:
- ExitThread method [.NET Framework debugging]
- ICorDebugManagedCallback::ExitThread method [.NET Framework debugging]
ms.assetid: 62db708b-6cf0-45c5-b897-4b5c75bd2505
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85247f2f3672e7827f4dd0c93e50cd5da914ee8f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755776"
---
# <a name="icordebugmanagedcallbackexitthread-method"></a><span data-ttu-id="71fb9-102">ICorDebugManagedCallback::ExitThread (Método)</span><span class="sxs-lookup"><span data-stu-id="71fb9-102">ICorDebugManagedCallback::ExitThread Method</span></span>
<span data-ttu-id="71fb9-103">Notifica al depurador que ha salido de un subproceso que se estaba ejecutando código administrado.</span><span class="sxs-lookup"><span data-stu-id="71fb9-103">Notifies the debugger that a thread that was executing managed code has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71fb9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="71fb9-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71fb9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="71fb9-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="71fb9-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="71fb9-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="71fb9-107">[in] Un puntero a un objeto ICorDebugThread que representa el subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="71fb9-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71fb9-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="71fb9-108">Remarks</span></span>  
 <span data-ttu-id="71fb9-109">Una vez el `ExitThread` se desencadena la devolución de llamada, el subproceso ya no aparecerá en las enumeraciones de subproceso.</span><span class="sxs-lookup"><span data-stu-id="71fb9-109">Once the `ExitThread` callback is fired, the thread will no longer appear in thread enumerations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71fb9-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="71fb9-110">Requirements</span></span>  
 <span data-ttu-id="71fb9-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71fb9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71fb9-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71fb9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71fb9-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71fb9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71fb9-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71fb9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71fb9-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="71fb9-115">See also</span></span>

- [<span data-ttu-id="71fb9-116">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="71fb9-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
