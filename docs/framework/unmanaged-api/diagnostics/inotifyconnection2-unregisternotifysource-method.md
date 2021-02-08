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
# <a name="inotifyconnection2unregisternotifysource-method"></a>INotifyConnection2::UnregisterNotifySource (Método)

Quita un objeto de origen de notificación especificado de la conexión.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `in_pNotifySource`  
 de Objeto de notificación cuya registro se va a anular.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Vea también

- [INotifyConnection2 (Interfaz)](inotifyconnection2-interface.md)
- [INotifySource2 (Interfaz)](inotifysource2-interface.md)
- [INotifySink2 (Interfaz)](inotifysink2-interface.md)
- [Método RegisterNotifySource](inotifyconnection2-registernotifysource-method.md)
