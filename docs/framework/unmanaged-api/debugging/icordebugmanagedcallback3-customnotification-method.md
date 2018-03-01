---
title: "ICorDebugManagedCallback3::CustomNotification (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugManagedCallback3.CustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3::CustomNotification
helpviewer_keywords:
- ICorDebugManagedCallback3::CustomNotification method [.NET Framework debugging]
- CustomNotification method [.NET Framework debugging]
ms.assetid: 5e5422ac-afa1-403d-a894-2d7348673e38
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9c42443b0d1e355d4233909357c341763298160e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallback3customnotification-method"></a><span data-ttu-id="c2110-102">ICorDebugManagedCallback3::CustomNotification (Método)</span><span class="sxs-lookup"><span data-stu-id="c2110-102">ICorDebugManagedCallback3::CustomNotification Method</span></span>
<span data-ttu-id="c2110-103">Indica que se ha producido una notificación del depurador personalizada.</span><span class="sxs-lookup"><span data-stu-id="c2110-103">Indicates that a custom debugger notification has been raised.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2110-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c2110-104">Syntax</span></span>  
  
```  
HRESULT CustomNotification(ICorDebugThread *    pThread,  
                           ICorDebugAppDomain * pAppDomain);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c2110-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c2110-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="c2110-106">[in] Un puntero al subproceso que generó la notificación.</span><span class="sxs-lookup"><span data-stu-id="c2110-106">[in] A pointer to the thread that raised the notification.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="c2110-107">[in] Un puntero al dominio de aplicación que contiene el subproceso que generó la notificación.</span><span class="sxs-lookup"><span data-stu-id="c2110-107">[in] A pointer to the application domain that contains the thread that raised the notification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2110-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c2110-108">Return Value</span></span>  
 <span data-ttu-id="c2110-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="c2110-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c2110-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c2110-110">HRESULT</span></span>|<span data-ttu-id="c2110-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2110-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c2110-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c2110-112">S_OK</span></span>|<span data-ttu-id="c2110-113">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="c2110-113">The method completed successfully.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="c2110-114">Excepciones</span><span class="sxs-lookup"><span data-stu-id="c2110-114">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2110-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c2110-115">Remarks</span></span>  
 <span data-ttu-id="c2110-116">Una llamada posterior a la [ICorDebugThread4:: GetCurrentCustomDebuggerNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md) método recupera el objeto de subproceso que se pasó a la <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="c2110-116">A subsequent call to the [ICorDebugThread4::GetCurrentCustomDebuggerNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md) method retrieves the thread object that was passed to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="c2110-117">Tipo del objeto de subproceso debe haberse habilitado previamente mediante una llamada a la [ICorDebugProcess3:: SetEnableCustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="c2110-117">The thread object's type must have been previously enabled by calling the [ICorDebugProcess3::SetEnableCustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md) method.</span></span> <span data-ttu-id="c2110-118">El depurador puede leer parámetros específicos del tipo de los campos del objeto de subproceso y puede almacenar respuestas en los campos.</span><span class="sxs-lookup"><span data-stu-id="c2110-118">The debugger can read type-specific parameters from the fields of the thread object, and can store responses into fields.</span></span>  
  
 <span data-ttu-id="c2110-119">El [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interfaz impone ninguna directiva sobre los tipos de notificaciones o su contenido y la semántica de las notificaciones es estrictamente un contrato entre depuradores, aplicaciones y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c2110-119">The [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface imposes no policy on the types of notifications or their contents, and the semantics of the notifications are strictly a contract between debuggers, applications, and the .NET Framework.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2110-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c2110-120">Requirements</span></span>  
 <span data-ttu-id="c2110-121">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2110-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2110-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2110-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2110-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2110-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2110-124">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2110-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2110-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2110-125">See Also</span></span>  
 [<span data-ttu-id="c2110-126">ICorDebugManagedCallback3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c2110-126">ICorDebugManagedCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-interface.md)  
 [<span data-ttu-id="c2110-127">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c2110-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="c2110-128">Depuración</span><span class="sxs-lookup"><span data-stu-id="c2110-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
