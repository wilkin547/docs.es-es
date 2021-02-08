---
description: 'Más información sobre: INotifyConnection2:: Unregisternotifysource ((método)'
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
ms.openlocfilehash: d3b82665375f54d33b6a5581241788d828060a83
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800310"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a><span data-ttu-id="9030d-103">INotifyConnection2::UnregisterNotifySource (Método)</span><span class="sxs-lookup"><span data-stu-id="9030d-103">INotifyConnection2::UnregisterNotifySource Method</span></span>

<span data-ttu-id="9030d-104">Quita un objeto de origen de notificación especificado de la conexión.</span><span class="sxs-lookup"><span data-stu-id="9030d-104">Removes a specified notification source object from the connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9030d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9030d-105">Syntax</span></span>  
  
```cpp  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9030d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9030d-106">Parameters</span></span>  

 `in_pNotifySource`  
 <span data-ttu-id="9030d-107">de Objeto de notificación cuya registro se va a anular.</span><span class="sxs-lookup"><span data-stu-id="9030d-107">[in] Notification object to be unregistered.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9030d-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9030d-108">Return Value</span></span>  

 <span data-ttu-id="9030d-109">S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="9030d-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9030d-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9030d-110">Requirements</span></span>  

 <span data-ttu-id="9030d-111">**Encabezado:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="9030d-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9030d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="9030d-112">See also</span></span>

- [<span data-ttu-id="9030d-113">INotifyConnection2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9030d-113">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
- [<span data-ttu-id="9030d-114">INotifySource2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9030d-114">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="9030d-115">INotifySink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9030d-115">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="9030d-116">Método RegisterNotifySource</span><span class="sxs-lookup"><span data-stu-id="9030d-116">RegisterNotifySource Method</span></span>](inotifyconnection2-registernotifysource-method.md)
