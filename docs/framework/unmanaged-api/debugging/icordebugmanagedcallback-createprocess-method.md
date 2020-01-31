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
ms.openlocfilehash: 0c3059697014cea33081f6cb81b9d93c7d028c2e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777471"
---
# <a name="icordebugmanagedcallbackcreateprocess-method"></a><span data-ttu-id="edcd4-102">ICorDebugManagedCallback::CreateProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="edcd4-102">ICorDebugManagedCallback::CreateProcess Method</span></span>
<span data-ttu-id="edcd4-103">Notifica al depurador cuando un proceso se ha adjuntado o Iniciado por primera vez.</span><span class="sxs-lookup"><span data-stu-id="edcd4-103">Notifies the debugger when a process has been attached or started for the first time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edcd4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="edcd4-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="edcd4-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="edcd4-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="edcd4-106">de Un puntero a un objeto ICorDebugProcess que representa el proceso que se ha adjuntado o iniciado.</span><span class="sxs-lookup"><span data-stu-id="edcd4-106">[in] A pointer to an ICorDebugProcess object that represents the process that has been attached or started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="edcd4-107">Notas</span><span class="sxs-lookup"><span data-stu-id="edcd4-107">Remarks</span></span>  
 <span data-ttu-id="edcd4-108">No se llama a este método hasta que se inicializa el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="edcd4-108">This method is not called until the common language runtime is initialized.</span></span> <span data-ttu-id="edcd4-109">La mayoría de los métodos [ICorDebug](icordebug-interface.md) devolverán CORDBG_E_NOTREADY antes de la devolución de llamada `CreateProcess`.</span><span class="sxs-lookup"><span data-stu-id="edcd4-109">Most of the [ICorDebug](icordebug-interface.md) methods will return CORDBG_E_NOTREADY before the `CreateProcess` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edcd4-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="edcd4-110">Requirements</span></span>  
 <span data-ttu-id="edcd4-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="edcd4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edcd4-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="edcd4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="edcd4-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="edcd4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="edcd4-114">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edcd4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edcd4-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="edcd4-115">See also</span></span>

- [<span data-ttu-id="edcd4-116">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="edcd4-116">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
