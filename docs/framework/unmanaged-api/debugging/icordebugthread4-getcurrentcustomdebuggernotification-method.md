---
title: "ICorDebugThread4::GetCurrentCustomDebuggerNotification (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread4.GetCurrentCustomDebuggerNotification Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread4::GetCurrentCustomDebuggerNotification
helpviewer_keywords:
- GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
- ICorDebugThread4::GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
ms.assetid: 57e0f2d2-5f0e-4e2d-99ec-3f26632eb693
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cd865e720e4ed938cf1634ebe5f1c324c4c3256e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugthread4getcurrentcustomdebuggernotification-method"></a><span data-ttu-id="b7c20-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification (Método)</span><span class="sxs-lookup"><span data-stu-id="b7c20-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification Method</span></span>
<span data-ttu-id="b7c20-103">Obtiene el actual [ICorDebugManagedCallback3:: CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) objeto en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="b7c20-103">Gets the current [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7c20-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7c20-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentCustomDebuggerNotification(  
    [out] ICorDebugValue **ppNotificationObject  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b7c20-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b7c20-105">Parameters</span></span>  
 `ppNOtificationObject`  
 <span data-ttu-id="b7c20-106">[out] Un puntero a la actual `ICorDebugManagedCallback3::CustomNotification` objeto en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="b7c20-106">[out] A pointer to the current `ICorDebugManagedCallback3::CustomNotification` object on the current thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7c20-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b7c20-107">Remarks</span></span>  
 <span data-ttu-id="b7c20-108">El valor de `ppNotificationObject` es null si no se llama al método desde un `ICorDebugManagedCallback3::CustomNotification` devolución de llamada, o si no hay ningún objeto de notificación actual.</span><span class="sxs-lookup"><span data-stu-id="b7c20-108">The value of `ppNotificationObject` is null if the method is not called from within a `ICorDebugManagedCallback3::CustomNotification` callback, or if no current notification object exists.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7c20-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7c20-109">Requirements</span></span>  
 <span data-ttu-id="b7c20-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7c20-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7c20-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7c20-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7c20-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7c20-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7c20-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7c20-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7c20-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7c20-114">See Also</span></span>  
 [<span data-ttu-id="b7c20-115">ICorDebugThread4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7c20-115">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 [<span data-ttu-id="b7c20-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="b7c20-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="b7c20-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="b7c20-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
