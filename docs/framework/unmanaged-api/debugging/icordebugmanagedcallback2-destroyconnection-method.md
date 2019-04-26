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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 35ae3a9761798ed9ea42b984f2c6c2cad4e42777
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704107"
---
# <a name="icordebugmanagedcallback2destroyconnection-method"></a><span data-ttu-id="25faf-102">ICorDebugManagedCallback2::DestroyConnection (Método)</span><span class="sxs-lookup"><span data-stu-id="25faf-102">ICorDebugManagedCallback2::DestroyConnection Method</span></span>
<span data-ttu-id="25faf-103">Notifica al depurador que ha finalizado la conexión especificada.</span><span class="sxs-lookup"><span data-stu-id="25faf-103">Notifies the debugger that the specified connection has been terminated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25faf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="25faf-104">Syntax</span></span>  
  
```  
HRESULT DestroyConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25faf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="25faf-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="25faf-106">[in] Un puntero a un objeto ICorDebugProcess que representa el proceso que contiene la conexión que se ha destruido.</span><span class="sxs-lookup"><span data-stu-id="25faf-106">[in] A pointer to an ICorDebugProcess object that represents the process containing the connection that was destroyed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="25faf-107">[in] El identificador de la conexión que se ha destruido.</span><span class="sxs-lookup"><span data-stu-id="25faf-107">[in] The ID of the connection that was destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25faf-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="25faf-108">Remarks</span></span>  
 <span data-ttu-id="25faf-109">Un `DestroyConnection` devolución de llamada se activará cuando llama un host [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) en el [API de hospedaje](../../../../docs/framework/unmanaged-api/hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="25faf-109">A `DestroyConnection` callback will be fired when a host calls [ICLRDebugManager::EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25faf-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="25faf-110">Requirements</span></span>  
 <span data-ttu-id="25faf-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25faf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25faf-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25faf-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25faf-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25faf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25faf-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25faf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25faf-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="25faf-115">See also</span></span>

- [<span data-ttu-id="25faf-116">ICorDebugManagedCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="25faf-116">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="25faf-117">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="25faf-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
