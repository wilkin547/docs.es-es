---
description: 'Más información acerca de: enumeración NOTIFY_FILTER'
title: NOTIFY_FILTER (Enumeración)
ms.date: 03/30/2017
api_name:
- NOTIFY_FILTER
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- NOTIFY_FILTER
helpviewer_keywords:
- NOTIFY_FILTER enumeration [.NET Framework debugging]
ms.assetid: 4789d08f-8683-45d3-ac30-73d48c61e470
topic_type:
- apiref
ms.openlocfilehash: 0ed09af0af302b08102b7b08fa72a2d255c5b231
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761491"
---
# <a name="notify_filter-enumeration"></a><span data-ttu-id="59f2d-103">NOTIFY_FILTER (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="59f2d-103">NOTIFY_FILTER Enumeration</span></span>

<span data-ttu-id="59f2d-104">Identifica las devoluciones de llamada para las funciones del depurador.</span><span class="sxs-lookup"><span data-stu-id="59f2d-104">Identifies callbacks for debugger functions.</span></span> <span data-ttu-id="59f2d-105">Para obtener más información, vea el método [INotifySource2 (:: SetNotifyFilter (](inotifysource2-setnotifyfilter-method.md) .</span><span class="sxs-lookup"><span data-stu-id="59f2d-105">For more information, see the [INotifySource2::SetNotifyFilter](inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59f2d-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59f2d-106">Syntax</span></span>  
  
```cpp  
enum tagNOTIFY_FILTER  
{  
    NOTIFY_FILTER_ONSYNCCALLOUT    = 0x1,  
    NOTIFY_FILTER_ONSYNCCALLENTER  = 0x2,  
    NOTIFY_FILTER_ONSYNCCALLEXIT   = 0x4,  
    NOTIFY_FILTER_ONSYNCCALLRETURN = 0x8,  
    NOTIFY_FILTER_ALLSYNC = NOTIFY_FILTER_ONSYNCCALLOUT | NOTIFY_FILTER_ONSYNCCALLENTER | NOTIFY_FILTER_ONSYNCCALLEXIT | NOTIFY_FILTER_ONSYNCCALLRETURN,  
    NOTIFY_FILTER_ALL              = 0xffffffff,  
    NOTIFY_FILTER_NONE             = 0  
};  
```  
  
## <a name="members"></a><span data-ttu-id="59f2d-107">Members</span><span class="sxs-lookup"><span data-stu-id="59f2d-107">Members</span></span>  
  
|<span data-ttu-id="59f2d-108">Miembro</span><span class="sxs-lookup"><span data-stu-id="59f2d-108">Member</span></span>|<span data-ttu-id="59f2d-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="59f2d-109">Description</span></span>|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|<span data-ttu-id="59f2d-110">Indica que se debe invocar el método [INotifySink2:: OnSyncCallOut (](inotifysink2-onsynccallout-method.md) .</span><span class="sxs-lookup"><span data-stu-id="59f2d-110">Indicates that the [INotifySink2::OnSyncCallOut](inotifysink2-onsynccallout-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|<span data-ttu-id="59f2d-111">Indica que se debe invocar el método [INotifySink2:: onsynccallenter (](inotifysink2-onsynccallenter-method.md) .</span><span class="sxs-lookup"><span data-stu-id="59f2d-111">Indicates that the [INotifySink2::OnSyncCallEnter](inotifysink2-onsynccallenter-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|<span data-ttu-id="59f2d-112">Indica que se debe invocar el método [INotifySink2:: onsynccallexit (](inotifysink2-onsynccallexit-method.md) .</span><span class="sxs-lookup"><span data-stu-id="59f2d-112">Indicates that the [INotifySink2::OnSyncCallExit](inotifysink2-onsynccallexit-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|<span data-ttu-id="59f2d-113">Indica que se debe invocar el método [INotifySink2:: onsynccallreturn (](inotifysink2-onsynccallreturn-method.md) .</span><span class="sxs-lookup"><span data-stu-id="59f2d-113">Indicates that the [INotifySink2::OnSyncCallReturn](inotifysink2-onsynccallreturn-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALLSYNC`|<span data-ttu-id="59f2d-114">Indica que se deben invocar todos los métodos [INotifySink2](inotifysink2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="59f2d-114">Indicates that all of the [INotifySink2](inotifysink2-interface.md) methods should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALL`|<span data-ttu-id="59f2d-115">Activa todas las notificaciones existentes y futuras.</span><span class="sxs-lookup"><span data-stu-id="59f2d-115">Activates all existing and future notifications.</span></span>|  
|`NOTIFY_FILTER_NONE`|<span data-ttu-id="59f2d-116">Indica que no se debe invocar ningún método de notificación.</span><span class="sxs-lookup"><span data-stu-id="59f2d-116">Indicates that no notification methods should be invoked.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="59f2d-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="59f2d-117">Requirements</span></span>  

 <span data-ttu-id="59f2d-118">**Encabezado:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="59f2d-118">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59f2d-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="59f2d-119">See also</span></span>

- [<span data-ttu-id="59f2d-120">Enumeraciones de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="59f2d-120">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)
