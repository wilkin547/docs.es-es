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
ms.openlocfilehash: d773368c85fd42fd169109cf1c7e6635705ebb7e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73090226"
---
# <a name="icordebugmanagedcallbackcreateprocess-method"></a><span data-ttu-id="ecb05-102">ICorDebugManagedCallback::CreateProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="ecb05-102">ICorDebugManagedCallback::CreateProcess Method</span></span>
<span data-ttu-id="ecb05-103">Notifica al depurador cuando un proceso se ha adjuntado o Iniciado por primera vez.</span><span class="sxs-lookup"><span data-stu-id="ecb05-103">Notifies the debugger when a process has been attached or started for the first time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecb05-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ecb05-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ecb05-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ecb05-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="ecb05-106">de Un puntero a un objeto ICorDebugProcess que representa el proceso que se ha adjuntado o iniciado.</span><span class="sxs-lookup"><span data-stu-id="ecb05-106">[in] A pointer to an ICorDebugProcess object that represents the process that has been attached or started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecb05-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ecb05-107">Remarks</span></span>  
 <span data-ttu-id="ecb05-108">No se llama a este método hasta que se inicializa el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="ecb05-108">This method is not called until the common language runtime is initialized.</span></span> <span data-ttu-id="ecb05-109">La mayoría de los métodos [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) devolverán CORDBG_E_NOTREADY antes de la devolución de llamada `CreateProcess`.</span><span class="sxs-lookup"><span data-stu-id="ecb05-109">Most of the [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) methods will return CORDBG_E_NOTREADY before the `CreateProcess` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecb05-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ecb05-110">Requirements</span></span>  
 <span data-ttu-id="ecb05-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecb05-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecb05-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ecb05-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ecb05-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecb05-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecb05-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecb05-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecb05-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ecb05-115">See also</span></span>

- [<span data-ttu-id="ecb05-116">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ecb05-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
