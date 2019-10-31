---
title: ICorDebugProcess::EnumerateAppDomains (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.EnumerateAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::EnumerateAppDomains
helpviewer_keywords:
- ICorDebugProcess::EnumerateAppDomains method [.NET Framework debugging]
- EnumerateAppDomains method [.NET Framework debugging]
ms.assetid: d508981f-e2b2-445b-a649-69951c22702d
topic_type:
- apiref
ms.openlocfilehash: e09e25503ad00ab3542f0c4f50221b6014b25561
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128880"
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="df65d-102">ICorDebugProcess::EnumerateAppDomains (Método)</span><span class="sxs-lookup"><span data-stu-id="df65d-102">ICorDebugProcess::EnumerateAppDomains Method</span></span>
<span data-ttu-id="df65d-103">Enumera todos los dominios de aplicación de este proceso.</span><span class="sxs-lookup"><span data-stu-id="df65d-103">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df65d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="df65d-104">Syntax</span></span>  
  
``` cpp 
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df65d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="df65d-105">Parameters</span></span>  
 `ppAppDomains`  
 <span data-ttu-id="df65d-106">enuncia Puntero a la dirección de un [ICorDebugAppDomainEnum (](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md) que es un enumerador para los dominios de aplicación de este proceso.</span><span class="sxs-lookup"><span data-stu-id="df65d-106">[out] A pointer to the address of an [ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df65d-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="df65d-107">Remarks</span></span>  
 <span data-ttu-id="df65d-108">Este método se puede usar antes de la devolución de llamada [ICorDebugManagedCallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="df65d-108">This method can be used before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df65d-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="df65d-109">Requirements</span></span>  
 <span data-ttu-id="df65d-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df65d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df65d-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df65d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df65d-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df65d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df65d-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df65d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
