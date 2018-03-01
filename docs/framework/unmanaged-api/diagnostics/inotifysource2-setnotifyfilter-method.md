---
title: "INotifySource2::SetNotifyFilter (Método)"
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
- INotifySource2.SetNotifyFilter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySource2::SetNotifyFilter
helpviewer_keywords:
- INotifySource2::SetNotifyFilter method [.NET Framework debugging]
- SetNotifyFilter method [.NET Framework debugging]
ms.assetid: 6351fc92-b126-4af6-9bf3-0a8ce92845fc
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bba34a9e28d1995ca04c7108ce33adc6e676b357
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="inotifysource2setnotifyfilter-method"></a><span data-ttu-id="4e1fe-102">INotifySource2::SetNotifyFilter (Método)</span><span class="sxs-lookup"><span data-stu-id="4e1fe-102">INotifySource2::SetNotifyFilter Method</span></span>
<span data-ttu-id="4e1fe-103">Asigna un filtro de notificación para su uso con este origen.</span><span class="sxs-lookup"><span data-stu-id="4e1fe-103">Assigns a notification filter for use with this source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e1fe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4e1fe-104">Syntax</span></span>  
  
```  
HRESULT SetNotifyFilter  
(  
    [in]  NOTIFY_FILTER   in_NotifyFilter,  
    [in]  USER_THREAD*    in_pUserThreadFilter  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4e1fe-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4e1fe-105">Parameters</span></span>  
 `in_NotifyFilter`  
 <span data-ttu-id="4e1fe-106">[in] Una combinación bit a bit de los [NOTIFY_FILTER](../../../../docs/framework/unmanaged-api/diagnostics/notify-filter-enumeration.md) valores de enumeración que identifica las devoluciones de llamada para la API del depurador.</span><span class="sxs-lookup"><span data-stu-id="4e1fe-106">[in] A bitwise combination of the [NOTIFY_FILTER](../../../../docs/framework/unmanaged-api/diagnostics/notify-filter-enumeration.md) enumeration values that identify callbacks for the debugger API.</span></span>  
  
 `in_pUserThreadFilter`  
 <span data-ttu-id="4e1fe-107">[in] Un puntero a un [USER_THREAD](../../../../docs/framework/unmanaged-api/diagnostics/user-thread-structure.md) estructura que identifica los subprocesos de la API del depurador.</span><span class="sxs-lookup"><span data-stu-id="4e1fe-107">[in] A pointer to a [USER_THREAD](../../../../docs/framework/unmanaged-api/diagnostics/user-thread-structure.md) structure that identifies threads for the debugger API.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e1fe-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4e1fe-108">Return Value</span></span>  
 <span data-ttu-id="4e1fe-109">S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="4e1fe-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e1fe-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4e1fe-110">Requirements</span></span>  
 <span data-ttu-id="4e1fe-111">**Encabezado:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="4e1fe-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e1fe-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e1fe-112">See Also</span></span>  
 [<span data-ttu-id="4e1fe-113">INotifySource2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e1fe-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [<span data-ttu-id="4e1fe-114">INotifyConnection2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e1fe-114">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 [<span data-ttu-id="4e1fe-115">INotifySink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e1fe-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
