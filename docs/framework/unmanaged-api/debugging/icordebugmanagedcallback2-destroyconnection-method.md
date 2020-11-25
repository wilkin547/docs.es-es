---
title: ICorDebugManagedCallback2::DestroyConnection (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.DestroyConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::DestroyConnection
helpviewer_keywords:
- DestroyConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::DestroyConnection method [.NET Framework debugging]
ms.assetid: cf7940e9-4558-4319-925c-09f6c98c8fcd
topic_type:
- apiref
ms.openlocfilehash: d725cbe89e0631630affb6b0540a7d5f57ab6b89
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720118"
---
# <a name="icordebugmanagedcallback2destroyconnection-method"></a><span data-ttu-id="c3c26-102">ICorDebugManagedCallback2::DestroyConnection (Método)</span><span class="sxs-lookup"><span data-stu-id="c3c26-102">ICorDebugManagedCallback2::DestroyConnection Method</span></span>

<span data-ttu-id="c3c26-103">Notifica al depurador que se ha terminado la conexión especificada.</span><span class="sxs-lookup"><span data-stu-id="c3c26-103">Notifies the debugger that the specified connection has been terminated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3c26-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c3c26-104">Syntax</span></span>  
  
```cpp  
HRESULT DestroyConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3c26-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c3c26-105">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="c3c26-106">de Un puntero a un objeto ICorDebugProcess que representa el proceso que contiene la conexión que se ha destruido.</span><span class="sxs-lookup"><span data-stu-id="c3c26-106">[in] A pointer to an ICorDebugProcess object that represents the process containing the connection that was destroyed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="c3c26-107">de IDENTIFICADOR de la conexión que se ha destruido.</span><span class="sxs-lookup"><span data-stu-id="c3c26-107">[in] The ID of the connection that was destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3c26-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c3c26-108">Remarks</span></span>  

 <span data-ttu-id="c3c26-109">Se `DestroyConnection` activará una devolución de llamada cuando un host llame a [ICLRDebugManager:: EndConnection](../hosting/iclrdebugmanager-endconnection-method.md) en la [API de hospedaje](../hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="c3c26-109">A `DestroyConnection` callback will be fired when a host calls [ICLRDebugManager::EndConnection](../hosting/iclrdebugmanager-endconnection-method.md) in the [Hosting API](../hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3c26-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c3c26-110">Requirements</span></span>  

 <span data-ttu-id="c3c26-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3c26-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3c26-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3c26-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3c26-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3c26-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3c26-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3c26-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3c26-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c3c26-115">See also</span></span>

- [<span data-ttu-id="c3c26-116">ICorDebugManagedCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c3c26-116">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="c3c26-117">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c3c26-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
