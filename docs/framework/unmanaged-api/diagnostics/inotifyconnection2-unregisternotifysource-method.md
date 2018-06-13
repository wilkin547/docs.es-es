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
ms.openlocfilehash: c4b4f90f918c872f3227ac22f4cccadcbf3194a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425485"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a>INotifyConnection2::UnregisterNotifySource (Método)
Quita un objeto de origen de notificación especificado de la conexión.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `in_pNotifySource`  
 [in] Objeto de notificación se va a anular.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método tiene éxito.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** ProtocolNotify2.idl  
  
## <a name="see-also"></a>Vea también  
 [INotifyConnection2 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 [INotifySource2 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [INotifySink2 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [RegisterNotifySource (método)](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-registernotifysource-method.md)
