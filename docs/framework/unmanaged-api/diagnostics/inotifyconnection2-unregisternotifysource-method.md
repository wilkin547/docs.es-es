---
title: INotifyConnection2::UnregisterNotifySource (Método)
ms.date: 03/30/2017
api_name:
- INotifyConnection2.UnregisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::UnregisterNotifySource
helpviewer_keywords:
- INotifyConnection2::UnregisterNotifySource method [.NET Framework debugging]
- UnregisterNotifySource method [.NET Framework debugging]
ms.assetid: 2fc6c715-646f-41fd-9c12-c59b40575269
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8b7125ad38bcec773fa2afa8eca09c1d56d90591
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475780"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a><span data-ttu-id="56973-102">INotifyConnection2::UnregisterNotifySource (Método)</span><span class="sxs-lookup"><span data-stu-id="56973-102">INotifyConnection2::UnregisterNotifySource Method</span></span>
<span data-ttu-id="56973-103">Quita un objeto de origen de notificación especificado de la conexión.</span><span class="sxs-lookup"><span data-stu-id="56973-103">Removes a specified notification source object from the connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56973-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56973-104">Syntax</span></span>  
  
```  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56973-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="56973-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="56973-106">[in] Objeto de notificación se va a anular.</span><span class="sxs-lookup"><span data-stu-id="56973-106">[in] Notification object to be unregistered.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="56973-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="56973-107">Return Value</span></span>  
 <span data-ttu-id="56973-108">S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="56973-108">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56973-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="56973-109">Requirements</span></span>  
 <span data-ttu-id="56973-110">**Encabezado**: ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="56973-110">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56973-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="56973-111">See also</span></span>
- [<span data-ttu-id="56973-112">INotifyConnection2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="56973-112">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [<span data-ttu-id="56973-113">INotifySource2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="56973-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="56973-114">INotifySink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="56973-114">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="56973-115">RegisterNotifySource (método)</span><span class="sxs-lookup"><span data-stu-id="56973-115">RegisterNotifySource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-registernotifysource-method.md)
