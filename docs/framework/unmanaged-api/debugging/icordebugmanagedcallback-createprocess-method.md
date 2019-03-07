---
title: ICorDebugManagedCallback::CreateProcess (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateProcess
helpviewer_keywords:
- ICorDebugManagedCallback::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
ms.assetid: 8e89d5ee-e4e3-4738-8302-0b7d1cf4846e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36e26101a21471fd840a07deef9f5085a88f2730
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487036"
---
# <a name="icordebugmanagedcallbackcreateprocess-method"></a><span data-ttu-id="b46bc-102">ICorDebugManagedCallback::CreateProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="b46bc-102">ICorDebugManagedCallback::CreateProcess Method</span></span>
<span data-ttu-id="b46bc-103">Notifica al depurador cuando se asocia un proceso o se inicia por primera vez.</span><span class="sxs-lookup"><span data-stu-id="b46bc-103">Notifies the debugger when a process has been attached or started for the first time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b46bc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b46bc-104">Syntax</span></span>  
  
```  
HRESULT CreateProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b46bc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b46bc-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="b46bc-106">[in] Un puntero a un objeto ICorDebugProcess que representa el proceso que se ha asociado o iniciado.</span><span class="sxs-lookup"><span data-stu-id="b46bc-106">[in] A pointer to an ICorDebugProcess object that represents the process that has been attached or started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b46bc-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b46bc-107">Remarks</span></span>  
 <span data-ttu-id="b46bc-108">No se llama a este método hasta que se inicializa common language runtime.</span><span class="sxs-lookup"><span data-stu-id="b46bc-108">This method is not called until the common language runtime is initialized.</span></span> <span data-ttu-id="b46bc-109">La mayoría de los [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) métodos devolverán CORDBG_E_NOTREADY antes el `CreateProcess` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="b46bc-109">Most of the [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) methods will return CORDBG_E_NOTREADY before the `CreateProcess` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b46bc-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b46bc-110">Requirements</span></span>  
 <span data-ttu-id="b46bc-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b46bc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b46bc-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b46bc-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b46bc-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b46bc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b46bc-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b46bc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b46bc-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b46bc-115">See also</span></span>
- [<span data-ttu-id="b46bc-116">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b46bc-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
