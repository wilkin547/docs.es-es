---
title: "ICorDebugManagedCallback::LoadClass (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.LoadClass
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::LoadClass
helpviewer_keywords:
- ICorDebugManagedCallback::LoadClass method [.NET Framework debugging]
- LoadClass method [.NET Framework debugging]
ms.assetid: e58dac7b-85c3-41ca-b9aa-3a7fc9ae6680
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f3e732b418398e9c917085d22507c9304981b06a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackloadclass-method"></a><span data-ttu-id="5d0a9-102">ICorDebugManagedCallback::LoadClass (Método)</span><span class="sxs-lookup"><span data-stu-id="5d0a9-102">ICorDebugManagedCallback::LoadClass Method</span></span>
<span data-ttu-id="5d0a9-103">Notifica al depurador que se ha cargado una clase.</span><span class="sxs-lookup"><span data-stu-id="5d0a9-103">Notifies the debugger that a class has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d0a9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d0a9-104">Syntax</span></span>  
  
```  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d0a9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5d0a9-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="5d0a9-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en la que se ha cargado la clase.</span><span class="sxs-lookup"><span data-stu-id="5d0a9-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the class has been loaded.</span></span>  
  
 `c`  
 <span data-ttu-id="5d0a9-107">[in] Un puntero a un objeto ICorDebugClass que representa la clase.</span><span class="sxs-lookup"><span data-stu-id="5d0a9-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d0a9-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5d0a9-108">Remarks</span></span>  
 <span data-ttu-id="5d0a9-109">Esta devolución de llamada solo se produce si se ha habilitado la carga de clase del módulo que contiene la clase.</span><span class="sxs-lookup"><span data-stu-id="5d0a9-109">This callback occurs only if class loading has been enabled for the module that contains the class.</span></span> <span data-ttu-id="5d0a9-110">La carga de clase siempre está habilitada para los módulos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="5d0a9-110">Class loading is always enabled for dynamic modules.</span></span>  
  
 <span data-ttu-id="5d0a9-111">El `LoadClass` devolución de llamada proporciona un momento adecuado para enlazar los puntos de interrupción a las clases generadas recientemente en módulos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="5d0a9-111">The `LoadClass` callback provides an appropriate time to bind breakpoints to newly generated classes in dynamic modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d0a9-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5d0a9-112">Requirements</span></span>  
 <span data-ttu-id="5d0a9-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d0a9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d0a9-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5d0a9-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d0a9-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d0a9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d0a9-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d0a9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d0a9-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d0a9-117">See Also</span></span>  
 [<span data-ttu-id="5d0a9-118">UnloadClass (método)</span><span class="sxs-lookup"><span data-stu-id="5d0a9-118">UnloadClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)  
 [<span data-ttu-id="5d0a9-119">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5d0a9-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
