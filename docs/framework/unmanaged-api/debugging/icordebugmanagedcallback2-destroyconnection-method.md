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
ms.openlocfilehash: a3093f33f2220b22b7b4b373f6d79a341abf8c9c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501942"
---
# <a name="icordebugmanagedcallback2destroyconnection-method"></a><span data-ttu-id="b02ef-102">ICorDebugManagedCallback2::DestroyConnection (Método)</span><span class="sxs-lookup"><span data-stu-id="b02ef-102">ICorDebugManagedCallback2::DestroyConnection Method</span></span>
<span data-ttu-id="b02ef-103">Notifica al depurador que se ha terminado la conexión especificada.</span><span class="sxs-lookup"><span data-stu-id="b02ef-103">Notifies the debugger that the specified connection has been terminated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b02ef-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b02ef-104">Syntax</span></span>  
  
```cpp  
HRESULT DestroyConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b02ef-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b02ef-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="b02ef-106">de Un puntero a un objeto ICorDebugProcess que representa el proceso que contiene la conexión que se ha destruido.</span><span class="sxs-lookup"><span data-stu-id="b02ef-106">[in] A pointer to an ICorDebugProcess object that represents the process containing the connection that was destroyed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="b02ef-107">de IDENTIFICADOR de la conexión que se ha destruido.</span><span class="sxs-lookup"><span data-stu-id="b02ef-107">[in] The ID of the connection that was destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b02ef-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b02ef-108">Remarks</span></span>  
 <span data-ttu-id="b02ef-109">Se `DestroyConnection` activará una devolución de llamada cuando un host llame a [ICLRDebugManager:: EndConnection](../hosting/iclrdebugmanager-endconnection-method.md) en la [API de hospedaje](../hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="b02ef-109">A `DestroyConnection` callback will be fired when a host calls [ICLRDebugManager::EndConnection](../hosting/iclrdebugmanager-endconnection-method.md) in the [Hosting API](../hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b02ef-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b02ef-110">Requirements</span></span>  
 <span data-ttu-id="b02ef-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b02ef-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b02ef-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b02ef-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b02ef-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b02ef-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b02ef-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b02ef-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b02ef-115">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="b02ef-115">See also</span></span>

- [<span data-ttu-id="b02ef-116">ICorDebugManagedCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b02ef-116">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="b02ef-117">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b02ef-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
