---
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
ms.openlocfilehash: b20e18d5f4314a0ab1442ac7bd5c6514e4db85d5
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609487"
---
# <a name="notify_filter-enumeration"></a><span data-ttu-id="7192b-102">NOTIFY_FILTER (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="7192b-102">NOTIFY_FILTER Enumeration</span></span>
<span data-ttu-id="7192b-103">Identifica las devoluciones de llamada para las funciones del depurador.</span><span class="sxs-lookup"><span data-stu-id="7192b-103">Identifies callbacks for debugger functions.</span></span> <span data-ttu-id="7192b-104">Para obtener más información, vea el método [INotifySource2 (:: SetNotifyFilter (](inotifysource2-setnotifyfilter-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7192b-104">For more information, see the [INotifySource2::SetNotifyFilter](inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7192b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7192b-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="7192b-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="7192b-106">Members</span></span>  
  
|<span data-ttu-id="7192b-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="7192b-107">Member</span></span>|<span data-ttu-id="7192b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="7192b-108">Description</span></span>|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|<span data-ttu-id="7192b-109">Indica que se debe invocar el método [INotifySink2:: OnSyncCallOut (](inotifysink2-onsynccallout-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7192b-109">Indicates that the [INotifySink2::OnSyncCallOut](inotifysink2-onsynccallout-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|<span data-ttu-id="7192b-110">Indica que se debe invocar el método [INotifySink2:: onsynccallenter (](inotifysink2-onsynccallenter-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7192b-110">Indicates that the [INotifySink2::OnSyncCallEnter](inotifysink2-onsynccallenter-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|<span data-ttu-id="7192b-111">Indica que se debe invocar el método [INotifySink2:: onsynccallexit (](inotifysink2-onsynccallexit-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7192b-111">Indicates that the [INotifySink2::OnSyncCallExit](inotifysink2-onsynccallexit-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|<span data-ttu-id="7192b-112">Indica que se debe invocar el método [INotifySink2:: onsynccallreturn (](inotifysink2-onsynccallreturn-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7192b-112">Indicates that the [INotifySink2::OnSyncCallReturn](inotifysink2-onsynccallreturn-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALLSYNC`|<span data-ttu-id="7192b-113">Indica que se deben invocar todos los métodos [INotifySink2](inotifysink2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="7192b-113">Indicates that all of the [INotifySink2](inotifysink2-interface.md) methods should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALL`|<span data-ttu-id="7192b-114">Activa todas las notificaciones existentes y futuras.</span><span class="sxs-lookup"><span data-stu-id="7192b-114">Activates all existing and future notifications.</span></span>|  
|`NOTIFY_FILTER_NONE`|<span data-ttu-id="7192b-115">Indica que no se debe invocar ningún método de notificación.</span><span class="sxs-lookup"><span data-stu-id="7192b-115">Indicates that no notification methods should be invoked.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7192b-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7192b-116">Requirements</span></span>  
 <span data-ttu-id="7192b-117">**Encabezado:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="7192b-117">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7192b-118">Consulta también</span><span class="sxs-lookup"><span data-stu-id="7192b-118">See also</span></span>

- [<span data-ttu-id="7192b-119">Enumeraciones de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="7192b-119">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)
