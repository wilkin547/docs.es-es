---
title: "ICorDebugManagedCallback::NameChange (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.NameChange
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::NameChange
helpviewer_keywords:
- ICorDebugManagedCallback::NameChange method [.NET Framework debugging]
- NameChange method [.NET Framework debugging]
ms.assetid: a7018a0e-880e-4b68-b52a-1cd22c7aad62
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f9ce32a68354c6bef43dfb55395cb6f9bb136dca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbacknamechange-method"></a><span data-ttu-id="45c27-102">ICorDebugManagedCallback::NameChange (Método)</span><span class="sxs-lookup"><span data-stu-id="45c27-102">ICorDebugManagedCallback::NameChange Method</span></span>
<span data-ttu-id="45c27-103">Notifica al depurador que se ha cambiado el nombre de un dominio de aplicación o un subproceso.</span><span class="sxs-lookup"><span data-stu-id="45c27-103">Notifies the debugger that the name of either an application domain or a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45c27-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45c27-104">Syntax</span></span>  
  
```  
HRESULT NameChange (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="45c27-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="45c27-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="45c27-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que tuvo un cambio de nombre o que contiene el subproceso que tuvo un cambio de nombre.</span><span class="sxs-lookup"><span data-stu-id="45c27-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that either had a name change or that contains the thread that had a name change.</span></span>  
  
 `pThread`  
 <span data-ttu-id="45c27-107">[in] Un puntero a un objeto ICorDebugThread que representa el subproceso que tuvo un cambio de nombre.</span><span class="sxs-lookup"><span data-stu-id="45c27-107">[in] A pointer to an ICorDebugThread object that represents the thread that had a name change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45c27-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="45c27-108">Requirements</span></span>  
 <span data-ttu-id="45c27-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45c27-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45c27-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45c27-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45c27-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45c27-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45c27-112">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45c27-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45c27-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="45c27-113">See Also</span></span>  
 [<span data-ttu-id="45c27-114">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="45c27-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
