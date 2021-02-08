---
description: 'Más información acerca de: ICorDebugManagedCallback:: CreateProcess (método)'
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
ms.openlocfilehash: 564c9862dd90431f0626204fdfe49e59b85a124d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791054"
---
# <a name="icordebugmanagedcallbackcreateprocess-method"></a><span data-ttu-id="74c3b-103">ICorDebugManagedCallback::CreateProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="74c3b-103">ICorDebugManagedCallback::CreateProcess Method</span></span>

<span data-ttu-id="74c3b-104">Notifica al depurador cuando un proceso se ha adjuntado o Iniciado por primera vez.</span><span class="sxs-lookup"><span data-stu-id="74c3b-104">Notifies the debugger when a process has been attached or started for the first time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74c3b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74c3b-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74c3b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="74c3b-106">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="74c3b-107">de Un puntero a un objeto ICorDebugProcess que representa el proceso que se ha adjuntado o iniciado.</span><span class="sxs-lookup"><span data-stu-id="74c3b-107">[in] A pointer to an ICorDebugProcess object that represents the process that has been attached or started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74c3b-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="74c3b-108">Remarks</span></span>  

 <span data-ttu-id="74c3b-109">No se llama a este método hasta que se inicializa el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="74c3b-109">This method is not called until the common language runtime is initialized.</span></span> <span data-ttu-id="74c3b-110">La mayoría de los métodos [ICorDebug](icordebug-interface.md) devolverán CORDBG_E_NOTREADY antes de la `CreateProcess` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="74c3b-110">Most of the [ICorDebug](icordebug-interface.md) methods will return CORDBG_E_NOTREADY before the `CreateProcess` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74c3b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74c3b-111">Requirements</span></span>  

 <span data-ttu-id="74c3b-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74c3b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74c3b-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="74c3b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74c3b-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74c3b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74c3b-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74c3b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74c3b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="74c3b-116">See also</span></span>

- [<span data-ttu-id="74c3b-117">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="74c3b-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
