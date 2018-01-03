---
title: "ICorDebugManagedCallback::CreateAppDomain (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.CreateAppDomain
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::CreateAppDomain
helpviewer_keywords:
- CreateAppDomain method [.NET Framework debugging]
- ICorDebugManagedCallback::CreateAppDomain method [.NET Framework debugging]
ms.assetid: 48d410d7-6749-4125-a8fd-f9562c7088e9
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f0f9b6322ee391edaba73e0c222b75aa86eee7e5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackcreateappdomain-method"></a><span data-ttu-id="da2e8-102">ICorDebugManagedCallback::CreateAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="da2e8-102">ICorDebugManagedCallback::CreateAppDomain Method</span></span>
<span data-ttu-id="da2e8-103">Notifica al depurador que se ha creado un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="da2e8-103">Notifies the debugger that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da2e8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="da2e8-104">Syntax</span></span>  
  
```  
HRESULT CreateAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="da2e8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="da2e8-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="da2e8-106">[in] Un puntero a un objeto ICorDebugProcess que representa el proceso en el que se creó el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="da2e8-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the application domain was created.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="da2e8-107">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="da2e8-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has been created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da2e8-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="da2e8-108">Requirements</span></span>  
 <span data-ttu-id="da2e8-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da2e8-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da2e8-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da2e8-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da2e8-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da2e8-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da2e8-112">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da2e8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da2e8-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="da2e8-113">See Also</span></span>  
 [<span data-ttu-id="da2e8-114">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="da2e8-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
