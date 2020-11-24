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
ms.openlocfilehash: 365bc0dc73b04d3afd171c40f336432f77552b6d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690959"
---
# <a name="notify_filter-enumeration"></a>NOTIFY_FILTER (Enumeración)

Identifica las devoluciones de llamada para las funciones del depurador. Para obtener más información, vea el método [INotifySource2 (:: SetNotifyFilter (](inotifysource2-setnotifyfilter-method.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
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
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|Indica que se debe invocar el método [INotifySink2:: OnSyncCallOut (](inotifysink2-onsynccallout-method.md) .|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|Indica que se debe invocar el método [INotifySink2:: onsynccallenter (](inotifysink2-onsynccallenter-method.md) .|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|Indica que se debe invocar el método [INotifySink2:: onsynccallexit (](inotifysink2-onsynccallexit-method.md) .|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|Indica que se debe invocar el método [INotifySink2:: onsynccallreturn (](inotifysink2-onsynccallreturn-method.md) .|  
|`NOTIFY_FILTER_ALLSYNC`|Indica que se deben invocar todos los métodos [INotifySink2](inotifysink2-interface.md) .|  
|`NOTIFY_FILTER_ALL`|Activa todas las notificaciones existentes y futuras.|  
|`NOTIFY_FILTER_NONE`|Indica que no se debe invocar ningún método de notificación.|  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones de almacén de símbolos de diagnósticos](diagnostics-symbol-store-enumerations.md)
