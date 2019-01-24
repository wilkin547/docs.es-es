---
title: INotifySource2::SetNotifyFilter (Método)
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2c46f2636d397f7f71cf3c119b177f721c6fc091
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54620950"
---
# <a name="inotifysource2setnotifyfilter-method"></a><span data-ttu-id="0fdce-102">INotifySource2::SetNotifyFilter (Método)</span><span class="sxs-lookup"><span data-stu-id="0fdce-102">INotifySource2::SetNotifyFilter Method</span></span>
<span data-ttu-id="0fdce-103">Asigna un filtro de notificación para su uso con este origen.</span><span class="sxs-lookup"><span data-stu-id="0fdce-103">Assigns a notification filter for use with this source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fdce-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0fdce-104">Syntax</span></span>  
  
```  
HRESULT SetNotifyFilter  
(  
    [in]  NOTIFY_FILTER   in_NotifyFilter,  
    [in]  USER_THREAD*    in_pUserThreadFilter  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0fdce-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0fdce-105">Parameters</span></span>  
 `in_NotifyFilter`  
 <span data-ttu-id="0fdce-106">[in] Una combinación bit a bit de los [NOTIFY_FILTER](../../../../docs/framework/unmanaged-api/diagnostics/notify-filter-enumeration.md) valores de enumeración que identifica las devoluciones de llamada para la API del depurador.</span><span class="sxs-lookup"><span data-stu-id="0fdce-106">[in] A bitwise combination of the [NOTIFY_FILTER](../../../../docs/framework/unmanaged-api/diagnostics/notify-filter-enumeration.md) enumeration values that identify callbacks for the debugger API.</span></span>  
  
 `in_pUserThreadFilter`  
 <span data-ttu-id="0fdce-107">[in] Un puntero a un [USER_THREAD](../../../../docs/framework/unmanaged-api/diagnostics/user-thread-structure.md) estructura que identifica los subprocesos de la API del depurador.</span><span class="sxs-lookup"><span data-stu-id="0fdce-107">[in] A pointer to a [USER_THREAD](../../../../docs/framework/unmanaged-api/diagnostics/user-thread-structure.md) structure that identifies threads for the debugger API.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0fdce-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0fdce-108">Return Value</span></span>  
 <span data-ttu-id="0fdce-109">S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="0fdce-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fdce-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0fdce-110">Requirements</span></span>  
 <span data-ttu-id="0fdce-111">**Encabezado**: ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="0fdce-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fdce-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="0fdce-112">See also</span></span>
- [<span data-ttu-id="0fdce-113">INotifySource2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0fdce-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="0fdce-114">INotifyConnection2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0fdce-114">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [<span data-ttu-id="0fdce-115">INotifySink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0fdce-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
