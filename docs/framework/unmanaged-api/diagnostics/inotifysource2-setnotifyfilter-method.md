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
ms.openlocfilehash: 7ba9f68e102696da107b5cb782c76cb55ed95ee6
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441973"
---
# <a name="inotifysource2setnotifyfilter-method"></a><span data-ttu-id="74d04-102">INotifySource2::SetNotifyFilter (Método)</span><span class="sxs-lookup"><span data-stu-id="74d04-102">INotifySource2::SetNotifyFilter Method</span></span>
<span data-ttu-id="74d04-103">Asigna un filtro de notificación para su uso con este origen.</span><span class="sxs-lookup"><span data-stu-id="74d04-103">Assigns a notification filter for use with this source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74d04-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74d04-104">Syntax</span></span>  
  
```cpp  
HRESULT SetNotifyFilter  
(  
    [in]  NOTIFY_FILTER   in_NotifyFilter,  
    [in]  USER_THREAD*    in_pUserThreadFilter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74d04-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="74d04-105">Parameters</span></span>  
 `in_NotifyFilter`  
 <span data-ttu-id="74d04-106">de Combinación bit a bit de los valores de enumeración de [NOTIFY_FILTER](notify-filter-enumeration.md) que identifican las devoluciones de llamada de la API del depurador.</span><span class="sxs-lookup"><span data-stu-id="74d04-106">[in] A bitwise combination of the [NOTIFY_FILTER](notify-filter-enumeration.md) enumeration values that identify callbacks for the debugger API.</span></span>  
  
 `in_pUserThreadFilter`  
 <span data-ttu-id="74d04-107">de Puntero a una estructura de [USER_THREAD](user-thread-structure.md) que identifica los subprocesos de la API del depurador.</span><span class="sxs-lookup"><span data-stu-id="74d04-107">[in] A pointer to a [USER_THREAD](user-thread-structure.md) structure that identifies threads for the debugger API.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74d04-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="74d04-108">Return Value</span></span>  
 <span data-ttu-id="74d04-109">S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="74d04-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74d04-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74d04-110">Requirements</span></span>  
 <span data-ttu-id="74d04-111">**Encabezado:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="74d04-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74d04-112">Consulta también</span><span class="sxs-lookup"><span data-stu-id="74d04-112">See also</span></span>

- [<span data-ttu-id="74d04-113">INotifySource2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="74d04-113">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="74d04-114">INotifyConnection2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="74d04-114">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
- [<span data-ttu-id="74d04-115">INotifySink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="74d04-115">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
