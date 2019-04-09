---
title: ICorDebugManagedCallback::CreateAppDomain (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateAppDomain
helpviewer_keywords:
- CreateAppDomain method [.NET Framework debugging]
- ICorDebugManagedCallback::CreateAppDomain method [.NET Framework debugging]
ms.assetid: 48d410d7-6749-4125-a8fd-f9562c7088e9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: afd8bd76f8d738c9eaa3a8e3d490e175e408b92b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204307"
---
# <a name="icordebugmanagedcallbackcreateappdomain-method"></a><span data-ttu-id="059ae-102">ICorDebugManagedCallback::CreateAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="059ae-102">ICorDebugManagedCallback::CreateAppDomain Method</span></span>
<span data-ttu-id="059ae-103">Notifica al depurador que se ha creado un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="059ae-103">Notifies the debugger that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="059ae-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="059ae-104">Syntax</span></span>  
  
```  
HRESULT CreateAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="059ae-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="059ae-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="059ae-106">[in] Un puntero a un objeto ICorDebugProcess que representa el proceso en el que se creó el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="059ae-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the application domain was created.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="059ae-107">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="059ae-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has been created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="059ae-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="059ae-108">Requirements</span></span>  
 <span data-ttu-id="059ae-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="059ae-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="059ae-110">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="059ae-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="059ae-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="059ae-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="059ae-112">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="059ae-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="059ae-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="059ae-113">See also</span></span>

- [<span data-ttu-id="059ae-114">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="059ae-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
