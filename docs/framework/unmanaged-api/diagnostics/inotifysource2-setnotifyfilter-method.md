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
ms.openlocfilehash: 554756bdda6e7167b013e7114e647f952cd1069d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435959"
---
# <a name="inotifysource2setnotifyfilter-method"></a><span data-ttu-id="9e600-102">INotifySource2::SetNotifyFilter (Método)</span><span class="sxs-lookup"><span data-stu-id="9e600-102">INotifySource2::SetNotifyFilter Method</span></span>
<span data-ttu-id="9e600-103">Asigna un filtro de notificación para su uso con este origen.</span><span class="sxs-lookup"><span data-stu-id="9e600-103">Assigns a notification filter for use with this source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e600-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9e600-104">Syntax</span></span>  
  
```cpp  
HRESULT SetNotifyFilter  
(  
    [in]  NOTIFY_FILTER   in_NotifyFilter,  
    [in]  USER_THREAD*    in_pUserThreadFilter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e600-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9e600-105">Parameters</span></span>  
 `in_NotifyFilter`  
 <span data-ttu-id="9e600-106">de Combinación bit a bit de los valores de enumeración de [NOTIFY_FILTER](../../../../docs/framework/unmanaged-api/diagnostics/notify-filter-enumeration.md) que identifican las devoluciones de llamada de la API del depurador.</span><span class="sxs-lookup"><span data-stu-id="9e600-106">[in] A bitwise combination of the [NOTIFY_FILTER](../../../../docs/framework/unmanaged-api/diagnostics/notify-filter-enumeration.md) enumeration values that identify callbacks for the debugger API.</span></span>  
  
 `in_pUserThreadFilter`  
 <span data-ttu-id="9e600-107">de Puntero a una estructura de [USER_THREAD](../../../../docs/framework/unmanaged-api/diagnostics/user-thread-structure.md) que identifica los subprocesos de la API del depurador.</span><span class="sxs-lookup"><span data-stu-id="9e600-107">[in] A pointer to a [USER_THREAD](../../../../docs/framework/unmanaged-api/diagnostics/user-thread-structure.md) structure that identifies threads for the debugger API.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e600-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9e600-108">Return Value</span></span>  
 <span data-ttu-id="9e600-109">S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="9e600-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e600-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9e600-110">Requirements</span></span>  
 <span data-ttu-id="9e600-111">**Encabezado:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="9e600-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e600-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e600-112">See also</span></span>

- [<span data-ttu-id="9e600-113">INotifySource2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9e600-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="9e600-114">INotifyConnection2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9e600-114">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [<span data-ttu-id="9e600-115">INotifySink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9e600-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
