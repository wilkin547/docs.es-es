---
description: 'Más información sobre: Inotifysource2 (:: SetNotifyFilter ((método)'
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
ms.openlocfilehash: 2aaf2a5253f8a9acb67c4b538f109a7a62559d12
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800232"
---
# <a name="inotifysource2setnotifyfilter-method"></a><span data-ttu-id="1d456-103">INotifySource2::SetNotifyFilter (Método)</span><span class="sxs-lookup"><span data-stu-id="1d456-103">INotifySource2::SetNotifyFilter Method</span></span>

<span data-ttu-id="1d456-104">Asigna un filtro de notificación para su uso con este origen.</span><span class="sxs-lookup"><span data-stu-id="1d456-104">Assigns a notification filter for use with this source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d456-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1d456-105">Syntax</span></span>  
  
```cpp  
HRESULT SetNotifyFilter  
(  
    [in]  NOTIFY_FILTER   in_NotifyFilter,  
    [in]  USER_THREAD*    in_pUserThreadFilter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d456-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1d456-106">Parameters</span></span>  

 `in_NotifyFilter`  
 <span data-ttu-id="1d456-107">de Combinación bit a bit de los valores de enumeración de [NOTIFY_FILTER](notify-filter-enumeration.md) que identifican las devoluciones de llamada de la API del depurador.</span><span class="sxs-lookup"><span data-stu-id="1d456-107">[in] A bitwise combination of the [NOTIFY_FILTER](notify-filter-enumeration.md) enumeration values that identify callbacks for the debugger API.</span></span>  
  
 `in_pUserThreadFilter`  
 <span data-ttu-id="1d456-108">de Puntero a una estructura de [USER_THREAD](user-thread-structure.md) que identifica los subprocesos de la API del depurador.</span><span class="sxs-lookup"><span data-stu-id="1d456-108">[in] A pointer to a [USER_THREAD](user-thread-structure.md) structure that identifies threads for the debugger API.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d456-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1d456-109">Return Value</span></span>  

 <span data-ttu-id="1d456-110">S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="1d456-110">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d456-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1d456-111">Requirements</span></span>  

 <span data-ttu-id="1d456-112">**Encabezado:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="1d456-112">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d456-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d456-113">See also</span></span>

- [<span data-ttu-id="1d456-114">INotifySource2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1d456-114">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="1d456-115">INotifyConnection2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1d456-115">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
- [<span data-ttu-id="1d456-116">INotifySink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1d456-116">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
