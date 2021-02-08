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
# <a name="inotifysource2setnotifyfilter-method"></a>INotifySource2::SetNotifyFilter (Método)

Asigna un filtro de notificación para su uso con este origen.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetNotifyFilter  
(  
    [in]  NOTIFY_FILTER   in_NotifyFilter,  
    [in]  USER_THREAD*    in_pUserThreadFilter  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `in_NotifyFilter`  
 de Combinación bit a bit de los valores de enumeración de [NOTIFY_FILTER](notify-filter-enumeration.md) que identifican las devoluciones de llamada de la API del depurador.  
  
 `in_pUserThreadFilter`  
 de Puntero a una estructura de [USER_THREAD](user-thread-structure.md) que identifica los subprocesos de la API del depurador.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Vea también

- [INotifySource2 (Interfaz)](inotifysource2-interface.md)
- [INotifyConnection2 (Interfaz)](inotifyconnection2-interface.md)
- [INotifySink2 (Interfaz)](inotifysink2-interface.md)
