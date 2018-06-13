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
ms.openlocfilehash: d7a2391527a7912c5def593438a71ed006955e8d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426151"
---
# <a name="inotifysource2setnotifyfilter-method"></a>INotifySource2::SetNotifyFilter (Método)
Asigna un filtro de notificación para su uso con este origen.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetNotifyFilter  
(  
    [in]  NOTIFY_FILTER   in_NotifyFilter,  
    [in]  USER_THREAD*    in_pUserThreadFilter  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `in_NotifyFilter`  
 [in] Una combinación bit a bit de los [NOTIFY_FILTER](../../../../docs/framework/unmanaged-api/diagnostics/notify-filter-enumeration.md) valores de enumeración que identifica las devoluciones de llamada para la API del depurador.  
  
 `in_pUserThreadFilter`  
 [in] Un puntero a un [USER_THREAD](../../../../docs/framework/unmanaged-api/diagnostics/user-thread-structure.md) estructura que identifica los subprocesos de la API del depurador.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método tiene éxito.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** ProtocolNotify2.idl  
  
## <a name="see-also"></a>Vea también  
 [INotifySource2 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [INotifyConnection2 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 [INotifySink2 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
