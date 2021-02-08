---
description: 'Más información acerca de: ICorDebugManagedCallback2::D estroyConnection (método)'
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
ms.openlocfilehash: f17def5599dc02ed6b7b49d7f8ed4db02eb40181
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790898"
---
# <a name="icordebugmanagedcallback2destroyconnection-method"></a><span data-ttu-id="f2ff7-103">ICorDebugManagedCallback2::DestroyConnection (Método)</span><span class="sxs-lookup"><span data-stu-id="f2ff7-103">ICorDebugManagedCallback2::DestroyConnection Method</span></span>

<span data-ttu-id="f2ff7-104">Notifica al depurador que se ha terminado la conexión especificada.</span><span class="sxs-lookup"><span data-stu-id="f2ff7-104">Notifies the debugger that the specified connection has been terminated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2ff7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2ff7-105">Syntax</span></span>  
  
```cpp  
HRESULT DestroyConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2ff7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f2ff7-106">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="f2ff7-107">de Un puntero a un objeto ICorDebugProcess que representa el proceso que contiene la conexión que se ha destruido.</span><span class="sxs-lookup"><span data-stu-id="f2ff7-107">[in] A pointer to an ICorDebugProcess object that represents the process containing the connection that was destroyed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="f2ff7-108">de IDENTIFICADOR de la conexión que se ha destruido.</span><span class="sxs-lookup"><span data-stu-id="f2ff7-108">[in] The ID of the connection that was destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2ff7-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f2ff7-109">Remarks</span></span>  

 <span data-ttu-id="f2ff7-110">Se `DestroyConnection` activará una devolución de llamada cuando un host llame a [ICLRDebugManager:: EndConnection](../hosting/iclrdebugmanager-endconnection-method.md) en la [API de hospedaje](../hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="f2ff7-110">A `DestroyConnection` callback will be fired when a host calls [ICLRDebugManager::EndConnection](../hosting/iclrdebugmanager-endconnection-method.md) in the [Hosting API](../hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2ff7-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f2ff7-111">Requirements</span></span>  

 <span data-ttu-id="f2ff7-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2ff7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2ff7-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2ff7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2ff7-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2ff7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2ff7-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2ff7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2ff7-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2ff7-116">See also</span></span>

- [<span data-ttu-id="f2ff7-117">ICorDebugManagedCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f2ff7-117">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="f2ff7-118">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f2ff7-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
